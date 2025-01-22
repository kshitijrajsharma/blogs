![grafik](https://github.com/user-attachments/assets/a101f08f-84c6-42f1-a895-66af1690f379)

## Task 1 

![grafik](https://github.com/user-attachments/assets/d7dd1e71-f1a0-4b2a-be92-a4a32d1ad4a8)


1 . Open ecognition & Create your workspace
![grafik](https://github.com/user-attachments/assets/29868c77-8d10-4082-bbbd-76bdb0e290d6)

### Task I 1. Load both (!) data sets in eCognition (full version 10.3)

#### Load Planet RGB image

2. Load Image to your workspace (DRAG and DROP)
![grafik](https://github.com/user-attachments/assets/370342b3-4478-41f0-8491-f9230003c919)

if you drag and dropped you will be looking at window like this and the area in red marker is where you can change the visualization parameter. It is called view settings window , Incase you loose it : Right click on the navbar and then click on view settings
![grafik](https://github.com/user-attachments/assets/285bf9be-27e1-4368-b0e0-df513f6d1dcf)

![grafik](https://github.com/user-attachments/assets/b8ec8b9b-6b48-4b7a-87b1-aa1ca0eb4141)

After changing the band combination RGB it looks like this 
![grafik](https://github.com/user-attachments/assets/30f7637e-1e1a-47a2-90f9-92b060b84d9b)

#### Load flood zone image 

Drag and drop the flood zone raster 

![grafik](https://github.com/user-attachments/assets/edf32b50-0a34-42d9-8c96-551d5d70e75a)

When you drag and drop it wont showup anywhere intially, you should be able to see new layer in your view settings 

![grafik](https://github.com/user-attachments/assets/2823779e-f093-48b7-a0e4-edc1edea8266)

Right click on the layer5 and rename it to flood
![grafik](https://github.com/user-attachments/assets/02857932-a48d-4a86-8cc0-a704df7fd25d)

Visualize the flood layer only 
![grafik](https://github.com/user-attachments/assets/7e8debd6-fa02-4cde-9622-7f52538b1a7e)

### Task I 2. Conduct a Land Cover (LC) classification 

Go to process tree window , if you dont see it in your screen , you can bring it back from right clicking on the navbar and clicking on the process tree 
![grafik](https://github.com/user-attachments/assets/a09c29ec-fbbc-43c2-97b1-9bbc1001eabc)

- Right click on Process Tree and Select Add New Process
  ![grafik](https://github.com/user-attachments/assets/4159f9ec-f3c0-4ae8-a1e6-56f4361b061e)
- Select Algorithm as multiresolution segmentation , domain as pixel level and Scale parameter as 100 
![grafik](https://github.com/user-attachments/assets/088d5547-f44a-4321-b8b4-6aae520110d6)
- Hit execute , You will see something like this and new level should be added in object levels in view settings
![grafik](https://github.com/user-attachments/assets/3513ff0f-ab2e-44dd-aa88-dfc6fc71f414)

##### Create samples for the classification 
![grafik](https://github.com/user-attachments/assets/75e14da2-48b3-4ba7-a946-bc3b465b5c2b)
Enable samples and then you would see those two buttons on the navbar 
![grafik](https://github.com/user-attachments/assets/397eafa9-2478-4e9b-8059-7441d22c1e93)
Click those two , Select samples and samples editor button as outlined red above 


