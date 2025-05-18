# 🧩 Progetto Tetris

**Tetris Game in Python with Tkinter**

This program is a Python-based implementation of the classic **Tetris** game using the **Tkinter** library for the graphical interface.  
It faithfully replicates core Tetris mechanics, including real-time gameplay, intuitive keyboard controls, line clearing, and dynamic scoring.

---

## 🎯 Key Features & Functionality

---

### 🧱 1. Grid Setup & Display

- **Grid Dimensions**:  
  Standard **10 columns × 20 rows**, rendered on a Tkinter `Canvas`.  
  Each cell measures **30×30 pixels**.

- **Grid Rendering**:  
  - Filled cells are shown in **blue**.
  - **Black outlines** define cell borders.

- **Tetromino Shapes**:  
  - Includes the classic 7 shapes: `I`, `O`, `T`, `L`, `J`, `S`, `Z`.  
  - Each shape is represented as a 2D array and appears at the **top-center** of the grid when spawned.

---

### 🎮 2. Player Controls

The player can use the keyboard for interactive gameplay:

| Key          | Action                          |
|--------------|----------------------------------|
| ⬅️ Left Arrow  | Move tetromino left              |
| ➡️ Right Arrow | Move tetromino right             |
| ⬇️ Down Arrow  | Accelerate tetromino descent     |
| ⬆️ Up Arrow    | Rotate tetromino (90° clockwise) |

Controls are validated to ensure:
- Tetrominoes **stay within boundaries**
- No **overlap with existing blocks**

---

### 🚧 3. Collision Detection

- The function `collision(dx, dy, shape)` checks for:
  - Collisions with grid borders
  - Overlaps with other blocks

- When a collision is detected:
  - The tetromino **locks in place**
  - A new tetromino starts falling

---

### 🧲 4. Locking & Clearing Lines

- Locked tetromino blocks are added to the **grid matrix**
- The game checks for **full lines**:
  - Full rows are **cleared**
  - Blocks above shift **downward**

- **Score Update**:
  - +10 points per locked block
  - +100 points per cleared line

---

### 🧮 5. Scoring System

- **+10 pts** for each block locked in place  
- **+100 pts** for each complete line cleared  
- The current score is shown at the **top of the game window**, updating in real-time

---

### 💀 6. Game Over Condition

- Game over occurs when a **new tetromino cannot be placed**
- Triggered when the **top row is blocked**

---

### ⏱️ 7. Automatic Falling

- Tetrominoes fall automatically every **150 milliseconds**
- Managed by the `schedule_update()` function:
  - Calls `move_down()` periodically
  - Locks tetromino if it can’t move further

---
