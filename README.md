<h1 align="center">Moonfin for Roku (Gelato)</h1>

---

A fork of [Moonfin for Roku](https://github.com/Moonfin-Client/Roku) that adds support for [Gelato](https://github.com/lostb1t/Gelato)

## Gelato Features

### Version Picker
Items with more than one source get a Versions button. Each source shows on three lines:

```
4K UHD · Ready
S1 E1-13 · EN/IT · Atmos 7.1 · BluRay DV
62.5 GB · 54.8 Mbps · RARBG · Torrentio
```

### Smart Play
- Picks the best source automatically: a local file if there is one, otherwise the highest-quality cached source
- Override the choice any time from the Versions picker

### Add from Search
- Selecting a movie or show in Search tells Gelato to add it
- Shows an "Added" confirmation instead of opening a half-loaded page

## Configuring Stream Labels

The picker reads the emoji tags AIOStreams writes into each source name, and is set up for the default AIOStreams templates out of the box.

To match a different AIOStreams setup, edit `gelatoStreamFormatConfig()` in `source/utils/gelato.bs`:

```brightscript
fields: {
    seasons:      "🍂",
    episodes:     "🎞️",
    languages:    "🗣️",
    audio:        "🎧",
    channels:     "🔊",
    quality:      "🎥",
    visualTags:   "📺",
    size:         "📦",
    bitrate:      "📊",
    releaseGroup: "🏷️",
    indexer:      "📡"
}
```

- `readyMarker` (⚡) and `notReadyMarker` (❌) set how a cached source is detected
- `languageFlags` maps flag emoji to short codes
- Resolution is read from the text, so any resolution emoji works

## Building from Source

```bash
npm install
npm run build
```

Sideload the zip from `out/`. Full install steps are in the [Moonfin README](https://github.com/Moonfin-Client/Roku#installation).

## Credits

- **[Moonfin for Roku](https://github.com/Moonfin-Client/Roku)** - making a better Roku client
- **[Gelato](https://github.com/lostb1t/Gelato)** - streaming source integration
- **[AIOStreams](https://github.com/Viren070/AIOStreams)** - stream aggregation

---
