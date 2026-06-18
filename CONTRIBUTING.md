# Contributing to Peanuts Trivia

Thanks for your interest in helping out! This is a small, single-file fan project, so contributing is low-ceremony. Whether you're fixing a typo, adding a trivia question, or polishing the UI, you're welcome here.

## Ways to contribute

- **Add or fix trivia questions** — the most useful contribution (see below).
- **Fix a bug** — timer quirks, scoring edge cases, layout issues on a particular device.
- **Improve the design** — animations, accessibility, responsive tweaks.
- **Improve the docs** — clearer wording in the README, fixing mistakes.

## Setup

There's no build step and nothing to install. The whole game is `peanuts-trivia.html`.

1. Fork and clone the repo.
2. Open `peanuts-trivia.html` in any modern browser.
3. Edit the file, refresh the browser, repeat.

That's the entire workflow.

## Adding trivia questions

Questions live in the `BANK` array near the top of the `<script>` block. Each entry looks like this:

```js
{ q:"What breed of dog is Snoopy?", a:["Dachshund","Beagle","Basset Hound","Labrador"], c:1 },
```

- `q` — the question text.
- `a` — exactly **four** answer options.
- `c` — the **zero-based index** of the correct option (so `1` means the second item, `"Beagle"`).

Guidelines for good questions:

- Keep it **factual and verifiable** — about the strip's characters, history, running gags, or the TV specials.
- Make the three wrong options **plausible**, not throwaways.
- Aim for a single clearly correct answer; avoid "all of the above" or trick phrasing.
- Don't worry about answer order — the game reshuffles options at runtime.
- Double-check the `c` index actually points at the right option.

The game draws a random subset each play (`ROUND_SIZE`), so growing the bank just adds variety — no other changes needed.

## Please don't add

This project intentionally avoids reproducing protected material. To keep it that way, contributions should **not** include:

- Drawings, images, or recreations of Peanuts characters (including stylized or renamed lookalikes).
- Verbatim dialogue or text lifted from the comic strips or specials.
- Copyrighted logos, fonts, or other branded assets.

Trivia *about* the series is fine; reproducing the series' artwork or writing is not. When in doubt, leave it out or ask in an issue.

## Code style

- Vanilla HTML, CSS, and JavaScript — no frameworks or build tools.
- Match the existing style: 2-space indentation, `const`/`let`, and the helper patterns already in the file.
- Use the CSS variables in `:root` for colors rather than hard-coding new hex values.
- Keep it a single file. If a change really needs to be split out, raise it in an issue first.
- Test in at least one desktop and one mobile-width browser before submitting, and check that keyboard play (`1`–`4` / `A`–`D` / `Enter`) and reduced-motion still behave.

## Submitting changes

1. Create a branch: `git checkout -b add-questions` (or a name describing your change).
2. Make your edits and test them in the browser.
3. Commit with a clear message, e.g. `Add 5 questions about the TV specials`.
4. Open a pull request describing what you changed and why.

Small, focused PRs are easier to review and merge than large mixed ones.

## Reporting bugs

Open an issue and include:

- What you did (steps to reproduce).
- What you expected to happen.
- What actually happened.
- Your browser and whether you were on desktop or mobile.

## Code of conduct

Be kind and constructive. Assume good faith, keep feedback focused on the work, and help make this a friendly place to contribute. Good grief is the only grief we want here.
