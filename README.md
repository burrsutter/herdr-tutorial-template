# Herdr tutorial template

A small public starter for learning to supervise Claude Code and Codex across several independent Git repositories in Herdr.

This repository deliberately contains no completed exercise implementation. Clone the same scaffold into four sibling folders: `hello`, `api`, `web`, and `batch`. Each clone has its own Git history. The tutorial assigns its role; the template does not select an account, install hooks, start agents, or install dependencies.

## Create the practice repositories

Prerequisites: Git 2.28+, Node.js 22.18.0+, npm, Python 3.11+, and the authenticated agent harnesses you intend to use. Herdr is installed separately.

Create the container folder (it may already exist and be empty):

```bash
mkdir -p "$HOME/ai-projects/herdr-tutorial-1"
```

Run each clone separately. Git refuses to overwrite a nonempty destination. If a destination already exists, inspect it before repeating a clone.

```bash
git clone --origin template https://github.com/burrsutter/herdr-tutorial-template.git "$HOME/ai-projects/herdr-tutorial-1/hello"
```

```bash
git clone --origin template https://github.com/burrsutter/herdr-tutorial-template.git "$HOME/ai-projects/herdr-tutorial-1/api"
```

```bash
git clone --origin template https://github.com/burrsutter/herdr-tutorial-template.git "$HOME/ai-projects/herdr-tutorial-1/web"
```

```bash
git clone --origin template https://github.com/burrsutter/herdr-tutorial-template.git "$HOME/ai-projects/herdr-tutorial-1/batch"
```

The remote is named `template`. If you later create a private practice repository, use `origin` for your own remote and explicitly push there. Do not push exercise solutions to this public source.

## Copy the lab notes

Copy these three supplied files from the hello clone into the container folder. Do this only for a new run; keep existing notes if resuming.

```bash
cp -n "$HOME/ai-projects/herdr-tutorial-1/hello/lab/.herdr-tutorial-lab" "$HOME/ai-projects/herdr-tutorial-1/"
```

```bash
cp -n "$HOME/ai-projects/herdr-tutorial-1/hello/lab/run-notes.md" "$HOME/ai-projects/herdr-tutorial-1/"
```

```bash
cp -n "$HOME/ai-projects/herdr-tutorial-1/hello/lab/queue.md" "$HOME/ai-projects/herdr-tutorial-1/"
```

`run-notes.md` records versions, starting template commit, checks, and results. `queue.md` is maintained by the human; it does not automatically dispatch work.

## Exercise roles

| Local clone | Stack | Work assigned by the tutorial |
| --- | --- | --- |
| hello | TypeScript on Node.js | A greeting function and Node tests |
| api | TypeScript on Node.js `node:http` | Health/products API; orders as a follow-up |
| web | Python standard library | Escaped HTML rendering of product data |
| batch | Python standard library | Product count and stock summary |

`src/` and `tests/` start empty apart from Git placeholders. The TypeScript exercises use a separate compiler check and Node's test runner. The Python exercises must add `tests/__init__.py` for discovery from the repository root. No packages or environments are installed by cloning.

The four clones initially contain the same scaffold. `lab/` contains reusable note templates, not another Git repository. The container folder itself is not a Git repository.

## Check and record the starting point

```bash
git -C "$HOME/ai-projects/herdr-tutorial-1/hello" rev-parse HEAD
```

Record that commit in your run notes. Before starting agents, check each clone's root path, branch, clean status, and `template` remote. Use the tutorial's one-writer / independent-reviewer workflow.

## Cleanup and another run

Save wanted results first. Stop only the named tutorial session. Move exactly `~/ai-projects/herdr-tutorial-1` to Trash, then create the folder and clone again. Keep daily projects, accounts, and tool installations. Removing local clones does not delete any private practice repositories you separately created on GitHub. Never delete `burrsutter/herdr-tutorial-template` as student cleanup.
