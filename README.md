# Data Engineering Pipeline — INE + Eurostat to Power BI

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/andreguichardd/Data-Engineering/blob/main/Entregable_2.ipynb)

**Python pipeline that extracts data from two public statistical APIs, joins them and pushes the result to Power BI.**
Built as part of the Executive Master in Big Data Science (Universidad de Navarra).

---

## Problem

Business teams often need indicators from different public sources combined in one place. This project builds a small, repeatable pipeline that pulls data from two official APIs, aligns them on a common time field and delivers an analysis-ready table to Power BI.

---

## Approach

1. **Extract (source A)** — Spanish quarterly GDP data from the **INE** web API (`requests`, JSON).
2. **Extract (source B)** — an indicator from **Eurostat** via the `eurostat` Python package.
3. **Transform** — aggregate both series to yearly values, clean types and missing values, and join them on `year`.
4. **Load** — convert the merged table to JSON and push it to a **Power BI push dataset** through the Power BI REST API.

---

## Tech Stack

```
Python    Pandas · Requests · eurostat
APIs      INE (Instituto Nacional de Estadística) · Eurostat · Power BI REST API
BI        Power BI Service
```

---

## How to Run

```bash
pip install pandas requests eurostat
jupyter notebook Entregable_2.ipynb
```

To load into Power BI, create a push (streaming) dataset in Power BI Service and paste its push URL where the notebook shows `<YOUR_POWER_BI_PUSH_URL>`.

---

## Project Structure

```
├── Entregable_2.ipynb   # Full pipeline: extract (INE, Eurostat), transform, load to Power BI
└── README.md
```
