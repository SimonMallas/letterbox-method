# Starter kit — the newest seat's first hour

For the person setting up a new seat to edit. Every line below cost time in a
first hour; the fix is placement, not new prose volume.

## Before you install anything

1. Run `letterbox --version` and `alb --version` first. A machine can
   have stray checkouts and private venvs; whatever is on PATH
   may be older than what other agents run. Install fresh
   (installer / pipx), then check again.
2. Your existing cmux panes will not be moved. Letterbox setup
   changes no layout; the Bridge needs one workspace of its own
   for its resident process. That is normal.

## Letterbox, in order

1. Install, then `letterbox cmux setup --agents <you>
   --automatic-doorbells`, then `source ~/.agent-letterbox/env.sh`.
2. From YOUR pane: `letterbox cmux register <you>`. Registration
   names the pane for the doorbell only. Your shell commands also
   need `export LETTERBOX_AGENT=<you>` or every verb refuses you.
3. `letterbox check` — empty is a passing result.

## Bridge, in order

The Bridge is an optional add-on — the person running this seat has either
already set it up or not. If it's there, the human's chat messages arrive as
letters. If not, nothing is missing: the Letterbox stands alone, and the
Bridge can be added later without touching anything you've built.

1. Integrated mode (you already have a Letterbox): mailbox is
   `~/.agent-letterbox/<you>`, participant `<you>`. Never the
   Letterbox root itself; the Bridge refuses it.
2. Token goes in a mode-600 file, passed with `--token-file`.
   Setup consumes (deletes) that file on purpose and stores the
   token in `bridge.env` (0600). Deletion is the design working.
3. Allowlist: choose `read` and give YOUR user ID. Setup resolves
   your DM pair. A deny-all allowlist is silent, not broken:
   `alb --doctor --root ~/.alb-<you>` tells you which you have.
4. Start: the wizard asks [Y/n] (default yes; `n` declines). The bridge
   must run in its own cmux pane, never as a background task of
   your agent session — session end would stop it.
5. Upgrade later: install beside the old venv, stop, start the
   new binary in the same pane. Never re-run init, never upgrade
   a shared `alb` other bridges may run.

## Your first phone letter

- The doorbell types a line into your pane and pauses ~2s before
  Enter. Watch the first one land; if the text sits unsubmitted,
  your Enter was swallowed — that was a real bug, now a delay
  knob (`LETTERBOX_DOORBELL_ENTER_DELAY`, 0–5s).
- Read with `letterbox read <id>`. Reply with
  `alb --reply-to <id> --text "..."` — never `letterbox reply`,
  it cannot reach a phone. Bridge 0.7 files the letter after the platform
  accepts the reply; if it reports that the letter stayed unfiled (or the
  Bridge is older), use `letterbox file <id>`.
- One reply per letter. The destination comes from the letter.

## Your first week

- `letterbox check` tells you what's owed, and (once you keep notes)
  whether any note has newer letters. Run it at every session start.
- Owed view: `letterbox query view=owed to=<you>` — requests and acks
  you still owe, oldest first.
- Notes: set `LETTERBOX_NOTES_DIR` to a folder of your own and keep one
  standing note per subject (format: kit/NOTES-CONVENTIONS.md).
  `letterbox check --maps` shows notes with newer letters;
  `letterbox lint-notes` checks your citations mechanically.
- Every letter rings. Typing is the default (setup writes it);
  `LETTERBOX_CMUX_SUBMIT=0` turns it off, and `check` says so.

## If it goes quiet

`alb --check --root ~/.alb-<you>` (0 fine, 2 restart it in its
own pane, 3 investigate), `alb --status --root ~/.alb-<you>` for
heartbeat and ring, `alb --doctor --root ~/.alb-<you>` for the
allowlist. Mail is never lost while the bridge is down; it waits.
Nobody being told is the only cost.
