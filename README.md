# Scripture Wordlinks Analyzer

This repository contains the complete **Scripture Wordlinks Analyzer** skill for Grok.

## Overview

A powerful, multi-layered skill for deep literary, lexical, historical-etymological, and quantitative analysis of scriptures. It supports:

- Gileadi-style word links and lexical core analysis
- 1828 Webster's Dictionary + Early Modern English insights
- Deeper etymology and original-language roots
- **Cluster Density Scoring** (primary quality metric)
- Scripture-Defined Symbolic Meanings
- Chiasmus detection (presence + absence)
- Hebrew Gematria
- Semitic Paronomasia & Wordplay
- Covenant Language Density + Thematic Polarity Scoring
- Temple symbolism and imagery clusters
- Integration of user-provided tagged lists (with ★ markers) and GitHub-backed data

It is designed for comprehensive analysis across the Bible, Book of Mormon, Doctrine and Covenants, Pearl of Great Price, Apocrypha, 1 Enoch, and related ancient texts.

## Installation (for Warp terminal or Grok environments)

This skill is designed to be installed using the `skill-installer` script available in Grok's bundled skills.

### Method 1: Using the install script (recommended)

```bash
# Ensure the skill-installer script is available (from /root/.grok/skills/skill-installer/scripts/ or in your PATH)
install-skill.sh --repo EzrasEagle/scripture-wordlinks-analyzer --path scripture-wordlinks-analyzer
```

Or using the full URL:

```bash
install-skill.sh --url https://github.com/EzrasEagle/scripture-wordlinks-analyzer/tree/main/scripture-wordlinks-analyzer
```

This downloads the skill zip and installs it directly into your `.grok/skills/scripture-wordlinks-analyzer/` directory.

### Method 2: Manual clone and copy

```bash
git clone https://github.com/EzrasEagle/scripture-wordlinks-analyzer.git
cp -r scripture-wordlinks-analyzer /path/to/your/.grok/skills/
```

## Usage

Once installed and activated in your Grok instance, this skill will automatically engage for queries involving scripture analysis, word links, intertextual connections, chiasmus, gematria, paronomasia, temple themes, and related deep study.

It follows a precise 13-step multi-layer procedure and outputs structured Markdown with tables, quantitative scores (Cluster Density High/Medium/Low), evidence grading, and comprehensive notes.

Full details, activation triggers, step-by-step instructions, output format requirements, and advanced module integration notes are in `scripture-wordlinks-analyzer/SKILL.md`.

## Companion Data & Modules Repository

For complete advanced features (full Python implementations of gematria calculator, chiasmus detector, morphology loader, paronomasia detector, temple symbolism module, sample tagged data, and processing scripts), clone the companion repository:

**https://github.com/EzrasEagle/scripture-wordlinks**

Place or symlink the modules so they are importable during `code_execution` tool use for heavy lifting.

## How to Download / Install for Warp or Local Grok Setup

- Use the `install-skill.sh` script as shown above (ideal for Warp terminal workflows or automated setups).
- The script handles authentication if needed for private repos (though this one is public) and places the skill correctly.
- After installation, the skill is ready to use immediately—no restart required in most Grok configurations.

## License & Attribution

Provided as an open skill definition for the Grok extensible agent/skill ecosystem. Feel free to fork, extend, or adapt the analysis methodology.

---

*This upload makes the skill easily downloadable and installable for users working in Warp terminals, local Grok instances, or any environment supporting the skill-installer.*