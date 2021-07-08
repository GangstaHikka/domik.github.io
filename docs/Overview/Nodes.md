# **Nodes**
Here is a list of avaliable nodes which you can use do write the Pipeline logic.
To create a new node Right Click in the graph -> Create Node -> *Select Category* -> *Select Node*



## **Action Nodes**

- ### **Create Override Skin Layer node**

	![[Create Override Skin Layer screenshot.png]]
	
	The Create Override Skin Layer node creates a special layer which you can use to define cells which should use a special skin. It'll not override other skins in this cells, instead of it it'll add a new skin in the top of skin applying queue.
	
	_Parameters:_
	
	- skin - a Skin which will be used to create a Skin Layer


- ### **Find And Replace Node**

	![[Find And Replace Node screenshot.png]]
	
	Finds Cells with target Part and replaces the target part with the newPart on them.

	_Parameters_:
	
	- **target** - part which we want to replace
	- **newPart** - part which will replace


- ### **Extract Positions Node**

	![[Extract Positions Node.png]]
	
	The Extract Positions node extracts positions of input node to the output positions array.



- ### **Merge Override Skin Layers Node**

	![[Merge Override Skin Layers Node.png]]
	
	The Merge Override Skin Layers node merges input layers to one layer.



- ### **Shift Node**

	![[Shift Node.png]]
	
	The Shift node shifts positions for all input cells. 
	
	_Parameters:_
	
	- **X** - x axis offset
	- **Y** - y axis offset
	- **Floor** - floor offset



- ### **Split Into Rooms Node**

	![[Split Into Rooms Node.png]]

	The Split Into Rooms node splits input cells to rooms by overriding their roomIDs.
	
	Strongly Recommended to use before [[Place Interiors node]]. 
	
	_Parameters:_
	
	* **Min Size** - the minimum possible size of rooms
	* **Max Size** - the minimum possible size of rooms



## **Add nodes**




- ### **Add Part Node**

	![[Add Part Node.png]]

	The Add Part node adds a part to the input cells.

	==Before Add Part==

	==After Add Part==




- ### **Add Part to Part Node**

	![[Add Part to Part Node.png]]

	The Add Part to Part node filters cells by part and add another part to these cells.
	
	_Parameters:_
	- **target** - a [[Part]] which will be used as filter
	- **part** - a [[Part]] which will be added to filtered cells
	- **mode** 
		- **No Rotation** - just find cells with target [[Part]] and add new part to them
		- **Rotate Only Target** - find cells with all possible target rotations and add new part to them
		- **Rotate Target And Part** - sync target part and new part rotations.
	
	==Before==
	
	==After==



- ### **Add Roof Cells Node**

	![[Add Roof Cells Node.png]]

	The Add Roof Cells node adds additional cells in tops of input cells.
	Result looks like a pyramid.
	
	==Before==
	
	==After==





## **Filter nodes**



- ### **Filter By Added Floors Node**

	![[Filter By Added Floors Node.png]]

	The Filter By Added Floors node filters cells which positioned on the floors which wasn't described in the **Floors** House Generator menu.
	
	_Parameters:_
	
	- **Invert** - return cells without added floors.



- ### **Filter By Floor Node**

	![[Filter By Floor Node.png]]
	
	The **Filter By Floor** node filters cells positioned on the target floor.
	
	_Parameters:_
	
	- **int field** - floor which you want to filter


- ### **Filter By Mask Node**

	![[Filter By Mask Node.png]]

	The Filter By Mask node returns cells filtered by special mask.

	_Parameters:_
	
	- **Mask** - a mask which you want to use as filter

- ### **Filter By Positions Node**

	![[Filter By Positions Node.png]]

	The Filter By Positions node returns cells which has the same positions as in input Positions array.



- ### **Filter By Tag Node**

	![[Filter By Tag Node.png]]

	The FiIter By Tag node returns cells with target Tag.
	
	_Input:_
	
	- **In** - all cells which we want to filter
	- **Positions** - cells positions array which we want to use as a filter


- ### **Filter Internel Doors Places Node**

	![[Filter Internel Doors Places Node.png]]

	The Filter By Internal Doors Places analyzes input cells and returns suitable cellses for doors between rooms.
	
	_Output:_
	
	- **Forward** - Cells where you should add the door part which shouldn't be rotated
	- **Backward** - Cells where you should add the door part which should be rotated by **180** degress.
	- **Right** - Cells where you should add the door part which should be rotated by **90** degress.
	- **Left** - Cells where you should add the door part which should be rotated by **270** degress.


