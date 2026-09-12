# Beads Setup and Workflow Playbook for dam

Personal issue tracking with cross-machine synchronization via Dolt and GitHub.

## Setup Summary

- **Backend:** Dolt (embedded mode, in-process database)
- **Issue prefix:** `dam-` (e.g., `dam-a3f2dd`)
- **Sync remote:** `git+ssh://git@github.com/life-itself/dam.git`
- **Database:** Stored in `.beads/embeddeddolt/`
- **Hooks:** Configured in `.beads/hooks/` with Git `core.hooksPath`

### Auto-sync Configuration

- **Auto-export:** Enabled. JSONL export (`.beads/issues.jsonl`) updates on issue changes for interchange and viewers.
- **Dolt remote:** GitHub origin (SSH). Provides actual cross-machine sync mechanism, not JSONL import/export.
- **Git hooks:** 
  - `post-merge`: Auto-pulls Dolt database after git pull
  - `post-checkout`: Auto-pulls Dolt on branch switch/clone update
  - `pre-push`: Starts background `bd dolt push` to `.beads/dolt-push.log`

## Normal Workflow

### Start of Session

```bash
git pull
bd dolt pull
bd status
```

### Create and Work on Issues

```bash
bd ready              # Show ready-to-work status
bd create "Issue title here"      # Create new issue
bd list               # List all issues
bd update dam-abc123 --claim      # Claim an issue
bd update dam-abc123 --status "in progress"
```

### End of Session

```bash
bd dolt push          # Wait for explicit confirmation that Dolt push completed
git add -A
git commit -m "Describe the work"
git push              # Git push triggers background Dolt push via pre-push hook
```

The explicit `bd dolt push` before git operations ensures deterministic sync state, especially important for session handoff.

## Fresh Clone or New Machine

```bash
git clone git@github.com:life-itself/dam.git
cd dam
bd doctor             # Check setup
bd dolt remote list   # Verify remote
bd dolt pull          # Pull database from remote
bd status             # Verify issue count matches expectations
```

If database is not initialized:

```bash
bd bootstrap
bd dolt pull
```

## Troubleshooting Sync

### Check State Without Changes

```bash
bd context
bd dolt remote list
bd dolt status
git status --short --branch
```

### Sync Not Working

```bash
git pull
bd dolt pull
bd dolt push
```

If both machines changed Beads concurrently, let Dolt report conflicts and resolve through the Beads/Dolt workflow. Do NOT delete `.beads/`, remove the remote, or reinitialize with force as a first response.

### Offline

Continue working locally. Failed hooks should not block Git operations. Synchronize with `bd dolt pull` and `bd dolt push` when connectivity returns.

## Git and Beads Interaction

- `.beads/config.yaml` and `.beads/metadata.json` are tracked by Git
- `.beads/issues.jsonl` is tracked by Git (auto-export for interchange)
- `.beads/embeddeddolt/` is ignored (machine-local Dolt database)
- `.beads/dolt-push.log` is ignored (background push log)
- `.beads/.auto-import-issues.jsonl` is ignored (runtime staging file)
- All other Dolt runtime files (sockets, locks, state) are ignored

## Reference

For detailed troubleshooting and advanced workflows, see:
- https://github.com/life-itself/dam/tree/main/.beads (Beads config)
- `bd --help`, `bd quickstart`, `bd config --help`
- Parent playbook: https://github.com/rufuspollock/agent-skills/blob/main/beads-sync-playbook.md
