# tiny-chess-01
[![make.fun · tiny-chess-01](https://make.fun/badge/tiny-chess-01.svg)](https://make.fun/bounty/tiny-chess-01?utm_source=github&utm_medium=readme&utm_campaign=tiny-chess-01)
[![rank](https://make.fun/badge/tiny-chess-01/Arijit178/tiny-chess-01/rank.svg)](https://make.fun/bounty/tiny-chess-01/leaderboard?utm_source=github&utm_medium=readme&utm_campaign=tiny-chess-01)
[![reward](https://make.fun/badge/tiny-chess-01/Arijit178/tiny-chess-01/reward.svg)](https://make.fun/bounty/tiny-chess-01?utm_source=github&utm_medium=readme&utm_campaign=tiny-chess-01)

A chess engine in 4 KB of Python, built for the [Build the strongest chess engine in 4 KB of Python bounty on make.fun](https://make.fun/bounty/tiny-chess-01).

## What it is

`main.py` is the whole engine (3,944 bytes): a 0x88-board negamax
alpha-beta search with iterative deepening to a fixed 50,000-node budget
per move, a transposition table, killer + history move ordering,
null-move pruning, late-move reductions, and quiescence over captures,
promotions and check evasions. The evaluation is tapered material plus
piece-square terms, maintained incrementally in make/unmake, with a
bishop-pair bonus and tempo. No clock, no randomness: the same position
always gets the same move, so trial replays match.

## Run it

The engine talks to the trial env at `$MAKEFUN_ENV_URL`:

    python3 main.py

It plays every game of the gauntlet through the env (`POST /game`,
`POST /move`) until the trial is done. Python 3.13, standard library
only.
