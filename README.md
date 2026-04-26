<p align="center">
  <img src="https://capsule-render.vercel.app/api?type=waving&color=0:050d1a,50:1A5276,100:00D4FF&height=220&section=header&text=IT%20Service%20Desk&fontSize=52&fontColor=ffffff&fontAlignY=38&desc=Strategic%20Analytics%20%26%20Operational%20Excellence&descAlignY=58&descSize=18&animation=fadeIn" width="100%"/>
</p>

<p align="center">
  <img src="https://readme-typing-svg.demolab.com?font=JetBrains+Mono&size=22&duration=2500&pause=800&color=00D4FF&center=true&vCenter=true&multiline=true&width=700&height=80&lines=Python+Engineering+%E2%86%92+Power+BI+Dashboard;Transforming+raw+ticket+logs+into+business+intelligence" alt="Typing SVG"/>
</p>

<br/>

<p align="center">
  <img src="https://img.shields.io/badge/Tickets%20Analyzed-100%2B-00D4FF?style=for-the-badge&logo=databricks&logoColor=white&labelColor=050d1a"/>
  &nbsp;
  <img src="https://img.shields.io/badge/SLA%20Compliance-68%25-2E86C1?style=for-the-badge&logo=checkmarx&logoColor=white&labelColor=050d1a"/>
  &nbsp;
  <img src="https://img.shields.io/badge/Visualizations-7-5DADE2?style=for-the-badge&logo=powerbi&logoColor=white&labelColor=050d1a"/>
  &nbsp;
  <img src="https://img.shields.io/badge/Python%20Phases-4-3776AB?style=for-the-badge&logo=python&logoColor=white&labelColor=050d1a"/>
</p>

<br/>

---

## 🖥️ Executive Summary

<img align="right" src="https://capsule-render.vercel.app/api?type=rect&color=0:1A5276,100:00D4FF&height=2&width=300&section=header" width="300"/>

In the modern enterprise, the **IT Service Desk** serves as the primary interface between technology and human productivity. This project delivers a complete analytical framework that transforms raw ticket logs into actionable business intelligence.

By combining the **deep processing power of Python** with the **interactive storytelling of Power BI**, this solution identifies operational bottlenecks, rewards high performance, and mitigates the risk of SLA breaches before they escalate.

<div align="center">

| 🎯 Objective | 🔬 Methodology | 📈 Outcome |
|:---:|:---:|:---:|
| Identify SLA breach patterns | Python temporal engineering + SLA logic | 68% compliance baseline with gap analysis |
| Map technician performance | Scatter quadrant analysis | Hero / Overloaded / Underused / Training |
| Forecast workload trends | 7-day rolling average smoothing | Long-term capacity planning intelligence |

</div>

<br/>

<p align="center">
  <img src="https://capsule-render.vercel.app/api?type=rect&color=gradient&customColorList=0,2,2,5,30&height=3&section=header&reversal=false" width="100%"/>
</p>

---

## 🛠️ Technical Stack

<p align="center">
  <img src="https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white"/>
  &nbsp;
  <img src="https://img.shields.io/badge/Pandas-150458?style=for-the-badge&logo=pandas&logoColor=white"/>
  &nbsp;
  <img src="https://img.shields.io/badge/NumPy-013243?style=for-the-badge&logo=numpy&logoColor=white"/>
  &nbsp;
  <img src="https://img.shields.io/badge/Power%20BI-F2C811?style=for-the-badge&logo=powerbi&logoColor=black"/>
  &nbsp;
  <img src="https://img.shields.io/badge/Jupyter-F37626?style=for-the-badge&logo=jupyter&logoColor=white"/>
  &nbsp;
  <img src="https://img.shields.io/badge/Excel-217346?style=for-the-badge&logo=microsoftexcel&logoColor=white"/>
  &nbsp;
  <img src="https://img.shields.io/badge/SQLite-003B57?style=for-the-badge&logo=sqlite&logoColor=white"/>
</p>

<div align="center">

