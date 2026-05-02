# Idea #4: Portal Puzzle Maze Game

## What is it?
First person maze game where you have to escape but there are portals everywhere that teleport you to different parts of the maze. You gotta find the exit before time runs out.

## Game Features
- Randomly generated mazes
- Portal system that tricks you 
- Timer that gets faster each level
- Enemies that chase you through portals
- Different difficulty modes

## Code Ranks

### Beginner Noob (Start Here)
Just learn how to make a basic maze on screen. Draw walls, make a player that can move around with arrow keys. No portals yet, just get movement working.

```python
# Super simple grid maze
maze = [
    [1,1,1,1,1],
    [1,0,0,0,1],
    [1,0,1,0,1],
    [1,0,0,0,1],
    [1,1,1,1,1]
]

player_x = 1
player_y = 1

# Check if can move
if maze[player_y + 1][player_x] == 0:
    player_y += 1
