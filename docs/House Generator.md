# House Generator

The House Generator component is the entry point to start generation of house.

![[Pasted image 20210105135339.png]]



To create a house generator: 
- Right Click on the scene hierarchy -> Create Empty -> select created gameObject -> AddComponent -> House Generator.
- Just drag-n-drop existed house generator prefab to the scene.

---

## Generate Section
![[b32819f4dfdc71e12ee5da5a8454e483.png]]

- **Generate Random** - triggers a house generation with random Seed.

- **Seed** - a number which uses to generate a house.

- **Generate** - triggers a house generation from current Seed. Pretty useful for regenerate a house after some changes.                    
- **Pipeline** - a reference to Pipeline Node Graph instance. If you want to change a generation rules just change the pipeline!
- **Combining Mode** - how accurate House Builder should combine meshes.
   - **Realtime**  - fast but with artifacts. 
                                 Pretty suitable for realtime generation or if you want to check what happens 
                                 after some changes.
                              
   - **Baked** - long but artifacts free. You can use it in realtime also!
  
---

## House Skins

![[Pasted image 20210105135701.png]]

Here is a list of base house skins. 
You can think about these skins as about skins by default.

---

## Floors
**Floors** is a description of expected house floors.

![[Pasted image 20210105155951.png]]


#### Floor Plans
Floor Plans is a list of expected floors.
Select some floor or add new to start changes.
**Panels below represents settings of selected house.**

- **Name** - name of selected floor.
- **Interiors** - List of possible [[Interior]] for selected floor. If you want to increase chance of placing some interior - reorder it to top of the list.
- **Tags** - floor tags. This floor will be marked by these tags, so you'll be able to filter this floor by some of these tags and make changes.
	
	Example of filtering by tag:
	
	![[Pasted image 20210105141516.png]]
	
	
	