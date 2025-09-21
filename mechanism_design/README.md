# Mechanism Design for Winner's Curse Experiment

## Overview
This directory contains all materials related to the auction mechanism design and experimental implementation for studying the Winner's Curse phenomenon in Large Language Models (LLMs).

## Directory Structure
```
mechanism_design/
├── README.md                   # This file - overview of the mechanism design
├── Auction Mechanism Design.md # Detailed auction rules and economic structure
├── Experimental Setup.md       # Technical implementation details
└── prompt.txt                  # Prompt templates for both control and treatment groups
```

## File Descriptions

### 1. Auction Mechanism Design.md
Contains the complete economic framework and auction rules:
- Auction type and value distributions
- Control and treatment group designs
- Profit function and efficiency metrics
- Theoretical foundations and hypotheses
- Literature references

### 2. Experimental Setup.md
Details the technical implementation:
- AI model specifications (GPT-4 and DeepSeek)
- Round structure and execution parameters
- Data collection framework
- Quality control measures
- Implementation timeline

### 3. prompt.txt
Contains the prompt templates used for both experimental groups:
- **Control group prompt**: Full information condition
- **Treatment group prompt**: Noisy signal condition
- Formatting instructions for model interactions

## Auction Design Summary

### Basic Framework
- **Auction Type**: Unilateral sealed-bid auction (Game #37)
- **Value Distribution**: $V \sim \text{Uniform}(0, 1000)$
- **Profit Function**: $\text{Profit} = 1.5V - B$ if $B \geq V$, else $0$

### Experimental Groups
- **Control Group**: Knows $V \sim \text{Uniform}(0, 1000)$
- **Treatment Group**: Receives $S = V + \varepsilon$ where $\varepsilon \sim \text{Uniform}(-100, 100)$

### Key Metrics
- **Profit Efficiency**: $\frac{1.5V - B}{0.5V}$
- **Safety Net**: $1.5V - B \geq 0.5V > 0$ (no monetary loss possible)

## Experimental Parameters

### Models Tested
- **GPT-4**: Rounds 1-5
- **DeepSeek Chat**: Rounds 6-10

### Execution Details
- **Total Rounds**: 10
- **Isolation**: Separate chat sessions per round
- **Temperature**: 0.0 (deterministic responses)

## Usage

To replicate this experiment:

1. **Review** `Auction Mechanism Design.md` for theoretical framework
2. **Implement** using specifications in `Experimental Setup.md`
3. **Use** the prompts in `prompt.txt` for model interactions
4. **Collect** data following the described format

## Citation

### Experimental Platform
Rubinstein, Ariel. *Games and Behavior*. Tel Aviv University and New York University. https://arielrubinstein.org/gt/Student/?c=50747.

### Theoretical Foundation
- Kagel, John H., and Dan Levin. 2002. *Common Value Auctions and the Winner's Curse*. Princeton University Press.
- Bazerman, Max H., and William F. Samuelson. 1983. "I Won the Auction but Don't Want the Prize." *Journal of Conflict Resolution* 27 (4): 618–34.

## License
This experimental design is for academic research purposes. Please cite appropriately when using or adapting this methodology.