# Flappy Bird NEAT AI

A Python project that trains an AI to play Flappy Bird using the NEAT (NeuroEvolution of Augmenting Topologies) algorithm. This project uses the NEAT algorithm to evolve neural networks that control the bird, enabling it to learn how to play the game on its own.

## Table of Contents

- [Project Overview](#project-overview)
- [Tech Stack & Libraries](#tech-stack--libraries)
- [How It Works](#how-it-works)
- [Algorithm: NEAT](#algorithm-neat)
- [How to Run](#how-to-run)
- [Project Structure](#project-structure)
- [Screenshots](#screenshots)
- [Credits](#credits)
- [License](#license)

---

## Project Overview

This project uses artificial intelligence to play the classic Flappy Bird game. The AI agent is trained using the NEAT algorithm, which evolves neural networks over generations to maximize the bird's score by avoiding pipes and surviving as long as possible.

The game is rendered using Pygame, and the training process is visualized in real-time, allowing you to watch as the AI learns to play Flappy Bird better over generations.

---

## Tech Stack & Libraries

- **Python 3.x**: Programming language used for the entire project.
- **Pygame**: For rendering the game graphics and handling user input.
- **NEAT-Python**: Implementation of the NEAT algorithm for evolving neural networks.
- **Pickle**: For saving and loading trained neural networks (optional).
- **OS, Time, Random**: Standard Python libraries for utility functions.

### Key Files

- `flappy_bird.py`: Main game logic and NEAT implementation.
- `config-feedforward.txt`: Configuration for the NEAT algorithm.
- `/imgs`: Directory containing game assets (bird, pipes, background, base).

---

## How It Works

1. **Game Setup**: The Flappy Bird game is loaded using Pygame, with all graphics and mechanics implemented as in the original game.
2. **NEAT Initialization**: The NEAT algorithm initializes a population of genomes, each representing a unique neural network.
3. **Simulation**: For each genome in the population:
   - A neural network is created and assigned to a Bird object in the game.
   - The neural network decides when the bird should jump based on its current position and the positions of upcoming pipes.
   - The bird earns a fitness score based on how far it travels (frames alive) and how many pipes it passes.
4. **Evolution**: After each generation, the NEAT algorithm selects the best-performing genomes, combines them, and introduces mutations to produce the next generation.
5. **Training Loop**: This process continues for a set number of generations or until a bird achieves a target score.

---

## Algorithm: NEAT

**NEAT** (NeuroEvolution of Augmenting Topologies) is a genetic algorithm that evolves both the structure and weights of neural networks. In this project:

- Each genome corresponds to a neural network that controls a bird.
- The neural network receives inputs like the bird's y position, the distance to the next pipe, and decides whether to jump.
- Over generations, networks evolve to improve performance (i.e., surviving and scoring higher).

---

## How to Run

1. **Install Requirements**
   ```bash
   pip install pygame neat-python
   ```

2. **Add Game Assets**
   - Make sure you have the `/imgs` directory with all required images:
     - `bird1.png`, `bird2.png`, `bird3.png`
     - `pipe.png`
     - `base.png`
     - `bg.png`

3. **Run the Game**
   ```bash
   python flappy_bird.py
   ```
   The AI will start training and playing Flappy Bird automatically. You can watch its progress in the Pygame window.

4. **Configuration**
   - The NEAT config file (`config-feedforward.txt`) can be tweaked to experiment with different NEAT parameters.

---

## Project Structure

```
flappy_bird.py
config-feedforward.txt
imgs/
  ├── bird1.png
  ├── bird2.png
  ├── bird3.png
  ├── pipe.png
  ├── base.png
  └── bg.png
visualize.py (optional)
README.md
```

---

## Screenshots

*(Add your own screenshots of the AI playing Flappy Bird!)*

---

## Credits

- Game inspired by the original [Flappy Bird](https://en.wikipedia.org/wiki/Flappy_Bird).
- NEAT algorithm powered by [NEAT-Python](https://neat-python.readthedocs.io/en/latest/).
- Pygame for game rendering.
