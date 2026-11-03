# Install in Codex

This repository contains one skill at `skills/reason-before-build`. Install that folder, rather than the entire repository, into a Codex skill location.

Choose the built-in installer or copy the skill folder into a local Codex skill location.

## Use the built-in installer

Ask Codex:

```text
$skill-installer install the skill from https://github.com/ahmed-samir-alayan/Reason-Before-Build/tree/main/skills/reason-before-build
```

The built-in installer chooses its supported local installation location. If it reports an existing destination, compare the installed copy and the incoming copy before deciding to replace either. Do not install another copy with the same skill name just to bypass the warning.

## Install a local copy

Copy `skills/reason-before-build` into one of the locations documented by Codex:

| Scope | Destination |
| --- | --- |
| Your user account | `~/.agents/skills/reason-before-build/` |
| One project | `<project-root>/.agents/skills/reason-before-build/` |

Both destinations should contain `SKILL.md` directly inside `reason-before-build/`. Preserve the `references`, `agents`, and `assets` directories. Include the repository's `LICENSE` with a redistributed copy.

For a downloaded or cloned copy, run this from its repository root on macOS, Linux, or another POSIX shell. It stops if the target already exists, including a symbolic link:

```sh
(
  set -eu
  test -f ./skills/reason-before-build/SKILL.md
  skill_parent="${REASON_BEFORE_BUILD_SKILLS_DIR:-$HOME/.agents/skills}"
  skill_target="$skill_parent/reason-before-build"
  if [ -e "$skill_target" ] || [ -L "$skill_target" ]; then
    printf '%s\n' 'A destination already exists. Compare it before replacing it.' >&2
    exit 1
  fi
  mkdir -p "$skill_parent"
  mkdir "$skill_target"
  cp -R ./skills/reason-before-build/. "$skill_target/"
)
```

The optional `REASON_BEFORE_BUILD_SKILLS_DIR` variable selects a different parent folder for this copy command. Leave it unset for the user location, or set it to your project's `.agents/skills` folder for project-only setup.

For project-only installation, copy the same files using your file manager into the project destination above. On Windows, use your file manager and your user profile's `.agents/skills` folder; the shell sample is for POSIX environments.

To obtain the repository, Git users can run:

```sh
git clone https://github.com/ahmed-samir-alayan/Reason-Before-Build.git
cd Reason-Before-Build
```

Alternatively, use GitHub's **Code → Download ZIP**, extract it, and open the repository folder.

## Confirm discovery

Open Codex in your application project and look for **Reason Before Build** in the skill selector. Explicit invocation uses `$reason-before-build`.

Codex detects skill changes automatically according to the [official documentation](https://learn.chatgpt.com/docs/build-skills). Restart Codex if the skill does not appear. If it remains missing, check the folder nesting, exact `SKILL.md` filename, and any existing skill-disable settings before changing configuration.

Duplicate skill names are not merged. Check existing project and user copies, including older installations under `~/.codex/skills`, before adding another one.

## Optional project guidance

If your team wants to request this workflow for application work, manually add the text from [AGENTS.md.snippet](../skills/reason-before-build/assets/AGENTS.md.snippet) to the project's existing `AGENTS.md`. Preserve the project's other instructions. This is optional; explicit invocation works without it.

## Update or remove

For updates, review the [changelog](../CHANGELOG.md) and compare the incoming folder with your installed copy. Preserve local modifications and replace only the copy you intend to update. For repeatable installs, select a reviewed commit or release rather than a moving branch.

To uninstall a manual copy, remove only the installed `reason-before-build` directory you selected. Remove any optional project guidance you added. No global Git or GitHub account changes are needed for installation.
