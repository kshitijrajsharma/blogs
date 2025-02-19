![grafik](https://github.com/user-attachments/assets/a101f08f-84c6-42f1-a895-66af1690f379)

## Task 1 

![grafik](https://github.com/user-attachments/assets/d7dd1e71-f1a0-4b2a-be92-a4a32d1ad4a8)

**1 . Open ecognition & Create your workspace**

![grafik](https://github.com/user-attachments/assets/29868c77-8d10-4082-bbbd-76bdb0e290d6)

### Task I 1. Load both (!) data sets in eCognition (full version 10.3)

#### Load Planet RGB image

**2. Load Image to your workspace (DRAG and DROP)**

![grafik](https://github.com/user-attachments/assets/370342b3-4478-41f0-8491-f9230003c919)

if you drag and dropped you will be looking at window like this and the area in red marker is where you can change the visualization parameter. It is called view settings window , Incase you loose it : Right click on the navbar and then click on view settings

![grafik](https://github.com/user-attachments/assets/285bf9be-27e1-4368-b0e0-df513f6d1dcf)

![grafik](https://github.com/user-attachments/assets/b8ec8b9b-6b48-4b7a-87b1-aa1ca0eb4141)

After changing the band combination RGB it looks like this 

![grafik](https://github.com/user-attachments/assets/30f7637e-1e1a-47a2-90f9-92b060b84d9b)

#### Load flood zone image 

**Drag and drop the flood zone raster **

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

**- Right click on Process Tree and Select Add New Process**

  ![grafik](https://github.com/user-attachments/assets/4159f9ec-f3c0-4ae8-a1e6-56f4361b061e)
  
**- Select Algorithm as multiresolution segmentation , domain as pixel level and Scale parameter as 100**

![grafik](https://github.com/user-attachments/assets/088d5547-f44a-4321-b8b4-6aae520110d6)

**- Hit execute , You will see something like this and new level should be added in object levels in view settings**

![grafik](https://github.com/user-attachments/assets/3513ff0f-ab2e-44dd-aa88-dfc6fc71f414)

##### Create samples for the classification 

![grafik](https://github.com/user-attachments/assets/75e14da2-48b3-4ba7-a946-bc3b465b5c2b)

**Enable samples and then you would see those two buttons on the navbar**

![grafik](https://github.com/user-attachments/assets/397eafa9-2478-4e9b-8059-7441d22c1e93)

**Click those two** , Select samples and samples editor button as outlined red above 

You should see window like this 

![grafik](https://github.com/user-attachments/assets/3de1ffc3-9cd3-4895-8a2f-5fba460d0683)

**Right click on the Sample Editor & Hit Select Features to Display**

![grafik](https://github.com/user-attachments/assets/f609bfba-b8e0-4ab8-adf9-12895cd355b1)

![grafik](https://github.com/user-attachments/assets/c1afdaf0-a4c1-40f9-9a70-35f4395526dc)

Search for Mean and Double click on left window 

![grafik](https://github.com/user-attachments/assets/aab4236a-7a21-4d93-a879-bc9a2ba8c87b)

It should go on right side of the window 

![grafik](https://github.com/user-attachments/assets/4506dfe7-9f6c-47cb-939c-a90e5d9306c0)

Now lets create classes , Click on the Class Hierarchy

![grafik](https://github.com/user-attachments/assets/6c876d75-d2bb-427d-9c9b-09bdaf5bc546)

Right click on the Class Hierarchy window and hit Insert Class 

![grafik](https://github.com/user-attachments/assets/bb80b954-53d4-43ab-98d3-eb3ab51cf5ab)

Lets create Water , Name it as Water 

![grafik](https://github.com/user-attachments/assets/aa313bcd-160d-4482-9494-0ce0ebef5fcd)

Now repeat this for the all classes mentioned 

![grafik](https://github.com/user-attachments/assets/1bd0d893-021f-4bc6-a130-5f581cae0431)

It would look like this 

![grafik](https://github.com/user-attachments/assets/aa2c67ed-a138-4cd4-a5ed-6f9f449b59ba)

#### Assign objects to sample 

Now on sample editor your should see the classes , select water for instance and start providing the samples 

![grafik](https://github.com/user-attachments/assets/32dccd0e-4514-47ce-b5c7-c1be2d6323fb)

Click on the Water and go back to map and double click on the object you want to classify as water sample 

The object should change the color after you double click on it 

![grafik](https://github.com/user-attachments/assets/4c831db2-4589-4227-b397-744ccff199bb)

Once you are done , you can go back to your view setting and view samples only , Turn off the Outline 

![grafik](https://github.com/user-attachments/assets/b86bfcf8-848c-461d-9182-c5ddb9627eca)

This is how my samples look like 

![grafik](https://github.com/user-attachments/assets/0f234b81-35af-4b9c-a64c-94cb6c1e6d57)

#### Supervised classification 

Go back to Process Tree and Right Click , Add new Process 

![grafik](https://github.com/user-attachments/assets/3d897c37-80a3-4f8d-aa21-1b1e05a792a3)

Select Algorithm as supervised classification , Domain as image object level 

![grafik](https://github.com/user-attachments/assets/13913739-ae52-480f-ab72-9fdd068f186d)

Here: Choose classifier as SVM , Features as Mean , similar to previous step , search for mean and double click on object features 

![grafik](https://github.com/user-attachments/assets/efc889be-2d10-47f7-8727-17857bffbfeb)
& then hit execute 

You won't see your prediction yet , Now you need to copy the process and paste it 
Go to Process tree and copy your last process and paste it 

![grafik](https://github.com/user-attachments/assets/fdb5bb34-95f8-49dc-bac4-207a9e6717b4)

Right Click on Pasted process and edit 

Change your operation to apply and execute 

![grafik](https://github.com/user-attachments/assets/58669ca3-7023-4569-8b8f-c3efda30477c)

Now go to View settings and Change Fill From samples to Class Color And Disable outline 

![grafik](https://github.com/user-attachments/assets/f12ab6b8-5afc-4dc4-acf8-2ecf7d9c34db)

You should be able to see your classification now , Voilaaaa done with task 1

![grafik](https://github.com/user-attachments/assets/cf584adb-9234-44ca-b125-1b11a3a3809d)

Lets export the project before moving to task 2 , In exam remember to do that 
File and Go to Export Project 

![grafik](https://github.com/user-attachments/assets/e75eefa7-3a8e-4e13-b95a-772843a8fa14)


## Task 2 Knowledge-based classification 

![grafik](https://github.com/user-attachments/assets/bce25d6b-3722-4904-8143-fa01bddd80b9)

Lets create two claseses : forest_flooded and lake 

Right click on Class hierarchy and insert new class 

![grafik](https://github.com/user-attachments/assets/ec5658fd-8292-4ad9-a2ca-617a565083bb)

Drag and drop the classes , i.e. lake inside water

![grafik](https://github.com/user-attachments/assets/2574261a-39cf-43ef-bb75-33f104a3f18c)

Now we will apply some condition to solve this 

![grafik](https://github.com/user-attachments/assets/fd34940d-400a-4d11-8326-bd32a313a555)

So we have one raster called flood or not flood that we added earlier , if you notice here the value of flooded area is 1 and not flooded area is 0 . Now our job is to find out the forest that we classified that overlaps with the flooded area in this layer called flood 

![grafik](https://github.com/user-attachments/assets/c7e8c339-e2d6-4dd8-8caa-0dca397379c5)

Now right click on process tree and add new process 
Choose algorithm as assign class 

![grafik](https://github.com/user-attachments/assets/42fc5e45-956e-44c9-bfe2-36cebc828e15)

On class filter choose Forest 

![grafik](https://github.com/user-attachments/assets/e7e87b45-4424-4e33-a5a4-df40ab38c15f)

Now go to condition 

![grafik](https://github.com/user-attachments/assets/4161f94f-2e4a-4f0d-bb02-282754926e87)

Choose value 1 be from feature 

![grafik](https://github.com/user-attachments/assets/a30cdd91-f934-490c-8ffb-34444cf1291e)

Choose flood mean from object feature 

![grafik](https://github.com/user-attachments/assets/d6db504f-97f5-4fe5-92b8-139816150a0e)

Now change value2 to 1  as we want to get forest that has value of flood as 1 and would be considered as flooded forest 

![grafik](https://github.com/user-attachments/assets/ff4abaaa-0d53-4987-8ba1-7702d9b175b5)

Now Change use class to forest_flooded 

![grafik](https://github.com/user-attachments/assets/e1d61a29-a26c-49d6-abf3-0a3fec22d033)

Execute and you should see the flooded forest 

![grafik](https://github.com/user-attachments/assets/58253152-3014-437d-8d5d-138763e23fc3)

Now lets merge the objects as per our class now , 
Add new process from Process Tree , Right click : Add new Process 
Choose algorithm as merge region and Execute 

![grafik](https://github.com/user-attachments/assets/a46f98d5-13eb-4c1d-bdb9-ec2e785dd1f0)

![grafik](https://github.com/user-attachments/assets/01ee41eb-86d7-4ac5-9e85-669912147d0d)

Now as you can see we have merged small classified object as one if it falls into the class so its like grouping of the objects 

Now lets find some lakes 

![grafik](https://github.com/user-attachments/assets/9121cfb1-8fa9-46b2-97bd-5ad7b7e1b84d)

Okay , create new process again 

Choose algorithm as find enclosed by class 

Class filter : Choose Water
Choose Enclosing classes as Bare_soil,forest,forest_flooded,grassland,impervious 

![grafik](https://github.com/user-attachments/assets/7f58dcea-df7e-4448-94c9-c49f167f5cb8)

Change active classes to lake because we wanna get result as lake from that filter 

![grafik](https://github.com/user-attachments/assets/0bac4f0c-ea9b-4ac7-94a6-082ca93e3c14)

Hit run and you should have lake identified now 

![grafik](https://github.com/user-attachments/assets/c59b6109-c846-4beb-b3aa-6b936bdcab77)

We are done with the Task II . Voilaa 

### Task III Higher level 

Now we are creating a higher level , level above current classification to classify the island as one object 

Add new process and add change algorithm to multiresolution segmentation 

Domain : Image object level 
Level : New Level 
New Level Name : L2 
Level usage as : Create Above 

and here you can play with scale parameter shape and compactness , it worked for me in 6000,0.4,0.7

![grafik](https://github.com/user-attachments/assets/67471bee-8fdd-4162-8191-467bc15cc76b)

Execute 

Now on view setting turn off new level and turn on the L2 and Outline 

![grafik](https://github.com/user-attachments/assets/68a6d781-3487-4ab5-adb2-684feb54b72a)

It should look like this and you should have single object for the island 
and we are done 

![grafik](https://github.com/user-attachments/assets/18a5face-347c-46a9-9262-4bd4c707380a)

Save your project and go home !
