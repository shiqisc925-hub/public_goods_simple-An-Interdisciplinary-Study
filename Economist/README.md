# Economist Analysis: Public Goods Game

## Overview
This section provides the theoretical foundation for the two-player public goods game analysis, establishing the Nash equilibrium prediction and examining its welfare implications.

## Theoretical Framework

### Equilibrium Concept
The appropriate solution concept for this simultaneous-move game is the **pure-strategy Nash equilibrium** in normal-form representation.

**Formal Definition:**

Let the game be defined as follows:
- Set of players: `N = {1, 2}`
- Strategy set for each player i: `S_i = [0, 150]` (all possible contribution amounts)
- Payoff function for player i: 
  `u_i(g_i, g_j) = 150 - g_i + 1.5 × (g_i + g_j)/2`
  where:
  - `150 - g_i` = amount kept privately
  - `1.5 × (g_i + g_j)/2` = share from public pool

A strategy profile `(g_1*, g_2*)` is a **Nash equilibrium** if for every player i and every alternative strategy g_i:
`u_i(g_i*, g_j*) ≥ u_i(g_i, g_j*)`

### Existence Proof
The existence of Nash equilibrium is guaranteed by:
1. **Compactness and convexity** of strategy sets `S_i = [0, 150]`
2. **Continuity** of payoff functions `u_i(g)` in all strategies
3. **Quasi-concavity** of `u_i(g)` in own strategy `g_i`
4. Application of **Kakutani's fixed-point theorem** to the best-response correspondence

## Analytical Results

### Equilibrium Characterization
- **Unique Nash equilibrium**: `(0, 0)` - both players contribute nothing
- **Dominant strategy**: Contributing zero is strictly dominant for both players
- **Theoretical justification**: Any positive contribution yields lower private benefit than cost when multiplier α = 1.5 < 2

### Welfare Analysis

#### Efficiency
- **Pareto inefficiency**: The (0,0) equilibrium is not Pareto optimal when αn > 1 (1.5 × 2 = 3 > 1)
- **Social optimum**: Full contribution (150,150) would yield total welfare of 675 vs 300 at equilibrium
- **Utilitarian improvement**: Social welfare increases with higher contributions

#### Fairness Considerations
- **Equity**: Zero contribution avoids burden sharing but also eliminates public benefits
- **Proportionality**: No benefits distributed in equilibrium despite potential gains from cooperation
- **Envy-freeness**: Trivially satisfied with equal endowments and outcomes, but substantively weak

## Interpretation

### Computational Tractability
- **Complexity class P**: Finding this equilibrium is computationally easy due to dominant strategies
- **Contrast with general games**: Most Nash equilibrium problems are PPAD-complete
- **Behavioral implications**: Human deviations from equilibrium cannot be attributed to computational difficulty

### Theoretical Significance
The stark prediction of zero contributions serves as:
1. A **theoretical benchmark** for measuring behavioral deviations
2. A demonstration of the **tension** between individual rationality and collective welfare
3. A foundation for understanding the role of **social preferences** and **bounded rationality**

## Key References

1. **Primary Textbook Reference**:
   - Osborne, M. J., & Rubinstein, A. (1994). *A course in game theory*. MIT Press.
     - Nash Equilibrium: p. 15
     - Existence Theorem: p. 19
     - Efficiency Analysis: pp. 8-10

2. **Computational Complexity**:
   - Roughgarden, T. (2016). *Twenty lectures on algorithmic game theory*. Cambridge University Press.
     - Lecture 2, pp. 10-20

3. **Behavioral Foundations**:
   - Fehr, E., & Schmidt, K. M. (1999). A theory of fairness, competition, and cooperation. *The Quarterly Journal of Economics, 114*(3), 817-868.

## Files in This Directory
- `README.md`: This documentation file
- `references/`: Folder containing reference materials

## Connection to Other Sections
This theoretical analysis provides the foundation for:
- **Computational verification** in `../computational_scientist/`
- **Behavioral experiments** in `../behavioral_scientist/`
- **Comparative analysis** of theoretical vs. actual behavior

The Nash equilibrium prediction of (0,0) serves as the baseline against which human and AI behavior are compared in subsequent analyses.