# Sali Marriage Invitation

A single-page Islamic Nikkah invitation styled like [this reference](https://marriage-muzammil.github.io/invitation/): cream and gold palette, Arabic verses, couple details, events, live countdown, floating petals, and a “Mabrook” overlay when the countdown ends.

## Quick start

1. Open `index.html` in a browser, or run a local server:

   ```bash
   cd SaliMarriage
   python3 -m http.server 8080
   ```

   Then visit http://localhost:8080

2. Edit the **`CONFIG`** object near the bottom of `index.html` (names, dates, venues, map link, countdown).

3. Couple photo: **`images/saalimarriage.jpg`** (update `CONFIG.photo` if you rename the file).

4. Background music: **`audio/saliAudio.mp3`** (update `CONFIG.music` if you rename the file).

## Customize

| Setting | What to change |
|--------|----------------|
| `groom` / `bride` | Full names and parents |
| `events` | Nikkah and reception (add more blocks if needed) |
| `countdownTarget` | ISO date/time for countdown end |
| `mapUrl` | Google Maps link for the Nikkah venue |
| `receptionMapUrl` | Google Maps link for reception |
| `music` | Path to MP3 (e.g. `audio/music.mp3`) |
| `musicVolume` | 0–1 (default 0.45) |
| `photo` | Filename of your image |
| `theme` | Color preset: `gold`, `blush`, `sage`, or `custom` |
| `colors` | When `theme` is `custom`, set hex values (see `THEMES` in `index.html`) |

### Change background / colors

In `index.html`, find `CONFIG` and change:

```javascript
theme: 'blush',   // try: 'gold' | 'blush' | 'sage'
```

For your own colors:

```javascript
theme: 'custom',
colors: {
  pageBg: '#F0F0F0',    // outer background
  cardBg: '#FFFFFF',    // invitation card
  accent: '#2563EB',    // titles, names, buttons
  // ... see THEMES.gold in index.html for all keys
},
```

For extra lineage (e.g. grandparents), set `extraLineage` on groom or bride to an HTML string, for example:

```javascript
extraLineage: `
  <span class="relation" style="margin-top:8px;">Granddaughter of</span>
  <strong>Name</strong> &amp; <strong>Name</strong>
`
```

## Deploy online

Full steps for **https://salihwedding.codeteak.com** and **GitHub Pages**: see **[DEPLOY.md](./DEPLOY.md)**.

## Reference site features replicated

- Bismillah and Qur’an 30:21 opening verse  
- Elegant typography (Cormorant Garamond, Cinzel, Amiri)  
- Corner ornaments and gold dividers  
- Two-column events (Nikkah + reception)  
- Live countdown with flip animation  
- Google Maps button  
- Falling gold petal animation  
- Congratulations screen (Qur’an 43:70) when countdown reaches zero  