- ### **Filter Interseсtions Node**

	![[Filter Interseсtions Node.png]]

	The Filter Intersections node returns cells whose positions intersect, so if you have cells set with positions **[0, 0, 0]**, [0, 1, 0], **[1, 1, 0]** and [3, 4, 0], **[0, 0, 0]**, **[1, 1, 0]**, [3, 4, 1], the result will be -> **[0, 0, 0]**, **[1, 1, 0]**.



- ### **Filter Neighbour Cells Node**

	![[Filter Neighbour Cells Node.png]]

	The Filter Neighbour Cells node returns neighbour cells sorted by directions.



- ### **Filter Random Cell Node**

	![[Filter Random Cell Node.png]]

	The Filter Random Cell node returns a random cell from input cells.



- ### **Filter Random Input Node**

	![[Filter Random Input Node.png]]

	The Filter Random Input node returns cells from a random input.



- ### **Filter With Part Node**

	![[Filter With Part Node.png]]

	The Filter With Part node returns cells with a target part.



- ### **Filter Without Part Node**

	![[Filter Without Part Node.png]]

	The Filter Without Part node returns cells without a target part.




## **Flow**


- ### **Exclude Node**

	![[Exclude Node.png]]
	
	The Exclude node returns cells from A input but without cells from B input.



- ### **Merge Node**

	![[Merge Node.png]]

	The Merge node merges cells from input into one cells set (parts sets also will be merged) and then returns them.




- ### **Override Node**

	![[Override Node.png]]

	The Override node merges input cells into one cells set, but intersected cells from an A input will be overrode by cells from a B input.



- ### **Shuffle Node**

	![[Shuffle Node.png]]

	The Shuffle node shuffles an input cells array. That's not change cells positions or other sort of data, it just makes a chaotic reordering of an input cells set.




## **Main Nodes**


- ### **End Node**

	![[End Node.png]]

	The End node returns an input cells as a result of Pipeline working.
	The Pipeline should always have one (and only one) End node or it'll not working properly.
	
	You can also use this node for debugging, just connect an input of this node with output of some node to see that's happening in this step of generation.



- ### **Start Node**

	![[Start Node.png]]

	The Start node is an entry point of generation process. This node collects data stored in the House Generator component and use them to make a house draft. 
	
	The Start node returns a set of cells which represents a gabarits of house, but these cells has no parts, they aren't splitted by rooms and so on. That's just raw cells.

## **Place Nodes**


- ### **Place Interiors Node**

	![[Place Interiors Node.png]]

	The Place Interiors node analysis input cells and sets a relevent interior for them.
	It also places furniture.



- ### **Place Part Node**

	![[Place Part Node.png]]

	The Place Part node filters cells by mask and add a [[Part]] to them.



- ### **Place Placeable Object Forced Node**

	![[Place Placeable Object Forced Node.png]]

	Unlike Place Placeable Object node, this node ignores placing requirements and just place this Placeable Object on input cell. 
	
	_Input_:
	
	* **All** - all accessible cells, needs to run actions after placing (read [[Placeable Object]]).
	* **Target** - here you want to place this PlaceableObject.
	
	_Parameters_:
	
	* **placeableObject** - a Placeable Object which you want to place
	* **turn** - how you want to turn it when placing



- ### **Place Placeable Object Node**

	![[Place Placeable Object Node.png]]

	The Place Placeable Object node places a PlaceableObject ot input cells.
	
	_Parameters:_
	
	- **Placing Mode:**

		* **One Per House** - try to place Placeable Object only once.
		* **One Per Floor** - try to place Placeable Object once on every accessible floor. 
		* **One Per Room** - try to place Placeable Object once on every room. 
		* **One Per Cell** - try to place Placeable Object on every input cell.



- ### **Place Stairs Node**

	![[Place Stairs Node.png]]

	The Place Stairs node tires to place stairs in the longest stairwells. 
	
	Your house can have more than one stairwell, mostly because of difference between floors planning.  Cells of floors which wasn't successfully connected returns to the **Failed** output, so you can handle them by less demanding rules.
	
	- _input:_
		- **In** - cells to process
		- **Forbidden** - cells which inaccessible for stairs placing
		
	- _output:_
		- **Successful** - cells of floors which was connected by placed stairs.
		- **Failed** - cells of floors which wasn't connected by stairwell
		
	- _parameters:_
		- **stairs** - a Placeable Object which represents stairs
		- **minStairwellLenght** - minimal length of stairwell


## **Remove Nodes**
- #### **Remove Part Node**

	![[Remove Part Node.png]]

	The Remove Part node removes a part from all input cells.