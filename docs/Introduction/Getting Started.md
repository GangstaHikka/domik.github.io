# Getting Started
Domik is a procedural house generator which you can use to create houses in the editor or runtime.


## **What can Domik do for you?**
- You can generate a lots of different houses to your game less than several minutes.
- [You can add your own 3D models](../How%20to%20replace%20models%20or%20materials.md) instead of built-in.
- You can create **your own furniture** or something else like a **spawn point**. Just use the furniture system.
- You can delete an  example folder and do everything your own way.
- No, coding is not necessary, the Domik includes a powerful **visual scripting system - the Pipeline**.
- You can change **walls**, **doors**, **ceiling**, **roof**... **everything**!
- You can generate a house **runtime** if you want to make something like a **roguelike game**.
- You can switch between different looks of the house by **skins system**.
- And yeah, skin system supports **2D and 3D assets** (there is no 2D skin examples at this moment, however).
- You can work with rooms view individually by an **interior system**.
- Multiple floors are supported.
- Stairs are supported.
- Elevators can be added pretty easy, but there is no example at this moment.
- Generation based on the **seed number**, so you can integrate the Domik with your own procedural worlds.
- You can use the seed number to generate houses in the **multiplayer** game too! Just send the seed number to client-side house generators and they were create the same houses as on the server.
- You can use it in **mobile**, **console**, **WebGL** and **PC** games (but be careful with performance, some tech tweaks can be necessary to provide a smooth experience).
- You can use it with **HDRP**, **URP** and **Built-in** scriptable pipeline. Just update project materials as it says in the Unity documentation.
- You can **change** things **by hands** after generation process.
- The Domik has it's own **mesh combine system**, so optimization process is little bit easy. But external house building solutions also possible.
- You can make beautiful and complex **facades**.
- You can make a house without facades if you wan't to make something like the Sims. Or without roof! Or without furniture! Or... You can do what you want, you're big boy (or girl, or something between), just use **the Pipeline**!

## **Create your first procedural house**

![[drag-n-drop.gif]]

1. Open the **Domik** folder 
2. Select **House Example prefab** 
3. Drag-n-Drop it on the scene.
4. Select it on the scene 
5. Click **Generate From Random** button in the Inspector.

Congrats!

Now let's **make them more**.

![[multiple houses.gif]]

1. Select **House Example Prefab** in the **Hierarchy**.
2. Press **Ctrl-D** to duplicate prefab instance in the scene. 
3. Change the position on duplicated house by dragging gizmo handle.
4. Click **Generate Random** button to regenerate it.
5. Repeat.

Wonderful bunch of houses, isn't it?

<br/>

You can also regenerate some house to change it's look.
![[regen.gif]]


**TODO:** все примеры создаваемой мебели разделить на колонны и описывать отдельно, чтобы чувак мог посмотреть как создать другой тип мебели просто кликнув на другую колонку. Колонок будет много, от самой простой вроде коробки на полу, до сложной, вроде лестницы, где надо будет создавать свою маску и лезть в пайплайн. Также будет и вариант, где надо будет сделать кастомный Place

> [[Create Preview System]] before starting work with articles below.


### **See Also**
- [[How to change house size]]
- [[How to change house floors]]
- [[How to change room walls]]
- [[How to change facade]]

- [[How to add new furniture]]
- [[What is a Placeable Object]]
