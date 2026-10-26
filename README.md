# ChessPuzzle

Chess puzzle packs for the Chess Sinta Android app. Data only: no code.

## Source

The [Lichess puzzle database](https://database.lichess.org/#puzzles) (`lichess_db_puzzle.csv.zst`), which Lichess releases under [CC0 1.0](https://creativecommons.org/publicdomain/zero/1.0/). Thanks to Lichess and its puzzle contributors.

Selection: puzzles with popularity ≥ 90 and at least 500 plays, grouped into rating bands of 100 points, up to 200 puzzles per band. Bands with fewer than 30 puzzles are left out.

## Releases

Each release tag (`puzzles-1`, `puzzles-2`, …) is a complete, fixed set. A published tag is never changed: new data gets a new tag.

| File | Content |
|---|---|
| `manifest.json` | `{"packs": [{"band", "url", "sha256", "count"}]}`, one entry per pack |
| `pack-<band>.json` | `{"band", "puzzles": [{"id", "fen", "moves", "rating", "rd", "themes"}]}` |

`band` is the rating divided by 100: `pack-15.json` holds puzzles rated 1500–1599. `fen` is the position before the opponent's move. `moves` is the whole line in UCI: the opponent plays `moves[0]`, then the solver and the opponent alternate. `id` is the Lichess puzzle ID (`https://lichess.org/training/<id>`).

## License

[CC0 1.0 Universal](LICENSE).
