[![make.fun · tiny-chess-01](https://make.fun/badge/tiny-chess-01.svg)](https://make.fun/bounty/tiny-chess-01?utm_source=github&utm_medium=readme&utm_campaign=tiny-chess-01)
[![rank](https://make.fun/badge/tiny-chess-01/hantnam/chess-bot-4kb/rank.svg)](https://make.fun/bounty/tiny-chess-01/leaderboard?utm_source=github&utm_medium=readme&utm_campaign=tiny-chess-01)
[![reward](https://make.fun/badge/tiny-chess-01/hantnam/chess-bot-4kb/reward.svg)](https://make.fun/bounty/tiny-chess-01?utm_source=github&utm_medium=readme&utm_campaign=tiny-chess-01)

# tiny-chess-01

Built for the [make.fun "Build the strongest chess engine in 4 KB of Python" bounty](https://make.fun/bounty/tiny-chess-01).

This is a small chess engine for the make.fun 4 KB Python challenge. The whole engine lives in `main.py`, a compact Python 3.13 program that searches with iterative-deepening alpha-beta. It keeps a transposition table, orders its candidate moves, and scores positions using material values combined with piece-square tables.

How far the search goes is controlled by a fixed node budget derived from `MAKEFUN_TRIAL_SEED`. The engine never looks at a clock, so a given position and seed always lead to the same decision. That lets a trial be replayed later with every move coming out identical.

## Running it

Start the bot by pointing it at the competition env and supplying a trial seed:

    MAKEFUN_ENV_URL=http://127.0.0.1:PORT MAKEFUN_TRIAL_SEED=42 python main.py

    Communication is over JSON/HTTP through three routes: `/game` to fetch the next game, `/move` to submit a UCI move, and `/resign` to give a game up.

    ## Size and license

    The readable source is kept in `main_src.py` and turned into the shipped `main.py` with the kit's `makefun compress` command, which keeps the entrypoint below 4096 bytes.

    This project is released under the MIT license.
    
