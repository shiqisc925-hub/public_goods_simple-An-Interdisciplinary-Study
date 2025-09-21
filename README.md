# Public Goods Game: An Interdisciplinary Study

## Project Overview

This repository contains a comprehensive interdisciplinary analysis of a two-player public goods game, integrating perspectives from economic theory, computational science, and behavioral experimentation. The study examines the tension between theoretical predictions and observed behavior in social dilemmas.

**GitHub Repository**: [https://github.com/shiqisc925-hub/public_goods_simple-An-Interdisciplinary-Study/tree/main]

## Game Parameters

- **Players**: 2
- **Endowment**: 150 points per player
- **Efficiency factor**: 1.5
- **Contribution range**: 0-150 points
- **Rounds**: 1 (one-shot game)

## Project Structure

```
public_goods_simple-An-Interdisciplinary-Study/
├── economist/                 # Part 1: Theoretical analysis
│   ├── README.md             # Economic theory documentation
│   └── references/           # Reference materials
├── computational_scientist/  # Part 2: Computational verification
│   ├── notebook.ipynb        # Jupyter notebook with all computations
│   ├── README.md             # Computational methods guide
│   └── gte_screenshot      # Game Theory Explorer visualizations
└── behavioral_scientist/     # Part 3: Experimental analysis
    ├── otree_app.zip         # Complete oTree experiment
    ├── README.md             # Experimental setup guide
    ├── screenshots/          # Experiment interface screenshots
    └── llm/                  # LLM interaction records
```

## Key Findings

### Theoretical Prediction (Part 1)
- **Nash equilibrium**: (0, 0) - both players contribute nothing
- **Dominant strategy**: Zero contribution is strictly dominant
- **Welfare implications**: Pareto inefficient but individually rational

### Computational Verification (Part 2)
- **NashPy & QuantEcon**: Both confirm (0,0) as unique equilibrium
- **Algorithmic complexity**: Class P (easily computable)
- **GTE analysis**: Normal form preferred for simultaneous games

### Behavioral Results (Part 3)
- **Human participants**: 100 points contribution (fairness heuristic)
- **LLM (DeepSeek)**: 100 points contribution (rational calculation)  
- **Researcher**: 50 points contribution (risk aversion)
- **Deviation reason**: Social preferences, not computational complexity

## Reproduction Instructions

### Part 1: Economist Analysis
See `economist/README.md` for theoretical framework and mathematical proofs.

### Part 2: Computational Analysis
```bash
cd computational_scientist
pip install nashpy quantecon
jupyter notebook notebook.ipynb
```

### Part 3: Behavioral Experiment
```bash
cd behavioral_scientist
unzip otree_app.zip
cd public_goods_2p
pip install otree
otree devserver
```

## Required Software Citations

- **NashPy**: Knight, V., & Campbell, M. (2021). *Journal of Open Source Software*, 6(59), 3075.
- **QuantEcon**: Sargent, T. J., & Stachurski, J. (2021). Version 0.5.1.
- **Game Theory Explorer**: Savani, R., & von Stengel, B. (2015). *Computational Management Science* 12, 5–33.
- **oTree**: Chen, D. L., et al. (2016). *Journal of Behavioral and Experimental Finance*, 9, 88–97.

## Main References

- Osborne, M. J., & Rubinstein, A. (1994). *A course in game theory*. MIT Press.
- Roughgarden, T. (2016). *Twenty lectures on algorithmic game theory*. Cambridge University Press.
- Fehr, E., & Schmidt, K. M. (1999). *The Quarterly Journal of Economics*, 114(3), 817–868.
- Fehr, E., & Gächter, S. (2000). *American Economic Review*, 90(4), 980–994.

## Ethical Considerations

This research followed standard ethical guidelines for behavioral experiments:
- Informed consent from all participants
- Anonymized data collection and analysis
- Voluntary participation with right to withdraw
- Full debriefing after experimental sessions

## Significance and Implications

This study demonstrates:
1. The persistent gap between theoretical predictions and actual behavior
2. The importance of social preferences in economic decision-making
3. The value of interdisciplinary approaches to complex problems
4. The potential of LLMs as rational agents in behavioral experiments

## Contact Information

For questions about this research, please open an issue in this repository or contact the maintainer.

## License

This project is for academic research purposes only. All rights reserved to the original authors of cited works.
```