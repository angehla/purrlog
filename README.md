# Purrlog

A game-style health tracker for Oreo and Louis: weight and body condition, play,
litter and barf logs, with moods, streaks, levels and badges.

- `web/`: **the no-login version.** `index.html` + `firestore.rules`, backed by a
  free Firebase database. Anyone with the link can log. Setup steps: `web/SETUP.md`.
- `index.html`: the Claude artifact version
  (https://claude.ai/artifact/74bwQwVQMYTGjUWYE1gAgS). Its data lives in the
  artifact's shared database, and only the owner and people invited as Editors can log.
