# Quarantine Deal

A lockdown-themed, set-collecting card game for 2 to 5 players, in the style of Monopoly Deal. The whole game is one file, `index.html`.

## How it runs

The page is published as a Claude artifact. It stores each table's state in the artifact's shared database (`claude.use("db")`), so there is no server to deploy and nothing to pay for hosting. Opened anywhere else (for example straight from this repo), the page shows the rules but cannot save games.

## How to play

- Everyone starts with 5 cards. On your turn you draw 2, then play up to 3 cards.
- Put properties on the table to build sets. Put rolls and unwanted action cards in your stockpile to pay bills.
- Bill Due cards charge rent on a set you own. Bills are paid from the stockpile or with properties, with no change given.
- Porch Pirate takes a property, Contactless Swap trades one, Lockdown Order takes a whole set. Six Feet Back cancels any action aimed at you.
- Bidet Upgrade (+3) and Panic Room (+4) raise the rent on a full set.
- Still Sharing shows you a hand for 10 seconds, Shared Doorknob trades hand cards, Leftovers Night takes back a recently played action, Back-Ordered makes a player skip a draw, and Spring Cleaning makes a player redraw their hand.
- End your turn with 7 cards or fewer. The first player with three full sets wins.

## Code layout

- Between the `/*ENGINE*/` and `/*END*/` markers: the deck and the rules (`newGame`, `act`), with no DOM access.
- After that: rendering and the database calls.

All hands live in one shared game document and the page only shows you your own, so this is for playing with friends you trust.
