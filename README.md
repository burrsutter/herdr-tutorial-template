# Herdr tutorial template

A public starter for learning to supervise Claude Code and Codex in Herdr. Start with one standalone Hello World repository. Add the multi-project exercise only after completing Hello World.

The scaffold contains empty source/test folders, instructions, and reusable notes. It includes no completed exercise implementation. Cloning does not install tools or dependencies, select accounts, install hooks, or start agents.

## Part 1: standalone Hello World

Prerequisites: Git 2.28+, Node.js 22.18.0+, npm, Herdr, and the authenticated Claude Code/Codex launchers you intend to use. Hello World uses TypeScript on Node.js; it does not require Python or the API/web/batch repositories.

Create the container folder:

```bash
mkdir -p "$HOME/ai-projects/herdr-tutorial-1"
```

Clone only hello. Git refuses to overwrite a nonempty destination; inspect existing work before repeating a clone.

```bash
git clone --origin template https://github.com/burrsutter/herdr-tutorial-template.git "$HOME/ai-projects/herdr-tutorial-1/hello"
```

```text
~/ai-projects/herdr-tutorial-1/
└── hello/    # independent Git repository
```

Copy the two supplied hello support files into the parent folder. The marker identifies the practice folder during cleanup; the run log records versions, tests, review, and the accepted commit. `-n` preserves existing destination files when resuming.

```bash
cp -n "$HOME/ai-projects/herdr-tutorial-1/hello/lab/.herdr-tutorial-lab" "$HOME/ai-projects/herdr-tutorial-1/"
```

```bash
cp -n "$HOME/ai-projects/herdr-tutorial-1/hello/lab/run-notes.md" "$HOME/ai-projects/herdr-tutorial-1/"
```

Record the initial template revision:

```bash
git -C "$HOME/ai-projects/herdr-tutorial-1/hello" rev-parse HEAD
```

Follow the instructor's Hello World lesson: implement the TypeScript greeting with Claude, verify the compiler and Node tests, review with Codex, and accept/commit the result. Confirm the greeting prints `Hello, Burr!`, the working tree is clean, and detach/reattach works. Record the evidence in `run-notes.md`.

**This completes the standalone route. You can stop and clean up here.** The worker queue, Python exercises, and additional repositories below belong to the optional advanced route.

## Part 2: advanced multi-project exercise

Complete Hello World first. Keep the accepted hello repository. Additional prerequisites: Python 3.11+ and curl, with no pip packages or virtual environment needed for the standard-library exercises.

Clone the three additional repositories separately:

```bash
git clone --origin template https://github.com/burrsutter/herdr-tutorial-template.git "$HOME/ai-projects/herdr-tutorial-1/api"
```

```bash
git clone --origin template https://github.com/burrsutter/herdr-tutorial-template.git "$HOME/ai-projects/herdr-tutorial-1/web"
```

```bash
git clone --origin template https://github.com/burrsutter/herdr-tutorial-template.git "$HOME/ai-projects/herdr-tutorial-1/batch"
```

```text
~/ai-projects/herdr-tutorial-1/
├── .herdr-tutorial-lab
├── run-notes.md
├── hello/    # completed and accepted
├── api/      # new independent Git clone
├── web/      # new independent Git clone
└── batch/    # new independent Git clone
```

Now add the shared worker queue:

```bash
cp -n "$HOME/ai-projects/herdr-tutorial-1/hello/lab/queue.md" "$HOME/ai-projects/herdr-tutorial-1/"
```

Open `queue.md` beside Herdr's sidebar. Mark hello accepted and use the remaining rows for the advanced workers. The human updates this file; it does not automatically dispatch tasks. Record each new clone's starting revision. Hello's HEAD now includes your completed work and can differ from the new clones.

| Advanced clone | Stack | Work assigned by the tutorial |
| --- | --- | --- |
| api | TypeScript on Node.js `node:http` | Health/products API; orders as a follow-up |
| web | Python standard library | Escaped HTML rendering of product data |
| batch | Python standard library | Product count and stock summary |

`src/` and `tests/` start empty apart from Git placeholders. TypeScript exercises use a separate compiler check and Node's test runner. Python exercises must add `tests/__init__.py` for root-level discovery.

## Source remote and optional publication

Each clone is independent and starts with the same scaffold. The container folder itself is not a Git repository. `lab/` holds reusable note templates.

The public source remote is named `template`. If you later create a private practice repository, use `origin` for your own remote and explicitly push there. Publish only the repos you completed; Hello World alone needs just a private hello copy if you choose to publish. Do not push exercise solutions to this public source.

## Cleanup and another run

Save wanted results first. Stop only the named tutorial session. Move exactly `~/ai-projects/herdr-tutorial-1` to Trash, then create the folder and start with the hello clone again. Keep daily projects, accounts, and tool installations. After Hello World alone, api/web/batch need not exist.

Removing local clones does not delete any private practice repositories you separately created on GitHub. Delete only copies you actually created. Never delete the reusable `burrsutter/herdr-tutorial-template` source as student cleanup.
