# How to change Facade?
As you may read before, everything about the appearance, changes through the skin system. So, if we want to change view of the facade we should change house base skins. But in case of house skins things little bit difficultly. Facade of the house is splitted to five segments - thin facade, regular facade, thick facade, columns and plinth, so you can combine them as you want by changing floors tags. Or you can override House Skins in the House Generator component by adding new skins in top of the list. 

## Method 1 - Change Floors Tags
This method provides by the Pipeline. To use it just select some floor and change it's facade tag.

![[change roof tag.gif]]

It works because an example pipeline includes special logic.
![[Pasted image 20210409145446.png]]

Here cells of floors with Facade tags will be filtered and processed to achive the final result. 
You can create your own Tags and generation steps also. 
Read more: [[What are floor tags]]

## Method 2 - Change House Skins

Select the House Generator prefab instance on the scene and look at the House Skins panel.
![[Pasted image 20210408121850.png]]

Here is already added a Facade pallets random container and three skins.
![[Pasted image 20210408122102.png]]


To change the house facade we should add new skin in top of this skins list. Facade is splitted into five skins, but in this tutorial we will change only one - **Facade Regular skin**.

To do it let's just duplicate already existed regular facade skin and edit it.
Go to the Domik folder -> House Example -> Skins -> Facade Walls Regular, duplicate some skin and open it.

![[dublicate facade regular.gif]]

Now replace materials with something other.

![[change facade wall mat.gif]]

Exit with saving, drag-n-drop this skin in top of the House Generator skins list and regenerate to checkout the result.


![[Checkout pink facade.gif]]

You can also change meshes of walls or add something new. Let's make this wall even worse and add new window frames.

![[add window frames.gif]]

## Method 3: Working with Palettes.
Palettes is a tool which mostly uses to make skins more randomly, but you can use it to work with skins more comfortable as well.

