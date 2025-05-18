# 🎮 Progetto Tetris
A classic Tetris game implemented in Python using Tkinter for the graphical interface. This version replicates the original mechanics of Tetris, including real-time updates, keyboard controls, score tracking, and automatic falling pieces.

## ✨ Key Features
🧱 Grid Setup & Display
Dimensions: Standard 10×20 grid, with each cell sized 30×30 pixels.

## Rendering:

**Grid drawn on a Tkinter Canvas.**

**Blue blocks represent filled cells.**

**Black outlines highlight cell boundaries.**

## Tetrominoes:

Includes all 7 standard shapes: I, O, T, L, J, S, Z.

Shapes are stored as 2D arrays and spawn at the top-center of the grid.

## 🎮 Player Controls
Control the tetromino using your keyboard:

Key	Action
⬅️ Left Arrow	Move tetromino one cell left
➡️ Right Arrow	Move tetromino one cell right
⬇️ Down Arrow	Accelerate descent
⬆️ Up Arrow	Rotate 90° clockwise

All movements are validated to prevent:

Exiting the grid boundaries.

Overlapping with existing blocks.

🧩 Collision Detection
The function collision(dx, dy, shape) checks if a tetromino would collide with the edge of the grid or with other blocks after a move.

When a collision is detected at the bottom or with another block, the tetromino locks in place and a new one spawns.

🔒 Locking Tetrominoes & Clearing Lines
Once locked, the tetromino’s blocks are added to the grid.

The program checks for full lines:

If a row is completely filled, it is cleared.

Blocks above the cleared line fall down.

Scoring:

+10 points per locked block.

+100 points per cleared line.

🧮 Scoring System
Score per Block: +10 points when a tetromino lands.

Score per Line: +100 points per completed line.

The current score is displayed and updates in real-time.

❌ Game Over
Triggered when a new tetromino cannot be placed due to blocked cells at the top of the grid.

This is checked immediately after a new tetromino spawns.

⏱️ Automatic Falling
Tetrominoes fall automatically every 150 milliseconds.

Controlled by the schedule_update() method, which calls move_down():

If the tetromino can't move down, it locks in place and the next shape begins.
