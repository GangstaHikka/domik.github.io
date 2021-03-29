# How to create mask
To create new floor select some folder in the **Project** window -> Right Mouse Click -> Create -> Domik -> Mask

Mask also knows as Adjacency Mask is a description of some place but in terms of accessibility from the target cell. Mostly useful in situations when you want to find borders of rooms or whole house.

- **Space** - what type of accessibility do you want to check?
	- **House** - you want to check that the neighboring cell belongs to the house (you want to find borders of house).
	- **Rooms** - you want to check that the neighboring cell belongs to target cell's room (you want to find borders of room).
 - **Floor** -  select floor where you want to edit cells checking mode.
 
To start working with cells select some cell in the grid.
**State** - select what you expect from this cell
-	**Not Important** - you don't want to check this cell.
-	**Accessible** - this cell should be belong to the same room as a target cell if you selected the **Rooms** space or this cell should be belong to the house if you selected the **House** space.
-	**Inaccessible** - this cell should be belong to another room or doesn't exist at all if you selected the **Room** space. If you selected the **House** space this cell shouldn't exist in this house. 