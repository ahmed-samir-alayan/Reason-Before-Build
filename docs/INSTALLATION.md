# Install in an AI coding agent

The installable folder is `skills/reason-before-build`. Its `SKILL.md` and supporting files follow the open [Agent Skills format](https://agentskills.io/specification). The format defines a portable skill package; it does not define where every agent stores skills or how each one discovers and invokes them. Use the host's documented installation location and activation method.

## Host documentation

### Codex

Ask Codex to install the skill from GitHub:

```text
$skill-installer install the skill from https://github.com/ahmed-samir-alayan/Reason-Before-Build/tree/main/skills/reason-before-build
```

Codex's [skill documentation](https://learn.chatgpt.com/docs/build-skills) describes its installer, local locations, and discovery behavior.

### GitHub Copilot CLI

Copilot CLI documents project and personal locations, including `.agents/skills`. Follow its current [agent skills guide](https://docs.github.com/en/copilot/how-tos/copilot-cli/customize-copilot/add-skills) to install the skill or copy its folder.

### Cursor

Cursor supports the Agent Skills format. Its [skills guide](https://cursor.com/docs/skills) lists the shared `.agents/skills` locations and Cursor-specific `.cursor/skills` locations, and describes discovery and invocation.

### Manual copy into a supported skills location

These official guides document the following locations:

| Host | Scope | Destination |
| --- | --- | --- |
| Codex, Copilot CLI, or Cursor | Your user account | `~/.agents/skills/reason-before-build/` |
| Codex, Copilot CLI, or Cursor | One project | `<project-root>/.agents/skills/reason-before-build/` |
| Cursor | Your user account | `~/.cursor/skills/reason-before-build/` |
| Cursor | One project | `<project-root>/.cursor/skills/reason-before-build/` |
| GitHub Copilot CLI | Your user account | `~/.copilot/skills/reason-before-build/` |
| GitHub Copilot CLI | One project | `<project-root>/.github/skills/reason-before-build/` |

Confirm the location with your host's own documentation before using it. The destination should contain `SKILL.md` directly inside `reason-before-build/`. Preserve `references`, `agents`, and `assets`, and include the skill's `LICENSE` when redistributing a copy.

From a downloaded or cloned repository, run this on macOS, Linux, or another POSIX shell. It stops if the destination already exists, including a symbolic link:

```sh
(
  set -eu
  test -f ./skills/reason-before-build/SKILL.md
  skills_parent="${AGENT_SKILLS_DIR:-$HOME/.agents/skills}"
  skill_target="$skills_parent/reason-before-build"
  if [ -e "$skill_target" ] || [ -L "$skill_target" ]; then
    printf '%s\n' 'A destination already exists. Compare it before replacing it.' >&2
    exit 1
  fi
  mkdir -p "$skills_parent"
  mkdir "$skill_target"
  cp -R ./skills/reason-before-build/. "$skill_target/"
)
```

The optional `AGENT_SKILLS_DIR` variable lets you choose any host-supported or project-only parent folder. On Windows, use your file manager to copy the skill folder into the destination documented by your host.

To get the repository, clone it or use GitHub's **Code → Download ZIP**:

```sh
git clone https://github.com/ahmed-samir-alayan/Reason-Before-Build.git
cd Reason-Before-Build
```

## Confirm discovery

Use your host's skill list, reload, or selector to confirm **Reason Before Build** is available. Invocation syntax and automatic selection vary by host. If it does not appear, check the documented location, exact `SKILL.md` filename, folder nesting, and whether another skill with the same name is installed.

The optional [AGENTS.md snippet](../skills/reason-before-build/assets/AGENTS.md.snippet) can be added to a project's `AGENTS.md` when the host reads that file. Otherwise, use the host's project-instruction mechanism. Preserve existing project instructions; this addition is not required for explicit skill use.

## Update or remove

For updates, review the [changelog](../CHANGELOG.md) and compare the incoming folder with your installed copy. Preserve local modifications and replace only the copy you intend to update. For repeatable installs, select a reviewed commit or release rather than a moving branch.

To uninstall a manual copy, remove only the installed `reason-before-build` directory you selected and any optional project guidance you added. The skill has no package-manager dependency, API key, MCP server, or bundled executable.
