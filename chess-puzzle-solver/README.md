# Chess Puzzle Solver

This subdirectory contains a dedicated terminal-based tool designed to solve **Mate-in-X chess puzzles** using Negamax search with Alpha-Beta pruning. 

It acts as a sandbox environment to test our search algorithm's ability to find forced checkmates.

---

## How It Works

1. **FEN Loading:** Loads a custom FEN position representing a tactical chess puzzle (e.g., a Mate-in-4 puzzle).
2. **Negamax Alpha-Beta Search:** Performs a search to the target depth to find the forced mating sequence.
3. **Move Path Recording:** Dynamically builds a list of the best moves from the root to the leaf node during the alpha-beta search.
4. **SAN Output:** Converts the best move path to Standard Algebraic Notation (SAN) (e.g., `Nxf5`, `Qh7#`) and prints it to the terminal alongside the final board state.

---

## 📁 Files

- `puzzle-solver.cpp`: The entry point. Contains the `main()` function, sets up a puzzle FEN, runs the search, and prints the solution.
- `chess-engine.h`: A specialized chess engine class containing:
  - `negamax_alpha_beta_pruning()`: Returns the best move sequence.
  - `alpha_beta_pruning()`: Basic alpha-beta search.
  - `findBestMove()`: Finds the best single move for a player.
- `chess.hpp`: The header-only chess library by Disservin for move generation, FEN parsing, and board mechanics.

---

## Usage

### Compilation
You can compile the puzzle solver from this directory (or the root directory by adjusting paths) using a C++17 compiler:

```bash
# Compile puzzle solver
g++ -O3 -std=c++17 puzzle-solver.cpp -o puzzle-solver.exe
```

### Running the Solver
```bash
./puzzle-solver.exe
```

Upon execution, it will solve the configured puzzle and output the move sequence:
```text
Nxg6+ hxg6 h7+ ...
```
 followed by the final board representation showing checkmate.
