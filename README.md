# Neural Gambit ♟️

A high-performance chess engine written from scratch in C++. 

**Neural Gambit** is an educational summer project developed for IIT Bombay's Summer of Code (SoC), designed to demonstrate skill in Data Structures and Algorithms, progressing from classical search techniques (Minimax, Alpha-Beta pruning) to modern neural evaluation via an **Efficiently Updatable Neural Network (NNUE)** — the same technology used in world-champion engines like Stockfish.

---

## Repository Description & Summary

> **Neural Gambit** is a custom-built, UCI-compatible chess engine designed to transition from traditional algorithmic game theory to modern deep learning-driven evaluation. Starting from board representations and alpha-beta pruning, the engine will ultimately load trained NNUE weights for fast inference inside its C++ search loop. 
>
> Currently, **Version 1** is complete: featuring a fully functional Minimax + Alpha-Beta search engine with **iterative deepening** that consistently defeats a random-move engine, runs UCI communication with chess GUIs, and solves mate-in-X tactical puzzles. Future phases will introduce advanced search optimizations (Zobrist hashing, transposition tables, quiescence search) and a custom NNUE evaluation function.

---

## Features (Version 1)
- **Iterative Deepening:** Incremental search depth advancement to deliver the best possible move within a specified time limit, similar to breadth-first search exploration of the game tree.
- **Universal Chess Interface (UCI) Protocol Support:** Communicates seamlessly with standard chess GUIs (like Cute Chess, Arena, or LiChess via bridge).
- **Adversarial Search:** Negamax & Minimax Alpha-Beta pruning for tactical evaluations.
- **Mate-in-X Optimization:** Incorporates depth-based checkmate scaling to ensure the engine targets the fastest possible route to checkmate.
- **Material Evaluation:** A fast, basic heuristic evaluator tracking pieces (Pawns, Knights, Bishops, Rooks, Queens, and Kings).

---

## 📦 Version 1 Release Binaries
The **Version 1** Release contains precompiled Windows executables:
1. `neural-gambit.exe`: The primary chess engine running the Alpha-Beta pruning search and UCI.
2. `random-mover.exe`: A benchmark utility that makes random legal moves, used for baseline testing and ensuring the main engine works correctly.

---

## How to use Neural Gambit with Cute Chess GUI

You can watch **Neural Gambit** play against the **Random Mover**, play against it yourself, or pit it against other engines in **Cute Chess GUI**.

### Step 1: Add the Engines to Cute Chess
1. Download and open **Cute Chess**.
2. Go to **Tools** **>** **Settings** (on macOS/Linux: **Preferences**).
3. Select the **Engines** tab, then click **Add...** at the bottom.
4. Set up the **Neural Gambit Engine**:
   - **Name:** `NeuralGambit`
   - **Command:** Browse and select your local `neural-gambit.exe` path.
   - **Protocol:** `UCI` (Cute Chess should automatically detect this).
5. Click **OK** to save.
6. Click **Add...** again to add the **Random Mover**:
   - **Name:** `RandomMover`
   - **Command:** Browse and select your local `random-mover.exe` path.
   - **Protocol:** `UCI`.
7. Click **OK** to save both.

### Step 2: Set Up a Match (Neural Gambit vs. Random Mover)
1. Go to **Game** **>** **New Game** (or press `Ctrl+N`).
2. For **Player 1**, select `NeuralGambit` from the dropdown list.
3. For **Player 2**, select `RandomMover` from the dropdown list.
4. Set the time control (e.g., **40 moves in 1 minute** or **10 seconds + 0.1s increment**).
5. Click **OK** to start the match! You will see Neural Gambit dominate and defeat the random-mover in real time.

---

## Building from Source

To compile the engine locally, use any standard C++ compiler supporting C++17 or newer.

### Using GCC (MinGW / Linux)
```bash
# Compile the main UCI engine
g++ -O3 -std=c++17 uci-gui.cpp -o neural-gambit.exe
```

---

## 📁 Repository Structure
```
├── chess-puzzle-solver/    # Chess mate-in-X puzzle solver
│   ├── chess-engine.h      # Puzzle solver engine implementation
│   ├── chess.hpp           # Disservin chess representation library
│   ├── puzzle-solver.cpp   # Puzzle solver entry point
│   └── README.md           
├── .gitignore              # Files to exclude from Git tracking
├── chess-engine.h          # Main Chess Engine class with minimax/alpha-beta search
├── uci-gui.cpp             # UCI protocol communication loop (Main Entry)
└── README.md               
```

## Project Context

This repository was developed as a university summer project under **Summer of Code (SOC)** at **IIT Bombay**. The primary objective of this project is to practically apply core Data Structures and Algorithms (DSA) and systems programming concepts by building a high-performance game engine from scratch.
