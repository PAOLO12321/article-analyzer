# article-analyzer

An AI agent skill that takes an article apart: facts, opinions, predictions, hidden premises, unstated reasoning steps and rhetorical framing. It checks the factual claims against sources and shows you what is actually being claimed.

**What it is:** a six-layer analysis framework, packaged as a skill (`SKILL.md`).
**What it isn't:** a judge. It never says "this article is wrong". It says "the article claims X; the source says Y".

## Why this exists

Most online writing mixes checkable facts, opinions, predictions and framing into one stream. Separating them is slow work, especially outside your own field. This skill does the separating and reports what it finds. The conclusion is yours.

## What it does and doesn't do

| ✅ Does | ❌ Doesn't |
|--------|-----------|
| Sort every sentence into fact, opinion, unverifiable narrative or prediction | Say whether an article is good or bad |
| Check factual claims against sources, preferring official first-hand data | Call something false because no source was found |
| Surface hidden premises and unstated reasoning steps | Replace your own judgement in a specialist field |
| Flag rewording, partial use of a source and missing conditions | Analyse content whose purpose is to evaluate a politician, government, political party or state body; judge whether a religion is true; or analyse content meant to help someone commit a crime or cause harm |
| Note rhetorical devices next to the sentences they appear in | Analyse feelings or taste in writing about art, photography, music, film, entertainment, sport, fashion or poetry |
| Give an audit opinion on the checked facts, with the date of the check | Give a "negative" opinion |

## Installation

Download the skill folder and put it where your agent loads skills from. For Claude Code:

```bash
git clone https://github.com/PAOLO12321/article-analyzer.git ~/.claude/skills/article-analyzer
```

Other agents that support `SKILL.md` skills can load the same file.

## How to use it

Paste the full text of an article (this works best) or a link, and ask in any language:

- "Analyze this article: [text or link]"
- "Fact-check this"
- "拆解这篇文章"
- "帮我看看这篇文章"

By default you get a short **overview**: the audit opinion, the fact-check counts and up to three of the most important issues. Ask for **focused** (重点) for the main problems in article order, or **full** (完整) for everything. Reports are written in the language you ask in. Ask for JSON if you want structured output for a pipeline.

## The six layers

| Layer | What it does |
|-------|-------------|
| 1. Main claim and classification | States the article's main claim, then sorts each sentence into one of four categories |
| 2. Fact verification | Checks each factual claim and gives one of five fixed labels: ✅ Accurate, ⚠️ Concept shift, ❌ Factually wrong, 🔍 No source found, ❓ Uncertain (with a reason) |
| 3. Hidden premises | Finds the assumptions an argument needs but does not state |
| 4. Selective presentation | Compares each claim with its own source: rewording, partial use of the source, missing conditions |
| 5. Reasoning chain | Maps the reasoning and marks the steps the article does not state |
| 6. Rhetorical devices | Notes framing such as authority without a source, emotional wording or an analogy applied beyond its domain |

Before Layer 1, a content screener decides the route. News is checked for accuracy against the most credible source, ideally official first-hand data. Writing about art, photography, music, film, entertainment, sport, fashion or poetry skips plot summary (except cast, roles and premise) and only checks objective facts. Academic papers get a notice that the report does not replace reading the paper.

## The audit opinion

Modelled on financial audit opinions, and limited to the factual claims that were checked:

- **Unqualified**: every checked claim is accurate
- **Qualified**: at least one claim is not accurate or could not be confirmed; each is listed
- **Unable to opine**: out of scope, fewer than three factual claims, selective presentation affecting most of what the main claim rests on, no web search, or most claims could not be confirmed

There is no "negative" opinion. Even if every claim is wrong, the opinion is Qualified with the problems listed.

## Example

See [EXAMPLES.md](EXAMPLES.md) for one paragraph before and after.

## Design principles

1. **Verify and deconstruct; do not judge.** "Not found" means not found, not false.
2. **No value judgements.** Describe structure ("three unstated steps"), not quality ("weak").
3. **Serve the reader.** Neutral towards the author.
4. **Never say whether an article is worth your time.** The report gives descriptive facts; you decide.
5. **Never lower quality silently.** If something could not be done (no web search, a paywall, too many claims), the report says so at the top.

## Limitations

- Verification is limited to what can be found publicly. Paywalled papers, paid databases and offline sources may be out of reach.
- Without a web search tool the skill does not verify facts. It says so rather than guessing from memory.
- The structural analysis reflects the model's reading and can be wrong, especially in specialist fields.
- The framework was first built on Chinese writing. It now writes reports in the user's language, but some patterns specific to other languages may be missed.

## Feedback

Please open an issue: https://github.com/PAOLO12321/article-analyzer/issues

Especially useful: sentences the classifier gets wrong, rhetorical devices it misses, and articles where the report is misleading or unhelpful.

## License

MIT. See [LICENSE](LICENSE).

## Acknowledgements

Designed by Paolo as part of a larger project on information deconstruction tools. The audit opinion pattern is borrowed from financial auditing.
