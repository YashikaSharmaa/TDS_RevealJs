# Quarterly Earnings Report — RevealJS

<style>
.reveal .footer {
  position: absolute;
  bottom: 12px;
  left: 24px;
  right: 24px;
  font-size: 18px;
  opacity: .7;
  display: flex;
  justify-content: space-between;
}
.badge {
  padding: .2rem .5rem;
  border-radius: 999px;
  background: rgba(255,255,255,.12);
}
.email-box {
  margin-top: 1.5rem;
  padding: .75rem 1rem;
  border: 2px dashed #ccc;
  border-radius: 12px;
  background: rgba(255,255,255,0.05);
}
</style>

---

# Quarterly Earnings Report

### 24f2001055@ds.study.iitm.ac.in

**Interactive stakeholder briefing**

**Email:** [24f2001055@ds.study.iitm.ac.in](mailto:24f2001055@ds.study.iitm.ac.in)

Welcome everyone. This interactive deck showcases our Q-on-Q performance and highlights.  
Use **right/left** keys to navigate; press **S** to open speaker view with presenter notes.

---

## Contact

**Email:** 24f2001055@ds.study.iitm.ac.in

Provide direct contact information before diving into financial details.

---

## Key Financial Highlights

* **Revenue Growth:** +12% YoY  
* **Net Profit Margin:** 15%  
* **CET1 Ratio:** 13.1%  
* **Active Customers:** +8%

Reveal each metric gradually to maintain focus. Mention revenue drivers and cost discipline sustaining margins.

---

## Pipeline to KPIs (Example)

```python
import pandas as pd

kpis = (
    pd.read_csv("earnings.csv")
      .groupby(["quarter"]).agg(
          revenue=("revenue", "sum"),
          net_income=("net_income", "sum"),
      )
)

kpis["margin"] = (kpis["net_income"] / kpis["revenue"]) * 100
print(kpis.round(2))
