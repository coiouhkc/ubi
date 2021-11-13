# UBI
Universal Battleship Interface

## History
Inspired by UCI (Universal Chess Interface), see https://en.wikipedia.org/wiki/Universal_Chess_Interface

## Architecture
The UBI protocol is based on `stdin`/`stdout`. Once the the UBI engine is started it waits for commands on `stdin` and communicates their results as well as its own shoot attempts via `stdout`.

## Commands

* `ìnfo`
* `start` 
* `stop`
* `reset`
* `quit`
* `option [option-name [option-value]]`
  * `game-mode`
    * `soviet` (default)
* `position [position-value]`
  * `position-value`
```
<position> ::== [<cell-value>+ <cell-value>+ <player-to-move-index>]
<cell-value> ::== <space> | . | x | o
<space> ~ unknown/unrevealed
. ~ miss
x ~ hit
o ~ ship
```
* `shoot <position>`
  * `<position>`to be specified in short algebraic notation, e.g. `a2`
  * possible replies
    * `hit`
    * `miss`
    * `sunk`
