# Placeable Object

Placeable Object is, basically, a [[Part]] with info where you want to place it.
Mostly uses for furniture, but you can use it even for place walls or something else.

![[Pasted image 20210104194857.png]]


Preview handles a placeable object automatically, so you can see changes instantly.

![[Pasted image 20210104195025.png]]


- Part - reference to the [[Part]] which you want to place somewhere.
- Find By - what you want to use to find a better place for this part?
	- Place - use [[Place]]
	- Mask - use Mask
- Reference to Place or Mask

> Please not that you don't wan't to make a Placeable Object for every rotations of [[Part]]. [[Part]] will be rotated automatically depending on found place.
> If [[Part]] didn't rotated check [[Part]] rotation references.



## Actions after placing

![[Pasted image 20210104195606.png]]


Sometimes you need to change placed Part environment.
To do it select cell which you want to change and add Parts to remove parts list and add parts list.

In the preview you'll see removed and

![[Pasted image 20210104195956.png]]