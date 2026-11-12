# Pop-Out AI Game Engine

This project is a Python implementation of **Pop-Out**, a Connect Four variant that introduces an additional strategic mechanic: players can remove their own bottom piece from a column, changing the board state and creating new tactical opportunities.

The project explores Artificial Intelligence techniques, focusing on Monte Carlo Tree Search (MCTS), performance optimization and decision tree learning.

## Technical Overview

The core of this project is the implementation and optimization of three MCTS agents, progressively improving computational efficiency through different board representations and simulation techniques.

**MCTS Easy:** Uses a traditional 2D matrix representation with Python lists and random simulations. Provides a baseline implementation of Monte Carlo Tree Search.

**MCTS Medium:** Uses immutable tuples (flat arrays) to reduce memory allocation overhead. Incorporates lightweight heuristic checks during simulations to improve decision-making.

**MCTS Hard:** Uses Bitboard representations with integer-based board operations and Numba JIT compilation. Optimizes victory detection and game simulations through low-level operations, significantly increasing computational performance.

**ID3 Decision Tree:** Implements the ID3 algorithm to generate a decision tree from game-state data collected during AI self-play, allowing the learned model to compete against the MCTS agents.

## Features

**Multiple AI Difficulties:** Three MCTS implementations (Easy, Medium and Hard), alongside an ID3 Decision Tree agent.

**Interactive Game Interface:** Graphical interface developed with Pygame, allowing users to play and test different AI agents.

**Pop-Out Mechanics:** Supports both standard piece insertion and the removal of a player's own bottom piece from a column.

**Tree Reuse:** Reuses previously explored MCTS subtrees between moves, reducing redundant computations.

**AI Benchmarking:** Includes automated AI-vs-AI matches to compare the performance and win rates of different agents.

**Decision Tree Visualization:** Supports the visualization of the ID3 decision tree and its learned structure.

## Performance Benchmarks

Based on the project evaluation:

| AI Agent | Win Rate |
|---|---:|
| MCTS Easy | 36.0% |
| MCTS Medium | 69.1% |
| MCTS Hard | 74.7% |
| ID3 Decision Tree | 20.2% |

The results highlight the impact of optimization techniques on agent performance, with MCTS Hard achieving the highest overall win rate.

The optimized Bitboard implementation also increased simulation speed from approximately 600 iterations per second in the initial implementation to over 3,000,000 iterations per second in the endgame.

## Technologies & Libraries

- Python 3
- Pygame
- Numba
- Matplotlib
- NetworkX
- PyVis

## How to Run

Install the required dependencies:

```bash
pip install pygame numba matplotlib networkx pyvis
```

Run the game:

```bash
python main_pygame.py
```

To run the AI benchmarking experiments:

```bash
python benchmark.py
```

Make sure the required project files, including the AI modules and `dataset.csv`, are available in the project directory.
