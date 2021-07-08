# Add new furniture
Now let's add something new to the house.
Something like a chair and candellar.
First, we need to have a prefab for new furniture, so let's make them.

==prepare new furniture prefabs gif==

Now we should add them to the base House Generator skin

==open skin and add new prefabs to root==

Add **Part Builder** component to prefabs

==Part builder components adding==

Unlike candellar, chair can be rotated around, so we shall to add an **[auto]** prefix to it's name

==prefix gif==

Now select skin prefab root and click **Update Binding** button.
Wait some time, that's not an instant process.

==Binging update==

Yay! We did it. Now it's time to check binding. Select created parts and checkout Part reference

==Check binding==

To be sure that everything works fine select Skin root and find created binds

==Finding binds==

So here we have these five binds
==candelar bind==
==chair binds==
As you can see chair contains four binds and candellar contains one bind.
That's because chair can be rotated by 90, 180 and 270 degresses unlike candellar.

Save skin prefab and close
==save and close skin prefab== 

Next we should create Placeable Objects for new furniture, however, there is something to be done before. 
To work effective you should use a **Preview** system.
It'll show all changes of Placeable Objects, Places and Masks instantly.
To do it just select **Preview** prefab and drop it on the scene.

==Drop preview==

Now it's time to create Placeable Objects for new furnitures.
==create new placeable objects for chair and candellar==

Select them and add references it relevant parts
==select po and add part references==

Now we should define where we want to place this furniture. 
To do it select some places in **Place** field
==Select places for PO==

> Preview shows how placing furniture will looks in the requested place.

We made our first Placeable Object. 
> Basically, Placeable Object is a part with place description where it should be placed.

Next we should add it to Interior.
To do it select some interior and add placeable objects to the furniture list

==Adding placeable objects to skin furniture list==

Now let's checkout what this interior is added to some floor

==Select House Generator and checking interior list==

Yay, that's here.
Now it's time to check results!
To do it just click **Generate Button** and try to find our furniture in the house:

==Checking house==


