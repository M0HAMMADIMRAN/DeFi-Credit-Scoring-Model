WALLET CREDIT SCORE ANALYSIS:

OVERVIEW:

This document analyzes the score distribution of wallets processed using the Aave V2 scoring engine. The goal is to interpret how wallet behaviors vary across the score spectrum.

SCORE DISTRIBUTION:

Scores are binned in ranges of 100, from 0 to 1000. The distribution histogram (see score_distribution.png) shows how many wallets fall into each range.

SCORE BUCKETS:

0–100: Very high risk wallets, often with few transactions, or sudden large redemptions.

100–300: Low activity wallets with very small deposits or frequent redemptions compared to deposits.

300–600: Average activity; somewhat balanced behavior but limited in volume or time span.

600–800: Good users; show repeated use, fair deposits and moderate redemptions.

800–1000: Highly reliable; large consistent deposits, long activity duration, and balanced or minimal redemptions.

BEHAVIOR INSIGHTS:

Low-Scoring Wallets (0–300):

Often show a high redeem/deposit ratio

Low deposit amount in USD

Activity spanned only 1 or 2 days

Transaction patterns look synthetic or one-time

High-Scoring Wallets (700–1000):

Active over multiple days

Consistent deposit patterns

Lower or balanced redemption rates

High total deposit volume (especially in stablecoins)

OBSERVATIONS:

Some wallets with high redemption but also high deposits received mid-range scores due to volume.

Bots or airdrop-hunters are likely to fall under <300 scores.

Reliable DeFi users tend to show signs of dollar-cost-averaging or long-term deposits.

Next Steps (for future improvement):

Include borrow, repay, liquidationcall actions

Use clustering or anomaly detection for edge-case behaviors

Add time-based decay on activity (recent behavior weighs more)

