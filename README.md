# ColourFlip 🎨

A colour memory game where you match pairs of rare colour shades while learning their history, etymology and presence in nature and culture.

Built as a single HTML file — no framework, no build step, no dependencies beyond Firebase.

---

## What it is

ColourFlip is a memory card game with an educational twist. Each card shows a rare colour shade with three facts:

- 📖 **Origin** — the etymology and history of the colour's name
- 🌿 **Nature** — where this colour appears in the natural world
- 🏛 **Culture** — its significance in art, fashion, architecture or history

When you flip a card, a **close-up modal** appears for 3 seconds so you can read the full card before it stays revealed. This makes the game both a memory challenge and a way to genuinely learn about colour.

---

## Colour families

The game includes **10 colour families**, each with a library of 20 rare shades:

| Family | Examples |
|--------|---------|
| 💙 Blues | Prussian Blue, Lapis, Smalt, Majorelle, Watchet |
| ❤️ Reds | Vermillion, Carmine, Titian, Dragon's Blood, Garance |
| 🩷 Pinks | Mountbatten, Baker-Miller, Cerise, Thulian Pink, Puce |
| 🧡 Oranges | Gamboge, Coquelicot, Tenne, Fulvous, Tuscany |
| 💚 Greens | Verdigris, Celadon, Hooker's Green, Lincoln Green, Feldgrau |
| 💛 Yellows | Naples Yellow, Indian Yellow, Aureolin, Mikado, Xanthic |
| 💜 Violets | Tyrian Purple, Heliotrope, Byzantium, Mauve, Porphyry |
| 🤎 Browns | Bistre, Sepia, Mummy Brown, Vandyke Brown, Chamoisee |
| 🩶 Greys | Payne's Grey, Marengo, Davy's Grey, Battleship, Feldgrau |
| 🌿 Naturals | Ecru, Flint, Hemp, Moss Agate, Chamomile |

At the start of each game, **8 shades are randomly selected** from the family's library of 20 — so no two games are identical.

---

## Game modes

### 🎯 Solo
- Find all 8 pairs as fast as possible, in as few moves as you can
- Live timer + move counter
- Personal best saved per colour family (stored in localStorage)
- View your best scores from the lobby

### 👥 Multiplayer (2 players)
- Real-time multiplayer over Firebase Realtime Database
- One player creates a game and shares a 6-character code
- The other player joins with that code
- Turn-based: find a pair and you play again; miss and the turn switches
- Both players see the same close-up in real time when a card is flipped

---

## How to play

1. Pick a **colour family**
2. Choose **Solo** or **Multiplayer**
3. Cards are laid face-down in a **4×4 grid** (16 cards, 8 pairs)
4. Tap a card — a **close-up** appears for 3 seconds showing full colour info
5. Tap a second card
6. If they match: keep the pair and go again
7. If they don't: both cards flip back face-down
8. First to find all pairs wins (multiplayer) — or beat your best time (solo)

---

## Technical details

- **Single HTML file** — everything in one `index.html`, no build process
- **Firebase Realtime Database** — for multiplayer game state sync
- **Web Audio API** — synthetic sound effects (flip, no-match, well done claps + melody, win fanfare)
- **CSS 3D transforms** — card flip animations with `preserve-3d` and `backface-visibility`
- **localStorage** — solo high scores, stored client-side only
- **Mobile-first** — responsive 4×4 grid, iOS safe-area support, no pinch-zoom

### Firebase setup

The project uses Firebase Realtime Database for multiplayer. If you fork this and want your own instance:

1. Create a project at [firebase.google.com](https://firebase.google.com)
2. Enable **Realtime Database** (start in test mode)
3. Replace the `firebaseConfig` object in the `<script type="module">` block with your own credentials

```js
const firebaseConfig = {
  apiKey: "YOUR_API_KEY",
  authDomain: "YOUR_PROJECT.firebaseapp.com",
  databaseURL: "https://YOUR_PROJECT-default-rtdb.REGION.firebasedatabase.app",
  projectId: "YOUR_PROJECT",
  storageBucket: "YOUR_PROJECT.appspot.com",
  messagingSenderId: "YOUR_SENDER_ID",
  appId: "YOUR_APP_ID"
};
```

---

## Deployment

The game is a static single-file app — deploy anywhere that serves HTML.

**GitHub Pages (recommended):**

```bash
# Put index.html at the root of your repo
# Enable GitHub Pages in Settings → Pages → Deploy from branch: main
# Your game will be live at https://YOUR_USERNAME.github.io/YOUR_REPO
```

No build step, no npm install, no configuration.

---

## Fonts used

- [Playfair Display](https://fonts.google.com/specimen/Playfair+Display) — titles, card names, scores
- [DM Mono](https://fonts.google.com/specimen/DM+Mono) — body text, labels, UI

Both loaded from Google Fonts.

---

## Lobby background

The lobby background is a CSS art interpretation of **Wassily Kandinsky's Composition VII (1913)** — layered radial gradients and geometric shapes in the spirit of the original painting's chaotic, colourful abstraction.

---

## Project history

| Version | Description |
|---------|-------------|
| v1 | Solo French version — *Nuances Bleues*, 20 blue shades, Playfair typography |
| v2 | English multiplayer version — Firebase integration, card design variants |
| v3 | 10 colour families, Kandinsky lobby background, mobile layout, sound effects |
| v4 | 4×4 grid (16 cards), 8-from-20 random selection, close-up modal, solo mode, personal bests |

---

## License

MIT — do what you like with it.
