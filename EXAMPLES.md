# Example: One Paragraph, Before and After

> The paragraph below is fabricated for demonstration. It imitates a common style of online business writing. Company names are used only to make it feel realistic and do not represent real statements by those companies.

## The original

> Amazon's dominance in cloud computing reveals the fundamental playbook for tech monopolies: vertical integration plus relentless price cuts. Amazon has achieved gross margins that Microsoft and Google can only dream of. Industry insiders have long whispered that AWS profits subsidize Amazon's entire retail operation. This same pattern will define which AI companies survive the next decade. Smaller AI startups without their own infrastructure are essentially walking dead, as one prominent VC recently told me.

## What the tool returns (overview)

```
Analysis or opinion (business commentary).
Audit opinion: Qualified, 1 concept shift and 1 claim not confirmed. Checked on [date].
Factual claims: 3 (✅ 1 / ⚠️ 1 / ❌ 0 / 🔍 0 / ❓ 1)
Other issues: hidden premises 1 · selective presentation 0 · logic jumps 1 · rhetorical devices 2
The most important issues:
1. 「gross margins that Microsoft and Google can only dream of」: ⚠️ public filings give segment operating margins, not comparable gross margins.
2. 「This same pattern will define」: the step from "Amazon won cloud this way" to "this decides who survives in AI" is not stated. It assumes AI markets work like cloud infrastructure.
3. 「AWS profits subsidize Amazon's entire retail operation」: ❓ filings show AWS as a separate profitable segment; whether that is "subsidizing" retail depends on interpretation. The claim is attributed to anonymous "industry insiders".
These are only the most important. Reply "focused" to see them all.
```

## How each sentence was sorted

| Sentence | Category | Result |
|----------|----------|--------|
| 「Amazon's dominance in cloud computing reveals…」 | Fact + opinion | "Amazon leads cloud computing": ✅. "Reveals the fundamental playbook" is the author's interpretation. |
| 「Amazon has achieved gross margins…」 | Fact | ⚠️ Concept shift. Rhetoric: "can only dream of" inflates the comparison. |
| 「Industry insiders have long whispered…」 | Unverifiable narrative + fact | Anonymous source. The subsidy claim itself: ❓. |
| 「This same pattern will define…」 | Prediction | Not verified. |
| 「Smaller AI startups… walking dead…」 | Opinion + unverifiable narrative | "Walking dead" is emotional wording. "One prominent VC told me" is an anonymous source. |

---

In real use, every verification result also names the source it was checked against. Results here are illustrative.
