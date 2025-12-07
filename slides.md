<!--
RevealJS Markdown presentation
Save this as `index.md` (or the markdown file your RevealJS setup expects).
Make sure your RevealJS HTML loads the Markdown plugin and KaTeX/Highlight plugins.
-->

<!-- Theme + custom footer styling (optional when using Markdown with a wrapper HTML) -->
<style>
.reveal .footer {
  position: absolute;
  bottom: 12px;
  left: 24px;
  right: 24px;
  font-size: 14px;
  opacity: .75;
  display: flex;
  justify-content: space-between;
  align-items: center;
  gap: 12px;
}
.badge {
  padding: .2rem .5rem;
  border-radius: 999px;
  background: rgba(255,255,255,.08);
}
.email-box {
  margin-top: 0.5rem;
  padding: .5rem .75rem;
  border: 1px dashed #ccc;
  border-radius: 8px;
  background: rgba(255,255,255,0.02);
  font-size: 13px;
}
</style>

---

# Quarterly Earnings — Interactive Briefing

**Presenter:** Data Science Team  
**Contact:** <span class="badge">24f2001055@ds.study.iitm.ac.in</span>

<aside class="notes">
Welcome — quick intro. Tell stakeholders this deck is interactive: use ← → to navigate, press **S** for speaker view.
</aside>

---

## Agenda
1. Key Financial Highlights <span class="fragment"> (quick snapshot)</span>  
2. Pipeline to KPIs <span class="fragment"> (data & reproducibility)</span>  
3. Valuation formulas <span class="fragment"> (math + sensitivity)</span>  
4. Appendix: Code + Data access <span class="fragment"> (how we calculated metrics)</span>

<aside class="notes">
Reveal each agenda item using fragments. Keep verbal transitions short (15–30s each).
</aside>

---

## Key Financial Highlights

* <span class="fragment">**Revenue Growth:** +12% YoY</span>  
* <span class="fragment">**Net Profit Margin:** 15%</span>  
* <span class="fragment">**CET1 Ratio:** 13.1%</span>  
* <span class="fragment">**Active Customers:** +8%</span>

<aside class="notes">
Use fragments so each metric appears in sequence. After showing Revenue Growth, briefly explain drivers (pricing, volume, channel mix).
</aside>

---

## Pipeline to KPIs — Code (reproducible)

```python
# earnings_kpis.py
import pandas as pd

kpis = (
    pd.read_csv("data/earnings.csv")
      .groupby("quarter", as_index=False)
      .agg(revenue=("revenue", "sum"),
           net_income=("net_income", "sum"))
)

kpis["margin_pct"] = (kpis["net_income"] / kpis["revenue"]) * 100
print(kpis.round(2))
