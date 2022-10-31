# floodfill

#I am using numbers for flood fill where all the 1 will turn into two however the last 1 on last row will still be one because there is no diagonal crossing 

#define grid to navigate 
def floodfill(grid,row,col,newColor):
    oldColor= grid[row][col]
    if newColor == oldColor:
        return grid

    recurse(grid,row,col,newColor,oldColor)
    return grid

# calling recursion when statement is true
def recurse(grid,row,col,newColor,oldColor):
    if grid[row][col]!= oldColor:
        return

    grid[row][col] = newColor

    if row !=0:
        recurse(grid,row-1,col,newColor,oldColor)

    if col !=0:
        recurse(grid,row,col-1,newColor,oldColor)

    if col != len(grid[0])-1:
        recurse(grid,row,col+1,newColor,oldColor)

    if row != len(grid)-1:
        recurse(grid,row+1,col,newColor,oldColor)



floodfill([[1,1,1],[1,1,0],[1,0,1]],1,1,2)
