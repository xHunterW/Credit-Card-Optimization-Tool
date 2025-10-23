# Credit-Card-Optimization-Tool
This Credit Card Optimizer Tool allows users to optimize their credit-card stack to maximize rewards and minimize annual fees based on your spending profile.

Built as a Mixed-Integer Linear Program with [PuLP] and the CBC solver.

# Current Personal Credit Card Stack
- Amex Blue (Groceries, Gas)
- Chase Sapphire Reserve (Dining, Travel)
- Robinhood Gold Card (Utilities, Tuition, Entertainment, Shopping, Etc.)

# Features (current)

Assigns one card per category to maximize cashback less annual fees. Optional 0% “NoCard” fallback so you’re not forced into a money-losing choice.
Optional wallet cap (e.g. “pick at most 3 cards”).

# Outputs:

Category → Card mapping, Net Value ($), and Unique Cards.

A per-card P&L table (spend, rewards, fee, net, break-even).

Not included (by design, for now): sign-up bonuses, first-year fee waivers, tier/cap modeling, points valuations.

# Requirements

Python 3.9+

Packages: 
1. pulp (MILP modeling; will use a bundled CBC on most platforms)
2. pandas (P&L table)

### Install:
pip install pulp pandas


# Limitations (current)

No sign-up bonuses or first-year fee waivers (In development).

No import sheet for credit card rates.

No tier/cap modeling (e.g., “6% groceries up to $6k then 1%”) and no time slicing (quarters/months).

No points valuations beyond explicit cash-back rates (no transfer partner modeling).

Deterministic spending only (no uncertainty/Monte Carlo).

Single-route per category (no splitting a category across multiple cards).

# Tips

Add a "Base": <rate> to a card to avoid sparse category maps.

Use max_cards to explore a wallet efficiency frontier.

If a category appears as "NoCard" (when allowed), it means no card beats 0% for that category under your inputs.

# License

MIT