| Layer | Tool | Purpose |
|:---|:---:|:---|
| 🐍 **Language** | Python 3.x | Data engineering & SLA automation |
| 📊 **Libraries** | Pandas, NumPy | Temporal processing & vectorized logic |
| 📈 **BI Tool** | Microsoft Power BI | Executive dashboard & visualization suite |
| 📁 **Data** | Excel (.xlsx) | Raw IT ticket logs |
| 📓 **Notebook** | Jupyter | EDA & feature engineering |
| 📄 **Docs** | Word (.docx) | Step-by-step implementation guide |

</div>

<br/>

<p align="center">
  <img src="https://capsule-render.vercel.app/api?type=rect&color=gradient&customColorList=0,2,2,5,30&height=3&section=header" width="100%"/>
</p>

---

## 🔬 Problem Statement

<p align="center">
  <img src="https://readme-typing-svg.demolab.com?font=JetBrains+Mono&size=16&duration=3000&pause=2000&color=00D4FF&center=true&vCenter=true&width=800&lines=How+can+IT+ticket+data+uncover+workload+trends%2C+performance+patterns%2C+and+drive+efficiency%3F" alt="Problem Statement"/>
</p>

---

## ⚙️ Phase 1 — Python Data Engineering Foundation

<p align="center">
  <img src="https://readme-typing-svg.demolab.com?font=JetBrains+Mono&size=13&duration=2000&pause=500&color=5DADE2&center=true&vCenter=true&width=700&lines=Phase+01%3A+Temporal+Engineering+%E2%86%92+Phase+02%3A+SLA+Automation+%E2%86%92+Phase+03%3A+Smoothing+%E2%86%92+Phase+04%3A+Severity" alt="Phases"/>
</p>

<details open>
<summary><b>🕐 Phase 1 — Advanced Temporal Engineering</b></summary>

<br/>

Raw date strings converted into high-precision `datetime` objects. **Resolution Days** calculated as the primary speed metric. Chronological integrity enforced by validating every resolved timestamp against its creation timestamp.

```python
import pandas as pd

df['created_at'] = pd.to_datetime(df['created_at'])
df['resolved_at'] = pd.to_datetime(df['resolved_at'])

# Validate chronological integrity
df = df[df['resolved_at'] > df['created_at']]

# Calculate resolution time in days
df['resolution_days'] = (df['resolved_at'] - df['created_at']).dt.total_seconds() / 86400
```

</details>

---

<details open>
<summary><b>⚖️ Phase 2 — Custom Vectorized SLA Automation Logic</b></summary>

<br/>

A **priority-weighted SLA system** engineered using NumPy — going far beyond standard reporting:

| Priority | SLA Window | Threshold |
|:---|:---:|:---:|
| 🔴 High | 24 hours | 1 day |
| 🟡 Medium | Standard window | 3 days |
| 🟢 Low | Broader window | 5 days |

```python
import numpy as np

conditions = [
    (df['priority'] == 'High')   & (df['resolution_days'] <= 1),
    (df['priority'] == 'Medium') & (df['resolution_days'] <= 3),
    (df['priority'] == 'Low')    & (df['resolution_days'] <= 5),
]
df['sla_met'] = np.select(conditions, [True, True, True], default=False)
```

</details>

---

<details open>
<summary><b>📉 Phase 3 — Advanced Statistical Smoothing</b></summary>

<br/>

A **7-day rolling average** calculated to separate random spikes from genuine shifts in organizational demand:

```python
daily_volume = df.groupby('date_created').size().reset_index(name='ticket_count')
daily_volume['rolling_avg_7d'] = daily_volume['ticket_count'].rolling(window=7).mean()
```

</details>

---

<details open>
<summary><b>🚨 Phase 4 — SLA Breach Severity Logic</b></summary>

<br/>

Not just *whether* a ticket failed SLA — but **how badly**. A severity distribution identifies the most critical process failures:

```python
sla_targets = {'High': 1, 'Medium': 3, 'Low': 5}
df['sla_target']         = df['priority'].map(sla_targets)
df['breach_severity_days'] = (df['resolution_days'] - df['sla_target']).clip(lower=0)
```

</details>

<br/>

<p align="center">
  <img src="https://capsule-render.vercel.app/api?type=rect&color=gradient&customColorList=0,2,2,5,30&height=3&section=header" width="100%"/>
