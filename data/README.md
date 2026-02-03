# Dataset Documentation

## Dataset identity
- Name: BankSim
- Type: Synthetic
- Domain: Online / card payment transactions
- Source: BankSim fraud detection simulator
- Accessed on:
- License / usage constraints:

## Unit of analysis
- One row represents a single transaction between a customer and a merchant.

## Target variable
- Target column name: fraud
- fraud = 1 indicates a fraudulent transaction
- Labels are assumed to be assigned after transaction execution.

## Feature groups (expected)
### Customer-level
- Customer identifier
- Age
- Gender

### Merchant-level
- Merchant identifier
- Merchant category

### Transaction-level
- Transaction amount
- Transaction type

### Temporal / context
- Time step / transaction order

## Behavioral assumptions
- Customers exhibit consistent spending patterns over time
- Fraudulent behavior deviates from a customer’s historical norms
- Certain merchant categories carry higher baseline risk

## Known or expected risks
- Class imbalance: severe
- Leakage candidates: any post-transaction fields
- Simulation artifacts: repetitive or overly regular patterns
- Bias / fairness considerations: demographic features may encode bias

## Planned data split (pre-EDA)
- Split strategy: time-aware split
- Justification: prevents future information leakage
- What information must not cross splits: customer history beyond cutoff
