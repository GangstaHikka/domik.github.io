# Deep dive into house building process

The process of house generation splits in three steps: 

1. Generating **house cells**
2. Extracting a **house build data** from **cells**
3. Building the house from an extracted **house build data**
	
## 1. **Generating house cells**.

![[Pipeline advanced.png]]

This step provides by the Pipeline - a visual scripting system. From the Pipeline perspective there is no 3D meshes, materials, textures etc. The Pipeline works with an abstract idea of parts of the house. And the name of this abstract thing is... **The Part**! Pretty obvious :D



----------

### **That is the Part?**

![[Pasted image 20210329181311.png]]

So, basically, **part** is a scriptable object with name and references to 3 other parts which represents exactly the same part but rotated by 90, 180 and 270 degrees. **Some parts has no rotations** (example: floor, ceiling, round table...) so **rotated parts references will be empty and that's fine**.

??? Abstract "Part without rotations"

	![[Pasted image 20210329181537.png]]

The most important aspect of the part instance is **it's name**. The part's name is all that the Pipeline should know to start working with it. You can even have two parts with different GUID but with the **same name** and the Pipeline will thinks that they **are equals**. 

---------

The Pipeline has only one target - create cells. 

--------

### **That are Cells?**

Cells is an abstract representation of house in the code. 
To understand the conception just image a house as a 3D grid of cells.

![[Снимок экрана 2021-03-29 182815.jpg]]

![[Снимок экрана 2021-03-29 182512.jpg]]

Each cell contains a floor, ceiling, walls and something else. 
Floor, ceiling and walls are **parts**.
So yeah, cells is just a 3D grid of parts lists. 





??? Abstract "Representation in code"

	=== "Cells"

    	![[Pasted image 20210329190104.png]]


	=== "Cell"

    	![[Pasted image 20210329190248.png]]
















		

-------

In the pipeline you creates cells, modifies them, removes, merges and so on.
And in the end you returns the result in the end node. 
Created cells comes to the second step of the generation - extracting a house build data from cells.

## 2. **Extracting a house build data from cells**.
Build Data Extractor transforms cells from an abstract representation of house to the house building instruction. It sorts cells to floors and rooms and finds part's builder for all cell's parts.
To do it Build Data Extractor asks skins if they have a PartBuilder for some part.

Priority of skins asking from highest to lowest:

1. Override Skin Layer 1 from the Pipeline
2. Override Skin Layer 2 from the Pipeline
3. Override Skin Layer 3 from the Pipeline
4. Room interior skins
5. House Base skins


??? Abstract "Skins"

	=== "Override Skin Layers"

    	![[Pasted image 20210329185321.png]]


	=== "Interior Skins"

    	![[Pasted image 20210329185529.png]]
		
		
	=== "House Base Skins"

    	![[Pasted image 20210329185651.png]]








So interior skins has always higher priority than house skins and by this reason you can override a view of room's walls by changing interior skins.

**Override Skin Layers** were created for special cases when you want to change view of some special cells filtered by your own rules in the Pipeline.

If there is no PartBuilder for some part this part will be ignored during house building.

So in the result it returns a structured collection of PartBuilders - a **House Build Data**. 


??? Abstract "Representation in code"

	=== "Floors"
	
		![[Снимок экрана 2021-03-29 195441.jpg]]

	=== "Floor"

    	![[Снимок экрана 2021-03-29 195559.jpg]]
		
	=== "Room"

    	![[Снимок экрана 2021-03-29 195702.jpg]]
		
	=== "Cell"

    	![[Снимок экрана 2021-03-29 195836.jpg]]





## 3. **Building of the house by the house build data.**

The House Builder takes a house build data and just build it!
Actually it's a little more complicated but there is no reason to dive so deep. 

## **But why so complicated?**
Well, there is only one reason - **flexibility**. 
If you are programmer you may know the conception of **model-view splitting**.
Here **Part is a model** and **PartBuilder is a view**. Part is an abstract idea of something, and it's very important to stay this idea clear. Thanks to this separation **we can redefine how cell should look right on the fly**. 

**For example** you created some pipeline which generates a simple village house. And you have a regular village where you want to place it. So you just do it. Awesome. But then you want to add a village which was corrupted by chaos, with lakes of blood, rusted chains and so on. But you have this innocent vibrant happy house! That's not that you want. Thanks to this separation, **you just need to edit skins** to change a view of house. **You don't need to touch the Pipeline at all**. And that's wonderful.