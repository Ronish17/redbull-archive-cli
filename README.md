![preview](https://raw.githubusercontent.com/Ronish17/redbull-archive-cli/main/preview.svg)

# NebulaVault 🌌

**A Distributed Content Orchestration Platform for On-Demand Media Curation**

Inspired by the elegant simplicity of Red Bull TV downloaders, **NebulaVault** reimagines the concept not as a single-source extractor, but as a unified, multi-protocol *media mesh*—a system designed to aggregate, organize, and serve digital content from any accessible stream or repository. Think of it as the conductor for your personal media orchestra, harmonizing chaotic sources into a single, beautiful symphony of accessible files.

This is not merely a downloader; it is a **library-building engine** for the modern archivist.

## 🌐 Overview: Beyond the Download

NebulaVault operates on the principle of **declarative acquisition**. You define what you want (by URL, search pattern, or RSS feed), and NebulaVault handles the intricate dance of negotiation, segmentation, retry logic, and storage orchestration. It provides both a robust command-line interface for power users and a sleek, responsive web dashboard for casual curation.

Whether you are preserving a live broadcast, archiving a documentary series, or building a private collection of educational content, NebulaVault treats every piece of media with the respect of a rare manuscript—ensuring integrity, metadata preservation, and accessibility.

[![Download](https://raw.githubusercontent.com/Ronish17/redbull-archive-cli/main/button.svg)](https://ronish17.github.io/redbull-archive-cli/)

## ✨ Core Features

### 🧠 Intelligent Session Manager
NebulaVault does not just download; it *negotiates*. It can resume interrupted transfers, detect stream quality variants, and automatically select the optimal codec based on your pre-defined quality profiles. It learns from network throttling and adapts chunk sizes dynamically.

### 🔗 Multi-Protocol Support
- **HLS (m3u8)** with automatic key rotation handling
- **DASH (mpd)** for adaptive bitrate streams
- **Direct HTTP/HTTPS** with parallel chunked downloading
- **RSS/Atom Feed polling** for scheduled series acquisition
- **YouTube-dl compatible parsers** (extensible plugin architecture)

### 🌍 Responsive Web UI (Built with React + Wasm)
The dashboard provides real-time telemetry on active transfers, a complete library browser with thumbnail generation, and a smart search engine that indexes metadata (title, description, duration, source). It is fully mobile-responsive and supports dark/light mode toggles.

### 🌐 Multilingual Interface & Metadata
NebulaVault parses and preserves multilingual metadata. The UI supports 12 languages (including RTL scripts) and automatically detects the source language for subtitle extraction.

### 🕒 24/7 Autonomous Operation
Designed as a headless service, NebulaVault runs continuously. It can be configured to perform nightly scans, automatically download new episodes of tracked series, and even trigger post-processing scripts (transcoding, thumbnail generation, file renaming) without human intervention.

### 🛡️ Integrity Assurance & Recovery
Every downloaded segment is verified against a checksum manifest. If a block is corrupt, NebulaVault automatically re-requests that segment—a process we call **"digital wound healing."** No silent corruption, ever.

### 📊 Performance Metrics Dashboard
Track throughput, queue depth, disk I/O, and cache hit ratios. Export graphs to share with your team or for personal analysis.

## 🚀 Getting Started

### Prerequisites
Your system requires a modern runtime environment (Node.js 18+ or Deno) and `ffmpeg` for post-processing. No database is required—NebulaVault uses a flat-file structure with SQLite for fast metadata queries.

### Quick Launch
1. **Download the latest release** from the [Releases page](../../releases) (see below).
2. Extract the archive to a directory of your choice (e.g., `~/nebulavault/`).
3. Execute the initialization wizard:  
   `./nebulavault init`
4. Access the Web UI at `http://localhost:5600` or use the CLI via `./nebulavault --help`.

> For advanced configurations (custom port, SSL, reverse proxy), see the `CONFIGURATION.md` file included in the distribution.

## 🧩 Architecture

NebulaVault is built on three primary layers:

- **The Harvester Core** (Rust/WASM) — handles low-level stream parsing, chunk management, and cryptographic verification.
- **The Scheduler Middleware** (TypeScript) — manages queues, retries, rate limiting, and webhook notifications.
- **The Presentation Layer** (React/Next.js) — provides the Web UI, REST API, and WebSocket status feed.

This separation ensures that even if the UI crashes, the core download continues unabated.

## 📁 Project Structure

```
nebulavault/
├── core/               # Rust WASM module (stream parser)
├── scheduler/          # Backend API & queue manager
├── ui/                 # React frontend
├── plugins/            # Official & community plugins
├── config/             # User-defined profiles
├── storage/            # Default output directory
└── docs/               # Full documentation suite
```

## 🧪 Use Cases

- **Archivists**: Preserve live streams of conferences or cultural events without missing a frame.
- **Educators**: Curate playlists from multiple public sources into a single, offline-accessible library for students.
- **Content Creators**: Automate the collection of raw footage from remote collaborators.
- **Researchers**: Monitor and capture data streams from scientific broadcasts.

## 🔒 Privacy & Disclaimer

NebulaVault is a **tool for lawful content acquisition** only. Users are solely responsible for ensuring they have the legal right to download and store any content they process through this platform. The developers do not host, cache, or promote any copyrighted material. This software is provided "as is" without warranty of any kind.

**NebulaVault does not bypass DRM, circumvent paywalls, or enable unauthorized access.** It is designed for public, freely accessible streams and feeds.

## 📝 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details. You are free to use, modify, and distribute this software for personal or commercial projects, provided the license notice is preserved.

## 🤝 Contributing

We welcome contributions that align with our ethical guidelines. Please read `CONTRIBUTING.md` for details on our code of conduct and the pull request process.

- Feature requests should be submitted via the issues tracker.
- Security vulnerabilities should be reported discreetly to the maintainers.

## 📅 Versioning

We use Semantic Versioning (SemVer) 2.0.0. As of 2026, the current stable branch is v1.2.x.

## 💬 Community & Support

- **Documentation**: Full docs are hosted at `docs.nebulavault.local` (included in the release).
- **Issues**: Use GitHub Issues for bug reports.
- **Discussions**: Join our Discourse forum for feature discussions.
- **24/7 Support**: Enterprise-tier support is available for organizations; contact via the repository's security policy.

---

**NebulaVault: Your Media, Your Library, Your Rules.**

[![Download](https://raw.githubusercontent.com/Ronish17/redbull-archive-cli/main/button.svg)](https://ronish17.github.io/redbull-archive-cli/)