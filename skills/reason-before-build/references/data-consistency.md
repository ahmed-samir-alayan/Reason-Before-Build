# Data consistency and useful mock fixtures

Read this for data displays, mock data, shared KPIs, or changes that span roles. Reuse the project's real data definitions and existing fixtures where possible.

## Shared data contract

- Establish entity relationships, identifiers, units, valid ranges/statuses, data source, access scope, filters, and time period before choosing values or visualizations.
- Give a shared measure one definition across views. For rates, aggregate the underlying numerator and denominator; do not average percentages unless that is the intended, documented measure. Handle zero denominators, unknown values, and rounding honestly.
- Derive summaries, charts, and table totals from the same records or a demonstrably equivalent aggregation. Respect deduplication and parent/child relationships; do not sum overlapping populations.
- Choose records, tables, comparisons, or trends according to the user's decision and authorized detail. The same source data can support different representations for different roles.

## Realistic mock data

- Build one small synthetic scenario with plausible entity sizes, relationships, dates, distributions, and status counts. It should reflect this application's domain rather than an arbitrary collection of attractive numbers.
- Use fixed fixtures or a stable seed when generation is needed. Do not randomize on each render or regenerate unrelated values for each screen. Avoid building a generator when a small fixed fixture is sufficient.
- Reuse identifiers and facts across connected views. For example, a synthetic school with 24 classes of 34 students has 816 students everywhere it appears. An administration total must reconcile with the schools included by its current scope and filters. This is an illustration, not a required education model or size.
- Include only states useful for the requested review: ordinary data plus relevant empty, shortage, error, large-value, or boundary cases. Keep the scenario simple; not every task needs every state.
- Label the experience as preview/demo where needed to avoid suggesting real records or measured results. Isolate fixtures from live accounts and production stores. Never write synthetic records to a real service merely to preview a screen.
- Do not add a backend, database, API, invented scoring formula, or production integration merely to supply preview values. When real integration is authorized, preserve the agreed contract or explicitly resolve a necessary contract change.

## Review

Check entity links and counts, compatible filters/periods, numerator/denominator math, row/chart/summary agreement, valid dates/statuses, stable rendering, and role access. Report whether the result uses synthetic fixtures, live data, or an unavailable source; these are different evidence states.
