# PatchSentinel — Automated guard for keeping systems patched and safe

---

## Table of Contents
1. [What is PatchSentinel?](#what-is-patchsentinel)
2. [Why is it needed?](#why-is-it-needed)
3. [How it works?](#how-it-works)
4. [Quick Start](#quick-start)
5. [Inside the Dev Container](#inside-the-dev-container)
6. [Handy Make Commands](#handy-make-commands)
7. [License](#license)

---

## What is PatchSentinel?
PatchSentinel is an **event-driven vulnerability-remediation framework** built on top of [StackStorm](https://stackstorm.com).
It keeps an eye on security feeds (like CVE announcements), decides *what actually matters*, and then triggers the right automation to patch or mitigate the issue—before it becomes a headache.

---

## Why is it needed?

| Pain | PatchSentinel’s Fix |
|---------|-----------------------|
| **Too many CVEs** to track manually | Automatically filters the noise and highlights what affects the fleet |
| **Slow patch cycles** under pressure | Kicks off remediation the moment a risk is spotted |
| **Fragmented tooling** across teams | Central hub using StackStorm actions that can be chained or extended. |

---

## How it works?

1. **Listen:** Sensors watch RSS feeds, APIs, and email lists for new vulnerability news.  
2. **Decide:** Rules check each alert against the asset inventory.  
3. **Act:** Pre-built or custom workflows apply patches, open tickets, or roll out config changes.  
4. **Report:** Slack/Teams updates and a full audit trail in StackStorm.

If one can write a shell script or an Ansible playbook, they can teach PatchSentinel to run at the perfect moment.

---

## Quick Start

```bash
# 1) Clone the repo
git clone https://github.com/Anjali-Khantaal/patchsentinel.git
cd patchsentinel

# 2) Build and enter the Dev Container (VS Code required)
make dev

# 3) Once the container is ready:
make lint   # style checks (ruff + flake8)
make test   # # run the unit tests
```
---

## Inside the Dev Container
The container ships with:
| Tool | Version (at build time) |
|---------|-----------------------|
| Python | 3.11 |
| Node | 18 |
| StackStorm CLI | latest PyPI |
| kind | v0.23.0 |
| Helm | 3.x |
| yq | 4.x |

---

## Handy Make Commands

| Command         | What it does                                           |
| --------------- | ------------------------------------------------------ |
| `make dev`      | Build & attach to the Dev Container.                   |
| `make lint`     | Run ruff + flake8 on the codebase.                     |
| `make test`     | Execute pytest test suite.                             |
| `make kind-lab` | Spin up a local Kubernetes cluster named **patchlab**. |
| `make clean`    | Tear down *patchlab* and remove build artefacts.       |

---

## License
PatchSentinel is released under the Apache License 2.0.
See [LICENSE](LICENSE) for the legal bits.


