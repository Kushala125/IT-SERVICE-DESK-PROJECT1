<div align="center">

<img src="https://readme-typing-svg.demolab.com?font=Courier+Prime&size=36&duration=3000&pause=1000&color=2E86C1&center=true&vCenter=true&width=900&lines=IT+Service+Desk+Strategic+Analytics;%26+Operational+Excellence" alt="Typing SVG" />

<br/>

![Tickets Analyzed](https://img.shields.io/badge/Tickets%20Analyzed-100%2B-2E86C1?style=for-the-badge&logo=databricks&logoColor=white)
![Python](https://img.shields.io/badge/Python-Data%20Engineering-3776AB?style=for-the-badge&logo=python&logoColor=white)
![Power BI](https://img.shields.io/badge/Power%20BI-Intelligence%20Suite-F2C811?style=for-the-badge&logo=powerbi&logoColor=black)
![Pandas](https://img.shields.io/badge/Pandas-Temporal%20Engineering-150458?style=for-the-badge&logo=pandas&logoColor=white)
![NumPy](https://img.shields.io/badge/NumPy-SLA%20Automation-013243?style=for-the-badge&logo=numpy&logoColor=white)

<br/>

> **A complete end-to-end analytical framework transforming raw IT ticket data into high-level business intelligence.**  
> Python data engineering → Power BI executive dashboard → Strategic operational insights.

---

</div>

## 🖥️ Executive Summary

In the modern enterprise, the **IT Service Desk** serves as the primary interface between technology and human productivity. This project delivers a complete analytical framework that transforms raw ticket logs into actionable business intelligence.

By combining the **deep processing power of Python** with the **interactive storytelling of Power BI**, this solution identifies operational bottlenecks, rewards high performance, and mitigates the risk of SLA breaches before they escalate.

<div align="center">

| 🎯 Objective | 🔬 Methodology | 📈 Outcome |
|:---:|:---:|:---:|
| Identify SLA breach patterns | Python temporal engineering + SLA logic | 68% compliance baseline with gap analysis |
| Map technician performance | Scatter quadrant analysis | Hero / Overloaded / Underused / Training segmentation |
| Forecast workload trends | 7-day rolling average smoothing | Long-term capacity planning intelligence |

</div>

---

## 🛠️ Technical Stack

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

---

## 🔬 Problem Statement

> **How can IT support ticket data be analyzed to uncover workload trends, identify performance patterns, and drive operational efficiency?**

---

## ⚙️ Phase 1 — Python Data Engineering Foundation

The intelligence of this project begins in the Python environment, where raw and often inconsistent logs are transformed into a structured analytical dataset across **four critical engineering phases**.

---

<details open>
<summary><b>🕐 1. Advanced Temporal Engineering</b></summary>

<br/>

Raw date strings were converted into high-precision `datetime` objects using Pandas. This enabled calculation of exact **Resolution Days** — the primary metric for measuring service speed.

Data integrity was enforced by validating that every resolution timestamp occurred **after** its creation timestamp, filtering out any chronological errors in the raw logs.

```python
import pandas as pd

df['created_at'] = pd.to_datetime(df['created_at'])
df['resolved_at'] = pd.to_datetime(df['resolved_at'])

# Validate chronological integrity
df = df[df['resolved_at'] > df['created_at']]

# Calculate resolution time
df['resolution_days'] = (df['resolved_at'] - df['created_at']).dt.total_seconds() / 86400
```

</details>

---

<details open>
<summary><b>⚖️ 2. Custom Vectorized SLA Automation Logic</b></summary>

<br/>

A **priority-weighted SLA system** was engineered using NumPy logic — going far beyond standard reporting. Each priority tier was evaluated against its own time window:

| Priority | SLA Window | Threshold |
|:---|:---:|:---:|
| 🔴 High | 24 hours | 1 day |
| 🟡 Medium | Standard window | 3 days |
| 🟢 Low | Broader window | 5 days |

This created a **binary pass/fail metric** per record, enabling the first accurate calculation of the departmental SLA compliance rate.

```python
import numpy as np

conditions = [
    (df['priority'] == 'High') & (df['resolution_days'] <= 1),
    (df['priority'] == 'Medium') & (df['resolution_days'] <= 3),
    (df['priority'] == 'Low') & (df['resolution_days'] <= 5),
]
df['sla_met'] = np.select(conditions, [True, True, True], default=False)
```

</details>

---

<details open>
<summary><b>📉 3. Advanced Statistical Smoothing</b></summary>

<br/>

To account for daily volatility of IT requests, a **7-day rolling average** of ticket volume was calculated. This technique — widely used at top-tier technology firms — helps leadership distinguish between a random spike and a genuine shift in organizational demand.

```python
daily_volume = df.groupby('date_created').size().reset_index(name='ticket_count')
daily_volume['rolling_avg_7d'] = daily_volume['ticket_count'].rolling(window=7).mean()
```

</details>

---

<details open>
<summary><b>🚨 4. SLA Breach Severity Logic</b></summary>

<br/>

Knowing that a ticket failed SLA is not enough — we must know **the degree of failure**. The delta between the target resolution time and actual resolution time was calculated to create a severity distribution identifying the most critical process failures.

```python
sla_targets = {'High': 1, 'Medium': 3, 'Low': 5}
df['sla_target'] = df['priority'].map(sla_targets)
df['breach_severity_days'] = df['resolution_days'] - df['sla_target']
df['breach_severity_days'] = df['breach_severity_days'].clip(lower=0)
```

</details>

---

## 📊 Phase 2 — Power BI Intelligence Suite

The frontend translates all Python-engineered metrics into an **interactive executive dashboard** through seven targeted visualization strategies.

---

### 📈 Visualization 1 — Time Series Trend Line Chart

> **How does ticket volume change over time, and when do peak workload periods occur?**

![Time Series Trend](images/chart1.png)

This line chart visualizes tickets created over time, highlighting daily volume fluctuations to detect **peak workload days** and low-activity periods. These insights directly inform staffing decisions and resource allocation during high-demand windows.

---

### 🥧 Visualization 2 — Issue Distribution Pie Chart

> **What proportion of tickets belongs to each issue category, and which issues are most frequent?**

![Issue Distribution](images/chart2.png)

This chart maps the proportional breakdown across issue categories — **Software, Hardware, Network, and Access**. Hardware and Software issues dominate the workload, suggesting that targeted automation or self-service portals in these areas would yield the highest ROI.

---

### 🎯 Visualization 3 — Technician Performance Scatter Plot

> **How do technicians compare in workload vs. resolution speed — and who are the top and low performers?**

![Technician Performance](images/chart3.png)

The **centerpiece of the dashboard**. This quadrant scatter plot segments every team member into one of four strategic groups:

<div align="center">

| 🦸 Heroes | 🔥 Overloaded | 💤 Underused | 📚 Training |
|:---:|:---:|:---:|:---:|
| High volume + fast speed | High volume + slowing speed | Low volume = hidden capacity | Low speed = needs upskilling |
| Reward & retain | Burnout risk — intervene now | Redistribute work here | Target coaching investment |

</div>

---

### 📉 Visualization 4 — Rolling Average Trend

> **What are the underlying long-term trends in ticket volume after smoothing daily noise?**

![Rolling Average](images/chart4.png)

Using the 7-day rolling average engineered in Python, this chart reveals the **true long-term trajectory** of the Service Desk — making it clear whether the department is becoming more efficient or whether workload is outpacing resources.

---

### ⚠️ Visualization 5 — SLA Breach Severity Distribution

> **How severe are SLA breaches, and how far do tickets exceed their defined limits?**

![SLA Breach](images/chart5%20.png)

A unique histogram showing the **frequency of late tickets grouped by days overdue**. Rather than simply counting breaches, this focuses management attention on the long tail of severely delayed tickets — those posing the highest risk to business continuity.

---

### 📊 Visualization 6 — Priority Load Composition (Stacked Bar)

> **How do different ticket priority levels contribute to each technician's workload?**

![Priority Load](images/chart6.png)

This stacked bar chart breaks down each technician's workload by **High / Medium / Low priority** tickets. It ensures work is distributed fairly and that senior technicians are focused on the most critical business issues.

---

### 📖 Visualization 7 — Storytelling Trend Chart

> **How can key workload events be highlighted to improve stakeholder communication?**

![Storytelling Chart](images/chart7.png)

This enhanced time series chart adds **annotations and visual markers** to highlight peak workload periods, stable phases, and inflection points — making insights immediately intuitive for non-technical stakeholders.

---

### 🖥️ Full Power BI Dashboard

![Power BI Dashboard](images/powerbi.png)

---

## 💡 Business Insights & Strategic Impact

<div align="center">

### 📌 SLA Compliance Rate — 68%

</div>

> The analysis revealed a departmental SLA compliance rate of **68%**. While the team is highly productive, this indicates a critical service delivery gap affecting nearly **one-third of all requests**.

This data-backed finding provides direct justification to either:
- **Increase headcount** during high-pressure periods, or
- **Implement AI-driven ticket triaging** to reduce first-response times

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

---

## 🧗 Challenges & Professional Growth

<div align="center">

| Challenge | Solution Applied |
|:---|:---|
| 🌐 Data quality across time zones and formats | Robust Python cleaning pipeline with datetime validation |
| 📋 Balancing technical depth with executive readability | High-level KPIs on dashboard + deep-dive filters for granular views |
| 📐 SLA thresholds varying by priority tier | Custom vectorized NumPy conditions per priority level |
| 📊 Daily volatility obscuring true trends | 7-day rolling average smoothing applied pre-visualization |

</div>

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
├── 🖼️ images/                   # All chart exports & dashboard screenshots
│
├── 📓 notebooks/                # Jupyter notebooks for Python EDA & engineering
│
└── 📋 README.md
```

---

## 📈 Strategic Conclusion

<div align="center">

> *"This project does more than report on the past —*  
> *it provides the foresight needed to manage a high-performing IT team."*

</div>

By integrating the **rigorous engineering of Python** with the **visual clarity of Power BI**, this project transforms technical logs into a genuine strategic asset:

<div align="center">

| 🔍 Transparency | ⚡ Efficiency | 🛡️ Resilience |
|:---:|:---:|:---:|
| Full visibility into team performance and SLA gaps | Workload trends identified before they become crises | Severity-based breach monitoring protects business continuity |

</div>

The result is a more **resilient**, more **efficient**, and more **transparent** IT Service Desk — where technology supports the business rather than bottlenecking it.

---

<div align="center">

**Built with 🖥️ data engineering, 📊 visual intelligence, and ⚙️ operational strategy**

![GitHub repo size](https://img.shields.io/github/repo-size/Kushala125/IT-SERVICE-DESK-PROJECT1?color=2E86C1&style=flat-square)
![GitHub last commit](https://img.shields.io/github/last-commit/Kushala125/IT-SERVICE-DESK-PROJECT1?color=2E86C1&style=flat-square)
![GitHub stars](https://img.shields.io/github/stars/Kushala125/IT-SERVICE-DESK-PROJECT1?color=2E86C1&style=flat-square)

</div>
