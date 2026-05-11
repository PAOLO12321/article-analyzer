# article-analyzer

A Claude skill that deconstructs articles into their structural components — facts, opinions, hidden premises, logical jumps, and rhetorical framing — so you can see what's actually being claimed and how.

**What it is:** A six-layer analysis framework, packaged as a Claude skill.
**What it isn't:** A judge. The tool never says "this article is wrong" — it says "this article claims X; the primary source says Y; here are the steps in between."

## Why this exists

Most online writing mixes verifiable facts, the author's opinions, predictions, and rhetorical framing into one continuous stream. A reader who wants to think clearly has to do the un-mixing themselves — and that work is exhausting, especially across topics where you don't have domain expertise.

This skill performs that un-mixing structurally and reports what it finds, without telling you what to conclude.

## What it does vs. doesn't do

| ✅ Does | ❌ Doesn't |
|--------|-----------|
| Classify every sentence into one of four types (fact, opinion, unverifiable narrative, prediction) | Tell you whether the article is "good" or "bad" |
| Search for primary sources of factual claims | Claim a piece is "fake news" — "no source found" ≠ "false" |
| Surface hidden premises an argument depends on | Replace your own judgment in specialized domains |
| Map the logical chain and flag unverified jumps | Cover political, religious, or moral controversies (returns "no opinion available") |
| Tag rhetorical devices in context | Analyze entertainment / sports / fashion writing (treated as opinion-domain by default) |
| Issue an audit opinion limited to factual claims only | Issue a "negative opinion" — only "unqualified / qualified / unable to opine" |

## Installation

This is a Claude skill, designed to be loaded by Claude Code or any Claude environment that supports skills.

```bash
# Clone into your Claude skills directory
git clone https://github.com/<your-username>/article-analyzer.git ~/.claude/skills/article-analyzer
```

Or copy `SKILL.md` into wherever your Claude environment loads skills from.

## How to use it

Once installed, trigger the skill with any of the following in Chinese or English:

- "Analyze this article: [paste text or URL]"
- "Break this down"
- "Fact-check this"
- "拆解这篇文章"
- "帮我看看这篇文章"

The skill activates automatically when these phrases are detected. It will produce a structured report with the six layers below.

## The six-layer framework

| Layer | What it does |
|-------|-------------|
| 1. Sentence classification | Sort every sentence into: factual claim / opinion / unverifiable narrative / prediction |
| 2. Fact verification | Search primary sources for each factual claim. Mark as ✅ supported, ⚠️ partial, ❌ contradicted, or 🔍 no source found |
| 3. Hidden premises | Identify assumptions the argument depends on but doesn't state |
| 4. Selective presentation | Compare to primary sources — does the article rewrite, cherry-pick, or strip context? |
| 5. Logical chain | Map the reasoning path; flag jumps where steps are skipped |
| 6. Rhetorical device tagging | Note framing techniques inline (pseudo-authority, emotional loading, over-extended analogy, etc.) |

A separate four-category classifier runs in layer 1, with explicit handling for tricky cases: analytical descriptions that sound factual, facts embedded in opinion paragraphs, opinions that slide in at the end of factual reporting, pseudo-authority phrasing ("research shows..."), and quotes with author-added emotional framing.

## Output: the audit opinion

The skill ends every report with a structured opinion, modeled on financial audit opinions but applied to factual claims only:

- **Unqualified (无保留)** — all factual claims verified consistent with primary sources
- **Qualified (保留)** — some factual claims inconsistent; specific issues listed
- **Unable to opine (无法表示)** — content red line, too few verifiable claims, or selective presentation too severe to assess by individual claims

The skill never issues a "negative" opinion. Even if every factual claim turns out to be inaccurate, it issues a Qualified opinion listing the specific problems — leaving the conclusion to the reader.

## Example

See [EXAMPLES.md](EXAMPLES.md) for a full walkthrough: three fabricated paragraphs (self-help, business analysis, tech-future) deconstructed through all six layers.

## Design principles

Four rules govern the skill's behavior:

1. **Verify and deconstruct; do not judge.** Output "the article says X; the primary source says Y." "Not found" means "not found" — not "false."

2. **No value judgments.** Describe argument quality structurally ("this paragraph crosses three unverified steps from premise to conclusion") rather than evaluatively ("this argument is weak").

3. **Serve the reader, not the critic.** Tone is neutral; the analysis is for the person who submitted the article, not against the author.

4. **Content red lines.**
   - Political / religious / illegal-or-immoral content → "no opinion available," analysis left blank
   - Major news outlets and official communications → source attribution only, no opinion analysis
   - Entertainment / sports / fashion → treated as opinion-domain by default; only specific factual claims (box office, sales rank) are verified

## Limitations

Verification is bounded by what's publicly searchable. Paywalled academic papers, paid databases, and offline sources may be invisible to the tool. "🔍 No source found" is reported honestly rather than treated as evidence of falsity.

Analytical layers reflect the model's structural understanding and may contain errors, especially in highly specialized domains.

The skill does not replace domain expertise. When a logical-chain analysis flags missing variables in a specialized field, the tool says those variables exist — judging how much they matter still requires the reader's knowledge.

English support is functional, not native. The framework was designed and tested primarily on Chinese-language writing; English handling works but may miss patterns specific to English-language rhetorical traditions.

## Contributing

Issues and pull requests welcome, especially:

- Edge cases the current four-category classifier mis-handles
- Rhetorical devices common in English-language writing that aren't currently tagged
- Examples of articles where the framework gives misleading or unhelpful output

## License

MIT — see [LICENSE](LICENSE).

You may use, modify, and redistribute, including for commercial purposes. Attribution required.

## Acknowledgments

Designed by Paolo as part of a larger project on information deconstruction tools. The "audit opinion" pattern is borrowed from financial auditing conventions.
