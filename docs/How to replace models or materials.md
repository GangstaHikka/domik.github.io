# **How to replace models or materials?**

Changes of things look provides by the **skin** system.
You want to replace a chair model? Replace it in the skin.  
What is a skin? Read here: [[Skin]]

The same for walls, doors, facades etc. Everything changes by changing skins.

Every skin contains a bunch of views of objects.  
House has two groups of skins:  

- Base skins.
- Interior skins.

Base skins usually contains facade objects, roof and 	 other things which don't belong to rooms. But these skins are able to contains default look for things, that's fine and that's because these skins uses as a fallback for situations then some room thing can't find a part builder in relevant interior skins.

So if you want to change look of the room - change Interior skin. If you want to change facade - change the base skin.

## **Replace a sofa model example**
Sofa is a part of room, so we need to change interior skins to get the result. 

!!! note
	You can change a view of object just for one interior, so all rooms with this interior will have this new look, but other rooms will not.   
	To change a look of some object for all rooms you should change it in all interior skins.


![[change_sofa.gif]]

1. Open a **Furniture Origin** Skin
2. Select **[auto] Chilling Section Small**
3. Remove sofa models.
4. Add new model as a child of the **[auto] Chilling Section Small** game object.
5. Fix position
6. Close the prefab workspace
7. Regenerate the house 

## **Replace a sofa model by skin overriding**

Another interesting way to replace something is a skin overriding. 

To find out that does it mean lets select some interior.
![[Pasted image 20210709114829.png]]

Take a closer look on the Skins section. It's a list of skins for this interior.  
Order of skins is important, top skins have higher priority than down, so you can create a new skin, add sofa to it and place it in the top of skins list. In result default sofa will be overriden by new.

![[change sofa by overriding.gif]]

1. Create prefab
2. Add **Skin** component to this prefab
3. Open prefab
4. Create an empty game object
5. Name it exactly as object which you want to replace 
6. Add **Part Builder** component to this object
7. Reset it's position
8. Place new model as a child of this game object
9. Fix position
10. Click an **Update Binding** button on the **Skin** component on the prefab root.
11. Close prefab workspace and select an interior
12. Add this skin in the top of the skins list
13. Regenerate the house