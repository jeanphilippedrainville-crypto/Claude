# 🍷 De la salle au domaine — From Floor to Estate

A bilingual (Français / English) **wine career trivia game** for adults who love
wine and want something fun to play in a group. Climb the trade in four stages —
**Restaurateur → Importateur → Vigneron → Propriétaire de domaine** — by answering
wine questions that get harder as you rise. Win the last stage and you own your
own vineyard.

It's a **single static `index.html`** with no dependencies, no build step, and no
network calls. Works on phones and computers, and runs offline by just opening the
file.

**▶️ Play it:** open `index.html` in any browser (or publish it on GitHub Pages — see below).

## How to play

- **2 to 8 players** on one device — pass the phone between turns.
- Each player builds an **avatar** (character, hairstyle, hair colour, skin tone),
  drawn entirely in SVG. The outfit changes automatically at each stage:
  sommelier → suit-and-tie → vineyard work clothes → elegant estate owner.
- On your turn you answer multiple-choice questions. **A wrong answer costs a
  bottle** (you have 3). Run out of bottles, or miss the pass mark for a stage,
  and your turn ends — your score is banked where you got to.
- Clear all four stages to **win the estate**.
- Scores land on a **local leaderboard** kept in this browser (it survives closing
  the tab, isn't shared between devices, and can be reset).

## Customizing the game

Everything lives at the top of the `<script>` block in `index.html`.

**Balance** — edit the `CONFIG` object:

```js
const CONFIG = {
  questionsPerStage: 5,            // how many questions are drawn per stage
  lives: 3,                        // "bottles" — wrong answers you can afford
  thresholds: [3, 4, 4, 5],        // correct answers needed to clear each stage
  pointsPerCorrect: stage => 10 * (stage + 1),
  stageBonus:       stage => 100 * (stage + 1),
  victoryBonus: 500
};
```

**Add or edit questions** — find `const BANK = [ ... ]`. It's an array of four
stages, each an array of questions. Each question has French + English text, the
options, the index of the correct answer, and a short explanation in both
languages:

```js
{
  q: { fr: "Question en français ?", en: "Question in English?" },
  o: [ { fr:"Option A", en:"Option A" }, { fr:"Option B", en:"Option B" } ],
  correct: 0,                      // 0 = first option is right
  e: { fr: "Explication courte.", en: "Short explanation." }
}
```

Keep at least `questionsPerStage` questions in each stage; the game draws a random
subset every game.

**Add a hairstyle** — add its name to `HAIRSTYLES`, add a label to the `UI` object
(e.g. `hairMohawk`), and draw it in `hairTopSVG()`.

**Add / change an outfit** — outfits are drawn per stage in `outfitSVG(stage, skin)`.
Each stage (0–3) returns SVG for the torso; edit those paths or add a new branch.

**Colours / fonts** — all design tokens are CSS custom properties in `:root` at the
top of the `<style>` block.

## Publishing on GitHub Pages

GitHub Pages serves a file named `index.html` automatically. The simplest setup is
a dedicated repository so the game is the homepage:

1. On GitHub, click **New repository**, give it a name (e.g. `wine-career-game`),
   and make it **Public** (Pages is free for public repos).
2. Upload **`index.html`** to the root of that repository (drag-and-drop on the
   web, or `git push`). The file must be named exactly `index.html`.
3. Go to **Settings → Pages**.
4. Under **Build and deployment**, set **Source: Deploy from a branch**.
5. Choose the branch (usually `main`) and folder **`/ (root)`**, then **Save**.
6. Wait a minute, then refresh the Pages settings page — your public address
   appears there, in the form `https://<your-username>.github.io/<repo-name>/`.

No build step is needed — it's a single static file.

> If you keep the game inside this repo's `wine-career-game/` subfolder instead, it
> will be served at `https://<your-username>.github.io/<repo-name>/wine-career-game/`
> once Pages is enabled for the repo.

Santé! 🥂
