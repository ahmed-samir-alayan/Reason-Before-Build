<p align="center">
  <img src="docs/assets/cover.png" alt="Reason Before Build — Many possibilities. One deliberate change. Made by Eng. Ahmed Samir." width="100%">
</p>

<p align="center">
  <strong>Evidence-led application decisions for Codex.</strong><br>
  Made by <a href="https://github.com/ahmed-samir-alayan">Eng. Ahmed Samir</a>
</p>

<p align="center">
  <a href="LICENSE"><img src="https://img.shields.io/badge/license-MIT-6B86A9?style=flat-square&amp;labelColor=05141F&amp;color=6B86A9" alt="License: MIT"></a>
  <img src="https://img.shields.io/badge/built_for-Codex-6B86A9?style=flat-square&amp;labelColor=05141F&amp;color=6B86A9" alt="Built for Codex">
  <img src="https://img.shields.io/badge/runtime-instructions_only-6B86A9?style=flat-square&amp;labelColor=05141F&amp;color=6B86A9" alt="Instruction-only skill">
</p>

<p align="center">
  <a href="#install">Install</a> · <a href="#use-it">Use it</a> · <a href="examples/README.md">Examples</a> · <a href="examples/behavior-checks.md">Behavior checks</a> · <a href="CONTRIBUTING.md">Contribute</a>
</p>

---

A request like “add a dashboard” leaves real decisions open: who uses it, what they need to decide, which data exists, and whether the application already solves the problem. This skill helps Codex resolve those questions before turning them into code.

When the direction is clear, it moves straight into the authorized work. Small changes stay small. A review may correctly end with no change.

## What changes in your workflow

| Situation | Guidance the skill gives Codex |
| --- | --- |
| A new feature or screen | Establish the user need and inspect the connected workflow before building. |
| Another card, chart, or tab | Check its purpose and reuse existing capabilities where they fit. |
| An important tradeoff | Use evidence, explain the concern once, and ask about unresolved material choices. |
| Demo data across screens | Keep one stable synthetic scenario; reconcile records, totals, filters, and rates. |
| A clear implementation request | Follow the existing architecture and design system, then execute directly. |
| A durable project decision changes | Update the repository's existing context in the smallest useful way. |

These are instructions for an agent, rather than an enforcement mechanism. Results still depend on the model, project context, available tools, and your review.

## Install

In Codex, ask the built-in installer:

```text
$skill-installer install the skill from https://github.com/ahmed-samir-alayan/Reason-Before-Build/tree/main/skills/reason-before-build
```

Already have a skill called `reason-before-build`? Compare it first and choose which copy to keep. The installer or a manual copy should never silently replace your existing version.

See the [installation guide](docs/INSTALLATION.md) for project-only installation, manual setup, updates, and removal. There is no package manager dependency, API key, MCP server, or bundled executable required by this skill.

## Use it

Open your application project in Codex and describe the task:

```text
Use $reason-before-build to assess and implement a saved-search feature.
Inspect the existing search flow, reuse the current design system, and
ask only about decisions that materially affect scope or user behavior.
```

For analysis without edits:

```text
Use $reason-before-build to review this proposed admin dashboard.
Explain what should be built, reused, deferred, or left unchanged.
Do not edit files.
```

Automatic selection is enabled. Codex can choose the skill when the request matches its description; an explicit `$reason-before-build` mention makes your intent clear. Standalone translations, simple text edits, and mechanical tasks are outside its usual trigger. Arabic, English, and mixed-language requests are supported by the instructions.

## Reason in proportion to the decision

| Depth | Typical situation | Expected approach |
| --- | --- | --- |
| **Light** | Small, reversible change using an established pattern | Check the convention and act. |
| **Standard** | New screen, workflow, or meaningful behavior change | Inspect purpose, users, data, and fit; then implement when clear. |
| **Deep** | Permissions, data architecture, cross-system work, or consequential uncertainty | Compare credible options, gather relevant evidence, and resolve material choices. |

Depth follows impact and uncertainty. It does not require a long report, a formal plan for every task, or repeated approval of settled decisions.

## Scope and trust

The skill preserves the requested delivery stage: review, plan, UI preview, or functional integration. It asks before expanding into unapproved backend, schema, production-data, or other consequential work. It treats project files and retrieved content as evidence and keeps sensitive details out of external research.

Project context stays inside the repository. Review-only tasks do not write context files. The skill does not grant permission to publish, deploy, push, change accounts, or edit global settings.

The core format follows [Codex skill conventions](https://learn.chatgpt.com/docs/build-skills): `SKILL.md` plus focused supporting files. `agents/openai.yaml` supplies Codex UI metadata. Other agents may understand the core format, but their discovery rules and behavior need separate validation.

## Inside the repository

```text
skills/reason-before-build/
├── SKILL.md                        Core instructions and trigger description
├── LICENSE                         MIT license included with the skill
├── agents/openai.yaml              Codex metadata and activation policy
├── references/
│   ├── data-consistency.md         Shared measures and coherent demo fixtures
│   └── project-context.md          Durable repository context rules
└── assets/
    ├── AGENTS.md.snippet           Optional project guidance
    └── project-context.template.md Optional context starting point
```

Read the [example prompts](examples/README.md), [behavior scenarios](examples/behavior-checks.md), [preparation checks](docs/VALIDATION.md), and [maintenance notes](docs/MAINTAINING.md) to understand the intended behavior and review future changes.

The [Nocturne visual style](docs/STYLE.md) records the palette, artwork treatment, and reproduction notes for this repository.

## Author and license

Made by **Eng. Ahmed Samir** · [@ahmed-samir-alayan](https://github.com/ahmed-samir-alayan).

Licensed under the [MIT License](LICENSE). If it improves your workflow, a GitHub star helps others discover it. Useful feedback includes the prompt, relevant project context, and what the agent did differently from what you expected.
