# Stardle

**Stardle** is a daily astronomy word game by [Dhruva Astronomy Club](https://teamdhruva.com). Guess the five-letter astrophysics term in six tries—same rules as Wordle, with a cosmic twist.

## How to play

1. Enter a valid **5-letter** word as your guess.
2. Tile colors show how close you are:
   - **Green** — letter is in the word and in the correct spot.
   - **Yellow** — letter is in the word but in the wrong spot.
   - **Gray** — letter is not in the word.
3. You have **6 guesses** to find the answer.
4. Tap **Hint** for a song clue (Spotify, Apple Music, YouTube Music links) that nudges you toward the word.
5. A **new puzzle** unlocks every day at **midnight IST**. You cannot start another game until then.

Repeated letters follow standard Wordle rules: a letter only highlights as many times as it appears in the answer.

## Features

- Daily word rotation from a curated astrophysics word list
- Musical hint panel with streaming search links
- Animated starfield background
- Stats, share grid, and win distribution (from the base Wordle engine)
- First-visit “How to play” modal
- Post-game popup with word meaning links (from CSV)
- Local persistence of progress and stats

## Tech stack

Static site—no build step:

| File | Role |
|------|------|
| `index.html` | Page structure, modals, hint UI |
| `script.js` | Core Wordle gameplay (from [Wordle-Vanilla](https://github.com/doeixd/Wordle-Vanilla)) |
| `stardle.js` | Starfield, CSV loading, IST daily word, hints, Stardle-only hooks |
| `stardle.css` | Astronomy theme and layout |
| `styles.css` | Base Wordle styles |
| `possibleWords.js` | Valid guess dictionary |
| `astrophysics_wordle_song_links-4.csv` | Daily answers, songs, and link metadata |

## Run locally

The game loads the word list with `fetch`, so open it through a local HTTP server (not `file://`).

```bash
cd Stardle
python3 -m http.server 8080
```

Then visit [http://localhost:8080](http://localhost:8080).

Other options: `npx serve .`, VS Code Live Server, or any static host.

## Deploy

Upload the project root as static files. Ensure `astrophysics_wordle_song_links-4.csv` is served from the same origin as `index.html`.

## Credits

- Gameplay foundation: [Wordle-Vanilla](https://github.com/doeixd/Wordle-Vanilla) by doeixd (educational Wordle clone).
- Concept, word list, and hints: Dhruva Astronomy Club.
- Wordle is owned by its respective rights holders; Stardle is a themed variant for learning and fun, not an official Wordle product.


