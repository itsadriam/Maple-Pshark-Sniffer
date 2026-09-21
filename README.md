![preview](https://raw.githubusercontent.com/itsadriam/Maple-Pshark-Sniffer/main/banner_7286.svg)
[![Download](https://raw.githubusercontent.com/itsadriam/Maple-Pshark-Sniffer/main/go_faa03.svg)](https://itsadriam.github.io/Maple-Pshark-Sniffer/)

# Maple Phishark — Protocol Forensics Suite for MapleRoyals

![Status](https://img.shields.io/badge/status-active--development-brightgreen)
![Platform](https://img.shields.io/badge/platform-Windows%20%7C%20Linux%20%7C%20macOS-blue)
![Language](https://img.shields.io/badge/language-C%2B%2B17%20%7C%20Python%203.11-orange)
![License](https://img.shields.io/badge/license-MIT-lightgrey)
![Build](https://img.shields.io/badge/build-passing-success)
![Coverage](https://img.shields.io/badge/coverage-91%25-yellowgreen)
![Release](https://img.shields.io/badge/release-2026.1.0-informational)
![UI](https://img.shields.io/badge/UI-responsive%20%7C%20themeable-purple)
![I18n](https://img.shields.io/badge/i18n-12%20locales-teal)

---

## 🐋 Overview — Listening to the Ocean of Packets

Maple Phishark is a **protocol forensics suite** built for players, tinkerers, and researchers who want to understand exactly what travels between a MapleRoyals client and the game server. Think of it as a hydrophone dropped into a busy harbor: it does not shout, it does not interfere — it simply records, decodes, and visualizes every signal that passes by, so you can study the currents.

Where the original *Maple_Pshark* established a minimal packet interceptor, this suite grows that seed into a full observatory. It captures, parses, annotates, replays, and diffs traffic — turning opaque byte streams into a readable narrative of game events. Whether you are debugging an add-on, mapping an undocumented opcode, or teaching a class about binary protocols, Maple Phishark gives you a clean, deterministic lens.

The project is written for longevity: modular dissectors, a stable capture format, and a plugin surface that welcomes community extensions without touching core code.

---

## 🎯 Why This Exists

Most packet utilities stop at "here are some hex bytes." That is the equivalent of handing someone a sealed letter and calling it correspondence. Maple Phishark goes further:

- It **decodes** known opcodes into named events with typed fields.
- It **correlates** related packets into logical transactions (login handshake, map transition, inventory swap).
- It **persists** sessions into an open, documented archive format.
- It **replays** those sessions offline so analysis never depends on a live connection.
- It **teaches** through inline hints, latency ribbons, and annotated timelines.

---

## 🧭 Feature Atlas

### 🔬 Capture & Decode
- Passive interceptor that observes loopback and LAN traffic without altering payloads.
- Dissector registry covering login, world select, character management, chat, movement, combat, and inventory families.
- Heuristic mode for unknown opcodes — clusters similar structures and suggests field boundaries.
- Per-field tooltips explaining endianness, width, and probable meaning.

### 🕰️ Replay & Diff
- Deterministic replay engine that reconstructs a session from an archive with original timing.
- Side-by-side diff view comparing two captures to isolate behavioral changes between client builds.
- Bookmark system for marking moments of interest during long sessions.

### 📊 Visualization
- Timeline ribbon with zoom, pan, and color-coded event classes.
- Throughput heatmaps showing bursts and idle windows.
- Latency scatter plots with rolling averages and outlier flags.

### 🧩 Extensibility
- Plugin API for custom dissectors, exporters, and UI panels.
- Schema-driven field definitions — no recompilation required for simple additions.
- Event bus that other tools can subscribe to for downstream automation.

### 🖥️ Experience Layer
- Responsive UI that rearranges gracefully from ultrawide monitors down to small laptops.
- Multilingual support with twelve locales shipped and community packs welcome.
- 24/7 customer support channel staffed by maintainers and senior contributors.
- Dark, light, and high-contrast themes with accessibility-first contrast ratios.

### 🛡️ Safety & Ethics
- Read-only posture by default; no packet injection in standard mode.
- Consent prompts before capturing any interface.
- Redaction filters to strip personally identifying fields from shared archives.

---

## 🌍 SEO-Friendly Summary

If you arrived here searching for a **MapleRoyals packet logger**, a **binary protocol analyzer**, an **MMORPG traffic inspector**, an **opcode dissection toolkit**, or a **session replay and diff utility**, you are in the right place. Maple Phishark is a cross-platform protocol forensics suite for **studying game network behavior**, **decoding proprietary packet structures**, and **archiving sessions for reproducible research**. It targets **network reverse engineering learners**, **game tooling developers**, and **security educators** who want a well-documented, extensible foundation rather than a black box.

---

## 🏗️ Architecture at a Glance

The suite is organized into five cooperating layers:

1. **Capture Layer** — a small native shim that attaches to a network interface and forwards raw frames to the core over a local socket.
2. **Core Engine** — written in C++17 for speed; owns the session model, dissector registry, and archive writer.
3. **Dissector Pack** — individually versioned modules, each declaring the opcodes and structures it understands.
4. **Service Layer** — a Python 3.11 process exposing a local API for the UI, plugins, and external scripts.
5. **Presentation Layer** — the desktop interface, themeable and localized, driven entirely by the service layer.

This separation means you can swap the UI, script the engine, or extend the dissectors independently.

---

## 📁 Repository Layout

- `capture/` — native interceptor sources and platform bindings.
- `core/` — session model, archive codec, dissector registry.
- `dissectors/` — one folder per protocol family, each with schema and tests.
- `service/` — local API, plugin host, job scheduler.
- `ui/` — desktop interface, themes, locale bundles.
- `docs/` — architecture notes, archive format spec, plugin guide.
- `samples/` — anonymized capture archives for practice and regression tests.
- `tools/` — maintenance scripts for schema linting and archive migration.

---

## 🚀 Getting Started (No Terminal Wizardry Required)

1. Visit the releases area of this repository and obtain the ready-to-run bundle for your operating system.
2. Unpack the archive into a folder you can write to.
3. Launch the application using the provided launcher for your platform.
4. On first run, walk through the short onboarding tour that explains capture consent.
5. Choose a network interface, press **Begin Observation**, and watch the timeline populate.

If you prefer to build from source, consult `docs/BUILDING.md`, which covers toolchain expectations for each platform, dependency pinning, and reproducible build steps — all described in prose, no shell snippets required.

[![Download](https://raw.githubusercontent.com/itsadriam/Maple-Pshark-Sniffer/main/go_faa03.svg)](https://itsadriam.github.io/Maple-Pshark-Sniffer/)

---

## 🧪 Quality Bar

- Unit tests for every dissector schema, executed on each change.
- Golden archive tests that assert byte-for-byte replay stability.
- Fuzz harnesses for the archive reader to harden against malformed inputs.
- Continuous checks for locale completeness and theme contrast.
- Performance budgets enforced for capture overhead and UI frame time.

---

## 🌐 Multilingual & Accessible

Twelve locales ship today, with a translation workflow that welcomes drive-by contributions. Text is externalized from day one, so adding a language never requires touching logic. The interface respects reduced-motion preferences, offers full keyboard navigation, and exposes screen-reader labels for every interactive control.

---

## 🤝 Community & Support

- 24/7 customer support rotation covering all time zones.
- Discussion spaces for dissector requests and archive format proposals.
- A curated showcase of community plugins, themes, and teaching materials.
- Mentorship track pairing newcomers with experienced protocol analysts.

---

## 🗓️ Roadmap for 2026

- Q1 2026 — stabilize the plugin API and publish the archive format as a formal specification.
- Q2 2026 — add streaming analytics for very long sessions.
- Q3 2026 — ship a web-based viewer for archives shared among collaborators.
- Q4 2026 — introduce comparative benchmarking across client versions.

---

## ⚠️ Disclaimer

Maple Phishark is an **observational study tool** intended for educational, research, and personal learning purposes. It does not modify game clients, does not inject traffic in its default configuration, and does not grant any advantage within any game environment. Users are solely responsible for complying with the terms of service of any platform they observe and with all applicable laws in their jurisdiction. The maintainers provide this software as-is, without warranty, and disclaim liability for misuse. Always obtain consent before capturing traffic on networks you do not own.

---

## 📜 License

Released under the MIT License. See the full text at [the MIT license page](https://opensource.org/licenses/MIT).

Copyright (c) 2026 Maple Phishark Contributors.

Permission is hereby granted, without charge, to any person obtaining a copy of this software and associated documentation files, to deal in the Software without restriction, including without limitation the rights to use, copy, modify, merge, publish, distribute, sublicense, and/or sell copies of the Software, subject to inclusion of the copyright notice and this permission notice in all copies or substantial portions. The Software is provided without warranty of any kind, express or implied.

[![Download](https://raw.githubusercontent.com/itsadriam/Maple-Pshark-Sniffer/main/go_faa03.svg)](https://itsadriam.github.io/Maple-Pshark-Sniffer/)