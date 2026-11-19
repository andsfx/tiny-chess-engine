# tiny-chess-engine

[![tiny-chess-01](https://make.fun/badge/tiny-chess-01.svg)](https://make.fun/competitions/tiny-chess-01)
[![rank](https://make.fun/badge/tiny-chess-01/andsfx/tiny-chess-engine/rank.svg)](https://make.fun/competitions/tiny-chess-01)
[![reward](https://make.fun/badge/tiny-chess-01/andsfx/tiny-chess-engine/reward.svg)](https://make.fun/competitions/tiny-chess-01)

A chess engine in under 4 KB of Python. `main.py` unpacks an lzma-compressed
payload and plays the gauntlet through the env at `MAKEFUN_ENV_URL`.

## Engine

Alpha-beta search on a 0x88 board with iterative deepening, null-move and delta pruning, quiescence, and a 300k node budget. Elo 1654 on the practice gauntlet.

- Board: 0x88 with Zobrist hashing and incremental evaluation
- Search: iterative-deepening alpha-beta on a fixed node budget, quiescence
  search, transposition table, MVV-LVA and killer move ordering
- Evaluation: material, piece-square tables, bishop pair, king phase blend
- Deterministic: no clock, no randomness, so replays match byte for byte
