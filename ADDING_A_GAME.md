# Adding a New Game to the Arcade

Every time we finish building a new game together, here's the whole
process to publish it — no rebuilding the home page needed.

## 1. Upload the game
Create a new folder under `games/` named after the game, for example
`games/tank-duel/`, and put its `index.html` (and any `images/` folder
it needs) inside — same pattern as `games/soldier-wars/`.

Tip: `games/_template/index.html` is a ready-made starting point with
the shared colors, the Telegram hooks, and the "← Games" back link
already wired up, so new games automatically feel like part of the
same set.

## 2. Add one entry to games.json
Open `games.json` in the root of the repository and add a new entry
to the list, for example:

```json
{
  "id": "tank-duel",
  "title": "Tank Duel",
  "subtitle": "One-shot artillery duel across no man's land",
  "tag": "2-Player",
  "icon": "💥",
  "path": "games/tank-duel/index.html",
  "status": "available"
}
```

Fields:
- `id` — short unique name, letters/numbers/dashes only
- `title` / `subtitle` — shown on the game's card
- `tag` — small optional label, e.g. "2-Player", "Solo", "Online"
- `icon` — a single emoji
- `path` — where the game's `index.html` lives
- `status` — `"available"` to show a live "Deploy" card, or
  `"locked"` to show it grayed out with a "Locked" badge (useful if
  we want to tease a game before it's finished)

## 3. Done
Save both files to GitHub. The home page reads `games.json` itself,
so the new game shows up automatically — nothing else to touch, and
no need to update BotFather or any Telegram settings.
