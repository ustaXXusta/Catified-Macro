# 🐱 Catified: Kedi Macerası

A cute, pink, cat-themed mini-game collection that runs in any browser. There are 10 short levels, a boss fight at the end, and an unlockable **dream-house builder**. It's one self-contained `index.html` with no install, no build step and no server.

> The in-game text is in **Turkish** 🇹🇷.

---

## ▶️ How to play

**Option 1: on your computer**
1. Download or clone this repo.
2. Double-click `index.html`. It opens in your browser and you can start playing.

**Option 2: online (GitHub Pages)**
1. Push this repo to GitHub.
2. Open **Settings → Pages**, set *Source* to **Deploy from a branch**, then pick `main` and `/ (root)`.
3. After a minute the game is live at `https://<your-username>.github.io/<repo-name>/`. Send that link to anyone, and it works on phones too 📱.

### Getting started in the game
1. Tap **🎮 Yeni Oyun** (New Game).
2. Enter **your name** and **your cat's name**. Both are optional; if you leave them empty, the defaults are `Kedisever` and `Pamuk`.
3. Pick a level on the **map** 🗺️. Each level unlocks the next one.
4. Read the short instructions, then press **Tamam, Başla!** to start.
5. Earn up to ⭐⭐⭐ per level. Beat the final boss to unlock **🎁 Ödüllerim** (rewards) and **🏡 Hayal Evim** (dream house).

---

## 🎮 Levels & controls

| # | Level | Goal | Mouse / touch | Keyboard |
|---|-------|------|---------------|----------|
| 1 | 🐭 Fare Avı | Catch 20 mice in 45 s | Tap the mice | n/a |
| 2 | 🏃 Yarış | Beat the rival cat to the finish line | Tap **TAP!** fast | `Space` |
| 3 | 🍗 Mama Kazan | Catch 25 falling treats in 30 s | ◀ ▶ buttons | `←` `→` / `A` `D` |
| 4 | 🍽️ Yemek Seç | Let 15 good foods through and pop the bad ones | ✋ button on the lane | `1` `2` `3` |
| 5 | 📖 Kelime Avı | Find every hidden word in the story | Tap the words | n/a |
| 6 | 🧶 Yün Topu Avı | Catch 25 yarn balls in 45 s | Move mouse / drag finger | `WASD` / arrows |
| 7 | 🎵 Şarkı Söyle | Hit 20 notes on the beat | Tap the circles | `A` `S` `D` |
| 8 | 🃏 Anı Albümü | Match all 8 pairs in 60 s | Tap cards | n/a |
| 9 | 🌊 Selden Kaç | Collect 10 hearts and outrun the flood | ◀ ⬆️ ▶ buttons | `A` `D` / arrows, jump `W` `↑` `Space` |
| 10 | 🧿 Nazar Canavarı | Defeat the boss | **SALDIRI!** button | `Space` / `↑` |

**🏡 Hayal Evim (Dream House)** unlocks after level 10. You decorate 5 rooms (garden, living room, kitchen, bedroom, bathroom) with emoji furniture:
- Tap an item in the list to add it, then drag it around the room.
- Double-click an item to remove it.
- **Kedinle Gez** lets you walk your cat around the room with `WASD`.
- **Odayı Kaydet** saves the house.

---

## 💾 Saving

- Progress is **auto-saved** in the browser, and the game resumes where you left off.
- **💾 Kaydet / Kayıt Yükle** gives you 3 manual save slots, so more than one person can play on the same device.
- Saves live in the browser's `localStorage`. Clearing site data, or switching to another browser or device, starts fresh.

---

## 🎨 Customize it (e.g. to make it a gift)

Open `index.html` in any text editor and find the `CONFIG` block at the top of the main `<script>`:

```js
const CONFIG = {
  defaultPlayerName: 'Kedisever',   // used when the player leaves the name empty
  defaultCatName: 'Pamuk',          // used when the cat name is left empty
  rewardLinks: [],                  // extra buttons on the final reward screen
  letter: ''                        // a message shown on the final reward screen
};
```

Example:

```js
const CONFIG = {
  defaultPlayerName: 'Elif',
  defaultCatName: 'Boncuk',
  rewardLinks: [
    { label: '🎵 Sürpriz Şarkı', url: 'https://www.youtube.com/watch?v=...' },
    { label: '📸 Fotoğraf Albümü', url: 'https://...' }
  ],
  letter: 'Tebrikler! Bütün bölümleri bitirdin 🎉\nSeninle gurur duyuyorum!'
};
```

Other easy things to change:
- **Level texts and goals:** the `LEVELS` array.
- **Hidden words and story (level 5):** `KEYWORDS` and `L5_TEXT`. Each keyword has to appear in the story as a whole word.
- **Memory cards (level 8):** `L8_CARDS`.
- **Dream-house furniture:** `HAYALI_ITEMS`.
- **Colors:** the CSS variables in `:root` at the top of the file (`--pink`, `--yellow`, `--navy`, …).

Save the file and refresh the browser to see your changes.

---

## 📁 Project structure

```
.
├── index.html   # the whole game (HTML + CSS + JS)
├── README.md
└── .gitignore
```

The only external resource is the Google Fonts stylesheet (Fredoka One + Nunito). Offline, the game still works and uses fallback fonts.

---

## 🚀 Push to your own GitHub

```bash
# create an empty repo on github.com first (no README), then:
git remote add origin https://github.com/<your-username>/<repo-name>.git
git push -u origin main
```
