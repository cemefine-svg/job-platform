# Decision Dashboard Pattern — Job Platform

**Live:** https://cemefine-svg.github.io/job-platform/ · Single HTML file, no backend, free hosting on GitHub Pages.

A reusable pattern for turning any "many options, one decision" problem into a visual, critical, self-updating dashboard. First used for [Dublin apartments](https://cemefine-svg.github.io/dublin-apartments/), now for part-time job applications. Works equally for funding calls, conference CFPs, consulting leads, literature triage, supplier selection.

## The pattern (5 parts)

**1. Structured data, not notes.** Every option is one object in a `JOBS` array: facts (salary, deadline, link) + judgements (fit subscores, effort, risks). Forcing judgement into numbers is what makes ranking possible.

**2. A decision score, not just a fit score.** `score = fit × urgency ÷ √effort`. Fit alone ranks dreams; dividing by effort and multiplying by deadline-urgency ranks *actions*. The quadrant chart (fit vs effort) shows the same thing visually: top-left = do first.

**3. Critical notes per option.** Each card carries "Why you" *and* "Watch out" — the dashboard argues both sides so the decision is honest, not aspirational. Verification status (✓ live / ⚠ verify / ✗ expired) keeps stale data from wasting effort.

**4. Decisions stay with the human.** ★ Will apply / ✗ Won't apply buttons store choices in the browser (localStorage) and build an exportable queue — the human decides, the assistant executes one by one.

**5. Weekly automated refresh.** A scheduled Claude task re-harvests sources every Friday, re-scores, marks expired entries, and republishes via the GitHub web upload flow. The dashboard is an ongoing pipeline, not a snapshot.

## Reuse in 4 steps

1. Fork or copy `index.html`, replace the `JOBS` array with your options and rename fields.
2. Adjust the fit subscores to your criteria (mission/skills/lightness → whatever matters).
3. Enable GitHub Pages (Settings → Pages → main branch, root).
4. Optional: give an AI assistant the harvest sources + scoring rules and schedule a weekly refresh.

Built by Elgasim Hamad with Claude, June 2026.
