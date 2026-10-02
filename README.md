# Quarantine Deal

A lockdown-themed, set-collecting card game for 2 to 5 players, in the style of Monopoly Deal. The whole game is one file, `index.html`.

## How it runs

The page is published as a Claude artifact. It stores each table's state in the artifact's shared database (`claude.use("db")`), so there is no server to deploy and nothing to pay for hosting. Opened anywhere else (for example straight from this repo), the page shows the rules but cannot save games.

## How to play

- Everyone starts with 5 cards. On your turn you draw 2, then play up to 3 cards.
- Put properties on the table to build sets. Put masks (M) and unwanted action cards on the masks side of your board to pay rent.
- Rent cards charge rent on a set you own. Bills are paid with masks or properties, with no change given.
- Close Business takes a property, Close Schools trades one, Close Borders takes a whole set. No! I'm in Quarantine cancels any action aimed at you.
- Toilet Paper Stash (+3) and Social Distancing (+4) raise the rent on a full set.
- Share Screen shows you a hand for 10 seconds, Cross Contaminate trades hand cards, False Positive takes back a recently played action, Delayed Shipment makes a player skip a draw, and Work From Home makes a player redraw their hand.
- End your turn with 7 cards or fewer. There are two ways to win: be first to three full sets, or first to own a property in all ten colours.

## Code layout

- Between the `/*ENGINE*/` and `/*END*/` markers: the deck and the rules (`newGame`, `act`), with no DOM access.
- After that: rendering and the database calls.

All hands live in one shared game document and the page only shows you your own, so this is for playing with friends you trust.
