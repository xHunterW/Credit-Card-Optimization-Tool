# Credit Card Optimization Tool
This Credit Card Optimizer Tool allows users to optimize their credit-card stack to maximize rewards and minimize annual fees based on your specific spending profile.

Built as a Mixed-Integer Linear Program with [PuLP] and the CBC solver.

# Current Personal Credit Card Stack
- Amex Blue (Groceries, Gas, Streaming, Subscriptions [Disney+, Spotify, Netflix, etc])
- Chase Sapphire Reserve (Dining, Travel)
- Robinhood Gold Card (Utilities, Tuition, Entertainment, Shopping)

# Features 

Algorithm assigns one card per user-defined category to maximize cashback less annual fees. Optional 0% “NoCard” fallback so you’re not forced into a money-losing choice.
Optional wallet cap (e.g. “pick at most 3 cards”).

# Outputs:

Category -> Card mapping, Net Value ($), and Unique Cards.

A per-card P&L table (spend, rewards, fee, net, break-even).

Not included (by design, for now): Sign-up bonuses, first-year annual fee waivers, points to USD valuations and credits through external collaborations (e.g. Lululemon credits w/ Amex).

# Requirements

Python 3.9+

Packages: 
1. pulp 
2. pandas (for P&L table)

### Install:
pip install pulp pandas


# Current Limitations

No sign-up bonuses or first-year fee waivers (In development).

No import sheet for up to date credit card rates (In development for Chase/CapitalOne/Amex/Citi/Robinhood Cards).

No tier/cap modeling (i.e., “6% groceries up to $6k then 1%”) and no time slicing (quarters/months).

No point valuations beyond explicit cash-back rates (no transfer partner modeling).

Deterministic spending only (no uncertainty in spending categories).

Single-route per category (no splitting a category across multiple cards).

# Tips

Add a "Base": <rate> to a card to avoid sparse category maps.

Use max_cards to explore a wallet efficiency frontier.

If a category appears as "No Card" (when allowed), it means no card beats 0% for that category under your given inputs.

# License

MIT

