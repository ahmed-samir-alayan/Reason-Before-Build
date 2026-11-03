# Preparation checks

Checked on **2026-11-03**. These checks cover the prepared local package and the two small fixtures described below. They do not establish behavior across every project or model.

| Check | Observed result |
| --- | --- |
| Codex bundled skill validator | Passed for `skills/reason-before-build`; validates basic frontmatter and naming. |
| Metadata and package structure | Author, MIT license, skill name, optional Codex activation/UI metadata, and issue-form YAML checked. |
| Documentation references | Local file links, assets, and heading anchors resolved. |
| Manual POSIX installation | The documented shell sample copied the complete skill, including its license, into a temporary destination. File contents matched the source. |
| Existing installation protection | A second install stopped and preserved the destination. A dangling symbolic-link destination was also preserved. |
| GitHub social preview | The refreshed preview was visually inspected at 1280 × 640 and 318 KB, below GitHub's 1 MB limit. |
| Read-only behavior trial | An independent agent reviewed a duplicate dashboard proposal and recommended keeping the existing report. Fixture file hashes stayed unchanged. |
| Small-change behavior trial | An independent agent changed a pagination constant from 20 to 50. The resulting source matched that single edit. The task's instruction not to run tests was respected. |
| Visual inspection | The Nocturne cover was visually reviewed for its title, author credit, and conceptual diagram. The artwork uses generated serif lettering rendered into a bitmap. A host-specific invocation was removed so the visual identity stays platform-neutral; the social-preview export uses the same composition. |
| Targeted public-file review | Checked for local machine paths, the primary account identifier, common credential formats, unfinished scaffold markers, stale artwork references, and trailing whitespace. No matching issue found. This is not an exhaustive security scan. |

The two earlier Codex trials used explicit skill invocation in isolated local fixtures. They exercised the read-only and Light-change paths from [behavior checks](../examples/behavior-checks.md). The read-only fixture contained product guidance, a small report module, and the proposal; the small-change fixture contained a README and pagination module. They were source-level trials without an application build or real services, and they do not establish behavior on other hosts.

Not independently exercised: automatic skill selection, the remaining behavior scenarios, installation through the remote GitHub URL after the portability edits, Windows installation, discovery or behavior on other agent hosts, real application integration, and authenticated or production behavior. The files follow the shared format, but that does not establish cross-host behavior. These checks do not claim a versioned release or marketplace listing.
