# Dataset Documentation

## Dataset Identity
- Name: IEEE-CIS Fraud Detection
- Type: Real-world data with privacy masking
- Domain: Online / e-commerce transactions
- Source: Kaggle – IEEE-CIS Fraud Detection competition
- Original context: Transactions processed by a real payment service provider
- License / usage: Kaggle competition terms (research and educational use)

## Unit of Analysis
- One row represents a single online transaction.
- Data is provided in two main tables:
  - Transaction table (financial and transactional attributes)
  - Identity table (device, browser, and identity-related signals)
- Tables are joined using a shared transaction identifier.

## Target Variable
- Target column: isFraud
- isFraud = 1 indicates a fraudulent transaction
- isFraud = 0 indicates a legitimate transaction
- Labels are assumed to be assigned after the transaction occurs based on downstream investigation.

## Feature Groups (High-Level)

### Transaction-Level Features
- Transaction amount
- Product and purchase-related attributes
- Transaction timing information
- Card or account-related identifiers (masked)

### Identity / Device Features
- Device type and browser information
- Email domain and network-related signals
- Address or identity proxies (masked)

### Anonymized Features
- Numerical features with abstract names (e.g. V-features)
- Represent engineered or aggregated behavioral signals
- No direct semantic interpretation available

## Behavioral Assumptions
- Legitimate users exhibit relatively consistent transaction patterns over time
- Fraudulent transactions deviate from historical or population-level norms
- Device, identity, and transaction context jointly influence fraud risk

## Known or Expected Risks
- Severe class imbalance (fraud is rare)
- High missingness in identity-related features
- Potential proxy variables for sensitive attributes
- Anonymized features limit column-level interpretability

## Data Leakage Considerations
- Time-based leakage must be avoided
- Features derived from future transactions must not be used
- Train/validation/test splits must respect transaction time ordering

## Planned Split Strategy (Pre-EDA)
- Split type: Time-based split
- Rationale: Mimics real-world deployment and prevents future information leakage
- Constraint: No information from transactions occurring after the split point may influence earlier samples
