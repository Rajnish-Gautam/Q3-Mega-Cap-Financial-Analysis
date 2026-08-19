# Q3 Mega-Cap Financial Analysis

## Overview

A Python-based financial analysis framework comparing six major U.S. companies using quarterly SEC filing data.

The project combines **financial strength, YOY momentum, earnings trajectory, and sensitivity analysis** to create a multi-factor ranking of the companies.

The analysis focuses on **Q3 FY2025 actual results compared with Q3 FY2024 results** for each company.

### Companies Analyzed

* Alphabet Inc.
* NVIDIA Corp.
* Microsoft Corp.
* Walmart Inc.
* Apple Inc.
* Meta Platforms, Inc.

---

## Key Results

| Rank | Company   | Financial Strength | YOY Momentum | Earnings Trajectory | Final Score | Classification   |
| ---: | --------- | -----------------: | -----------: | ------------------: | ----------: | ---------------- |
|    1 | Alphabet  |              0.817 |        0.720 |               0.767 |   **0.778** | Leader           |
|    2 | NVIDIA    |              0.600 |        0.860 |               0.883 |   **0.735** | Leader           |
|    3 | Microsoft |              0.733 |        0.400 |               0.500 |   **0.587** | Quality / Mature |
|    4 | Walmart   |              0.467 |        0.580 |               0.650 |   **0.537** | Growth           |
|    5 | Apple     |              0.600 |        0.200 |               0.333 |   **0.427** | Quality / Mature |
|    6 | Meta      |              0.283 |        0.240 |               0.367 |   **0.287** | Weak             |

---

## Methodology

The analysis follows a multi-stage financial ranking framework:

```text
SEC Financial Data
        ↓
Q3 FY2025 / Q3 FY2024 Fiscal Quarter Alignment
        ↓
Revenue / Net Income / Margin
        ↓
Financial Strength Score
        ↓
YOY Revenue / Net Income / Margin Change
        ↓
YOY Momentum Score
        ↓
Earnings Trajectory
        ↓
Composite Score
        ↓
Weight Sensitivity Analysis
        ↓
Final Ranking
```

## 1. Fiscal Quarter Alignment

The analysis compares **Q3 FY2025 with Q3 FY2024** for each company.

Because companies use different fiscal calendars, the exact dates of Q3 differ across companies. Therefore, the analysis identifies each company's fiscal reporting period rather than assuming that Q3 corresponds to the same calendar dates.

### NVIDIA Example

**Current period — Q3 FY2025**

July 29, 2024 → October 27, 2024

Revenue:

**$35.082B**

**Prior comparable period — Q3 FY2024**

July 31, 2023 → October 29, 2023

Revenue:

**$18.120B**

Therefore, NVIDIA's YOY comparison is:

**Q3 FY2025 vs Q3 FY2024**

The same principle is applied to all companies in the peer group.

---

## 2. Financial Strength

Financial Strength evaluates absolute quarterly performance using:

* Revenue
* Net Income
* Net Profit Margin

Each metric is ranked across the six-company peer group and converted into a normalized score.

The three scores are combined to produce the **Financial Strength Score**.

---

## 3. YOY Momentum

YOY Momentum evaluates the rate of change between **Q3 FY2025 and Q3 FY2024**.

### Revenue YOY Growth

```text
(Current Q3 FY2025 Revenue - Q3 FY2024 Revenue)
------------------------------------------------ × 100
             Q3 FY2024 Revenue
```

### Net Income YOY Growth

```text
(Current Q3 FY2025 Net Income - Q3 FY2024 Net Income)
------------------------------------------------------ × 100
                 Q3 FY2024 Net Income
```

### Margin Change

```text
Q3 FY2025 Net Margin - Q3 FY2024 Net Margin
```

Margin change is measured in **percentage points (pp)**.

---

## 4. Earnings Trajectory

Earnings Trajectory evaluates the direction and quality of earnings performance between **Q3 FY2024 and Q3 FY2025**.

It considers:

* Revenue growth
* Net income growth
* Margin movement

The framework classifies companies as:

### Accelerating

Positive earnings momentum supported by improving revenue, earnings and/or margins.

### Profitable Growth

Revenue and earnings are growing, but the trajectory is less aggressive than the strongest performers.

### Deteriorating

Earnings performance is weakening, particularly when declining net income and margin contraction offset revenue growth.

---

## 5. Final Composite Score

The final model combines three factors:

| Factor              | Weight |
| ------------------- | -----: |
| Financial Strength  |    50% |
| YOY Momentum        |    30% |
| Earnings Trajectory |    20% |

```text
Final Score =
    0.50 × Financial Strength
  + 0.30 × YOY Momentum
  + 0.20 × Earnings Trajectory
```

---

## Key Findings

### Alphabet — Overall Leader

Alphabet achieved the highest final score of **0.778**.

Its primary advantage is its strong Financial Strength Score of **0.817**, combined with positive YOY growth and an accelerating earnings trajectory.

### NVIDIA — Strongest Momentum

NVIDIA recorded the strongest growth profile between **Q3 FY2024 and Q3 FY2025**:

* Revenue YOY: **+93.61%**
* Net Income YOY: **+108.90%**
* Margin Change: **+4.03 pp**
* Earnings Trajectory Score: **0.883**

NVIDIA therefore represents the strongest momentum-driven company in the peer group.

### Microsoft — Quality / Mature

Microsoft combines strong absolute financial strength with more moderate recent YOY momentum.

### Walmart — Improving Growth

Walmart's absolute financial strength is more moderate, but its YOY momentum and earnings trajectory indicate improving performance.

### Apple — Strong Quality, Weak Momentum

Apple maintains relatively strong absolute financial characteristics but has comparatively weaker recent YOY momentum.

### Meta — Deteriorating Earnings Quality

Meta's revenue increased **26.25%**, while net income declined **82.73%** and margin contracted by **33.36 pp** between Q3 FY2024 and Q3 FY2025.

This demonstrates why revenue growth alone is insufficient when evaluating earnings quality.

---

## Sensitivity Analysis

The model was tested under different Financial Strength / YOY Momentum weighting assumptions:

* 70% / 30%
* 60% / 40%
* 50% / 50%
* 40% / 60%
* 30% / 70%

Alphabet and NVIDIA remained the two strongest companies across the tested weighting scenarios, while NVIDIA became increasingly competitive as greater weight was assigned to momentum.

The final ranking also remained unchanged after adding the Earnings Trajectory factor.

---

## Technology

* Python
* Pandas
* NumPy
* Matplotlib
* Jupyter Notebook
* SEC filing data
* Data normalization
* Multi-factor scoring
* Sensitivity analysis

---

## Project Structure

```text
Q3-Mega-Cap-Financial-Analysis/
│
├── Q3_Financial_Analysis.ipynb
├── README.md
├── data/
├── outputs/
└── requirements.txt
```

---

## Limitations

This is a financial-performance ranking framework and not an investment recommendation.

Current limitations include:

* Six-company peer group
* Q3 FY2025 as the current analysis period
* Q3 FY2024 as the YOY comparison period
* Relative scoring
* No valuation analysis
* No stock-price performance
* No DCF
* No balance-sheet risk scoring
* No free-cash-flow factor in the current model

---

## Disclaimer

This project is intended for educational and analytical purposes only.

The rankings represent the output of a predefined quantitative framework and should not be interpreted as investment advice or a recommendation to buy or sell securities.

---

## Author

**Rajnish Gautam**

Financial analysis and data analytics portfolio project combining equity research concepts with Python-based quantitative analysis.