</p>

---

## 📊 Phase 2 — Power BI Intelligence Suite

<p align="center">
  <img src="https://readme-typing-svg.demolab.com?font=JetBrains+Mono&size=13&duration=2500&pause=1000&color=00D4FF&center=true&vCenter=true&width=700&lines=7+Targeted+Visualizations+%E2%86%92+One+Executive+Dashboard" alt="Power BI"/>
</p>

---

### 📈 Visualization 1 — Time Series Trend Line Chart

> **How does ticket volume change over time, and when do peak workload periods occur?**

![Chart 1](images/chart1.png)

This line chart highlights daily volume fluctuations to detect **peak workload days** and low-activity periods — driving smarter staffing and resource allocation decisions.

---

### 🥧 Visualization 2 — Issue Distribution Pie Chart

> **What proportion of tickets belongs to each issue category?**

![Chart 2](images/chart2.png)

Hardware and Software issues **dominate the workload** — suggesting targeted automation or self-service portals in these areas would yield the highest ROI.

---

### 🎯 Visualization 3 — Technician Performance Scatter Plot

> **Who are the top and low performers across workload and resolution speed?**

![Chart 3](images/chart3.png)

The **centerpiece of the dashboard** — a quadrant scatter plot that segments every team member:

<div align="center">

| 🦸 Heroes | 🔥 Overloaded | 💤 Underused | 📚 Training |
|:---:|:---:|:---:|:---:|
| High volume + fast speed | High volume + slowing speed | Low volume = hidden capacity | Low speed = needs upskilling |
| **Reward & retain** | **Burnout risk — intervene** | **Redistribute work here** | **Target coaching** |

</div>

---

### 📉 Visualization 4 — Rolling Average Trend

> **What are the true long-term trends in ticket volume after smoothing daily noise?**

![Chart 4](images/chart4.png)

The 7-day rolling average reveals the **true trajectory** of the Service Desk — making it immediately clear whether efficiency is improving or workload is outpacing resources.

---

### ⚠️ Visualization 5 — SLA Breach Severity Distribution

> **How severe are SLA breaches, and how far do tickets exceed defined limits?**

![SLA Breach](images/chart5%20.png)

A unique histogram showing **frequency of late tickets grouped by days overdue** — focusing management on the long tail of severely delayed tickets posing the highest business risk.

---

### 📊 Visualization 6 — Priority Load Composition

> **How do different ticket priority levels contribute to each technician's workload?**

![Chart 6](images/chart6.png)

This stacked bar ensures senior technicians are focused on **critical business issues** and that workload distribution remains fair and balanced across the team.

---

### 📖 Visualization 7 — Storytelling Trend Chart

> **How can key events be highlighted to improve stakeholder communication?**

![Chart 7](images/chart7.png)

Annotations and visual markers highlight **peak periods, stable phases, and inflection points** — making insights immediately intuitive for non-technical stakeholders without deep analysis.

---

### 🖥️ Full Power BI Executive Dashboard

![Power BI Dashboard](images/powerbi.png)

<br/>

<p align="center">
  <img src="https://capsule-render.vercel.app/api?type=rect&color=gradient&customColorList=0,2,2,5,30&height=3&section=header" width="100%"/>
</p>

---

## 💡 Business Insights & Strategic Impact

<div align="center">

### 📌 SLA Compliance Rate

<img src="https://readme-typing-svg.demolab.com?font=JetBrains+Mono&size=42&duration=2000&pause=99999&color=00D4FF&center=true&vCenter=true&width=300&lines=68%25" alt="68%"/>

</div>

The analysis revealed a departmental SLA compliance rate of **68%**. While the team is highly productive, this indicates a critical service delivery gap affecting nearly **one-third of all requests** — providing data-backed justification to either increase headcount or implement AI-driven ticket triaging.

---

<div align="center">

### 📌 Aging Ticket Analysis

</div>

| Metric | Finding |
|:---|:---|
| ⚡ Average Resolution Time | Under **2 days** |
| 🐢 Long-Tail Outliers | Small percentage open **10+ days** |
| 🔍 Root Cause | Complex cross-departmental dependencies |
| 🛠️ Recommended Action | Executive intervention protocol for aging tickets |

