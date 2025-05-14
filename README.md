# Progetto-Tetris
Tetris Game in Python with Tkinter
This program is a Python-based implementation of the classic Tetris game using the Tkinter library for the graphical interface. The game faithfully replicates the core mechanics of Tetris, featuring real-time updates, player controls, and scoring.

Key Features & Functionality
1. Grid Setup & Display
Grid Dimensions:
The game grid is 10 columns by 20 rows (standard Tetris grid), rendered on a Tkinter canvas. Each cell is 30x30 pixels in size.

Grid Rendering:
The grid is drawn on the canvas, with blue blocks representing filled cells and black outlines to define the boundaries.

Tetromino Shapes:
The game uses seven distinct tetromino shapes (I, O, T, L, J, S, Z), stored as 2D arrays, randomly selected to fall in the game. Each block is initially placed at the top-center of the grid.

2. Player Controls
The player can interact with the game using the following keyboard inputs:

Left Arrow: Move the tetromino left by one cell.

Right Arrow: Move the tetromino right by one cell.

Down Arrow: Accelerate the tetromino’s descent.

Up Arrow: Rotate the tetromino by 90 degrees clockwise.

These actions are validated to ensure:

The tetromino does not move outside the grid boundaries.

The tetromino doesn’t overlap with existing blocks in the grid.

3. Collision Detection
The function collision(dx, dy, shape) checks whether the tetromino, after a move, would collide with existing blocks or go out of bounds.

When a tetromino reaches the bottom of the grid or collides with another block, it locks in place, and the next tetromino starts falling.

4. Locking Tetrominoes & Clearing Lines
When a tetromino locks into place, its blocks are added to the grid.

The program checks for full lines (rows that are completely filled with blocks). Any full lines are cleared, and the blocks above them shift down.

Score Update: Players earn points for each block that locks in place and for every line that is cleared.

5. Scoring System
Score per Block:
Players earn 10 points for each block that is locked in place when the tetromino lands.

Score per Line:
Clearing a full line rewards 100 points per line.

The current score is displayed at the top of the game window, and it updates dynamically as the game progresses.

6. Game Over Condition
The game ends when a new tetromino cannot be placed because the grid is filled. This is detected by checking for collisions as soon as a new tetromino is spawned.

Game Over is triggered if the top row is blocked.

7. Automatic Falling
The tetromino falls automatically, updating every 150 milliseconds.
This is controlled by the schedule_update() method, which calls the move_down() function to make the tetromino drop. If it cannot move further, it locks into place.

