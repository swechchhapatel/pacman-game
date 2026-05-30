# Pacman Game

![HTML](https://img.shields.io/badge/HTML-5-orange)
![CSS](https://img.shields.io/badge/CSS-3-blue)
![JavaScript](https://img.shields.io/badge/JavaScript-ES6-yellow)
[![License](https://img.shields.io/badge/License-MIT-green)](LICENSE)

The goal of this project is to understand and implement the pacman game using Javascript for the game mechanics and HTML5 Canvas to render the game map and its graphics.

---

## ✦ Game Screenshot
<img src="image_assets\\game_screenshot.png" alt="Pac-Man Game Screenshot" style="width:70%; height:auto;">

---

## ✦ Technologies Used

| Technology | Purpose | Version / Type |
|-----------|--------------|-------|
| **HTML5** |  Structure of the web page and Canvas element | HTML5 |
| **CSS3** | Styling the page layout and canvas container | CSS3 |
| **JavaScript (Vanilla)** |  Core game logic, rendering, and interactivity | ES6+ |
| **HTML5 Canvas API** |  Drawing game elements (Pacman, ghosts, walls, food) | Built-in Browser API |
| **PNG Image Assets** |  Sprites for Pacman (4 directions), ghosts, walls | Image Files |
| **VS Code** | Code editor used during development	| IDE |

---

## ✦ File Structure

```text
pacman-game/
│
├── image_assets/
│   ├── ghost_image             # Ghost sprite images
│   │   ├── blueGhost.png
│   │   ├── orangeGhost.png
│   │   ├── pinkGhost.png
│   │   └── redGhost.png
│   │
│   ├── pacman_moves            # Directional sprites for Pacman character
│   │   ├── pacmanDown.png
│   │   ├── pacmanUp.png
│   │   ├── pacmanLeft.png
│   │   └── pacmanRight.png
│   │
│   └── wall.png                # Wall tile image used in the tilemap
│
├── index.html                  # Contains the <canvas> element and links JS/CSS
│
├── pacman.css                  # Stylesheet for page layout and canvas styling
│
├── pacman.js                   # Contains all game logic
│
├── LICENSE           
└── README.md                      

``` 
---

## ✦ System Design and Architecture

### 1. Tilemap System

* The game map is defined as a **2D array (the tileMap) with 21 columns × 23 rows**. Each number in the array represents:
    *	*0 - Empty space (walkable path)*
    *	*1 - Wall tile (blocks movement)*
    *	*2 - Food pellet (small dot Pacman collects)*
    *	*3 - Empty block (open space with no pellet)*
* Each tile is drawn on the HTML5 Canvas at a fixed block size. 

### 2. Pacman (Player Character)

* Pacman is represented as an object with properties like x, y (position), direction, and speed.
* When a key/click is registered, Pacman's direction is updated.

### 3. Ghost AI (Non-Player Characters)

* The game features four ghosts: Red, Pink, Blue, and Orange.
* The ghosts move in a random valid direction at each intersection (when they collide with a wall). This gives the appearance of patrolling enemies without requiring complex pathfinding. The ghosts are given different starting positions on the map to spread them across the board.



### 4. Collision Detection

Two types of collision detection are implemented:
*	**Pacman vs. Walls:** Before Pacman moves, the target tile is checked. If it is a wall tile (value = 1 in the tileMap), movement is blocked.
*	**Pacman vs. Ghosts:** The distance between Pacman's center position and each ghost's center position is calculated. If the distance is below a threshold (roughly equal to half a tile size), a collision is triggered — the game resets.
*	**Pacman vs. Food:** When Pacman moves over a tile containing food (value = 2), the tile is updated to 0 (empty) and the player's score increases.

---

### ✦ Installation & Setup

#### ∘ Method 1: Download and Run Locally

1. **Clone the repository**
   ```bash
   git clone https://github.com/swechchhapatel/pacman-game.git
   cd pathfinding-visualizer
   ```

2. **Open in browser**
   - Simply double-click `index.html`
   - Or right-click → "Open with" → Choose your browser

3. **Start Playing!**

#### ∘ Method 2: Use with Live Server (Recommended for Development)

1. **Install Live Server** (VS Code extension or npm package)
   ```bash
   npm install -g live-server
   ```

2. **Navigate to project folder**
   ```bash
   cd pacman-game
   ```

3. **Start the server**
   ```bash
   live-server
   ```

4. **Open in browser**
   - Automatically opens at `http://localhost:8080`
   - Auto-refreshes on file changes

---

## ✦ Contribution

Contributions are welcome and appreciated! 

If you'd like to improve this project, please follow these steps:

1. Fork the repository
2. Create a new branch  
   ```bash
   git checkout -b feature/your-feature-name
   ```
3. Make changes and commit
   ```bash
   git commit -m "Add: your message"
   ```
4. Push to your branch and open a Pull Request
 
---

**Made with ❤️**