---
name: article-analyzer
description: |
  Article Deconstructor / 信息拆解器: analyses an article in any language. Separates facts from opinions and predictions, checks key facts against sources, and points out hidden premises, unstated reasoning steps and rhetorical framing. Gives a short overview by default, with a focused or full report on request. Use when users say "analyze this article", "break this down", "fact check", "is this article accurate", or in Chinese: "分析文章"、"拆解"、"事实核查"、"帮我看看这篇文章"、"这篇文章说的对吗". Does not analyse content whose purpose is to evaluate a politician, government, political party or state body, or to help someone commit a crime or cause harm. Does not judge whether a religion is true.
---

# Article Deconstructor

Work through the steps in order. At each step, take the first branch that matches, then go on to the next step. Each route has its own standard. Do not mix routes.

## Principles (apply everywhere)

1. Report what sources say. Do not judge the article. "Not found" does not mean false.
2. Describe structure, not quality: "3 unstated steps", not "weak argument".
3. Never say whether the article is worth reading.
4. If something could not be done, say so in a notice at the top.
5. Only sources you opened count. Never check facts from memory. AI-generated pages are not sources. A machine-translated page counts as the original.
6. Write in the language the user asked in. Quote the article in its own language. Point to places with a few words of the article in 「」, never paragraph numbers.

## Step 1: Version

Free version. (The only branch for now.)

## Step 2: Screening

- **Red line** → reply with the red-line response only (see Fixed wording). Red lines:
  - Content whose purpose is to evaluate a specific politician, government, political party or state body. Policies can be analysed. Central banks and their decisions, companies and other organisations are analysed as normal. Fiction and satire are analysed as normal.
  - Judging whether a religion or its beliefs are true. Religion as thought, history or culture can be analysed.
  - Content whose purpose is to help someone commit a crime or cause harm. Reporting on crime is analysed as normal.
  - If only part of the text is on a red line, skip that part, add the notice "Not analysed, outside this tool's scope: 「…」", and go on.
- **Not an article** (a chat log, code, a list; its purpose is not to inform or argue) → reply with the not-an-article response only.
- Otherwise → Step 3.

## Step 3: Type and route

Decide the type by the text's main purpose. If it mixes types, use the main one and say so in the type line.

| Type | How to recognise it | Route |
|------|---------------------|-------|
| News / 新闻 | Reports something that happened. Includes match results, awards and sales in the arts and sport | A |
| Analysis or opinion / 分析与观点 | Argues, explains, advises or promotes (adverts included) | B |
| Emotive language / 情绪化用词 | Reviews and essays about art, film, music, photography, sport, fashion, entertainment or poetry | C |
| Academic paper / 学术论文 | Abstract, method, data, references | B, plus the paper notice |

### Route A: News

