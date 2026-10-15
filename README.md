# Durable Agent Engineering

A portable, instruction-only skill for designing or building agent workflows that retain work across interruptions and remain inspectable by reconnecting clients.

## Install

From this repository root, run the following after cloning or downloading the repository. It refuses to replace an existing skill directory or symlink.

```sh
target="${CODEX_HOME:-$HOME/.codex}/skills/durable-agent-engineering"
if [ -e "$target" ] || [ -L "$target" ]; then
  printf 'Refusing to overwrite existing path: %s\n' "$target" >&2
  exit 1
fi
mkdir -p "$(dirname "$target")"
cp -R "skills/durable-agent-engineering" "$target"
```

## Use

Invoke the installed skill with **`$durable-agent-engineering`**. State the authorized outcome, current runtime and ownership boundaries, required clients, and the evidence needed for acceptance.

Read [the skill instructions](skills/durable-agent-engineering/SKILL.md). The Pi Durable note is a linked-source reading guide; check the selected runtime version and APIs before relying on them. This package provides guidance, not a runtime, implementation, or proof of model behavior. Installation does not establish that a host loaded the skill or that a workflow survives interruptions.

## License

MIT. See [LICENSE](LICENSE).
