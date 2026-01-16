# 2048 Game

> **A focused implementation of the classic 2048 puzzle.**

**Live demo:** [https://VvynnykV.github.io/2048-game/](https://VvynnykV.github.io/2048-game/)

---

## 🎯 Project Overview

This repository contains a JavaScript implementation of the **2048** game. The goal of the task is to implement the game logic and to create a robust, well-tested `Game` class that powers the UI.

The project is designed as two main parts:

* **Game logic**: `src/modules/Game.class.js` — exports the `Game` class and contains all rules, state management and core mechanics.
* **UI**: `src/index.html` + `main.js` — consumes the `Game` class instance and renders the board, buttons and messages.

---

## 📜 Game Rules

1. The board is **4 × 4**.
2. Each cell is either empty or contains a number: 2, 4, 8, ... (powers of two).
3. Player moves tiles using arrow keys (UI will call `move*` methods).
4. On a move, tiles slide as far as possible in the chosen direction.

   * Equal tiles that collide merge into a single tile with doubled value.
   * A tile can only merge once per move.
5. A move is considered **valid** (and triggers spawning a new tile) only if at least one cell changes its value or position.
6. After a valid move, a new tile (2 or 4) is placed in a random empty cell. The probability of spawning **4** is **10%** (otherwise spawn **2**).
7. When any tile reaches **2048**, the game status becomes `won` and a win message should be shown.
8. The game is `over` when there are no valid moves left.
9. The start message must be hidden once the game starts.
10. The main button should change from **Start** to **Restart** after the first move.
11. Clicking **Restart** resets the game to the initial state.
12. **Score** increases by the sum of all merged tile values on each move (e.g., merging 4 and 4 → 8 increases score by 8).
13. Keep UI and logic separated — `Game` must not directly manipulate DOM elements.

---

## 🛠️ Tech Stack

* **HTML5** + **CSS3**
* **JavaScript (ES6+)** — main focus

---

## 🚀 Getting Started (development)

Clone the repo and install dependencies:

```bash
git clone https://github.com/VvynnykV/2048-game.git
cd 2048-game
npm install
```

Run locally:

```bash
npm start
```

Run tests:

```bash
# Run full test suite
npm run test

# Fast tests (ignore linter)
npm run test:only -- -n

# Fast tests with additional console info
npm run test:only -- -l
```

Build for production:

```bash
npm run build
```

---

## 📦 Project Structure (suggested)

```
├─ src/
│  ├─ modules/
│  │  └─ Game.class.js   # implement the Game class here
│  ├─ index.html         # provided UI
│  ├─ main.js            # UI glue (uses Game instance)
│  └─ styles/
├─ test/                 # tests provided by the task
├─ package.json
└─ README.md
```

---

## ✉️ Author & Contact

**Author:** VvynnykV

* GitHub: [https://github.com/VvynnykV](https://github.com/VvynnykV)
* Live demo: [https://VvynnykV.github.io/2048-game/](https://VvynnykV.github.io/2048-game/)

---
