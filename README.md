# Galope Libertador (5y Variant) — 2D Endless Runner Game

A variant of the "Galope Libertador" 2D endless runner game: a gaucho/Argentine-themed runner built with Next.js and the HTML5 Canvas API. Ride through the pampas, jump over cacti, and collect mate and empanadas for points.

## What It Does

- Renders a full-screen, auto-scrolling 2D runner on `<canvas>` with `requestAnimationFrame`
- Animated player character (5-frame sprite animation) with gravity physics, jumping, double jump, and fast-drop
- Randomly spawning cactus obstacles (3 variants) and collectible items (mate 🧉, empanadas 🥟, +100 points each)
- Infinite scrolling desert background
- Background soundtrack with mute/unmute toggle
- Top-5 high scores persisted in `localStorage`
- Floating "+100" score popups on pickup
- Mobile support: touch-to-jump controls and a rotate-to-landscape prompt on portrait phones
- Menu / playing / game-over states with Spanish-language UI

## Features

- Canvas-based 2D game loop (60fps via `requestAnimationFrame`)
- Single and double jump, gravity, and fast-drop (↓ key)
- Obstacle collision → game over; collectible collision → score
- Score increases over time plus pickups
- High-score leaderboard saved locally
- Responsive canvas that fills the window
- Looping background music (Vercel Blob-hosted MP3) with toggle

## Tech Stack

- **Framework:** Next.js 15 (App Router), React 19, TypeScript
- **Rendering:** HTML5 Canvas 2D API
- **UI:** Tailwind CSS, shadcn-style Radix UI (Button, Card), lucide icons
- **Styling:** Tailwind CSS + `tailwindcss-animate`
- **Analytics:** @vercel/analytics

## Quick Start

```bash
# install dependencies
pnpm install
# or: npm install

# run the dev server
pnpm dev
# open http://localhost:3000

# build for production
pnpm build

# start the production server
pnpm start
```

### How to Play

- **Desktop:** `Space` to jump (press again mid-air for a double jump), `↓` for fast drop
- **Mobile:** tap the screen to jump (double tap for double jump)
- Dodge the cacti 🌵, grab mate and empanadas for +100 points each

## Project Structure

```
2d-endless-runner-game-5y/
├── app/
│   ├── page.tsx          # entire game: loop, physics, sprites, UI states
│   ├── layout.tsx        # root layout + theme provider
│   └── globals.css       # global styles
├── components/
│   ├── theme-provider.tsx
│   └── ui/               # shadcn UI primitives (button, card, …)
├── lib/
│   └── utils.ts          # shared utilities (cn helper)
├── public/
│   └── images/           # background.jpeg, guemes1-5.png, cactus1-3.png, logo.png
├── styles/
│   └── globals.css
├── components.json       # shadcn component config
├── next.config.mjs
├── tailwind.config.ts
└── tsconfig.json
```

## Environment Variables

None required for local development.

## Deployment Notes

- The original v0 project deploys to Vercel (`next build && next start`).
- All game logic is client-side; assets live under `public/images/`.
- Related project: [`2d-endless-runner-game`](https://github.com/girishlade111/2d-endless-runner-game) — the sibling variant of this game.

## License

MIT

---

Built by Girish Lade — https://ladestack.in
