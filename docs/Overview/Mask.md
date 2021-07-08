# Mask
Mask, also known as adjacency mask, is a description about accessibility from central cell to neighbour cells.

You can use it as way as [[Place]], but in more brutal manner. Use it if you wan't to find house or rooms borders, some holes or something like that, and you don't care about parts inside of them. 

![[Pasted image 20210104202130.png]]

- Space - what type of adjacency you want to check
	- House - cell is accessible if exists in the house. Good choice if you want to find something like a borders of house.
	- Room - cells is accessible if exists in the house and if it has the same RoomID as the current cell. Use it if you want to find borders of rooms.
- Floor - changes floor for cells grid panel
- Grid of cells - click on the cell which checking status you want to change.
- State - which accessibility status this cell should have?
	- Accessible - this cell should be accessible from current cell
	- Inaccessible - this cell should be inaccessible from current cell

