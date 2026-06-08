# Contributing to FreeCryptoStore

Want to add a blockchain or cryptography simulation? Here's how.

## What we accept

Self-contained interactive HTML simulations that teach crypto/blockchain concepts. Each simulation is a single `index.html` file — no build step, no dependencies, no framework.

## Quick start

1. Copy the template:
```bash
cp -r store/items/_template store/items/your-sim-name
```

2. Edit `store/items/your-sim-name/index.html` — build your simulation

3. Add an entry to `store/registry.json`

4. Open a PR

## Design rules

| Rule | Value |
|------|-------|
| Background | `#0a0a0a` |
| Text | `#fafafa` |
| Accent | `#f59e0b` (amber) |
| Font | Manrope via Google Fonts, system-ui fallback |
| Max file size | ~30KB (keep it lean) |
| External deps | None except Google Fonts |
| Back link | `<a class="back" href="/">Back to Store</a>` at top left |
| Cross-linking | `<script src="/related.js"></script>` before `</body>` |

## Registry entry format

Add to the `robots` array in `store/registry.json`:

```json
{
  "id": "your-sim-name",
  "name": "Your Simulation Title",
  "description": "One-line description of what it does.",
  "icon": "🔗",
  "iconBg": "#f59e0b",
  "category": "blockchain|cryptography|consensus|contracts|defi|network|wallet|history",
  "storeType": "behavior",
  "creator": "your-github-username",
  "creatorName": "Your Name",
  "creatorAvatar": "https://github.com/your-username.png?size=96"
}
```

## Categories

| Category | Topics |
|----------|--------|
| `cryptography` | Hash functions, signatures, ZKPs, encryption |
| `blockchain` | Blocks, chains, mining, forks |
| `consensus` | PoW, PoS, PBFT, BFT |
| `contracts` | Smart contracts, VMs, gas |
| `defi` | AMMs, yield, tokens, bonding curves |
| `network` | P2P, gossip, propagation, attacks |
| `wallet` | Key derivation, addresses, HD wallets |
| `history` | Timeline, milestones, evolution |

## What makes a good simulation

- **Interactive** — user can change inputs and see results immediately
- **Visual** — use canvas, SVG, or animated HTML to show concepts
- **Educational** — teaches HOW something works, not just WHAT it is
- **Self-explanatory** — include enough context that someone new can understand it
- **Performant** — runs smoothly on a phone browser

## SHA-256 helper

Many crypto simulations need SHA-256. Use this compact implementation (public domain):

```javascript
const SHA256=(function(){/* ... see any existing demo for the full implementation */})();
```

Copy it from any existing simulation in `store/items/`.

## Questions?

Open an issue or look at existing simulations for examples.
