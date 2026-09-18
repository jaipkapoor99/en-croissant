<br />
<div align="center">
  <a href="https://github.com/jaipkapoor99/en-croissant">
    <img width="120" height="120" src="src-tauri/icons/icon.png" alt="En Croissant 2.0 Logo">
  </a>

<h1 align="center">En Croissant 2.0</h1>

  <p align="center">
    <strong>The Ultimate Modern Chess Toolkit & Database</strong>
    <br />
    Maintained and developed by <a href="https://github.com/jaipkapoor99"><strong>Jai Kapoor (@jaipkapoor99)</strong></a>
    <br />
    <br />
    <a href="https://github.com/jaipkapoor99/en-croissant/releases"><strong>Download Releases</strong></a>
    ·
    <a href="https://github.com/jaipkapoor99/en-croissant/issues"><strong>Report Bug</strong></a>
    ·
    <a href="https://github.com/jaipkapoor99/en-croissant/issues"><strong>Request Feature</strong></a>
  </p>
</div>

---

**En Croissant 2.0** is an open-source, cross-platform chess GUI and database toolkit designed for speed, flexibility, and deep analysis. Built with Rust, Tauri 2, and React 19, it provides tournament players, Grandmasters, and chess enthusiasts with the most powerful free analysis workbench available.

> [!IMPORTANT]
> **Platform Compatibility Note**: Currently, this repository is only working and supported on **Linux**. It is not working on **Windows**, and compatibility on **macOS** is currently unverified.

---

## ⚡ What's New in Version 2.0

- 🏎️ **Zero-Allocation Bitwise Tree Hashing**: Custom fast 32-bit state hashing with 0 heap string allocations—delivering **26.1% faster repertoire and tree operations**.
- 🖥️ **Live System Hardware Configs & Auto-Discovery**: Real-time detection of CPU (cores and threads), GPU model, VRAM, and total/available system RAM with automatic optimal thread and hash sizing.
- 📁 **Zero-Friction App Directory Storage**: All saved games, engine match series, imported engine binaries, and avatars are automatically mirrored and organized within the app directory—no annoying file-picker save dialogs.
- ⚔️ **Consolidated Engine Match Series**: Play multi-game engine matches (up to 100 games) saved as unified multi-game PGN series files, with graceful match abortion that preserves only completed rounds.
- 📚 **Precompiled High-Density Binary Opening Database**: Replaced legacy loose TSV tables with an ultra-compact zstd-compressed binary opening book (3,641 lines in 78 KB) with sub-millisecond lookup and zero build-time overhead.
- 🎲 **Algorithmic Fischer Random (Chess960)**: Mathematical FRC position generator supporting all 960 positions with zero static lookup tables.
- 💾 **Unified Global Syzygy Tablebases**: Configure your 3–7 piece Syzygy endgame tablebase directory once; En Croissant 2.0 automatically propagates and wires it to all supported UCI engines with single-click master toggling.
- 🧠 **High-Performance Memory & Database Layer**: Integrated `mimalloc` high-performance global memory allocator in Rust and tuned SQLite database pragmas for ultra-responsive games indexing.
- 📦 **Modernized 2026 Tech Stack**: Upgraded to **React 19**, **Vite 8**, **Tauri 2.11**, **TanStack Router 1.170**, **Jotai 2.20**, and **Zustand 5**, trimming client entry bundle size by **17.6%**.

---

## 🌟 Core Features

- ♟️ **Multi-Engine UCI Analysis**: Run local engines (Stockfish 17+, Berserk, Koivisto, Lc0, etc.) and cloud engines (ChessDB) concurrently with multi-PV and evaluation graphs.
- 📖 **Repertoire Training**: Build opening repertoires and master lines using spaced repetition learning.
- 📊 **Database Management**: Import, filter, and inspect millions of games in PGN format with exact or partial position search.
- 🌐 **Lichess & Chess.com Sync**: Seamlessly fetch user games, fide rating cards, and personal statistics.
- 🎯 **Syzygy Endgame Tablebases**: Instant tablebase lookups with DTZ (Distance to Zero) and WDL (Win-Draw-Loss) calculations.
- 🎨 **Deep Customization**: High-resolution piece sets, custom boards, interactive arrows/annotations, and exportable game charts.

