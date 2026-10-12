<div align="center">
  <h1>Drisha</h1>
  <p><em>दृशा — Sanskrit for sight</em></p>
  <p>An AI-powered accessibility companion that gives visually impaired users an independent voice on any screen.</p>
  <br />
  <a href="https://drisha.ai">Website</a> · <a href="#roadmap">Roadmap</a> · <a href="#contributing">Contributing</a>
</div>

---

## What is Drisha?

Drisha is a Chrome extension that uses Claude AI to describe and narrate any webpage, making the web genuinely navigable for people with visual impairments — without the broken tab-order and ARIA-label hell that standard screen readers depend on.

Most screen readers treat accessibility as a parsing problem. Drisha treats it as an understanding problem. It reads the DOM, infers intent from context, and speaks what the page *means* — not just what it says.

> "A guide dog doesn't just help you move. It gives you independence."

## How it works

1. **Install** — Add the Chrome extension. No account needed.
2. **Navigate** — Drisha monitors the active tab and detects meaningful page changes.
3. **Listen** — Claude AI synthesises a natural language description, spoken through the browser's voice API.

## Tech stack

| Layer | Technology |
|---|---|
| Extension runtime | Chrome MV3 |
| AI understanding | Claude API (Anthropic) |
| DOM analysis | Content scripts, MutationObserver |
| Voice output | Web Speech API |
| Privacy | Zero logging, no user data leaves the device |

## Features

- **DOM-first analysis** — Reads structure, not screenshots. Works on any site, even those with poor accessibility markup.
- **Context-aware narration** — Understands modals, dynamic content, and SPAs. Doesn't re-read the whole page on every interaction.
- **Voice-first UX** — Entirely keyboard and voice navigable. No mouse required.
- **Privacy-first** — Page content is processed via API and immediately discarded. No storage, no telemetry.
- **Offline roadmap** — Future versions will run a local small language model on-device with zero data leaving the machine.

## Roadmap

### v0.1 — Chrome extension (current)
- [x] DOM parsing and Claude AI narration
- [x] Web Speech API voice output
- [ ] Keyboard shortcut controls
- [ ] Configurable verbosity levels
- [ ] Support for dynamic content (SPAs, infinite scroll)

### v0.2 — Smart navigation
- [ ] Element-level focus descriptions
- [ ] Form-filling assistance
- [ ] Image alt-text generation

### v1.0 — Digital guide dog
- [ ] Cross-platform: macOS / Windows desktop app
- [ ] Mobile (Android + iOS)
- [ ] On-device SLM (no internet required)
- [ ] Multilingual narration

## Privacy

Drisha processes page content through the Claude API to generate descriptions. No data is stored, logged, or associated with a user identity. Page content is sent only at the moment of analysis and is not retained by Drisha or used for model training.

See our [Privacy Policy](#) for the full statement.

## Development

```bash
# Clone the repo
git clone https://github.com/drisha-ai/drisha.git
cd drisha

# Install dependencies
npm install

# Build the extension
npm run build

# Load in Chrome:
# chrome://extensions → Enable developer mode → Load unpacked → select /dist
```

Requires a Claude API key. Copy `.env.example` to `.env` and add your key:

```env
VITE_CLAUDE_API_KEY=your_key_here
```

## Contributing

Drisha is early-stage and contributions are very welcome, especially from people with lived experience of visual impairment.

Open an issue to discuss what you'd like to change. For accessibility feedback specifically — if you use a screen reader and find something broken — please open an issue with `[a11y]` in the title.

## License

MIT © 2026 Drisha — [help@drisha.ai](mailto:help@drisha.ai)