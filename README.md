# Tsukuyumi Board Generator

This is a board generator for the board game [Tsukuyumi](https://boardgamegeek.com/boardgame/299450/tsukuyumi-full-moon-down-second-edition).

The rules say to place the area tiles randomly, but humans are notoriously bad at randomness. This is especially so considering the fact that the tiles are double sided, so it's hard to avoid being influeced by the partially built board when placing new tiles.

The generator begins with the Moon tiles in the center and will attempt to place new tiles outward until the given number of tiles (which depends on the number of players) has been placed.

The algorithm takes 3 params to modify its behavior:
 - `tileProbability` The probability of placing adding a tile to the board versus leaving that space empty.
 - `adjancencyRequirement` The number of tiles already on the board a new tile must be adjacent to.
 - `allowHoles` Whether placing a tile which would create a hole on the board is permitted.

These params are summarized in a **Scatter Level** with four presets:

|          | `tileProbability` | `adjancencyRequirement` | `allowHoles` |
|----------|------------------:|------------------------:|:------------:|
| **None** |                 1 |                       1 |     False    |
| **Low**  |              0.75 |                       2 |     False    |
| **Mid**  |              0.75 |                       1 |     False    |
| **High** |               0.5 |                       1 |     True     |


**Live site:** https://fonse.github.io/tsukuyumi/
