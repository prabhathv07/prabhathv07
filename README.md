<h1 align="center">Hi, I'm Prabhath Vipparthi 👋</h1>

<p align="center">
  <b>MS Data Science · NJIT (GPA 3.7, May 2026)</b><br/>
  Data Engineer &nbsp;·&nbsp; Data Scientist &nbsp;·&nbsp; ML Engineer<br/>
  📍 Harrison, NJ &nbsp;·&nbsp; F-1 STEM OPT · Open to any US location
  <br/><br/>
  <a href="https://prabhathv07.github.io">Portfolio</a> &nbsp;·&nbsp;
  <a href="https://www.linkedin.com/in/prabhath-vipparthi-90544b225/">LinkedIn</a> &nbsp;·&nbsp;
  <a href="mailto:vipparthi.prabhathvinay23@gmail.com">Email</a>
</p>

<p align="center">
  <img src="https://komarev.com/ghpvc/?username=prabhathv07&color=blue&style=flat" alt="Profile Views"/>
</p>

---

## About Me

MS Data Science graduate from NJIT building end-to-end systems — not just models. My projects ship with real pipelines, real data, real tests, and CI that actually runs the code.

I'm drawn to problems where the challenge is making the whole system reliable: cleaning bad data before it corrupts dashboards, wiring data-quality tests into the pipeline so failures are loud, running A/B tests with proper power analysis so the null result is a *confident* null rather than "we didn't find anything."

Graduated May 2026 · F-1 STEM OPT eligible · actively seeking full-time Data Engineer / Data Scientist / ML Engineer roles in the US.

---

## Featured Projects

