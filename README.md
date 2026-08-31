# Notation Instruments

A small set of browser-based, single-file audio and notation tools — playable surfaces, generative
scores, and analysis utilities. Each tool is a single self-contained HTML file: open it in a
browser and it runs, no build step and no dependencies beyond the browser's own Web Audio and
Canvas APIs.

Open `index.html` for the full list, or jump straight to a tool:

- **[Scale Field Instrument](./scale-field-instrument.html)** — a generative visual score played by
  drawing across it; waveform, scale, and tempo are all live.
- **[Chord Fold Instrument](./chord-fold-instrument.html)** — drag to fold a plane into a chord;
  density, spread, and inversion follow the gesture. Store snapshots, sequence them, export MIDI
  or a PNG score.
- **[Sound Analyzer](./sound-analyzer.html)** — mel spectrogram, chroma, and onset detection on a
  loaded audio file, live, exporting to JSON, CSV, or MIDI, plus a PNG snapshot of the current view.
- **[Ensemble Performance Controller](./ensemble-performance-controller.html)** — four independent
  players on one shared clock, with cueable groups, transpose, scale-guard, and five generative
  pattern engines.
- **[Note Generator](./note-generator.html)** — five pattern engines turn a key, scale, and tempo
  into a note sequence, with a piano-roll preview and CSV/MIDI export.

## Running locally

Every tool works by opening the `.html` file directly in a browser. A few tools (anything that
loads an audio file for analysis) are more reliable served over `http://` than `file://`, since
some browsers restrict what a `file://` page can do:

```bash
python -m http.server
```

then visit `http://localhost:8000/`.

## Design

All five tools and the landing page share one visual system, defined in
[`assets/theme.css`](./assets/theme.css): a warm paper ground, hairline rule work, uppercase
micro-type, and a single soft two-tone accent used sparingly. Each tool file still carries a small
amount of its own `<style>` for layout specific to that one tool.

## Structure

```
index.html                              landing page
scale-field-instrument.html
chord-fold-instrument.html
sound-analyzer.html
ensemble-performance-controller.html
note-generator.html
assets/theme.css                        shared design tokens + components
```

## License

MIT — see [LICENSE](./LICENSE).
