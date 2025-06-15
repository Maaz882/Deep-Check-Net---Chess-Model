# Deep-Check-Net---Chess-Model

An AlphaZero-style self-learning chess engine powered by deep reinforcement learning, MCTS, and a custom neural network called **DeepCheckNet**.

![Chessboard Banner](assets/banner.png) <!-- Optional visual -->

---

## ♟️ Overview

This project implements a self-improving chess AI using modern reinforcement learning techniques:

* Self-play reinforcement learning
* Monte Carlo Tree Search (MCTS)
* Neural network policy & value prediction
* GUI for Human vs AI gameplay

Trained completely from scratch using only the game rules, with no human gameplay data.

---

## 🚀 Features

* `DeepCheckNet`: Residual CNN with separate policy and value heads
* MCTS enhanced with Dirichlet noise for exploration
* Full training loop with early stopping and learning rate scheduling
* Human vs Model and Model vs Model GUI via Pygame
* Game state, policy, and value saved in `.npz` for training

---

## 📁 Project Structure

```
.
├── Auto_train_loop.py        # Self-play + training automation
├── model.py                  # DeepCheckNet architecture
├── Mcts_Engine.py            # MCTS with UCB and expansion
├── Self_Play_Loop.py         # Self-play game generation
├── Chess_Dataset_RL.py       # Dataset class for training
├── chess_engine.py           # Terminal play with model
├── gui_chess.py              # GUI game interface (pygame)
├── parse_pgn.py              # Board/tensor conversion utils
├── images/                   # Piece sprites for GUI
├── saved_models/             # Trained models
└── self_play_data.npz        # Training data from self-play
```

---

## 🛠️ Installation

```bash
# Clone the repository
$ git clone https://github.com/yourusername/deepcheck-chess.git
$ cd deepcheck-chess

# Create virtual environment (optional but recommended)
$ python -m venv venv
$ source venv/bin/activate  # or .\venv\Scripts\activate on Windows

# Install dependencies
$ pip install -r requirements.txt
```

---

## 🧠 Training from Scratch

```bash
python Auto_train_loop.py
```

This will:

* Play N games of self-play
* Save data to `self_play_data.npz`
* Train on that data for several epochs
* Repeat, improving the model over time

Trained models are saved as `DeepCheckNet_model.pth`

---

## 🎮 Play Against the Model

### CLI version:

```bash
python chess_engine.py
```

### GUI version:

```bash
python gui_chess.py
```

Choose Human vs Model or Model vs Model at runtime.

---

## 📊 Evaluation

* Early stopping based on validation loss
* Model only saved if performance improves
* Designed for continued self-improvement through self-play

---

## 📦 Requirements

* Python 3.8+
* `torch`, `numpy`, `pygame`, `python-chess`

Install all dependencies with:

```bash
pip install -r requirements.txt
```

---

## 🙏 Acknowledgements

Inspired by:

* DeepMind's AlphaZero paper

Built with by Maaz Hasan
