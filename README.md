# Atlas of Statistics

An interactive map of everything a data scientist needs to know about statistics, wired together by what you need to learn first. One HTML file, no build step, no dependencies.

![Concepts](https://img.shields.io/badge/concepts-453-F0B95E?style=flat-square)
![Prerequisite links](https://img.shields.io/badge/prerequisite%20links-821-4FD1E0?style=flat-square)
![Fields](https://img.shields.io/badge/fields-26-9A8CF0?style=flat-square)
![Single file](https://img.shields.io/badge/build-none%2C%20single%20file-8593B0?style=flat-square)
![License](https://img.shields.io/badge/license-MIT-8593B0?style=flat-square)

![The atlas](assets/atlas-preview.png)

Rings are difficulty. Wedges are fields. Circles are core statistics, squares are the craft that grew around it. Gold means mastered, dashed cyan means every prerequisite is already gold.

## Two views of the same map

**Star chart.** Click any concept to see what it needs, what it unlocks, and to mark it done. Node size grows with how many things depend on it, so the load-bearing concepts stand out on sight: multiple regression carries 21 dependents, expectation 14, maximum likelihood 12, A/B testing 12.

**Checklist.** The same 453 concepts as a numbered study sequence. Each field is ordered by a topological sort of its own prerequisites, so step 07 never depends on step 12. Mathematical foundations runs functions, set theory, combinatorics, limits, vectors, derivatives, integrals, and on to measure theory. Filter by level, search, or hide what you have finished.

![What is inside](assets/fields.png)

## Use it

1. Download `statistics-atlas.html`
2. Open it in any browser

To share a live link, turn on GitHub Pages for this repo (Settings, Pages, deploy from `main`, root folder) and the atlas will be served at `https://<your-username>.github.io/<repo-name>/statistics-atlas.html`.

## Progress and backup

Checkmarks save automatically in the browser, and the built in **Progress and backup** panel shows completion by level and by field, a day by day progress line, and two ways to keep your work outside the browser:

- **Backup code**, a plain list of your completed concept ids. Copy it anywhere, paste it back to restore on any machine.
- **Markdown export**, the full checklist with `- [x]` boxes, step numbers, and level tags, grouped by field. Drops straight into Notion, Obsidian, or a repo.

## The five levels

Level is prerequisite depth, not importance. A concept never sits at a lower level than anything it depends on, so any level filter shows a self consistent slice of the map.

| Level | Name | Concepts | What it covers |
| --- | --- | ---: | --- |
| 1 | Bedrock | 14 | Vocabulary and arithmetic of data. No prerequisites. |
| 2 | Core mechanics | 53 | Random variables, distributions, summaries, first models. |
| 3 | Working analyst | 112 | Estimation and testing done properly. The analyst bar. |
| 4 | Practitioner | 153 | Model families, experiment craft, assumptions that break in production. |
| 5 | Specialist | 121 | Theory and advanced methods. Statistician rather than analyst. |

## Under the hood

Every concept is one record, and the graph is a validated DAG: no cycles, no orphans, no dangling prerequisites, and three entry points with no prerequisites at all (set theory, functions and notation, data types and measurement scales).

```json
{
  "id": "bayes-theorem",
  "label": "Bayes' theorem",
  "level": 2,
  "domain": "prob",
  "prereqs": ["conditional-probability", "joint-probability", "law-total-probability"],
  "note": "Invert a conditional. Base rates, false positive puzzles, and the root of Bayesian inference."
}
```

The data lives in the `DATA` array at the top of the script block, so you can add a concept, drop one, or rewire a prerequisite by editing that array. The step ordering, the layout, the levels, and the checklist all recompute from it.

## License

MIT. Use it, fork it, rewire it for your own field.
