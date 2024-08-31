Machine used in experiment : 
<img width="211" alt="image" src="https://github.com/user-attachments/assets/77f6d69a-f698-4e1a-bc36-f0012a91eb74">


1. Install osm2pgsql 
```shell
brew install osm2pgsql
```
Version used : 
2024-08-30 22:08:07  osm2pgsql version 1.11.0
Build: Release
Compiled using the following library versions:
Libosmium 2.20.0
Proj [API 6] 9.4.1
Lua 5.1.4 (LuaJIT 2.1.1723675123)

2. Download Asia data
Using geofabrik : https://osm-internal.download.geofabrik.de//asia.html
pbf file is around 14.9 GB 

3. Lets experiment with custom lua script 

```lua
local srid = 4326
local tables = {}

tables.nodes = osm2pgsql.define_table ({
    name='nodes',
    ids = {type='node',id_column = 'id' },
    columns = {{ column = 'geom', type = 'point', projection = srid, not_null = true },},
})

tables.ways_line = osm2pgsql.define_table ({
    name='ways_line',
    ids = {type='way',id_column = 'id' },
    columns = {{ column = 'geom', type = 'linestring', projection = srid, not_null = true },},
})

tables.ways_poly = osm2pgsql.define_table ({
    name='ways_poly',
    ids = {type='way',id_column = 'id' },
    columns = {{ column = 'geom', type = 'polygon', projection = srid, not_null = true },},
})
tables.rels = osm2pgsql.define_table ({
    name='relations',
    ids = {type='relation',id_column = 'id' },
    columns = {{ column = 'geom', type = 'geometry', projection = srid, not_null = true },},

})


-- Returns true if there are no tags left.
function clean_tags(tags)
    tags.odbl = nil
    tags['source:ref'] = nil
    return next(tags) == nil
end

function osm2pgsql.process_node(object)
    if clean_tags(object.tags) then
        return
    end
    tables.nodes:insert({
        geom = object:as_point()
    })
end


function osm2pgsql.process_way(object)

    if clean_tags(object.tags) then
        return
    end
    if object.is_closed and (#object.nodes >3) then
        tables.ways_poly:insert({
            geom = object:as_polygon()
        })
    else
        tables.ways_line:insert({
            geom = object:as_linestring()
        })
    end
end

function osm2pgsql.process_relation(object)
    if clean_tags(object.tags) then
        return
    end
    local relation_type = object:grab_tag('type')
    -- check if it is route cause route will be multilinestring
    if relation_type == 'route' then
        tables.rels:insert({
            geom = object:as_multilinestring()
        })
        return
    end

    if relation_type == 'boundary' or relation_type == 'multipolygon' or object.tags.boundary  then
        -- first try to convert object to mulitpolygon if not store it as multilinestring
        local geom = object:as_multipolygon()
        if geom then
            tables.rels:insert({
                geom = geom
            })AUT/KTM/270824/0006/01 
        else
            tables.rels:insert({
                geom = object:as_multilinestring():line_merge()
            })
        end
        return
    end
    -- at this point if nothing is satisfied then may be its polygon or its linestring or anything combined ,  we don't know so bundling all them to geometry collection
    tables.rels:insert({
        geom= object:as_geometrycollection()
    })


end
```
4. Insert the data 
```shell
osm2pgsql --create --slim ./asia-latest-internal.osm.pbf --extra-attributes --middle-with-nodes --number-processes 8 --style raw.lua --output=flex --prefix raw_osm -d postgres -U admin
```
