# How to add new furniture?
From the Domik perspective there is no difference between walls, doors, furniture or something else.
It's all parts. 
If you want to add new furniture you should add new part. 
Part is an abstract idea of some object, so you need to add view to it also. 
Skins system provides it. 
That's how this system works:

1. You clicks **Generate button** 
2. **House Generator** requests it's **Pipeline** generate house cells (each cell is a container of parts) 
3. The **Pipeline** returns house cells 
4. **House Generator** iterates over all cells and then asks **skins** if they have some view (**PartBuilder**) for this part of the cell and if it found **House Generator** sends request to build it.

Read more: 	[[Deep Dive Into House Building Process]]

Lets add new chair to see how it works.
There is two workflow which you can use to add new house parts:

## Manual Workflow
Manual workflow is a **slow** and **ineffective** method of adding new house parts, but it's simple and intuitive. **Don't recommend to use it anyway**.

First, we need to create a chair part.
To do it click on some folder -> Create -> Domik -> Part
![[create chair part.gif]]
But that's not enough. Chair can have at least four rotations, so we have to add three more parts.

![[Pasted image 20210402151023.png]]

Now let's look at the Chair Part's inspector.
Here we have references to other three rotated parts
![[Pasted image 20210402151129.png]]

We should fill them to make things works properly.
![[part rotations fill.gif]]
Repeat it for Chair Right, Chair Left and Chair Backward parts.
Result will looks like that:

![[Pasted image 20210402153511.png]]
![[Pasted image 20210402151756.png]]
![[Pasted image 20210402153304.png]]
![[Pasted image 20210402153422.png]]

Now we need to create views for these parts. To do it we should use the Skins system. We can extend existed skin or create brand new. 
Let's extend the furniture skin.
To do it go to the Domik folder -> House Example -> Skins -> Furniture -> open Furniture Origin
![[open furniture skin.gif]]
Basically, Skin is a prefab with Skin component, so you can use it as regular prefab. In this example we open a Furniture Origin prefab because it's a root prefab. 
Furniture Black, Furniture White and Furniture Wooden Light are nested prefabs, so if you'll add something in the Furniture Origin prefabs it automatically will be added to these nested furniture prefabs.

### Adding Part's view to the furniture skin
That's how regular skin looks like.
In the hierarchy window you can see a tons of objects. 
They're parts views.
![[Pasted image 20210402161038.png]]
Enable objects which you want to edit or which represents an environment and disable other.
![[enable chilling section.gif]]

Note that these object contains a PartBuilder component.

Skin component is in the root object, so to work with it just select root object.

![[select root skin obj.gif]]

-------------

Now let's add a view for our chair!
To do it drag'n'drop some prefab or model to the skin's hierarchy.
![[drag'n'drop chair to skin.gif]]

Now we should add a Part Builder component to this chair.

![[add part builder to the chair.gif]]
 After that we should register this PartBuilder in the Skin.
 To do it we should add new bin to the Binds list in the Skin component, and drag Chair Part Builder and Chair Part to it. And set a rotation offset to the zero.
![[register chair part builder.gif]]
Repeat this with the rest of the turns.
![[add other chair rotations.gif]]

Congrats!
Let's checkout the result.
![[check manual made parts.gif]]

If Preview Systems draws parts you did everything right.
Now you can use it to create Placeable Object!

Read next: [[What is a Placeable Object]]

## Automated Workflow
Different way to add new stuff is using auto-binding tools. **This workflow is recommended.**

In this workflow we should add a PartBuilder for our new furniture to the skin, name it properly and start the AutoBinding process.
Skin will scan all Parts in the project and if It'll find Part and PartBuilder with the same name (except prefix in square brackets) - binds them together.
What if there is no Part for some PartBuilders?
Well, if you enabled a **Create Parts for unbound?** option they will be created automatically with relevant names. 

Also here we will use an **[auto]** prefix which means that this object can be rotated and the Skin will try to find or create four parts with **[0]**, **[90]**, **[180]** and **[270]** prefixes instead of **[auto]** prefix. 

Let's see it in action!

Open the Furniture skin and drag-n-drop the chair prefab to it's hierarchy.
![[drag-n-drop chair body.gif]]

Add **Part Builder** component to it.
![[add part builder to chair.gif]]

Add an **[auto]** prefix to it's name.

![[add part builder to chair 1.gif]]

Use this name prefix with things which can be rotated.
It'll works only if you use an auto-binding function.

Go to the Skin component and enable a **Create Parts for unbound?** checkbox if it disabled.
![[create parts for unbound checkbox.gif]]
Now the Skin will create parts for all **PartBuilders** for which there were no relevant parts. 

Select a folder there you want to put new parts.
![[select folder.gif]]
No all new parts will be dropped to this folder.

Click an **Update Binding** button.

![[update binding.gif]]

Done!
Let's check it.
![[check binding.gif]]

As you can see the chair rotates with little shift. 
That's because chair is not in the center of cell. ![[Pasted image 20210405173055.png]]

Let's fix it!
To do it move chair to the center of cell.
 ![[move to center of cell.gif]]

Checking out.![[check fixed chair.gif]]
Congratulations! 
Now you can use these parts to create a PlaceableObject.