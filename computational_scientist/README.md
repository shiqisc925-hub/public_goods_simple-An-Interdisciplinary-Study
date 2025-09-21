# Computational Scientist Analysis: Public Goods Game

## Overview

This section provides computational analysis of the two-player public goods game using Python libraries NashPy and QuantEcon. The game parameters are:
- Endowment per player: 150 points
- Efficiency factor: 1.5
- Number of players: 2
- Contribution options: [0, 50, 100, 150]

## How to Run the Code

### Prerequisites
- Python 3.7+
- Google Colab or Jupyter Notebook environment

### Installation
```bash
pip install nashpy
pip install quantecon
Running the Analysis
Open the provided Jupyter notebook (notebook.ipynb) in Google Colab

Run all cells sequentially

The code will:

Install required packages

Generate the payoff matrix

Compute Nash equilibria using both NashPy and QuantEcon

Display results

Complete Python Code
python
# Install required packages
!pip install --upgrade setuptools
!pip install --upgrade pip
!pip install nashpy
!pip install quantecon

import numpy as np
import nashpy as nash
import quantecon.game_theory as gt

# Game parameters
endowment = 150
multiplier = 1.5
players = 2
contributions = [0, 50, 100, 150]
n_strategies = len(contributions)

# Initialize payoff matrix
payoff_matrix = np.zeros((n_strategies, n_strategies, 2))

# Calculate payoffs for all strategy combinations
for i, c0 in enumerate(contributions):
    for j, c1 in enumerate(contributions):
        public_pool = (c0 + c1) * multiplier
        share = public_pool / players
        payoff_matrix[i, j, 0] = endowment - c0 + share
        payoff_matrix[i, j, 1] = endowment - c1 + share

# Separate payoff matrices for each player
A = payoff_matrix[:,:,0]  # Row player
B = payoff_matrix[:,:,1]  # Column player

# Create game object
game = nash.Game(A, B)

print("=== NashPy: Normal Form Game Matrix ===")
print(game)

print("\n=== NashPy: Nash Equilibria (Support Enumeration) ===")
equilibria = game.support_enumeration()
for eq in equilibria:
    print(eq)

# QuantEcon analysis
g_pg = gt.NormalFormGame(payoff_matrix)
print("\n=== QuantEcon: Normal Form Game Matrix ===")
print(g_pg)

NE_pure = gt.pure_nash_brute(g_pg)
print("\n=== QuantEcon: Pure Strategy Nash Equilibria ===")
print(NE_pure)

NE_mixed = gt.support_enumeration(g_pg)
print("\n=== QuantEcon: Mixed Strategy Nash Equilibria ===")
print(NE_mixed)

# Print detailed payoff information
print("\n=== Detailed Payoff Analysis ===")
print("Contribution options:", contributions)
print("\nPayoff matrix (Row Player, Column Player):")
for i, c1 in enumerate(contributions):
    for j, c2 in enumerate(contributions):
        payoff1 = payoff_matrix[i, j, 0]
        payoff2 = payoff_matrix[i, j, 1]
        print(f"({c1}, {c2}): ({payoff1:.1f}, {payoff2:.1f})")
Expected Output
text
=== NashPy: Normal Form Game Matrix ===
Bi matrix game with payoff matrices:

Row player:
[[150.  187.5 225.  262.5]
 [137.5 175.  212.5 250. ]
 [125.  162.5 200.  237.5]
 [112.5 150.  187.5 225. ]]

Column player:
[[150.  137.5 125.  112.5]
 [187.5 175.  162.5 150. ]
 [225.  212.5 200.  187.5]
 [262.5 250.  237.5 225. ]]

=== NashPy: Nash Equilibria (Support Enumeration) ===
(array([1., 0., 0., 0.]), array([1., 0., 0., 0.]))

=== QuantEcon: Normal Form Game Matrix ===
2-player NormalFormGame with payoff profile array:
[[[150. , 150. ],  [187.5, 137.5],  [225. , 125. ],  [262.5, 112.5]],
 [[137.5, 187.5],  [175. , 175. ],  [212.5, 162.5],  [250. , 150. ]],
 [[125. , 225. ],  [162.5, 212.5],  [200. , 200. ],  [237.5, 187.5]],
 [[112.5, 262.5],  [150. , 250. ],  [187.5, 237.5],  [225. , 225. ]]]

=== QuantEcon: Pure Strategy Nash Equilibria ===
[(0, 0)]

=== QuantEcon: Mixed Strategy Nash Equilibria ===
[(array([1., 0., 0., 0.]), array([1., 0., 0., 0.]))]
```
Expected Output
```text
=== NashPy: Normal Form Game Matrix ===
Bi matrix game with payoff matrices:

Row player:
[[150.  187.5 225.  262.5]
 [137.5 175.  212.5 250. ]
 [125.  162.5 200.  237.5]
 [112.5 150.  187.5 225. ]]

Column player:
[[150.  137.5 125.  112.5]
 [187.5 175.  162.5 150. ]
 [225.  212.5 200.  187.5]
 [262.5 250.  237.5 225. ]]

=== NashPy: Nash Equilibria (Support Enumeration) ===
(array([1., 0., 0., 0.]), array([1., 0., 0., 0.]))

=== QuantEcon: Normal Form Game Matrix ===
2-player NormalFormGame with payoff profile array:
[[[150. , 150. ],  [187.5, 137.5],  [225. , 125. ],  [262.5, 112.5]],
 [[137.5, 187.5],  [175. , 175. ],  [212.5, 162.5],  [250. , 150. ]],
 [[125. , 225. ],  [162.5, 212.5],  [200. , 200. ],  [237.5, 187.5]],
 [[112.5, 262.5],  [150. , 250. ],  [187.5, 237.5],  [225. , 225. ]]]

=== QuantEcon: Pure Strategy Nash Equilibria ===
[(0, 0)]

=== QuantEcon: Mixed Strategy Nash Equilibria ===
[(array([1., 0., 0., 0.]), array([1., 0., 0., 0.]))]
```
## Game Theory Explorer (GTE) Analysis

### GTE Screenshots
![GTE Normal Form Analysis](".\GTE.png")

### GTE Configuration
Game Type: Strategic Form

Players: 2

Strategies: 4 each (0, 50, 100, 150)

Information Sets: Simultaneous moves

### Interpretation
The computational analysis confirms the theoretical prediction:

Unique Nash Equilibrium: (0, 0) - both players contribute nothing

Dominant Strategy: Contributing zero dominates all other strategies

Social Dilemma: Individual rationality leads to Pareto-inefficient outcome

Free-Rider Problem: The equilibrium demonstrates classic public goods dilemma
