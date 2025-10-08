# An Interdisciplinary Study of Strategic Behavior: Public Goods Game and Winner's Curse Auction

**Author:** Shiqi Chen

## Abstract

This project presents an interdisciplinary investigation into strategic decision-making, combining perspectives from economics, computational science, and behavioral science. The study is divided into three parts:

1.  **Public Goods Game:** This part analyzes a classic social dilemma through theoretical analysis, computational simulation (using NashPy and QuantEcon), and behavioral experiments (with human participants and LLMs via oTree and DeepSeek). It demonstrates the contrast between the theoretical Nash equilibrium (zero contributions) and observed cooperative behavior, attributing the divergence to social preferences and bounded rationality.

2.  **Winner's Curse Auction:** This part explores bounded rationality in decision-making under uncertainty. By designing an experiment with a "noisy signal" treatment, it tests whether LLMs (GPT-4 and DeepSeek) exhibit the "winner's curse" bias. Results show that LLMs are susceptible to this bias, which manifests as a significant erosion of profit potential, measured by a proposed "Profit Efficiency Ratio."

3.  **Voting Mechanism:** This part proposes and evaluates a **Quadratic Voting (QV)** mechanism for collective decision-making in the context of the EU's burden-sharing asylum policy. It addresses the limitations of ordinal voting systems (as highlighted by Arrow's Impossibility Theorem) and incorporates preference intensity to enhance fairness and legitimacy.

## Task Summary

This repository contains the complete workflow for a multi-method research project:

*   **Part 1 - Economist (Theory & Welfare):** Formal game definition, Nash equilibrium analysis, and discussion of efficiency and fairness.
*   **Part 2 - Computational Scientist:** Solving the game's normal form using `NashPy` and `QuantEcon.py`, and modeling the extensive form using `Game Theory Explorer (GTE)`.
*   **Part 3 - Behavioral Scientist:** Conducting a modified Public Goods game experiment using `oTree` with human participants and an LLM (DeepSeek), followed by a comparative analysis.
*   **Problem Set 2 - Winner's Curse:** Design and execution of an auction experiment to test for the winner's curse in LLMs, including prompt design, experiment execution, and results analysis.
*   **Voting Mechanism:** Design and simulation of a Quadratic Voting mechanism for collective choice in a real-world policy context (EU asylum policy), including theoretical grounding and classroom simulation guidelines.

## Reproduction Steps

### 1. Public Goods Game Reproduction

#### Theoretical & Computational Analysis (Parts 1 & 2)
1.  Navigate to the `/computational_scientist` directory.
2.  Install required packages: `pip install nashpy quantecon`
3.  Run the provided Python scripts to compute equilibria.

#### Behavioral Experiment (Part 3 - oTree)
1.  Navigate to `/behavioral_scientist/otree_public_goods`.
2.  Install oTree: `pip install otree`
3.  Start the server: `otree devserver` and access via `http://localhost:8000`.

#### Behavioral Experiment (Part 3 - LLM)
1.  Prompts are documented in the main report and can be found in the `/behavioral_scientist` directory.
2.  Use the provided prompts in a new chat session with an LLM (e.g., DeepSeek Chat).

### 2. Winner's Curse Auction Reproduction
1.  Navigate to `/winner_curse_auction`.
2.  Use the prompts provided in the directory to run experiments with GPT-4 or DeepSeek.
3.  Analyze results using the data files provided in the directory.

### 3. Voting Mechanism Simulation
1.  Navigate to the `/voting_mechanism` directory.
2.  Review the proposed Quadratic Voting (QV) mechanism design and simulation setup.
3.  Run the classroom simulation script to test the mechanism under different preference intensity profiles.
4.  Compare outcomes with traditional ordinal voting methods.

## Dependencies

*   Python 3.8+
*   Key packages: `numpy`, `nashpy`, `quantecon`, `otree`, `pandas`

## References

*   Osborne, M. J., & Rubinstein, A. (1994). *A course in game theory*. MIT Press.
*   Fehr, E., & Schmidt, K. M. (1999). A theory of fairness, competition, and cooperation. *The Quarterly Journal of Economics*.
*   Knight, V., & Campbell, M. (2021). Nashpy: A Python library for the computation of Nash equilibria. *Journal of Open Source Software*.
*   Chen, D. L., Schonger, M., & Wickens, C. (2016). oTree. *Journal of Behavioral and Experimental Finance*.
*   Savani, R., & von Stengel, B. (2015). Game Theory Explorer. *Computational Management Science*.
*   Kagel, J. H., & Levin, D. (2002). *Common Value Auctions and the Winner's Curse*. Princeton University Press.
*   Bazerman, M. H., & Samuelson, W. F. (1983). I won the auction but don't want the prize. *Journal of Conflict Resolution*.
*   Arrow, K. J. (1972). *Social Choice and Individual Values*.
*   Buchanan, J. M. (1986). *The Constitution of Economic Policy*. Nobel Prize Lecture.
*   Lalley, S., & Weyl, E. G. (2018). Quadratic Voting: How Mechanism Design Can Radicalize Democracy. *American Economic Association Papers & Proceedings*.

## Software Citations

*   Nashpy (Knight, 2021)
*   QuantEcon (Sargent & Stachurski, 2021)
*   Game Theory Explorer (Savani & von Stengel, 2015)
*   oTree (Chen, Schonger, & Wickens, 2016)
