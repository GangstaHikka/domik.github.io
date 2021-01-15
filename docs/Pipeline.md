# Pipeline
The Pipeline is a visual scripting language which uses to generate a house.
To create a new instance of Pipeline right click on some folder -> Create -> Domik -> Pipeline.
To open some existed Pipeline just double click to it.

![[Pasted image 20210105162713.png]]

In pipeline you describes a process of house generation step-by-step.
The pipeline consists of nodes.
Every node is a step of generation of house.

![[Pasted image 20210105163126.png]]

In most cases typical node has two pines: 
- In - Input cells.
- Out - output cells.

Node get cells from Input, process them and returns to Output.
Sometimes it contains parameters. 


Every pipeline instance should have at least two nodes: Start Node and End Node. 
Start Node gets an info from [[House Generator]] and constructs raw cells.
End Node returns processed nodes to the House Builder.

Here is an example of primitive pipeline.

![[Pasted image 20210105163924.png]]

- **Start** Node  - creates a set of nodes based an info from [[House Generator]].
- **Add Parts** Node - adds Floor part and Ceiling part to all cells from input.
- **End** node - returns input cells with floors and ceilings to the House Builder.

![[Pasted image 20210105164400.png]]

To get more information about possible nodes read nodes description below: