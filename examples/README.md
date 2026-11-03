# Example prompts

Use these in an application repository. Replace feature details with your real task. The response sketches describe intended behavior; they are illustrative, not captured test results.

## A clear, small change

```text
Use $reason-before-build to change the orders page's default page size
from 20 to 50. Keep the existing pagination pattern.
```

Codex should inspect the affected convention and make the bounded change. It should not request a new product brief or redesign the page.

## A feature worth questioning

```text
Use $reason-before-build to review my proposal for a second analytics
dashboard for store managers. Check whether the existing reports already
cover their decisions. Recommend a direction without editing files.
```

If the existing report already covers the workflow, the recommendation can be to improve discoverability or leave it as it is. An implementation would require an implementation request.

## A feature ready to implement

```text
Use $reason-before-build to add saved filters to the support inbox.
Inspect the current filter and persistence patterns. Build within those
conventions, and ask only if ownership or visibility needs a product decision.
```

Codex should inspect the project, resolve routine details from existing patterns, and proceed. A missing decision about personal versus team visibility may warrant a concise question.

## A preview with honest data

```text
Use $reason-before-build to create a UI preview of the attendance overview.
Use stable synthetic data across the table, summary, and chart. Keep this
within the frontend; do not add a backend or connect a real account.
```

The totals and periods should agree, and the preview should be identified as synthetic where needed. Working layout is evidence of a preview, rather than a completed live integration.

## A consequential permissions decision

```text
Use $reason-before-build to plan a district supervisor view of school
attendance. Establish the necessary access level from existing policy.
Ask before changing permissions or exposing student-level records.
Do not implement yet.
```

Codex should compare the requested decision with the existing access policy. Organizational seniority alone should not be treated as permission to expose individual records.

## Evidence before adding a dependency

```text
Use $reason-before-build to assess whether this application needs a new
background-job service. Inspect the existing workload and infrastructure,
verify relevant service limits from official sources, and recommend the
smallest useful approach. Keep this as a review.
```

The recommendation should distinguish measured workload, documented service limits, and assumptions. It should explain what evidence could change the decision.

## Mixed-language input

```text
Use $reason-before-build. راجع شاشة المعلم الحالية وشوف هل محتاجة
summary cards فعلًا ولا الجدول الموجود كفاية. قدّم توصية فقط من غير تعديل.
```

Codex should understand the request as a teacher-screen review and normally answer in the user's language. It should avoid adding metrics merely to fill space.

## A successful no-change review

```text
Use $reason-before-build to review this workflow against its stated goal.
If the current implementation already serves it, say so and leave it unchanged.
```

A useful review can report that the workflow is sound, with the evidence inspected and any limits on verification.
