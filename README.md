from typing import List

board = [
    "......................",
    "......##########......",
    "......#........#......",
    "......#........#......",
    "......#........#####..",
    "....###............#..",
    "....#............###..",
    "....##############....",
]


def flood_fill(input_board: List[str], old:str, new:str, x:int, y:int) -> List[str]:
    """Returns board with old values replaced with new values
    through flood filling starting from the coordinates x, y
    Args:
        input_board (List[str])
        old (str): Value to be replaced
        new (str): Value that replaces the old
        x (int): X-coordinate of the flood start point
        y (int): Y-coordinate of the flood start point
    Returns:
        List[str]: Modified board
  
    # Implement your code here.
"""
def dfs(input_board,x,y,old_t,new_t):
    n= len(input_board)
    m= len(input_board[0])
    
    if x < 0 or x>=n or y<0 or y>=m or input_board[x][y]!=old_t:
        return

    else:

        input_board[x][y]=new_color
        dfs (input_board,x+1,y,old_t,new_t)
        dfs (input_board,x-1,y,old_t,new_t)
        dfs (input_board,x,y+1,old_t,new_t)
        dfs (input_board,x,y-1,old_t,new_t)
    
    
def flood_fill(input_board,x,y,new_t):
    old_t=input_board[x][y]
    if old_t==new_t:
        return
    dfs(input_board,x,y,old_t,new_t)


modified_board = flood_fill(input_board=board, old=".", new="~", x=5, y=12)

for a in modified_board:
    print(a)

