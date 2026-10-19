# Example: one paragraph, before and after

> The paragraph below is fabricated for demonstration. It imitates a common style of online business writing. Company names are used only to make it feel realistic and do not represent real statements by those companies. Source names in brackets are placeholders: in real use the tool names the actual source it opened.

## The original

> Amazon's dominance in cloud computing reveals the fundamental playbook for tech monopolies: vertical integration plus relentless price cuts. Amazon has achieved gross margins that Microsoft and Google can only dream of. Industry insiders have long whispered that AWS profits subsidize Amazon's entire retail operation. This same pattern will define which AI companies survive the next decade. Smaller AI startups without their own infrastructure are essentially walking dead, as one prominent VC recently told me.

## What the tool returns (overview)

```
Analysis or opinion (business commentary).
Audit opinion: Qualified, 1 concept shift. Checked on [date].
Factual claims checked: 3 (✅ 2 / ⚠️ 1 / ❌ 0 / 🔍 0 / ❓ 0)
Other issues: hidden premises 1 · selective presentation 0 · unstated steps 1 · rhetorical devices 2
The most important issues:
1. 「gross margins that Microsoft and Google can only dream of」: ⚠️ [company annual reports] give segment operating margins, not comparable gross margins.
2. 「This same pattern will define」: the step from cloud to AI is not stated.
3. 「which AI companies survive」: assumes AI markets work like cloud infrastructure; the text does not say why.
These are only the most important. Reply 'focused' for the main problems, or 'full' for everything.
This analysis is AI-assisted. Verification relies on publicly searchable sources; not found does not mean it does not exist. The structural analysis reflects the tool's reading and may contain errors. Check important information independently.
Feedback: https://github.com/PAOLO12321/article-analyzer/issues
```

Main claim used for ranking: vertical integration plus price cuts is the winning playbook, and it will decide which AI companies survive. All three issues sit on that claim, so they rank above the emotional wording.

## How each sentence was sorted

| Sentence | Category | Result |
|----------|----------|--------|
| 「Amazon's dominance in cloud computing reveals…」 | Analysis or opinion | Contains a factual claim, "Amazon leads cloud computing": ✅ [market-share report]. "Reveals the fundamental playbook" is the author's interpretation. |
| 「Amazon has achieved gross margins…」 | Factual claim | ⚠️ Concept shift. Rhetorical device: emotional wording, "can only dream of" presents the gap as very large without a figure. |
| 「Industry insiders have long whispered…」 | Unverifiable narrative (anonymous source) | Contains a factual claim, "AWS is profitable": ✅ [Amazon annual report, segment results]. Whether that "subsidizes" retail depends on interpretation, so that part is opinion. |
| 「This same pattern will define…」 | Prediction | Not verified. |
| 「Smaller AI startups… walking dead…」 | Analysis or opinion | Rhetorical device: emotional wording, "walking dead". "One prominent VC told me" is an anonymous source. |
