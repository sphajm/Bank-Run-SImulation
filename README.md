# Bank-Run-SImulation

A Python-based simulation that models how bank runs occur through customer panic, social influence, and bank reserve depletion.

## Overview

This simulation models the dynamics of a bank run - a situation where a large number of customers withdraw their deposits simultaneously due to concerns about the bank's solvency. The model demonstrates how individual decisions, social influence, and increasing rumors can lead to cascading effects that potentially cause bank failure.

## Features

- Realistic customer decision-making based on:
  - Individual trust levels
  - Neighbor/social network influence
  - Increasing rumor strength over time
- Bank system with:
  - Fractional reserve banking model
  - Real-time reserve ratio tracking
  - Failure conditions when reserves are depleted
- Detailed visualization showing:
  - Withdrawal patterns over time
  - Bank financial status (reserves and deposits)
  - Key statistics and metrics

## How It Works

The simulation creates a network of customers, each with:
- A random initial deposit amount (between $1,000-$5,000)
- A trust level (between 0.5-1.0)
- A social network of 3-7 random neighbors

During each time step:
1. Rumor strength increases gradually
2. Each customer decides whether to withdraw based on:
   - Their personal trust level
   - How many of their neighbors have withdrawn
   - Current rumor strength
3. The bank processes withdrawals if it has sufficient reserves
4. If reserves are depleted, the bank fails and simulation ends

## Requirements

- Python 3.6+
- Required libraries:
  - numpy
  - pandas
  - matplotlib
  - random (standard library)

## Usage

Simply run the script to execute a standard simulation:

```python
python bank_run_simulation.py
```

Or import and call the main functions in your own code:

```python
from bank_run_simulation import simulate_bank_run, run_and_visualize

# Run simulation with default parameters
history, bank, customers = simulate_bank_run()

# Run and display visualization
history, bank, customers = run_and_visualize()
```

## Customization

You can modify simulation parameters by passing arguments:

```python
# Custom simulation with 200 customers and 30 timesteps
history, bank, customers = simulate_bank_run(num_customers=200, num_timesteps=30)
```

## Output

The simulation provides:

1. Terminal output showing individual customer decisions and bank status at each step
2. Visualization with two plots:
   - Number of withdrawals over time
   - Bank reserves and deposits over time
   - Statistical annotations showing key metrics

## Example Output

Terminal output example:
```
--- Time Step 1 ---
Customer_42 withdrew 3245.21
  Influenced by 0/5 neighbors who withdrew
  Trust level: 0.52

Step Summary:
New withdrawals: 12
Bank reserves: 56432.19
Bank deposits: 187623.97
Rumor strength: 0.15
```

The visualization shows withdrawal patterns and bank financial status with annotations for key statistics.

## Future Improvements

Potential enhancements could include:
- Different customer personalities and risk profiles
- Bank interventions to prevent failure
- Multiple competing banks
- Government policies and regulations
- Economic impact indicators
