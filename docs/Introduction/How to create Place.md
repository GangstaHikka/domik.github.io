# How to create Place
To create new floor select some folder in the **Project** window -> Right Mouse Click -> Create -> Domik -> Place

Place is a description of some... place :D
Basically it's a small 3x3x3 grid  with parts. Filter node or Placing System will use it to filter cells with identical environment. 
So you can use it to define where you want to place some Placeable Object or you can use it to filter cells in the Pipeline.

### Parts
**Floor** -  select floor which cells you want to edit.
#### Cells Grid
Here is a grid of cells which represent some place. Click on some cell to start working with it.

- **Enable** - set true if you want to check this cell in filtration progress.
- **Parts List** - add here all parts which you expect to see in this cell.

!Note: disabled cell and enabled cell but without parts are not equal! If you enable some cell but didn't add parts means that you expect that this cell will be totally empty. 



