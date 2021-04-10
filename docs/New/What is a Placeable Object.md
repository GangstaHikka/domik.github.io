# What is a Placeable Object?

Placeable Object is a generalization for all items which can be placed, including furniture.
Basically it's a container for part with placing requirements.
![[Pasted image 20210402143042.png]]

To create new floor select some folder in the **Project** window -> Right Mouse Click -> Create -> Domik -> PlaceableObject
![[create po.gif]]

### Preview
**Preview panel** helps you to work with the **Preview system**.
To continue we should create a **Preview** system instance. 
The Domik contains a preconfigured **Preview** instance prefab so you can just drag-n-drop it to the scene. To do it go to the **Domik** folder and select the **Preview** prefab and drop it somethere in the scene.

This system will draw all changes of selected Placeable Object, so watch it when you working with some Placeable Object.

Now let's go back to the **Preview** panel in the Placeable Object.

**Turn** - select special turn for preview.
**Build** button - press it to rebuild preview manually.
**Find** button - press it to find the **Preview** system instance in the scene.

### Settings
**Part** - this is the core of the Placeable Object. Basically, Placeable Object is just a **part** with placing rules. So here you should select that exactly do you want to place in the house cell.
![[Placeable Object part change preview.gif]]

**Possible Places** - here you should define where this part can be placed. 
Just add some **Places** or **Masks** to the list.
To see how this part will looks like in this place just select some of them.
![[Placeable Object place change preview.gif]]
You can add more than one place and Placeable Object will find much more potential places in the room.
![[Placeable Object multiple places preview.gif]]



### Actions after placing
Some objects should change environment around, and here you can describe it.
Basically, you just need to select some neighbour cell and add some actions to them which will be called after placing.

![[Pasted image 20210402143251.png]]

**Floor** - select a floor where you want to pick the cell
- **Top** - show cells on the floor above
- **Current** - show cells of the same floor where the target cell is
- **Down** - show cells on the floor below

Here you can see cells grid. Click on some cell to start working with it.

In the panel below you can see two lists:
- **remove list** - add here parts which will be removed from this cell after placing
- **add list** - add here parts which will be added to this cell after placing

![[Placeable Object add remove preview.gif]]

Added and removed parts will be showed on the **preview** with transparent green and red materials.