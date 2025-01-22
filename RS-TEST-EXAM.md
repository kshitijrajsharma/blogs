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

You should see window like this 
![grafik](https://github.com/user-attachments/assets/3de1ffc3-9cd3-4895-8a2f-5fba460d0683)

Right click on the Sample Editor & Hit Select Features to Display 

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

You should be able to see your classification now , Volaaaa

![grafik](https://github.com/user-attachments/assets/cf584adb-9234-44ca-b125-1b11a3a3809d)

