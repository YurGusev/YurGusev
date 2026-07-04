<h1 align="center">Yura Gusev</h1>

<p align="center">
  Python / ML Engineer focused on data pipelines, trading research infrastructure,
  backend automation, and production-minded developer tooling.
</p>

<p align="center">
  <a href="https://github.com/YurGusev">
    <img src="https://img.shields.io/badge/GitHub-YurGusev-181717?style=flat-square&logo=github&logoColor=white" alt="GitHub" />
  </a>
  <a href="https://github.com/YurGusev?tab=repositories">
    <img src="https://img.shields.io/badge/Portfolio-Repositories-2563EB?style=flat-square&logo=github&logoColor=white" alt="Repositories" />
  </a>
  <a href="https://github.com/YurGusev/YurGusev/tree/main/portfolio">
    <img src="https://img.shields.io/badge/Case_Studies-Portfolio-0F766E?style=flat-square&logo=readme&logoColor=white" alt="Case studies" />
  </a>
</p>

---

## About

I build practical software around data, machine learning, and automation. My work is centered on reliable Python systems: market data ingestion, dataset preparation, feature engineering, offline model training, APIs, tests, and documentation that engineers can actually use.

Current focus:

- ML-first trading research infrastructure for MOEX/Finam workflows.
- Reproducible dataset and feature pipelines for offline training.
- Backend services with clear boundaries, typed configuration, migrations, and health checks.
- Engineering discipline around tests, linters, type checking, CI-ready structure, and technical documentation.

I am also studying Data Science at SENATOROVAI and use GitHub as a portfolio for engineering practice, research notes, and project work.

---

## Tech Stack

<p>
  <img src="https://img.shields.io/badge/Python-3.12-3776AB?style=for-the-badge&logo=python&logoColor=white" alt="Python" />
  <img src="https://img.shields.io/badge/FastAPI-Backend-009688?style=for-the-badge&logo=fastapi&logoColor=white" alt="FastAPI" />
  <img src="https://img.shields.io/badge/PostgreSQL-Data-4169E1?style=for-the-badge&logo=postgresql&logoColor=white" alt="PostgreSQL" />
  <img src="https://img.shields.io/badge/SQLAlchemy-ORM-D71F00?style=for-the-badge&logo=sqlalchemy&logoColor=white" alt="SQLAlchemy" />
  <img src="https://img.shields.io/badge/Redis-Cache-DC382D?style=for-the-badge&logo=redis&logoColor=white" alt="Redis" />
  <img src="https://img.shields.io/badge/RabbitMQ-Queues-FF6600?style=for-the-badge&logo=rabbitmq&logoColor=white" alt="RabbitMQ" />
  <img src="https://img.shields.io/badge/Docker-Infra-2496ED?style=for-the-badge&logo=docker&logoColor=white" alt="Docker" />
  <img src="https://img.shields.io/badge/Pandas-Data-150458?style=for-the-badge&logo=pandas&logoColor=white" alt="Pandas" />
  <img src="https://img.shields.io/badge/NumPy-Numerics-013243?style=for-the-badge&logo=numpy&logoColor=white" alt="NumPy" />
  <img src="https://img.shields.io/badge/Polars-DataFrame-CD792C?style=for-the-badge&logo=polars&logoColor=white" alt="Polars" />
  <img src="https://img.shields.io/badge/PyTorch-ML-EE4C2C?style=for-the-badge&logo=pytorch&logoColor=white" alt="PyTorch" />
  <img src="https://img.shields.io/badge/scikit--learn-ML-F7931E?style=for-the-badge&logo=scikitlearn&logoColor=white" alt="scikit-learn" />
  <img src="https://img.shields.io/badge/MLflow-Tracking-0194E2?style=for-the-badge&logo=mlflow&logoColor=white" alt="MLflow" />
  <img src="https://img.shields.io/badge/pytest-Tests-0A9EDC?style=for-the-badge&logo=pytest&logoColor=white" alt="pytest" />
  <img src="https://img.shields.io/badge/Ruff-Linting-D7FF64?style=for-the-badge&logo=ruff&logoColor=black" alt="Ruff" />
  <img src="https://img.shields.io/badge/mypy-Typing-2A6DB2?style=for-the-badge&logo=python&logoColor=white" alt="mypy" />
</p>

---

## Selected Work

| Project | Scope | Stack |
|---|---|---|
| [AI Trading Bot](portfolio/ai-trading-bot.md) | Private research and engineering project for MOEX/Finam trading infrastructure: ingestion, features, dataset artifacts, offline training, validation, and API services. | Python, FastAPI, PostgreSQL, Redis, RabbitMQ, PyTorch, pandas |
| [Data Science Course Work](https://github.com/YurGusev/DataScientist_at_SENATOROVAI) | Learning portfolio and structured Data Science practice. | Python, notebooks, data analysis |
| [Data Science From Scratch](https://github.com/YurGusev/Data-Science-For-Beginners-from-scratch-course) | Forked educational repository used for foundational DS practice and exercises. | Python |

Most production-style work is summarized as case studies because some repositories are private or client-facing.

---

## Case Study: AI Trading Bot

**Business goal:** create a maintainable foundation for trading research and future automation on the Russian market.

**Engineering challenge:** trading ML work requires clean historical data, reproducible datasets, leakage-aware features, model validation, and operational services before live execution can be considered.

**Solution delivered:**

- Market data ingestion for MOEX/AlgoPack-style workflows.
- PostgreSQL-backed storage for raw and normalized market data.
- Feature snapshots with schema hashing and no-leakage audit metadata.
- Dataset artifact pipeline for offline ML training, including sharded datasets for multi-year ranges.
- PyTorch offline training CLI with experiment manifests, metrics, registry metadata, and report artifacts.
- FastAPI health endpoints and Docker-based local infrastructure.
- Test suite around data, features, labels, model training, backtesting, validation, and API health.

**Impact:** the project turns trading model research from ad hoc scripts into a reproducible engineering workflow with explicit data lineage, repeatable training commands, and safety gates before model promotion.

[Read the full case study](portfolio/ai-trading-bot.md)

---

## Engineering Principles

- I document design decisions and operational commands, not only code.
- I prefer reproducible pipelines over manual notebooks for critical workflows.
- I keep risk-heavy systems behind dry-run, paper, validation, and preflight gates.
- I treat tests, type checks, linting, migrations, and docs as part of the product.

---

## GitHub Stats

<p align="center">
  <img height="165" src="https://github-stats-extended.vercel.app/api?username=YurGusev&show_icons=true&theme=github_dark&hide_border=true" alt="GitHub stats" />
  <img height="165" src="https://github-stats-extended.vercel.app/api/top-langs/?username=YurGusev&layout=compact&langs_count=8&theme=github_dark&hide_border=true" alt="Top languages" />
</p>

<p align="center">
  <img src="https://streak-stats.demolab.com?user=YurGusev&theme=github-dark-blue&hide_border=true" alt="GitHub streak" />
</p>

<p align="center">
  <img src="https://github-profile-trophy.vercel.app/?username=YurGusev&theme=flat&no-frame=true&no-bg=true&margin-w=8&row=1&column=6" alt="GitHub trophies" />
</p>

---

## Portfolio Maintenance

This profile is intentionally concise. Supporting materials live here:

- [AI Trading Bot case study](portfolio/ai-trading-bot.md)
- [Repository presentation plan](portfolio/repository-descriptions.md)
- [Reusable repository README template](templates/repository-readme-template.md)

