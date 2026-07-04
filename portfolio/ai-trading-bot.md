# AI Trading Bot Case Study

Adaptive ML-first trading infrastructure for research, dataset preparation, offline model training, and future execution workflows.

> This is an engineering case study, not investment advice and not a promise of trading performance.

## Context

Trading ML projects fail quickly when data, features, labels, experiments, and execution assumptions are mixed together in notebooks or one-off scripts. The goal of this project is to build a controlled research system where every stage is explicit, testable, and repeatable.

## Business Goal

Create a maintainable platform for strategy research on MOEX/Finam workflows:

- ingest and normalize market data;
- build feature snapshots with point-in-time correctness;
- produce reproducible training datasets;
- run offline model training with validation artifacts;
- prepare the system for safe dry-run and paper-trading stages.

## Engineering Scope

The repository is structured as a Python application with clear modules:

```text
src/trading_bot/
  api/          FastAPI service and health checks
  broker/       Finam client boundary
  common/       config, logging, database helpers
  data/         ingestion, MOEX datasets, futures chains, queue workers
  execution/    execution service boundary
  features/     feature engine, artifacts, feature service
  labeling/     triple-barrier labels and trade simulation
  ml/           datasets, offline training, validation, backtesting, registry
  storage/      repositories and migrations
tests/          focused tests across the pipeline
docs/           architecture, roadmap, pipeline and ML documentation
```

## Technical Highlights

- Python 3.12 project managed with `uv`.
- FastAPI service with live and readiness health checks.
- PostgreSQL storage with migrations and repository boundaries.
- Redis and RabbitMQ for local infrastructure and ingestion queues.
- MOEX/AlgoPack-style historical ingestion workflows.
- Feature layer with schema hashes, shifted features, source timestamp tracking, and leakage checks.
- Dataset artifact builder with tensors, trading targets, audit metadata, reports, and sharded mode.
- Offline training CLI with PyTorch, metrics, experiment manifests, validation reports, registry entries, and notebook reports.
- Optional CatBoost and LightGBM baselines behind explicit flags.
- Test suite covering data ingestion, storage, features, labels, datasets, training, validation, backtesting, and API health.
- Quality tooling: pytest, mypy strict mode, Ruff, coverage, pre-commit, Bandit, pip-audit, MkDocs.

## Dataset Pipeline

The DB dataset pipeline builds a reproducible `TrainingDataset` artifact from PostgreSQL-backed market data.

The artifact contains:

- feature tensors from versioned feature schemas;
- action labels such as `FLAT`, `LONG`, and `SHORT`;
- trading targets such as success, expected R, result R, utility, MAE, and MFE;
- sample IDs, timestamps, regimes, and chronological split metadata.

The sharded dataset mode is designed for multi-year ranges on limited workstation memory. It writes multiple dataset shards plus a manifest and allows chronological training without materializing the whole dataset at once.

## Validation and Risk Controls

The project treats model training as a gated workflow:

- dataset preflight blocks empty or invalid train/validation/test splits;
- timestamps must remain chronological;
- sample IDs must not leak across splits;
- NaN and Inf values are rejected;
- labels and trading targets are validated before training;
- feature scalers are fitted on the train split only;
- validation and test data stay chronological.

This design is intentionally conservative because trading systems need auditability before automation.

## Commercial Value

The project demonstrates the ability to:

- translate an uncertain research idea into a structured software system;
- separate data engineering, ML, API, storage, and execution boundaries;
- build repeatable pipelines instead of fragile manual workflows;
- design safety gates for high-risk domains;
- maintain a real Python codebase with tests, docs, and operational commands.

## Stack

Python, FastAPI, PostgreSQL, SQLAlchemy, Alembic, Redis, RabbitMQ, Docker, pandas, NumPy, Polars, PyArrow, PyTorch, scikit-learn, CatBoost, LightGBM, MLflow, Optuna, Evidently, pytest, mypy, Ruff, MkDocs.

## Status

Private engineering project. Public profile contains the case study and technical summary; source code visibility can be changed separately when the repository is ready for public review.