### 🚕 [NYC Taxi Medallion Pipeline](https://github.com/prabhathv07/nyc-taxi-pipeline)
[![CI](https://github.com/prabhathv07/nyc-taxi-pipeline/actions/workflows/ci.yml/badge.svg)](https://github.com/prabhathv07/nyc-taxi-pipeline/actions/workflows/ci.yml)

Built a bronze → silver → gold medallion pipeline over **5.97M real NYC TLC Yellow Taxi trips (Jan–Feb 2024)**. PySpark cleaning job drops **528,764 bad rows (8.85%)** — bad fares, zero-distance, inverted timestamps, impossible occupancy. dbt builds 4 gold analytics marts and runs **19 data-quality tests, all passing**, wired into a daily Airflow DAG. CI runs the full pipeline end-to-end on every push.

- Manhattan accounts for **75% of revenue ($111.9M of $149.1M total)** — yellow taxis are a Manhattan + airport product
- Credit card generates **$128.3M (86%)** of revenue; airport-run hours (4–6 AM) carry **avg fares of $23–$28**
- Evening hours (5–9 PM) have the **highest tip rates (20%+)** despite lower individual fares

`PySpark` `dbt` `DuckDB` `Airflow` `Docker` `GitHub Actions` `Parquet`

---

### 📈 [FinSight — Pre-Market Intelligence Platform](https://github.com/prabhathv07/finsight)
[![CI](https://github.com/prabhathv07/finsight/actions/workflows/ci.yml/badge.svg)](https://github.com/prabhathv07/finsight/actions/workflows/ci.yml)

Production pre-market briefing system — **live at [finsight-api-7ghk.onrender.com](https://finsight-api-7ghk.onrender.com)**. Pulls **~130 symbols** (futures, macro, sector ETFs, mover universe, watchlist) every weekday morning via yfinance + Polygon.io fallback, computes RSI/MA/sparkline indicators, feeds a structured summary to **Gemini 2.5 Flash**, and emails the HTML briefing to confirmed subscribers. FastAPI service hosts the public dashboard and double opt-in signup flow.

- Every LLM call is logged to Postgres with the exact input, output, model name, latency, and status — model regression or latency spike shows up as a query, not a missing alert
- Double opt-in with per-address unsubscribe tokens; **two email backends** (Gmail SMTP local, Resend production) behind one interface
- **57 tests** across 8 modules, fully offline — SQLite + deterministic fake providers, zero network or API keys needed

`FastAPI` `PostgreSQL` `SQLAlchemy` `Gemini` `Docker` `Render` `GitHub Actions`

---

### 📊 [Olist SQL + A/B Experimentation](https://github.com/prabhathv07/olist-sql-experimentation)
[![CI](https://github.com/prabhathv07/olist-sql-experimentation/actions/workflows/ci.yml/badge.svg)](https://github.com/prabhathv07/olist-sql-experimentation/actions/workflows/ci.yml)

End-to-end SQL analysis and hypothesis test on **96,096 real Olist customers (99,441 orders, Sep 2016 – Oct 2018)**. Six DuckDB window-function queries, a monthly cohort retention matrix, and a two-proportion z-test on whether credit-card-first customers retain better than boleto-first customers.

- Observed repeat rates: credit card **2.07%** vs boleto **2.10%** (Δ = −0.03 pp, **p = 0.76**)
- Power analysis: the test can detect gaps ≥ **0.34 pp** at 80% power — the null is *confident*, not underpowered
- Bigger finding: only **3.1% of customers ever order a second time** — the retention opportunity is first→second purchase

`Python` `DuckDB` `SQL` `statsmodels` `scipy` `pandas` `matplotlib`

---

### ₿ [Crypto Market Analysis — Hadoop MapReduce](https://github.com/prabhathv07/crypto-hadoop-analysis)
[![CI](https://github.com/prabhathv07/crypto-hadoop-analysis/actions/workflows/ci.yml/badge.svg)](https://github.com/prabhathv07/crypto-hadoop-analysis/actions/workflows/ci.yml)

Three-job MapReduce pipeline on a **4-node AWS EC2 Hadoop cluster**, processing **2 GB of OHLCV tick data** across 100+ cryptocurrency trading pairs (Apr–Aug 2024). Computes volatility rankings, open-to-close performance, and cumulative volume with peak-volume timestamps in parallel across the cluster. Single reducer per job forces a **global** Top-10 rather than per-node local rankings.

`Java` `Apache Hadoop` `MapReduce` `HDFS` `AWS EC2`

---

### 🤖 [AI Digital Badge Classification](https://github.com/prabhathv07/AI_Digital_Badge_Classification)

Production NLP classification system delivered to NJIT's Learning & Development Initiative. **351-test validation suite, 100% pass rate, 100% accuracy** on 20 real-world badge submissions. Three-stage engine (Category → Type → Cognitive Level) with 130+ lexicon phrase patterns and 44 regex rules. Actively used by NJIT staff.

`FastAPI` `React` `spaCy` `SQLite` `Python` `TDD`

---

### 🧠 [StarCoder2 Self-Alignment Pipeline](https://github.com/prabhathv07/StarCoder2-Self-Alignment-Pipeline)

Multi-stage instruction-tuning dataset pipeline over **30K+ code samples** from The Stack v2. Syntax validation, static analysis, and LLM-based quality evaluation using vLLM for batched inference.

`Python` `vLLM` `Hugging Face` `PyTorch` `Tree-sitter`

---

### 🎲 [Cluedo AI — Logical Deduction Agent](https://github.com/prabhathv07/Cluedo-AI-Logical-Deduction-Agent)

Text-based Cluedo with an AI player using knowledge representation and constraint propagation. Zero external dependencies.

`Python`

---

## 🛠️ Tech Stack

**Languages**

![Python](https://img.shields.io/badge/Python-3776AB?style=flat&logo=python&logoColor=white)
![SQL](https://img.shields.io/badge/SQL-4479A1?style=flat&logo=mysql&logoColor=white)
![Java](https://img.shields.io/badge/Java-ED8B00?style=flat&logo=openjdk&logoColor=white)
![TypeScript](https://img.shields.io/badge/TypeScript-3178C6?style=flat&logo=typescript&logoColor=white)
![R](https://img.shields.io/badge/R-276DC3?style=flat&logo=r&logoColor=white)

**Data Engineering**

![PySpark](https://img.shields.io/badge/PySpark-E25A1C?style=flat&logo=apachespark&logoColor=white)
![dbt](https://img.shields.io/badge/dbt-FF694B?style=flat&logo=dbt&logoColor=white)
![DuckDB](https://img.shields.io/badge/DuckDB-FFF000?style=flat&logo=duckdb&logoColor=black)
![Airflow](https://img.shields.io/badge/Airflow-017CEE?style=flat&logo=apacheairflow&logoColor=white)
![Hadoop](https://img.shields.io/badge/Hadoop-66CCFF?style=flat&logo=apachehadoop&logoColor=black)
![Parquet](https://img.shields.io/badge/Parquet-50ABF1?style=flat&logo=apacheparquet&logoColor=white)

**ML / Data Science**

![PyTorch](https://img.shields.io/badge/PyTorch-EE4C2C?style=flat&logo=pytorch&logoColor=white)
![scikit-learn](https://img.shields.io/badge/scikit--learn-F7931E?style=flat&logo=scikit-learn&logoColor=white)
![Hugging Face](https://img.shields.io/badge/HuggingFace-FFD21E?style=flat&logo=huggingface&logoColor=black)
![statsmodels](https://img.shields.io/badge/statsmodels-3C3C3C?style=flat)
![spaCy](https://img.shields.io/badge/spaCy-09A3D5?style=flat)
![pandas](https://img.shields.io/badge/pandas-150458?style=flat&logo=pandas&logoColor=white)

**Infrastructure**

![Docker](https://img.shields.io/badge/Docker-2496ED?style=flat&logo=docker&logoColor=white)
![AWS](https://img.shields.io/badge/AWS_EC2-232F3E?style=flat&logo=amazon-aws&logoColor=white)
![GitHub Actions](https://img.shields.io/badge/GitHub_Actions-2088FF?style=flat&logo=github-actions&logoColor=white)
![PostgreSQL](https://img.shields.io/badge/PostgreSQL-4169E1?style=flat&logo=postgresql&logoColor=white)
![FastAPI](https://img.shields.io/badge/FastAPI-009688?style=flat&logo=fastapi&logoColor=white)

---

## 📊 GitHub Stats

<p align="center">
  <img src="https://github-readme-stats.vercel.app/api?username=prabhathv07&show_icons=true&theme=dark&hide_border=true&count_private=true&include_all_commits=true" height="165"/>
  <img src="https://github-readme-stats.vercel.app/api/top-langs/?username=prabhathv07&layout=compact&theme=dark&hide_border=true&langs_count=8" height="165"/>
</p>

---

## 📬 Let's Connect

Actively seeking **Data Engineer**, **Data Scientist**, and **ML Engineer** roles. Graduated May 2026 · F-1 STEM OPT (no sponsorship needed) · open to any US location.

- 🌐 [Portfolio](https://prabhathv07.github.io)
- 🔗 [LinkedIn](https://www.linkedin.com/in/prabhath-vipparthi-90544b225/)
- 📧 [vipparthi.prabhathvinay23@gmail.com](mailto:vipparthi.prabhathvinay23@gmail.com)