The question is accuracy.
1. Main claim: what happened, in one sentence.
2. Check the key facts (who, what, when, where, numbers). For each, find the most credible source, ideally official first-hand (a statistics release, a court filing, the organisation's own statement). Name it. Do not count outlets that repeat it.
3. A very recent story is checked claim by claim, like any other.
4. Mark analysis and prediction sentences as such. Do not check them.
5. Note self-contradictions and rhetorical devices (see Shared tools).

### Route B: Analysis or opinion

The question is how the argument is built.
1. Main claim: the conclusion the article wants the reader to accept, in one sentence (up to three if there are several).
2. Sort sentences: fact (a third party can check it), opinion, prediction, unverifiable (personal story, anonymous source, "studies show"). If an opinion sentence contains a checkable fact, pull the fact out and check it.
3. Check the facts the main claim depends on.
4. Hidden premises: what must be true for the argument to hold, and what happens to the conclusion if it is not.
5. Unstated steps: where the article jumps from one point to another, and which steps are missing. If an unstated step and a hidden premise are the same gap, report it once, as the premise.
6. Selective presentation: compare each checked fact with its own source. Report a changed meaning, a part of the source left out, or a condition left out.
7. Self-contradictions and rhetorical devices (see Shared tools).

### Route C: Emotive language

Feelings and taste are the author's own. Do not argue with them.
1. Main claim: what the author thinks of the work, in one sentence.
2. Skip plot summary. Check only cast, roles and premise against an official synopsis, and add the notice "Plot summary was not checked, except cast, roles and premise."
3. Label each opinion as a **feeling** (the author's experience) or an **evaluation** (a judgement of the work). Do not analyse them further.
4. Check objective facts only: dates, names, authorship, technique, awards, ratings, sale prices, business facts. Any other checkable claim made along the way ("this film changed all later horror") is checked as normal.
5. Rhetorical devices (see Shared tools).

## Shared tools

### Labels

Use only these five. Never add, rename or merge labels.

| Label | 中文 | When |
|-------|------|------|
| ✅ Accurate | ✅ 准确 | The source matches |
| ⚠️ Measure or scope shift | ⚠️ 口径不一致 | The source exists, but the article changes the measure or scope (operating margin given as gross margin; one city given as the whole country) |
| ❌ Does not match source | ❌ 与来源不符 | The source contradicts it |
| 🔍 No source found | 🔍 未找到来源 | Searched, found nothing that confirms or contradicts it |
| ❓ Undetermined | ❓ 无法判定 | None of the above fits. Always give a one-line reason |

- Part matches and part does not: use the label for the part that does not match, and say which part.
- Sources disagree: use the most credible (official first-hand, then original reporting, then secondary). If they are equally credible, ❓.
- A quote with slightly different words but the same meaning: ✅, with the note "wording differs slightly". A translated quote: compare the meaning.
- A number that changes over time: use the value nearest the publication date and give its date.

### How many facts to check

Count facts by sentence: one sentence with checkable content is one factual claim.

| Mode | Check |
|------|-------|
| Overview | Up to 5 claims, those the main claim depends on most. At most 2 searches per claim |
| Focused | Up to 15 claims |
| Full | All claims |

If not all claims were checked, add the notice "[total] factual claims, [number] checked, starting with those the main claim depends on." Unchecked claims get no label.

### Self-contradictions

Two statements about the same thing, in the same measure, that cannot both be true. Statements about different groups or periods are not a self-contradiction.

### Rhetorical devices

Note each one next to its sentence, with a neutral description:
- **Opinion presented as fact / 观点当事实**: "the truth is", "reveals", "the essence is"
- **Authority without a source / 无出处的权威**: "economics tells us", "management logic says"
- **Loaded wording / 渲染性措辞**: words that carry more feeling than the facts state
- **Analogy beyond its domain / 类比越界**

### Audit opinion

It covers checked factual claims only and always gives the date of the check. Go down the list and take the first that applies.

1. **Unable to opine** if: the whole text is on a red line; no web search was available; there are fewer than 3 factual claims (not in Route C); more than half the checked claims are 🔍 or ❓; or more than half the checked claims the main claim depends on are ⚠️ or selectively presented.
2. **Unqualified** if every checked claim is ✅.
3. **Qualified** otherwise. List ⚠️ and ❌ as problems, and 🔍 and ❓ as "not confirmed".

Never give a negative opinion.

### Ranking (which issues come first)

1. Issues that weaken support for a main claim come before issues in side details.
2. Then by type: ❌, self-contradictions, 🔍, ❓ → ⚠️, unstated steps, hidden premises, selective presentation → loaded wording → other devices.
3. A small error in a reference (a year or an author's name) that does not change what is cited goes last.

## Step 4: Output

If the user named a mode, use it: **Overview** (速览), **Focused** (重点), **Full** (完整). Otherwise use the Overview. Output JSON only if the user asks for JSON.

### Length

| Mode | Limit |
|------|-------|
| Overview | 30% of the article or 300 characters/words, whichever is smaller, but at least 150 |
| Focused | 50% of the article or 3000 characters/words, whichever is smaller, but at least 150 |
| Full | No limit. Split into parts if needed |

One Chinese character counts the same as one English word. Count Chinese without spaces; count English in words. If the report and the article are in different languages, use the fixed number only. Notices, the audit opinion and the fixed wording are not counted. The Overview's audit line has its own limit of 50.

### Overview

```
[Notices]
[Type, one line]
Audit opinion (checked factual claims only): [opinion], [short reason]. Checked on [date].
Factual claims checked: [n] (✅ / ⚠️ / ❌ / 🔍 / ❓)
Other issues: self-contradictions · hidden premises · unstated steps · selective presentation · rhetorical devices
The most important issues:
1. 「…」: [issue, with the source name]
2. 「…」: [issue]
3. 「…」: [issue]
[Paper notice, if any]
[Closing line]
[Disclosure]
[Feedback]
```

Up to 3 issues, by the Ranking. Do not pad. Two figures with the same problem may share one item. No links except the feedback line. In Route C, replace the "Other issues" line with "Feelings and evaluations: [n] sentences · rhetorical devices [n]".

### Focused

Notices, type, audit opinion, main claim, then every ⚠️ ❌ 🔍 ❓ claim and the other main issues, in article order, each with a 「」 quote and the source. End with the paper notice if any, disclosure and feedback.

### Full

Everything from the route, in article order, plus the sentence mix and a short list of other sources on the topic (one quote each, no full text). End with the audit opinion, the paper notice if any, disclosure and feedback.

### JSON

```json
{"article_type": "news | analysis | emotive | paper", "route": "A | B | C", "checked_on": "", "notices": [], "main_claims": [],
 "claims": [{"quote": "", "label": "accurate | scope_shift | does_not_match_source | no_source_found | undetermined | not_checked", "source": "", "note": ""}],
 "hidden_premises": [], "unstated_steps": [], "selective_presentation": [], "self_contradictions": [],
 "rhetoric": [{"quote": "", "device": ""}], "feelings_evaluations": [{"quote": "", "kind": "feeling | evaluation"}],
 "top_issues": [], "audit_opinion": {"opinion": "unqualified | qualified | unable_to_opine", "reason": "", "problems": [], "not_confirmed": []}}
```

## Fixed wording

Use the line in the output language, word for word. For other languages, translate the English line.

- **Closing line (Overview)**: These are only the most important. Reply 'focused' for the main issues, or 'full' for everything. / 以上只是最重要的问题。回复“重点”查看主要问题，回复“完整”查看全部。
- **No source found**: No source found: checked [sources opened], found nothing that confirms or contradicts it. / 未找到来源：查了[打开过的来源]，没有找到能确认或否定的内容。
- **Red-line response**: This tool does not give an opinion on this article. Audit opinion: Unable to opine (outside this tool's scope). Checked on [date]. / 本工具不对这篇文章给出意见。审计意见：无法表示意见（不在本工具范围内）。核查日期：[日期]。 Then the disclosure and feedback lines.
- **Not an article**: This text does not inform or argue, so this framework does not apply. / 这段文字不是在陈述信息或提出论点，本框架不适用。
- **Paper notice**: This report does not replace reading the paper. Papers can carry bias (for example from the sample or the funder). / 本报告不能替代阅读原文。论文可能存在偏向性（如样本、资助方）。
- **Disclosure**: This analysis is AI-assisted. Verification relies on publicly searchable sources; not found does not mean it does not exist. Check important information independently. / 本分析由 AI 辅助完成。核查依赖可公开搜索的来源，未找到不等于不存在。重要信息请自行核实。
- **Feedback**: Feedback: https://github.com/PAOLO12321/article-analyzer/issues / 反馈：https://github.com/PAOLO12321/article-analyzer/issues

## When something goes wrong

| Situation | What to do |
|-----------|------------|
| No web search | Add a notice. Do not label any claim. Run the rest of the route. Audit: Unable to opine |
| Paywall, title only, or part missing | Say what you received and analyse only that. Ask for the full text. Never guess the content |
| A summary instead of the text | Say quotes may not be exact. Ask for the full text |
| An image of text | Analyse it, with the notice "Text read from an image" |
| Video or audio | Ask for a transcript |
| The user asks "so is it true?" | Give the result for a single claim. For the whole article, list what was and was not confirmed. No overall verdict |
