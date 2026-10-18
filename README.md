<div align="center">

# 📡 Repo Radar

**Discover viral GitHub repositories before everyone else.**

[![Python](https://img.shields.io/badge/Python-3.9+-3776AB?style=for-the-badge&logo=python&logoColor=white)](https://python.org)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow?style=for-the-badge)](LICENSE)
[![Made in India](https://img.shields.io/badge/Made%20in-India-FF9933?style=for-the-badge)](https://en.wikipedia.org/wiki/India)

A tiny CLI that finds brand-new repos gaining stars fastest — the ones going **viral right now**.

</div>

---

## How it works

GitHub gives every repo a birth date and a star count. Repo Radar searches for
repos created in the last N days and ranks them by **stars per day of age** —
a simple velocity score that surfaces what the community is piling onto today.

## Install

```bash
git clone https://github.com/mehulpatel23b-pixel/repo-radar
cd repo-radar
pip install -r requirements.txt
```

## Usage

```bash
# Top viral repos from the last 7 days, all languages
python3 -m repo_radar.cli trending

# Viral Python repos only, last 30 days, top 50
python3 -m repo_radar.cli trending --lang python --days 30 --limit 50

# Generate a markdown report
python3 -m repo_radar.cli report --lang rust --days 14 -o VIRAL.md
```

Optional: set `GITHUB_TOKEN` in your environment for a higher API rate limit.

## Sample output

```
  1. someorg/some-repo — ⭐3,735 (Rust)
     Blazing-fast tool that does the thing everyone wanted
```

This repo also **self-updates**: a GitHub Action runs Repo Radar every week and
commits the freshest viral list to [VIRAL.md](VIRAL.md). The report writes itself.

## Project structure

```
src/repo_radar/
├── cli.py          # argparse CLI (trending / report)
├── github_api.py   # GitHub Search API wrapper
├── ranking.py      # stars-per-day viral score
└── report.py       # markdown report generator
tests/
└── test_ranking.py
```

## License

MIT — see [LICENSE](LICENSE).

---

<div align="center">Built by [@mehulpatel23b-pixel](https://github.com/mehulpatel23b-pixel)</div>
