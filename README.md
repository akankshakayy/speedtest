# speedtest
# ⚡ NetPulse — Network Speed Intelligence

> A sleek, real-time internet speed test web app that measures your connection and diagnoses network issues — all in a single HTML file.

![NetPulse](https://img.shields.io/badge/NetPulse-v2.0-00d4ff?style=for-the-badge)
![HTML](https://img.shields.io/badge/Built%20With-HTML%20%2F%20CSS%20%2F%20JS-7b61ff?style=for-the-badge)
![License](https://img.shields.io/badge/License-MIT-00ffb3?style=for-the-badge)

---

## 🌐 Live Demo

👉 **[https://akankshakayy.github.io/speedtest](https://yourusername.github.io/speedtest)**


---

## 📸 Features

- 🚀 **Real-time Download Speed** — measures actual Mbps using live data fetches
- 🏓 **Ping / Latency Test** — measures round-trip time to a fast server
- 📤 **Upload Speed** — tests your outgoing bandwidth
- 📊 **Animated Speedometer Gauge** — beautiful SVG arc that fills in real time
- 🧠 **Smart Network Analysis** — automatically diagnoses your connection and lists possible issues
- ✦ **Verdict System** — rates your connection as Excellent, Acceptable, or Poor
- 🎨 **Stunning UI** — dark futuristic design with animated background orbs, neon glows, and smooth transitions
- 📱 **Fully Responsive** — works on mobile, tablet, and desktop
- 🗂️ **Zero Dependencies** — pure HTML, CSS, and JavaScript. No frameworks, no installs.

---

## 🛠️ How It Works

### Speed Measurement
The app uses the browser's native `fetch()` API to download and upload real data, then calculates speed using:

```
Speed (Mbps) = (bytes × 8) ÷ (seconds × 1,000,000)
```

| Test | Method | Endpoint |
|------|--------|----------|
| Ping | 4 fetch requests, drops worst result | Cloudflare trace |
| Download | Fetches ~8MB of data in parallel | Cloudflare speed endpoint |
| Upload | POSTs a 2MB random blob | Cloudflare speed endpoint |

### Analysis Engine
After testing, results are compared against standard thresholds:

| Metric | Excellent | Acceptable | Poor |
|--------|-----------|------------|------|
| Ping | < 50ms | 50–100ms | > 100ms |
| Download | > 25 Mbps | 10–25 Mbps | < 10 Mbps |
| Upload | > 5 Mbps | 1–5 Mbps | < 1 Mbps |

---

## 🚀 Getting Started

### Option 1 — Just open it
Download `index.html` and open it in any browser. No server needed.

### Option 2 — Deploy to GitHub Pages (free)
1. Fork or clone this repository
2. Go to **Settings → Pages**
3. Set source to **main branch**
4. Your site is live at `https://yourusername.github.io/speedtest`

### Option 3 — Deploy to Netlify (30 seconds)
1. Go to [netlify.com/drop](https://netlify.com/drop)
2. Drag and drop `index.html`
3. Get an instant live URL

---

## 📁 Project Structure

```
speedtest/
└── index.html      ← The entire app (HTML + CSS + JS in one file)
└── README.md       ← This file
```

---

## 🎨 Customization

All design tokens are CSS variables at the top of the `<style>` block — easy to change:

```css
:root {
  --bg:    #04060f;   /* page background */
  --glow:  #00d4ff;   /* primary accent color */
  --glow2: #7b61ff;   /* secondary accent */
  --ok:    #00ffb3;   /* good result color */
  --warn:  #ffd166;   /* warning color */
  --bad:   #ff4d6d;   /* bad result color */
}
```

To change the **max speed on the gauge**, find this line in the JavaScript:

```js
setGauge(parseFloat(dl), 200);  // change 200 to your max expected Mbps
```

---

## ⚠️ Notes

- Results are **estimates** based on real browser fetch timings and may vary slightly from tools like Speedtest.net, which use dedicated infrastructure.
- CORS restrictions in browsers mean some upload measurements use timing approximations.
- For most accurate results, close other tabs and apps before testing.

---

## 🧑‍💻 Built With

- **HTML5** — structure
- **CSS3** — animations, gradients, glassmorphism, CSS variables
- **Vanilla JavaScript** — fetch API, requestAnimationFrame, SVG manipulation
- **Google Fonts** — Orbitron, Syne, JetBrains Mono
- **Cloudflare Speed Endpoints** — for real download/upload data

---

## 📄 License

This project is open source and available under the [MIT License](LICENSE).

---

## 🙌 Author

Built by **[Akanksha K Kashyap]**


> *"NetPulse — because your internet deserves a diagnosis, not just a number."*
