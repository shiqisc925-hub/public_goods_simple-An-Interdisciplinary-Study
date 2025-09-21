
# Behavioral Scientist: Public Goods Game Experiment

## Experiment Overview

A two-player public goods game implemented using oTree. Each participant starts with an endowment of 150 points. Players simultaneously decide how much to contribute to a public pool (0-150 points). The total contributions are multiplied by an efficiency factor of 1.5 and then divided equally between both players.

**Final Earnings Formula:**
`150 - personal contribution + (total contributions × 1.5 ÷ 2)`

## Installation and Deployment

### Prerequisites
- Python 3.7+
- oTree framework

### Quick Setup
```bash
# Install oTree
pip install otree

# Extract and run the experiment
unzip otree_app.zip
cd public_goods_2p
otree devserver
```

### Access the Experiment
Open your browser and navigate to: `http://localhost:8000`

## Session Configuration

The experiment uses the following settings in `settings.py`:

```python
SESSION_CONFIGS = [
    {
        'name': 'public_goods_2p',
        'display_name': '2-Player Public Goods Game',
        'num_demo_participants': 2,
        'app_sequence': ['public_goods_2p'],
        'participation_fee': 2.00,
    }
]
```

## File Structure

```
behavioral_scientist/
├── otree_app.zip                 # Complete oTree application
├── screenshots/
│   ├── instructions.png         # Game instructions page
│   ├── decision.png            # Contribution decision page
│   └── results.png             # Results page
├── llm/
│   ├── prompts.txt             # LLM interaction prompts
│   ├── transcript.md           # Complete LLM conversation
│   └── settings.json           # LLM parameters and settings
└── README.md                   # This file
```

## Experimental Procedure

1. **Instructions Phase**: Participants read game rules
2. **Decision Phase**: Simultaneous contribution decisions (0-150 points)
3. **Results Phase**: Display of outcomes and earnings
4. **Post-Experiment Interview**: Qualitative feedback collection

## Human Session Results

### Participant Decisions
- **Participant 1**: Contributed 100 points
- **Participant 2**: Contributed 100 points

### Post-Experiment Interview Responses
**Question 1**: "What was your strategy when deciding how much to contribute?"
> *"We contributed 100 because it is two-thirds of 150, which felt like a fair and balanced amount. We believed that if both contributed 100, each would end up with 200 points, which is better than the initial endowment."*

**Question 2**: "Did you trust your partner would contribute a similar amount? Why or why not?"
> *"Yes, we trusted each other because 100 seemed like a reasonable and fair amount that would benefit both players equally."*

## LLM Session with DeepSeek

### Prompt Used
```
"This is a public goods game with 2 players per group, an endowment of 150 points, and an efficiency factor of 1.5. How much will you contribute?"
```

### LLM Response
**Contribution**: 100 points

**Reasoning**: 
*"I choose to contribute 100 points. If the other player also contributes 100, the total pool becomes 200 points. After multiplying by 1.5, it becomes 300 points, split equally yielding 150 points each. Adding the 50 points I kept, my final payoff is 200 points—a Pareto improvement over the initial endowment. Even if the other player contributes less, I still receive a reasonable return. One hundred points strikes a balance between cooperation and self-protection."*

### Researcher's Decision
**Contribution**: 50 points

**Reasoning**: 
*"I chose 50 points because I was cautious about the possibility of the other player contributing very little or nothing. If I contribute 50, I keep 100 points. Even if the other contributes zero, I still get 100 + (50 × 1.5 ÷ 2) = 137.5 points, which is acceptable. If the other also contributes 50, we each get 175 points. I preferred a safer strategy."*

## Comparative Analysis

| Aspect | Theoretical Prediction | Human Behavior | LLM Behavior |
|--------|-----------------------|----------------|--------------|
| **Contribution** | 0 points | 100 points | 100 points |
| **Reasoning** | Dominant strategy | Fairness heuristic | Rational calculation |
| **Risk Approach** | N/A | Moderate risk-taking | Risk-neutral |

## Ethical Considerations

This experiment follows standard ethical guidelines for behavioral research:
- **Informed Consent**: Participants were fully briefed about the experiment
- **Anonymity**: All data is anonymized and used only for research purposes
- **Voluntary Participation**: Participants could withdraw at any time
- **Debriefing**: Full explanation provided after the experiment
- **Compensation**: Fair monetary compensation for participation


## Reproduction Steps

1. Extract `otree_app.zip`
2. Run `otree devserver`
3. Access via `http://localhost:8000`
4. Configure sessions in `settings.py`
5. Conduct experiments and collect data
6. Use admin interface for data export
