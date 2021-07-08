# Skin
**Skin** is a bridge between [[Part]] and it's in-game representation.
From [[House Generator]] perspective, house is a structured collection of [[Part]], so you need to convert these parts to real game objects. Luckily, we have a system that does this automatically.
And this system is... the **Skin**, yay!

Skin contains a list of [[Part Builder]]. Every [[Part Builder]] contains a bind to [[Part]].
In process of building, the HouseBuilder asks every available **Skin** if it has anything for this part.

If skin contains a PartBuilder with binding to the processing part, HouseGenerator takes this PartBuilder and runs the Part Building Process.
Some internal fairy tale magic and...
Yay!
You have a built wall. Or window. Or... Some sort of criminal scenes! Or maybe the Spawn Point? PartBuilder can build that you want, just ask him! :D

>To find out how to work with the PartBuilder component read the PartBuilder section. 

Another interesting side of Skins System is that you can use more than one skin for the single house.
Why do you need it? 
Well, you can use an individual skin for every single room, whereby you will be able to change wallpapers, furniture vision or even add something absolutely new only for this room. 

>To find out how to do it read an Interior documentation section here.

Another way to use multiple skins is using the Pipeline Skins Layer.

Now take a closer look at the Skin stored in the HouseGenerator component: 

![[2cd21576337fa0e4b37e8f5da021403c.png]]


As you can see Skin is a regular prefab with the Skin component on the root, so you can open it in Prefab Mode by double clicking.
Skin contains a tons of children GameObjects, most of them contains a PartBuilder component.

![[bfb3430121ed6183f031e4626e8c4d2a.png]]



Now lets take a closer look at the Skin

![[743ae66db928aacea80252eedbea7482.png]]


## Settings

- Cell Width - width and length sizes of the cell. Just write a floor mesh width here (in meters).
- Cell Height - height of the cell. Just write a wall mesh height here (in meters).

## Binding
