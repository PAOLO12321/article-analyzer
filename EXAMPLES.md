# Example: one paragraph, before and after

> The paragraph below is fabricated for demonstration. Company names are used only to make it feel realistic and do not represent real statements by those companies. Source names in brackets are placeholders, and the figure is illustrative.

## The original

> Amazon's dominance in cloud computing reveals the fundamental playbook for tech monopolies: vertical integration plus relentless price cuts. AWS has achieved a 37% gross margin that Microsoft and Google can only dream of. Industry insiders have long whispered that AWS profits subsidize Amazon's entire retail operation. This same pattern will define which AI companies survive the next decade. Smaller AI startups without their own infrastructure are essentially walking dead, as one prominent VC recently told me.

## What the tool returns (Overview)

```
Analysis or opinion (business commentary).
Audit opinion (checked factual claims only): Qualified, 1 measure or scope shift. Checked on [date].
Factual claims checked: 3 (✅ 2 / ⚠️ 1 / ❌ 0 / 🔍 0 / ❓ 0)
Other issues: self-contradictions 0 · hidden premises 1 · unstated steps 0 · selective presentation 0 · rhetorical devices 3
The most important issues:
1. 「a 37% gross margin」: ⚠️ [Amazon annual report] gives 37% as AWS's operating margin, not its gross margin.
2. 「This same pattern will define」: assumes AI markets work like cloud infrastructure; the text does not say why.
3. 「walking dead」: loaded wording; the text gives no figures on startup failure.
These are only the most important. Reply 'focused' for the main issues, or 'full' for everything.
This analysis is AI-assisted. Verification relies on publicly searchable sources; not found does not mean it does not exist. Check important information independently.
Feedback: https://github.com/PAOLO12321/article-analyzer/issues
```

Route B (analysis or opinion). Main claim: vertical integration plus price cuts is the winning playbook, and it will decide which AI companies survive. All issues bear on that claim, so the type order decides: the measure or scope shift and the hidden premise come first, then loaded wording. The jump from cloud to AI is the same gap as the hidden premise, so it is reported once.

## How each sentence was sorted

| Sentence | Sorted as | Result |
|----------|-----------|--------|
| 「Amazon's dominance in cloud computing reveals…」 | Opinion | Fact pulled out, "Amazon leads cloud computing": ✅ [market-share report]. Opinion presented as fact: "reveals" presents an interpretation as a discovery. |
| 「AWS has achieved a 37% gross margin…」 | Fact | ⚠️ The source's 37% is operating margin. Loaded wording: "can only dream of". |
| 「Industry insiders have long whispered…」 | Unverifiable (anonymous source) | Fact pulled out, "AWS is profitable": ✅ [Amazon annual report]. "Subsidizes" is interpretation. |
| 「This same pattern will define…」 | Prediction | Not checked. |
| 「Smaller AI startups… walking dead…」 | Prediction (anonymous source) | Not checked. Loaded wording: "walking dead". |
