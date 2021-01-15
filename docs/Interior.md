# Interior
Interior is a scriptable object with info about room transformation. (Yea, that's just an interior, lol).
Place Interiors Node will try to find suitable interiors for all rooms in the house.

![[Pasted image 20210104205240.png]]

---

## Furniture
Furniture - a list of [[Placeable Object]] or [[Placeable Objects Container]]. Add here all that you want to see in this room.

---

## Skins
Skins - skins which will override a Base Skin from the [[House Generator]]. If you want to change a default look of walls, ceiling, floor, etc. just make new Skin with different materials for them and add here.

---

## Placing Rules
Here you can write special requirements for room.
- Max Count Per Floor - limit for that type of interiors per floor. If you don't want to have more than two toilets per floor just write here ```2```.
- Prefer Room - requirements for room size
	- Small - prefer small rooms
	- Medium - prefer medium rooms
	- Big  - prefer big rooms
	- Random - you don't care


---

## Parts Limit

![[Pasted image 20210104210426.png]]
Here you can describe which parts you don't want to see in this interior.
If you don't want to have windows in the toilet add a window part here and select an **Unacceptable** mode.

---

#### Possible States

![[Pasted image 20210104210708.png]]
- Fixed - you want to see the concrete count of this part in this room
- Rande - count of this Part can be in range between min and max.
- At least one - acceptable if this room has at least one exemplar of this part
- Unacceptable - this part is prohibited in this room