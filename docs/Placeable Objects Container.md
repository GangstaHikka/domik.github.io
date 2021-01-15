# Placeable Objects Container
Placeable objects container is a scriptable object with references to [[Placeable Object]] or [[Placeable Objects Container]].

![[Pasted image 20210104200256.png]]


- Mode - placing mode
	- Place All - try to place all PlaceableObjects from list below
	- Place First Relative - iterates over Placeable Objects list and stops after first success.
	- Place Random Relative - collect all potentially successed Placeable Objects but place only one by random.

---
### Tips


There are a lots of ways to use it.

- First, you should use it if you have a PlaceableObject which can be placed in multiple places. To do it create a PlaceableObjects for every possible Place, add them to the PlaceableObjects list below and change mode to **Place First Relative** or **Place Random Relative** mode.

- Second case is then you have multiple similiar PlaceableObjects but want to add only one. To do it add them to the list and change mode to **Place Random Relative** mode.

- And the last is the case when you want to place a list of PlaceableObjects at the same time. Pretty suitable when you want to stay interiors list little bit cleaner.

>And yes, you can make something like a container with **Place All** mode and fill it by containers with  **Place Random Relative** mode, so this container will try to place all child containers.