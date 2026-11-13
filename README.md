# Purrlog

A game-style health tracker for Oreo and Louis: weight and body condition, play,
litter and barf logs, with moods, streaks, levels and badges.

Published as a Claude artifact: https://claude.ai/artifact/74bwQwVQMYTGjUWYE1gAgS

- `index.html` is the page source as published (the artifact host wraps it in the
  document skeleton).
- Data lives in the artifact's shared database (`db` capability): `cats/<id>`,
  `logs/<id>` (one document per entry), and `settings/main`.
- The page also declares the `downloads` capability for CSV and backup files.

To update the live app, republish `index.html` to the same artifact URL.