---

<div align="center">

### 📌 Key Workload Findings

</div>

| Finding | Strategic Implication |
|:---|:---|
| Hardware + Software dominate ticket mix | Prime candidates for self-service portal investment |
| Overloaded technician quadrant identified | Burnout risk — proactive redistribution required |
| Weekly cycle confirmed in rolling average | Predictable demand → smarter pre-scheduled staffing |

<br/>

<p align="center">
  <img src="https://capsule-render.vercel.app/api?type=rect&color=gradient&customColorList=0,2,2,5,30&height=3&section=header" width="100%"/>
</p>

---

## 🧗 Challenges & Professional Growth

<div align="center">

| Challenge | Solution Applied |
|:---|:---|
| 🌐 Data quality across time zones and formats | Robust Python cleaning pipeline with datetime validation |
| 📋 Balancing technical depth with executive readability | High-level KPIs on dashboard + deep-dive interactive filters |
| 📐 SLA thresholds varying by priority tier | Custom vectorized NumPy conditions per priority level |
| 📊 Daily volatility obscuring true trends | 7-day rolling average smoothing applied pre-visualization |

</div>

<br/>

<p align="center">
  <img src="https://capsule-render.vercel.app/api?type=rect&color=gradient&customColorList=0,2,2,5,30&height=3&section=header" width="100%"/>
</p>

---

## 📁 File Structure

```
IT-SERVICE-DESK-PROJECT1/
│
├── 📊 dashboard/
│   └── dashboard.pbix           # Full Power BI interactive dashboard
│
├── 📁 data/
│   └── tickets.xlsx             # Raw IT support ticket dataset
│
├── 📄 docs/
│   └── guide.docx               # Step-by-step Power BI implementation guide
│
├── 🖼️ images/                   # chart1–7.png + powerbi.png
│
├── 📓 notebooks/                # Jupyter notebooks for Python EDA & engineering
│
└── 📋 README.md
```

---

## 📈 Strategic Conclusion

<p align="center">
  <img src="https://readme-typing-svg.demolab.com?font=JetBrains+Mono&size=14&duration=3000&pause=1500&color=00D4FF&center=true&vCenter=true&multiline=true&width=750&height=70&lines=More+than+reporting+the+past+%E2%80%94;providing+the+foresight+to+lead+a+high-performing+IT+team." alt="Conclusion"/>
</p>

By integrating the **rigorous engineering of Python** with the **visual clarity of Power BI**, this project transforms technical logs into a genuine strategic asset:

<div align="center">

| 🔍 Transparency | ⚡ Efficiency | 🛡️ Resilience |
|:---:|:---:|:---:|
| Full visibility into team performance and SLA gaps | Workload trends identified before they become crises | Severity-based breach monitoring protects business continuity |

</div>

The result is a more **resilient**, more **efficient**, and more **transparent** IT Service Desk — where technology supports the business rather than bottlenecking it.

<br/>

<p align="center">
  <img src="https://capsule-render.vercel.app/api?type=waving&color=0:00D4FF,50:1A5276,100:050d1a&height=140&section=footer&fontSize=16&fontColor=ffffff&animation=fadeIn" width="100%"/>
</p>

<p align="center">
  <img src="https://img.shields.io/badge/Built%20with-Python%20%7C%20Power%20BI%20%7C%20Pandas%20%7C%20NumPy-2E86C1?style=flat-square&labelColor=050d1a"/>
  &nbsp;
  <img src="https://img.shields.io/github/repo-size/Kushala125/IT-SERVICE-DESK-PROJECT1?color=00D4FF&style=flat-square&labelColor=050d1a"/>
  &nbsp;
  <img src="https://img.shields.io/github/last-commit/Kushala125/IT-SERVICE-DESK-PROJECT1?color=2E86C1&style=flat-square&labelColor=050d1a"/>
  &nbsp;
  <img src="https://img.shields.io/github/stars/Kushala125/IT-SERVICE-DESK-PROJECT1?color=00D4FF&style=flat-square&labelColor=050d1a"/>
</p>
