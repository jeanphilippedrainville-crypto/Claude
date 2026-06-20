# 🍇 Vin Vivant — A Natural Wine Bar Idle Game

A cozy, ever-growing idle game for someone who loves natural wine. Start with an empty
room and a dream, pour glasses by hand, then build a low-intervention wine empire that
runs itself — from humble piquette all the way to a living vineyard estate.

**▶️ Play it:** https://jeanphilippedrainville-crypto.github.io/Claude/
*(also works fully offline — just open `index.html` in any browser)*

## How to play

- **Pour a glass** to earn ₲. Every pour drops a little money in the till.
- Spend ₲ in the **Cellar** on natural-wine "producers" that pour for you automatically —
  Piquette Jugs, Glou-Glou Carafes, Pét-Nat Crates, Skin-Contact Barrels, Biodynamic Plots,
  Amphorae, Wild-Yeast Cellars, Cult Cuvées, a Natural Wine Fair, and a Living Vineyard Estate.
  Each new one costs a bit more, so the numbers keep climbing.
- Buy **Upgrades** (×1 / ×10 / Max buy modes) for big multipliers — "No Added Sulphites",
  "Hire a Sommelier", "Featured in a Wine Zine", and more.
- Chase **Achievements** in the Almanac — each one gives a permanent +1% boost.
- When a vintage has run its course, **Declare a New Vintage** to reset for **Terroir points ★**,
  a permanent bonus to everything. This is the long game — each reset makes the next one faster.

It keeps earning while you're away (at half pace, up to 8 hours), and greets you with a
welcome-back summary. Progress **saves automatically** in your browser. Use **Export / Import**
to move your save to another device, and **Reset** to start fresh.

Every wine in the cellar has a true one-line note on what makes it special, so it's a little
love letter to natural wine as much as a game.

## Hosting notes

The game is published to GitHub Pages by `.github/workflows/deploy-pages.yml`. A few things to know:

- Pages needs the repository to be **public** (or on a plan that includes Pages for private repos).
- The workflow tries to enable Pages automatically. If the first run fails with a
  "Pages not enabled" error, set **Settings → Pages → Build and deployment → Source: GitHub Actions**
  once (an admin has to do this), then re-run the workflow.
- No build step, no dependencies — it's a single static `index.html`, so it also runs perfectly
  by just double-clicking the file.

Made with 🍇. Santé!
