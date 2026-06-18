# Peanuts Trivia — The Sunday Funnies Quiz

A self-contained, Sunday-funnies-styled web quiz that tests your Peanuts knowledge against the clock — with speed scoring, high-score tracking, and shareable result cards.

Everything lives in a single `peanuts-trivia.html` file. No build step, no frameworks, no install — just open it in a browser and play.

## Quick start

1. Download `peanuts-trivia.html`.
2. Double-click it (or drag it into any modern browser).
3. Hit **Let's Play**.

That's it. An internet connection is only used to load the display fonts from Google Fonts; offline, the game still works and gracefully falls back to system fonts. Opening the downloaded file locally also lets your high score persist between sessions.

## How to play

You get twelve multiple-choice questions, each on a 15-second timer. Answer fast for more points, then see your rank, review the answer key, and share a result card.

Controls:

- **Mouse / touch** — tap an answer, then tap **Next**.
- **Keyboard** — press `1`–`4` or `A`–`D` to answer, and `Enter` to advance.

## Scoring

- Each correct answer is worth **100 base points** plus a **speed bonus of up to 100**, scaled to how much time is left on the clock.
- Maximum is **200 points per question**, so a flawless, lightning-fast run tops out at **2,400**.
- A wrong answer or a timeout scores zero and reveals the correct choice.
- Your best total is saved and shown on the start and results screens.

Rank tiers are based on how many you got right, from "Good Grief!" at the bottom up to "Round-Headed Champ!" for a perfect score.

## Features

- **A shuffling question bank** — 23 questions, with a fresh random 12 dealt each play and the answer order reshuffled every time.
- **Per-question timer** with a draining ring that pulses when time runs low.
- **Speed-based scoring** and a running point total.
- **Instant feedback** — correct answers turn green, wrong ones turn red and shake the question.
- **Review screen** — a full answer key showing your pick and the correct answer for every question.
- **Shareable result card** — a comic-styled PNG drawn on an HTML canvas, plus a Wordle-style emoji summary you can copy into any chat, plus native sharing on supported devices.
- **Persistent high score** via the browser's local storage, with a graceful in-session fallback if storage is unavailable.
- **Generated sound effects** (Web Audio API — no audio files needed) with a mute toggle on the start and quiz screens.
- **Accessible and responsive** — visible focus outlines, keyboard play, a mobile-friendly layout, and full support for reduced-motion preferences.

## Design notes

The look is built from the visual language of mid-century newspaper comics rather than any specific character:

- **Palette** — aged-newsprint cream, warm ink-black line work, and the four-color Sunday register of comic red, golden yellow, and sky blue (all defined as CSS variables in `:root`).
- **Type** — *Luckiest Guy* for the chunky hand-lettered headers and *Nunito* for the body text.
- **Motifs** — a recurring zigzag stripe, halftone Ben-Day dots, comic-panel borders, speech-balloon questions, and a handful of original doodles (a kite, a baseball, autumn leaves, sparkles) drifting around the title.

## Customizing it

Everything is in the one file and easy to tweak:

- **Questions** — edit the `BANK` array near the top of the `<script>`. Each entry is `{ q, a, c }`, where `q` is the question, `a` is the array of four options, and `c` is the zero-based index of the correct one.
- **Round length** — change `ROUND_SIZE` (questions per game) and `ROUND_TIME` (seconds per question).
- **Scoring** — adjust `BASE_PTS` and `SPEED_MAX`.
- **Colors** — change the variables under `:root` in the `<style>` block.

## Tech

Plain HTML, CSS, and vanilla JavaScript. The only external dependency is the Google Fonts stylesheet linked in the `<head>`. The result card is rendered with the Canvas 2D API, sound is synthesized with the Web Audio API, and the high score uses `localStorage` — so the whole thing runs from a single static file.

## A note on copyright

The code, layout, and all artwork in this project are original. It deliberately does **not** reproduce any Peanuts characters or Charles Schulz's drawings — the trivia consists of factual questions, and the visuals use generic comic-strip motifs only.

*Peanuts* and its characters are trademarks and copyrights of Peanuts Worldwide LLC. This project is an unofficial fan-made quiz and is not affiliated with, authorized, or endorsed by the rights holders. Use the code freely for personal and educational purposes; the Peanuts name and characters are not ours to license.
