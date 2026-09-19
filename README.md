<div align="center">

# Maze Runner Game
# 🌀🏁

### A Desktop Maze Game Built with Python and Pygame

A desktop maze runner with a **randomly generated maze**, **arrow-key movement**, **wall collision**, a **goal gate**, and a **live timer** — written as small Python modules and ready to run locally.

<br>

# 👨‍💻 **Sadra Hatami**

### *Developer • Software Engineer • Creator*

<br>

![Python](https://img.shields.io/badge/Python-3.8%2B-3776AB?style=for-the-badge&logo=python&logoColor=white)
![Pygame](https://img.shields.io/badge/Pygame-Desktop%20Game-green?style=for-the-badge)
![Algorithm](https://img.shields.io/badge/Maze-DFS%20Backtracking-6f42c1?style=for-the-badge)
![Controls](https://img.shields.io/badge/Controls-Arrow%20Keys-0078D6?style=for-the-badge)
![Platform](https://img.shields.io/badge/Platform-Windows%20%7C%20macOS%20%7C%20Linux-2C3E50?style=for-the-badge)
[![License](https://img.shields.io/badge/License-MIT-green.svg?style=for-the-badge)](LICENSE)
![GitHub](https://img.shields.io/badge/Open_Source-Project-black?style=for-the-badge&logo=github)

<br>

[🌐 GitHub Profile](https://github.com/sadra-hatami)
•
[📧 Contact](mailto:sadra.hatami.1732@gmail.com)

</div>

---

# 📑 Table of Contents

- [About](#-about)
- [Why Maze Runner?](#-why-maze-runner)
- [Key Features](#-key-features)
- [How to Play](#-how-to-play)
- [How the Maze Is Built](#-how-the-maze-is-built)
- [Project Structure](#-project-structure)
- [Technologies](#️-technologies)
- [Usage](#️-usage)
- [Target Audience](#-target-audience)
- [Roadmap](#-roadmap)
- [FAQ](#-frequently-asked-questions)
- [Contributing](#-contributing)
- [Contact](#-contact)
- [License](#-license)
- [Copyright](#-copyright)
- [Support](#-support)

---

# 📖 About

**Maze Runner Game** is a desktop maze game written in Python with Pygame.

Each run builds a new maze with a depth-first search / recursive-backtracking generator. The player starts in the first cell and must reach the gate on the last cell. A sidebar shows the move instructions, the elapsed time, and a win message when the gate is reached.

The project is split into small modules for the window loop, maze, cells, player, goal, and timer.

> **Tagline:** *A Python and Pygame maze runner with random DFS mazes, arrow-key movement, wall collision, a goal gate, and a live timer.*

---

# 🚀 Why Maze Runner?

Many maze demos are a single file that only draws walls.

This project keeps the pieces separate:

- The maze generator carves a perfect maze
- The player moves with arrow keys and stops at walls
- The goal is a visible gate image
- The clock records how long the run takes
- The sidebar keeps instructions on screen

The result is a small but complete desktop game, not only a maze drawing.

---

# ✨ Key Features

- 🌀 New maze on every launch
- 🧱 Perfect maze (one path between cells, no loops)
- ⬆️ Arrow-key movement
- 🚧 Wall collision
- 🚪 Goal gate on the last cell (`img/gate.png`)
- ⏱️ Live timer in minutes and seconds
- 🏆 "You Win!!" message when the gate is reached
- 🖥️ Sidebar with controls and time
- 🧩 Separate modules for maze, player, game, cell, and clock
- ⚡ 60 FPS Pygame loop

---

# 🎮 How to Play

1. Start the game with `python main.py`.
2. The player appears as an orange square in the first cell.
3. Use the **arrow keys** to move.
4. Walls block movement.
5. Reach the **gate** in the far cell.
6. The timer stops and the win message appears.

There is no lose state and no score. The run ends when the player reaches the goal.

Window layout:

- Maze area: `602 × 602`
- Extra sidebar: `150` pixels
- Cell size: `30` pixels
- Caption: `Maze`

---

# 🧭 How the Maze Is Built

`maze.py` and `cell.py` generate the maze before the loop starts.

1. The grid is filled with cells. Every wall starts closed.
2. Generation begins at the first cell.
3. An unvisited neighbor is chosen at random.
4. The shared wall between the current cell and that neighbor is removed.
5. If no neighbor is left, the algorithm backtracks.
6. The process continues until every cell has been visited.

That is a randomized depth-first search, also called recursive backtracking. The finished maze is a perfect maze: every cell is reachable and there are no loops.

The goal cell is the last cell in `grid_cells`. `game.py` draws the gate there and checks whether the player has reached it.

---

# 📁 Project Structure

```text
Maze-Runner-Game/
├── main.py        # Window, event loop, sidebar, draw order
├── maze.py        # Grid setup and DFS generation
├── cell.py        # Cell walls, drawing, neighbor checks
├── player.py      # Movement, drawing, wall collision
├── game.py        # Goal gate and win message
├── clock.py       # Start, update, stop, and display the timer
└── img/
    └── gate.png   # Goal image
```

| File | Role |
|------|------|
| `main.py` | Creates the window (`752 × 602`), starts the maze, and runs the 60 FPS loop |
| `maze.py` | Builds the cell grid and carves paths |
| `cell.py` | Stores walls and draws them |
| `player.py` | Moves a 10×10 player at speed 4 and blocks walls |
| `game.py` | Places the gate and tests the win condition |
| `clock.py` | Shows elapsed minutes and seconds |

---

# 🛠️ Technologies

- Python 3.8+
- Pygame

---

# ▶️ Usage

### Requirements

```bash
pip install pygame
```

### Run

```bash
git clone https://github.com/sadra-hatami/Maze-Runner-Game.git
cd Maze-Runner-Game
python main.py
```

Keep the `img/gate.png` file next to the code so the goal can load.

---

# 🎓 Target Audience

- Players who want a short maze run
- Python learners studying Pygame
- Students looking at DFS maze generation
- Anyone who wants a small desktop game with separate modules

---

# 🚀 Roadmap

Possible later improvements:

- 🔁 Restart key for a new maze without closing the window
- 🗺️ Maze size or difficulty options
- 🎵 Sound for move and win
- 🏆 Best-time save
- 📱 Touch or on-screen controls
- 🎨 Extra player or wall themes

---

# ❓ Frequently Asked Questions

### Does every run use the same maze?

No. The generator picks neighbors at random, so the paths change each time you start the program.

### How do I restart?

Close the window and run `python main.py` again.

### Is there a time limit?

No. The timer only measures how long you take. It stops when you win.

### Why is the extra panel on the right?

That sidebar holds the arrow-key instructions, the timer, and the win message.

### What happens if `gate.png` is missing?

The maze and player can still run, but the goal image will not draw. Keep the `img` folder in place.

---

# 🤝 Contributing

Contributions are welcome.

You can:

- Report bugs
- Improve collision or controls
- Add a restart key
- Suggest visual changes
- Submit Pull Requests

---

# 📬 Contact

**Developer:**

### **Sadra Hatami**

📧 [Email](mailto:sadra.hatami.1732@gmail.com)

🌐 [GitHub](https://github.com/sadra-hatami)

---

# 📄 License

This project is licensed under the **MIT License**.

You are free to use, modify, and distribute this project under the terms of the MIT License.

---

# © Copyright

© 2026 **Sadra Hatami**

All rights reserved.

The source code, game design, documentation, and project assets are protected under applicable copyright laws.

---

# ⭐ Support the Project

If you enjoyed the maze, please consider:

⭐ Starring this repository

🐛 Reporting issues

💡 Suggesting improvements

---

<div align="center">

## Designed & developed with ❤️ for the developer community of Iran and the world

<br>

## 👨‍💻 **Sadra Hatami**

### Developer • Software Engineer • Creator

⭐ If you like this project, don't forget to star the repository!

</div>
