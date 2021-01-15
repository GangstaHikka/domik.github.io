# Part Builder
![[Pasted image 20210101154748.png]]


Part Builder is a component responsible for creating a Part look.
To make a Part Builder for some Part just drag'n'drop some GameObject (which represents how this part should looks like) under into the Skin hierarchy, add the PartBuilder component, rename this gameObject to the same name as Part and Click the **Update Binding** button in the Skin. If this Part should has rotations, Add `[auto]` to the name of the Part. Binding will handle all rotations automatically. 

- **Own Part** - link to the automatically binded Part. Using for debug, the real information about binding stored in the Skin component. 
- **Combine** - do you want to combine this part meshes? 
- **Space** - select the building space
   - **Room** - place this part to the room space.
   - **Floor** - place this part to the floor space.
   - **House** - place this part to the house space.

> *What space should I select?*
> Well, that's not so hard to find it out. <br/>
> If it's something what should be in the room, select the **Room Space**.
> **Example: ** room (internal) walls, furniture, loot. <br/>
> If it's something relative for whole floor, select the **Floor Space**
> **Example: ** water on the floor, gas, Post Processing Volume with horror preset for the vault floor. <br/>
> And the same for the **House Space**
> **Example: ** Facade (external) walls, roof, facade plinth.