---

## 💾 Syzygy Endgame Tablebases (Download & Setup)

To enable offline, instant, and perfect endgame evaluations up to 7 pieces, you can download the Syzygy tablebases using the open-source **[Syzygy-Tablebase-Downloader](https://github.com/jj-jaguar/Syzygy-Tablebase-Downloader)**.

> **Beginners Guide**: If you are just getting started, download the **3-4-5 piece tablebases** (approx. 1 GB total)—this covers the vast majority of practical endgame positions without taking up heavy disk space (6-piece is ~150 GB, 7-piece is ~18 TB).

> ⚡ **Faster Download**: In the downloader tool, make sure to select the **`sesse`** mirror option, as it is significantly faster and provides superior throughput compared to standard mirrors.

### Setting Up in En Croissant 2.0:

1. Open **En Croissant 2.0** and navigate to the **Engines** page.
2. Under the **Syzygy Endgame Tablebases** section at the top, click **Select Folder** and choose the directory containing your downloaded tablebase files (`.rtbw` / `.rtbz`).
3. En Croissant 2.0 will automatically configure and link your tablebases to all supported engines (Stockfish, Berserk, Koivisto, etc.) in a single click!

---

## 🛠️ Building from Source

### Prerequisites

- [Node.js](https://nodejs.org/) (v20+ recommended)
- [pnpm](https://pnpm.io/) (`npm install -g pnpm`)
- [Rust](https://rustup.rs/) (latest stable toolchain)
- Platform-specific Tauri prerequisites (see [Tauri Prerequisites](https://tauri.app/start/prerequisites/))

### Build Steps

```bash
# Clone the repository
git clone https://github.com/jaipkapoor99/en-croissant.git
cd en-croissant

# Install frontend dependencies
pnpm install

# Run in development mode
pnpm dev

# Build production executable
pnpm build
```

Production binaries will be compiled to `src-tauri/target/release/`.

---

## 🧪 Testing & Code Quality

```bash
# Run unit tests
pnpm test

# Check linting
pnpm lint

# Format code
pnpm format
```

---

## 🤝 Call for Contributors & UI/UX Designers

En Croissant 2.0 is actively seeking passionate contributors to help build the future of open-source chess software!

While we have significantly overhauled the core performance, data structures, backend memory allocators, and tablebase infrastructure, **there remains immense scope for further optimization, design modernization, and polish**.

We especially invite:

- 🎨 **UI / UX Designers**: Modernizing application themes, board styling, evaluation indicators, mobile/responsive layout improvements, and design system harmonization.
- ⚡ **Performance Engineers & Rust Developers**: Low-level UCI optimizations, lock-free concurrency, database search speedups, and SIMD-accelerated chess data processing.
- 💻 **Frontend Developers (React / TypeScript / Vite / Mantine)**: Panel ergonomics, keybinding customization, analysis tooling, and accessibility improvements.
- 🌍 **Translators & Localization Specialists**: Expanding and perfecting internationalization coverage across all supported languages.

If you are interested in contributing, check out the [Contributing Guide](./CONTRIBUTING.md) or open an [Issue / Discussion](https://github.com/jaipkapoor99/en-croissant/issues) to share ideas, mockups, or PRs!

---

## 👤 Author & Maintainer

**Jai Kapoor**

- GitHub: [@jaipkapoor99](https://github.com/jaipkapoor99)
- Repository: [https://github.com/jaipkapoor99/en-croissant](https://github.com/jaipkapoor99/en-croissant)

_Based on original foundational work by Francisco Salgueiro._

---

## 📜 License

This project is licensed under the **GNU General Public License v3.0 (GPL-3.0)**. See the [LICENSE](LICENSE) file for details.
