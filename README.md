# DeFi-Credit-Scoring-Model
Aave V2 Wallet Credit Scoring System

OVERVIEW:

This project creates a machine learning-based scoring system for wallets interacting with the Aave V2 protocol on the Polygon network. Each wallet receives a credit score between 0 and 1000, representing the reliability and responsible behavior of the wallet. The scoring is based on historical transaction activity.

PROBLEM STATEMENT:

Given raw transaction-level data with actions like deposit, borrow, repay, redeemunderlying, and liquidationcall, develop a model that:

Engineers behavioral features for each wallet

Assigns a credit score based on usage

Outputs a score distribution for analysis

DATA FORMAT:

The data is provided as a JSON file with entries containing:

userWallet: Wallet address

action: e.g., deposit, redeemunderlying

actionData: includes amount, assetSymbol, assetPriceUSD

timestamp: UNIX time of the transaction

ARCHITECTURE AND FLOW:

user_transactions.json
-->
[Data Preprocessing & Feature Extraction]
-->
[Feature Engineering]
        - total transaction count
        - number of deposits/redeems
        - total deposit/redeem USD amount
        - activity days
        - redeem/deposit ratio
-->
[MinMax Scaling & Weighted Scoring]
-->
[Score Generation (0-1000)]
        |
        +---> wallet_scores.csv
        +---> score_distribution.png

SCORING METHODOLGY:

Extracted 7 key features per wallet

Normalized features using MinMaxScaler

Applied weighted scoring:

total_tx: 10%

deposit_count: 10%

redeem_count: 5%

total_deposit_usd: 25%

total_redeem_usd: 20%

active_days: 20%

redeem_deposit_ratio: 10%

Final scores are scaled to a 0–1000 range

OUTPUT:

wallet_scores.csv: List of wallets with assigned scores

score_distribution.png: Histogram of scores across 0–1000

HOW TO RUN:

pip install -r requirements.txt

python score_generator.py

DEPENDENCIES:

pandas

numpy

matplotlib

scikit-learn

NOTES:

Only deposit and redeemunderlying actions are analyzed in this version.

Further iterations can include borrow, repay, and liquidationcall.

Scores aim to reflect real, responsible usage—not bot or exploitative behavior.

