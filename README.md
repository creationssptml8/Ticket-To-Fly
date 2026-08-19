# NASA × STARDANCE — Interplanetary Booking Portal

An ultra-premium, dark-themed interstellar booking portal, built as a **single self-contained
`index.html`** — no build step, no server required. Open it in any browser and it runs.

## Quick start

| Method | How |
|---|---|
| Double-click | Open `index.html` directly (all assets load from CDNs) |
| Local server | `python3 -m http.server 8080 --directory stardance` → `http://localhost:8080` |

## What's inside

**Flow (6-step wizard)**
1. **Departure Setup** — round-trip enforced (One-Way triggers the sarcastic `NO` modal), Earth origin, destination cards with live trajectory factors, dates, traveler count (1–4).
2. **Mission Requirements** — training status ($3B surcharge vs $2B certification) + mission class tier (Standard ×1.00 / Commander ×1.15 / Ambassador ×1.30).
3. **Life Support & Catering** — 4 × $10M microgravity menu items + optional extras (abort insurance, priority boarding, memory crystal, comms bundle).
4. **Passenger Manifest** — per-traveler names (letters-only, auto BOLD CAPS), 16-digit card with live VISA / MASTERCARD / AMEX / random-network badges, 3–4 digit CVV. Strict no-PII: no email, phone, age, address, or SSN, ever.
5. **Simulated Payment** — full fare breakdown, USD ↔ ★STARDUST unit toggle, count-up total animation, glowing authorize button that morphs spinner → checkmark → confetti.
6. **Digital Boarding Pass** — titanium-styled pass: randomized spacecraft/seat, crew manifest, mission code, orbit details, real scannable QR, CSS barcode, T-minus countdown, download-as-PNG, copy code.

**Persistence**
- Wizard draft auto-saves to `localStorage` (key `stardance.draft`) — refresh resumes where you left off.
- Issued passes are archived (key `stardance.passes`) and browsable via the gold **ARCHIVE** button in the header; any pass can be re-rendered.

**Design**
- Void Black `#05050A` base, animated starfield + drifting nebulae, glassmorphism with cyan glow, gold shimmer branding, Orbitron/Rajdhani type.
- Fully responsive, keyboard-friendly (Enter advances, Esc closes modals), `prefers-reduced-motion` respected.

## Pricing engine

```
per traveler:  $3B base × destination factor × mission-class multiplier
training:      +$3B (untrained) or +$2B (NASA certified) per traveler
catering:      +$10M per shared item
extras:        flat add-ons
```

Destination factors: Mars ×1.25 · Lunar Surface ×1.10 · Lunar Orbit ×1.05 · ISS ×0.95 ·
Shuttle ×1.00 · Skylab ×0.98 · Mir ×0.95 · Gemini Express ×0.90.
The Sun and all outer planets are blocked — hover/click them to read why.

## Tech

HTML5 + Tailwind CSS (CDN) + Lucide icons + Canvas-Confetti + qrcode-generator + html2canvas.
All client-side; nothing is transmitted anywhere.
