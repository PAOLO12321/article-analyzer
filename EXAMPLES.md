# Example: one paragraph, before and after

> The paragraph below is fabricated for demonstration. It imitates a common style of online business writing. Company names are used only to make it feel realistic and do not represent real statements by those companies. Source names in brackets are placeholders, and the figure is illustrative: in real use the tool names the actual source it opened.

## The original

> Amazon's dominance in cloud computing reveals the fundamental playbook for tech monopolies: vertical integration plus relentless price cuts. AWS has achieved a 37% gross margin that Microsoft and Google can only dream of. Industry insiders have long whispered that AWS profits subsidize Amazon's entire retail operation. This same pattern will define which AI companies survive the next decade. Smaller AI startups without their own infrastructure are essentially walking dead, as one prominent VC recently told me.

## What the tool returns (overview)

```
Analysis or opinion (business commentary).
Audit opinion (checked factual claims only): Qualified, 1 measure or scope shift. Checked on [date].
Factual claims checked: 3 (✅ 2 / ⚠️ 1 / ❌ 0 / 🔍 0 / ❓ 0)
Other issues: self-contradictions 0 · hidden premises 1 · selective presentation 0 · unstated steps 0 · rhetorical devices 3
The most important issues:
1. 「a 37% gross margin」: ⚠️ [Amazon annual report] gives 37% as AWS's operating margin, not its gross margin.
2. 「This same pattern will define」: assumes AI markets work like cloud infrastructure; the text does not say why.
3. 「walking dead」: emotional wording; the text gives no figures on startup failure.
These are only the most important. Reply 'focused' for the main issues, or 'full' for everything.
This analysis is AI-assisted. Verification relies on publicly searchable sources; not found does not mean it does not exist. The structural analysis reflects the tool's reading and may contain errors. Check important information independently.
Feedback: https://github.com/PAOLO12321/article-analyzer/issues
```

Main claim used for ranking: vertical integration plus price cuts is the winning playbook, and it will decide which AI companies survive. All the issues bear on that claim, so the tiers decide: the measure or scope shift and the hidden premise (tier 2) come first, then emotional wording (tier 3). "Reveals" is another rhetorical device, so it ranks after the tiers. The missing step from cloud to AI is the same gap as the hidden premise, so it is reported once, as the premise. The other emotional wording, 「can only dream of」, is in the same tier; the Overview has only three slots, so it appears in the Focused and Full reports.

## How each sentence was sorted

| Sentence | Category | Result |
|----------|----------|--------|
| 「Amazon's dominance in cloud computing reveals…」 | Analysis or opinion | Contains a factual claim, "Amazon leads cloud computing": ✅ [market-share report]. Rhetorical device: opinion presented as fact, "reveals" presents the author's interpretation as a discovery. |
| 「AWS has achieved a 37% gross margin…」 | Factual sentence | ⚠️ Measure or scope shift: the source's 37% is operating margin. Rhetorical device: emotional wording, "can only dream of" presents the gap as very large without a figure. |
| 「Industry insiders have long whispered…」 | Unverifiable narrative (anonymous source) | Contains a factual claim, "AWS is profitable": ✅ [Amazon annual report, segment results]. Whether that "subsidizes" retail depends on interpretation, so that part is opinion. |
| 「This same pattern will define…」 | Prediction | Not verified. |
| 「Smaller AI startups… walking dead…」 | Prediction | Not verified. Source type: anonymous source ("one prominent VC told me"), noted inside the prediction. Rhetorical device: emotional wording, "walking dead". |
