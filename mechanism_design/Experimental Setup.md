# Experimental Setup

## 1. AI Model Selection

### Models Tested
- **GPT-4** (OpenAI)
- **DeepSeek Chat** (DeepSeek)

### Selection Rationale
- Both models represent state-of-the-art large language models
- Diverse architectural backgrounds (OpenAI vs. DeepSeek)
- Publicly accessible through API interfaces
- Capable of complex reasoning and numerical analysis

## 2. Experimental Structure

### Round Configuration
- **Total rounds**: 10 rounds
- **Rounds 1-5**: GPT-4 model testing
- **Rounds 6-10**: DeepSeek model testing
- **Each model tested with both control and treatment conditions**

### Value Generation Process
```python
# Pseudocode for value generation
import random

def generate_round_parameters():
    V = random.uniform(0, 1000)          # True value
    epsilon = random.uniform(-100, 100)  # Noise term
    S = V + epsilon                      # Signal value
    return V, epsilon, S
```

### Experimental Parameters
| Parameter | Value | Description |
|-----------|-------|-------------|
| Value Range | [0, 1000] | Uniform distribution |
| Noise Range | [-100, 100] | Uniform distribution |
| Resale Multiplier | 1.5x | Fixed premium |
| Rounds per Model | 5 | Sufficient for pattern observation |

## 3. Execution Protocol

### Chat Interface Setup
- **Platform**: Standard chat interface via API
- **Context Management**: New chat session for each round
- **Memory Isolation**: No information carry-over between rounds
- **Temperature Setting**: 0.0 (deterministic responses)

### Prompt Implementation

#### Control Group Prompt
```
You are an economic agent playing a game. Follow these rules exactly:

- The value V of a painting is uniformly distributed between 0 and 1000.
- You can resell it for 1.5 * V.
- You must submit a single bid B.
- If B >= V, you win and your profit is (1.5*V - B).
- If B < V, you lose, and profit is 0.
- You know the distribution of V but not its exact value.

Your goal is to choose a bid B that maximizes your expected profit.

**Instructions:**
1. Think step by step.
2. Output your final bid B as a single number, and nothing else.
3. Do not use any punctuation, units, or explanatory text.

What is your optimal bid B?
```

#### Treatment Group Prompt
```
You are an economic agent playing a game. Follow these rules exactly:

- The value V of a painting is uniformly distributed between 0 and 1000.
- You can resell it for 1.5 * V.
- You must submit a single bid B.
- If B >= V, you win and your profit is (1.5*V - B).
- If B < V, you lose, and profit is 0.
- You do not know the distribution of V. Instead, you receive a noisy signal S = V + ε, where ε ~ Uniform(-100, 100).
- Your signal for this round is S = [INSERT_S_VALUE_HERE].

Your goal is to choose a bid B that maximizes your expected profit.

**Instructions:**
1. Think step by step.
2. Output your final bid B as a single number, and nothing else.
3. Do not use any punctuation, units, or explanatory text.

What is your optimal bid B?
```

## 4. Data Collection Framework

### Recorded Variables per Round
- **Round Number**: 1-10
- **Model**: GPT-4 or DeepSeek
- **Group**: Control or Treatment
- **True Value (V)**: Randomly generated
- **Noise (ε)**: Randomly generated  
- **Signal (S)**: Calculated as S = V + ε
- **Bid (B)**: Model's output
- **Profit**: 1.5V - B if B ≥ V, else 0
- **Profit Efficiency**: (1.5V - B) / (0.5V)

### Data Storage Format
```csv
round,model,group,V,epsilon,S,B,profit,profit_efficiency
1,GPT-4,Control,456.23,,,500,184.345,0.808
2,GPT-4,Treatment,723.45,32.1,755.55,780,305.175,0.843
...
```

## 5. Quality Control Measures

### Validation Checks
- **Bid Format Validation**: Ensure output is numerical only
- **Profit Calculation Verification**: Cross-check all calculations
- **Signal Accuracy**: Verify S = V + ε computation
- **Data Integrity**: Manual spot-check of recorded data

### Reproducibility Features
- **Random Seed**: Fixed seed for value generation (if applicable)
- **Protocol Documentation**: Complete recording of all steps
- **Raw Data Preservation**: Storage of original model outputs

## 6. Ethical Considerations

### Transparency
- Clear communication of experimental nature to API providers
- Compliance with terms of service for both platforms
- Proper attribution of model outputs

### Data Handling
- Anonymization of experimental data
- Secure storage of results
- Ethical use of AI model capabilities

## 7. Implementation Timeline

### Phase 1: Preparation (1 day)
- API setup and authentication
- Value generation algorithm implementation
- Prompt template finalization

### Phase 2: Execution (1 day)
- Sequential round execution
- Real-time data recording
- Quality control checks

### Phase 3: Analysis (2 days)
- Data processing and cleaning
- Statistical analysis
- Visualization and interpretation

## 8. Expected Outputs

### Primary Data
- Complete dataset of 10 rounds
- Model bidding patterns
- Profit efficiency calculations

### Secondary Analysis
- Comparative performance between models
- Treatment effect quantification
- Behavioral pattern identification

### Documentation
- Experimental logs
- Code repository
- Methodology description

This experimental setup ensures rigorous testing of the auction mechanism while maintaining reproducibility and ethical standards in AI research.