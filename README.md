# bseptember.github.io

A modern, high-performance static rickroll page hosted on GitHub Pages.

> *Send the link. Watch the magic happen.*

## Live

**[https://bseptember.github.io](https://bseptember.github.io)**

## What It Does

When someone opens the link, they're greeted with what looks like a sleek, modern "exclusive content" reveal page. One click later — they're watching Rick Astley in full cinematic glory with audio blasting. Classic rickroll, premium delivery.

## Features

### Visual Effects (Pure CSS + Vanilla JS)
- **Animated background grid** — slow-scrolling cyberpunk grid lines
- **Floating gradient orbs** — blurred, animated colour blobs (cyan, magenta, gold)
- **Particle system** — 80 connected dots with proximity lines drawn on `<canvas>`
- **Conic gradient spinning border** — animated neon frame around the video
- **CRT scanlines** — subtle retro scanline overlay on the video
- **Corner bracket accents** — sci-fi UI corner markers on the video frame
- **Glassmorphism UI** — frosted glass "Now Playing" bar and status pill
- **Vignette overlay** — radial gradient darkening at screen edges
- **Audio visualiser ring** — real-time FFT frequency visualisation drawn as a circular waveform using the Web Audio API

### Audio / Video
- **Instant muted autoplay** — video begins playing immediately on page load (muted to comply with browser policies)
- **One-click unmute** — clicking the disguised intro overlay unmutes audio and starts the full experience
- **Fallback re-activation** — if the browser blocks audio on first try, any subsequent click retries unmute
- **Preloaded video** — `<link rel="preload">` ensures the video is fetched ASAP
- **Cinematic mode** — after the zoom sequence, the video expands to full-width widescreen

### The Disguise
- **Page title:** "You Won a Free Gift Card!"
- **Open Graph / Twitter meta tags** — link previews in chat apps show the fake gift card title and description
- **Intro screen** — gradient background with "Something Special Awaits You", a glowing CTA button, typing dots animation, and a "100% free • no signup required" hint
- **Toast notifications** — "Now Playing..." followed by "You just got Rickrolled!" a few seconds later

### Performance
- Video `preload="auto"` + `<link rel="preload" as="video">`
- DNS prefetch for the hosting domain
- No external dependencies — zero HTTP requests beyond the HTML and video file
- All CSS is inlined (single file, no render-blocking requests)
- `requestAnimationFrame` for all animations
- Particle count scales with viewport width
- `{ passive: true }` on all scroll/interaction listeners

### Security
- `Content-Security-Policy` meta tag — restricts sources to `'self'` for scripts, styles, media, images, and fonts
- `X-Content-Type-Options: nosniff` via meta tag
- `Referrer-Policy: no-referrer` — no referrer leakage
- Right-click disabled on video (`oncontextmenu="return false"`)
- Picture-in-picture and download controls disabled
- Print stylesheet hides all content

### Accessibility
- Semantic HTML5 structure
- `aria-label` attributes on interactive elements
- `aria-hidden="true"` on decorative layers
- Keyboard activation support (`Enter` / `Space`) on the intro overlay
- `role="button"` and `tabindex="0"` on the intro overlay
- `role="alert"` with `aria-live="polite"` on toast notifications
- `@media (prefers-reduced-motion: reduce)` disables all animations

### Standards
- Valid HTML5
- CSS custom properties (design tokens)
- `box-sizing: border-box` reset
- `viewport-fit=cover` for notched devices
- Responsive breakpoints at 768px and 480px
- System font stack with `-webkit-font-smoothing`

## File Structure

```
.
├── index.html      # The entire app — HTML, CSS, JS all inlined
├── media_asset     # Rick Astley - Never Gonna Give You Up (MP4)
├── README.md       # This file
└── LICENSE         # MIT
```

## Usage

1. Share `https://bseptember.github.io` with someone
2. They open it and see what looks like an exclusive content reveal
3. They click the button
4. Rick Astley takes over their screen

## Development

It's a single HTML file. Open it in any browser. Edit it in any text editor. No build tools, no dependencies, no framework.

```bash
# Clone
git clone https://github.com/bseptember/bseptember.github.io.git

# Open locally
open index.html
# or
start index.html
```

## Browser Support

| Browser | Autoplay (muted) | Click-to-unmute | Visualiser | Particles |
|---------|:-:|:-:|:-:|:-:|
| Chrome 90+ | Yes | Yes | Yes | Yes |
| Firefox 85+ | Yes | Yes | Yes | Yes |
| Safari 15+ | Yes | Yes | Yes | Yes |
| Edge 90+ | Yes | Yes | Yes | Yes |
| Mobile Chrome | Yes | Yes | Yes | Yes |
| Mobile Safari | Yes | Yes | Partial | Yes |

## License

[MIT](LICENSE) &copy; 2023 bseptember
