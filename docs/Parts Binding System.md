# Parts Binding System

![[743ae66db928aacea80252eedbea7482.png]]

The easiest way to understand how to use the Parts Binding System is just looks to it in action. As you can see in screenshot above we have a list with pairs of objects. It's a binding list. 

---
Let's take a closer look at the binding element:

![[binding element.png]]


1. Reference to the [[Part Builder]].
2. Reference to relevant [[Part]].
3. **Rotation offset**.


!!! note
	Please note that they have the same names. It's a very important detail.


---


In process of generation the House Builder tries to find a relevant look to the [[Part]], so it asks every accessible skin if they have some look to the current [[Part]]. Look is a [[Part Builder]] as you might have guessed. And [[Skin]] answers him something like "Yey, I have one, take this ([[Part Builder]] and then rotate it by (**Rotation offset**)".

That's how it works.
But how to use it? 
Well, here are several ways to do it.

---

## Manual Binding

The easiest way is just add new binding element and drag'n'drop relevant [[Part]] and [[Part Builder]], and write a rotation offset.

But I don't recommend it because it makes workflow too tiring.
Instead of it I definitely recommend to use an **Auto Binding**.

---

## Auto Binding
Auto Binding is a much faster way to work with Skin.
You don't need to add binding pairs manually, instead of it you must comply the **PartBuilders namin convention**.

---

### PartBuilders naming convention
- Part and PartBuilder names should be the same. 
- If you want to add some special rotation you shall write it in square brackets.<br/>

	!!! example
    	**[90] Internal Wall** <br/>
   
- If PartBuilder should have 4 standard rotations (0, 90, 180, 270) you must write **[auto]** name prefix 

	!!! example
		**[auto] Internal Wall** <br/>
		
- If you want to change a look of some object turn separately, you can make an **[auto]** PartBuilder for the general rotations and one with **[special rotation]** for your special case.

	!!! example
		**[auto] Internal Wall** - with regular wallpapers <br/>
	    **[180] Internal Wall** - with dirty wallpapers
---


In process of binding [[Skin]] tries to find a part with the same name as current [[Part Builder]]. If it's found, it makes a new binding pair, else there are two scenarious:

1. Ignore this [[Part Builder]]
2. Make new [[Part]] for this [[Part Builder]]. 

	!!! note ""
		To find out how to select what to do with unbound PartBuilders read below. <br/>

If [[Part Builder]] has an  **[auto]** prefix, Binding System will try to find 4 Parts with **[0]**, **[90]**, **[180]** and **[270]** prefixes. Result will looks like that:

![[Pasted image 20210102185737.png]]

As you can see here we have 4 references to the same [[Part Builder]], but with different Parts, and we also have relevant rotation offsets for them. 

---

### Binding Panel

Now it's time to show how to apply changes.
An Auto Binding panel look

![[auto binding panel.png]]

1. **Create Parts for unbound?** - if true Skin will create new Parts for failed PartBuilders.
2. Path for new Parts.
3. **Change Folder** - press it to change a path for new Parts
4. **Update Binding** - click it to apply PartBuilding changes. 