# Day 1 Environment Record — inventory-platform

**Date verified:** 2026-09-19
**Machine:** Windows, PowerShell, VS Code

## Verified Tool Versions

| Tool           | Command used                        | Result                           | Baseline                                                  | Status                              |
| -------------- | ----------------------------------- | -------------------------------- | --------------------------------------------------------- | ----------------------------------- |
| Python         | `py -3.14 --version` (via Launcher) | 3.14.6                           | 3.14.7                                                    | PASS (one patch behind, acceptable) |
| pip            | `py -3.14 -m pip --version`         | 26.1.2                           | —                                                         | PASS                                |
| Java (JDK)     | `java -version`                     | OpenJDK 25.0.2 (Zulu LTS)        | 25.0.4.1                                                  | PASS (one patch behind, acceptable) |
| javac          | `javac -version`                    | 25.0.2                           | —                                                         | PASS (matches `java`)               |
| JAVA_HOME      | `$env:JAVA_HOME`                    | `C:\Program Files\Zulu\zulu-25\` | —                                                         | PASS (matches java/javac install)   |
| VS Code        | `code --version`                    | 1.137.0                          | 1.138                                                     | PASS (one minor behind, acceptable) |
| Git            | `git --version`                     | 2.49.0.windows.1                 | 2.55.0                                                    | PASS (behind, acceptable)           |
| Docker CLI     | `docker --version`                  | 29.3.1                           | 4.91.0 (Desktop app version — different numbering scheme) | PASS                                |
| Docker Compose | `docker compose version`            | v5.1.1                           | —                                                         | PASS                                |
| Docker Engine  | `docker ps` (empty table returned)  | Running                          | —                                                         | PASS                                |

## Notable Findings

- **Two Python installs coexist:** `python` on PATH resolves to 3.13.5; the Python Launcher (`py`) defaults to 3.14.6. Decision: leave PATH untouched, use `py -3.14` explicitly for all project work to avoid ambiguity.
- **Java, javac, and JAVA_HOME are all consistent**, pointing to the same Zulu 25.0.2 install — no fix needed.
- **Docker Engine confirmed running**, not just the CLI installed — verified via `docker ps` returning a valid (empty) table rather than a connection error.

## Reproducing This Environment

1. Install Python 3.14.x (Launcher: `py -3.14`)
2. Install JDK 25.x (Zulu build used here; any OpenJDK 25 distribution is compatible)
3. Install VS Code 1.13x+
4. Install Git 2.4x+
5. Install Docker Desktop (includes Engine + Compose)
6. Verify each with the commands in the table above
