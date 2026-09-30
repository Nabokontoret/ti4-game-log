# ti4-game-log

[**Live page**](https://nabokontoret.github.io/ti4-game-log/) — a paginated stats
page (wins, faction popularity, attendance, and other fun facts) covering the
group's Twilight Imperium games.

## Structure

- `index.html` — the published page (GitHub Pages serves this from `main`).
  It's a single self-contained file: all game data is embedded directly in a
  `<script>` block near the bottom, not loaded from `data/` at runtime
  (a static page can't read local files) — it's a manually kept-in-sync copy.
- `data/` — the source game log (CSVs + notes). **Gitignored, never pushed.**
  It's where new games actually get recorded; see `data/README.md`.

## Updating the page after logging a new game

1. Add the game to `data/games.csv` and `data/game_players.csv` as usual
   (see `data/README.md`).
2. Copy the same rows into the `GAMES` and `PICKS` arrays inside
   `index.html`'s `<script>` block — that embedded copy is what the published
   page actually reads.
3. Commit and push `index.html`. Pages redeploys automatically.
