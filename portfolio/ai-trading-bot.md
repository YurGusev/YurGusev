# Кейс: AI Trading Bot

Adaptive ML-first trading infrastructure для research, подготовки датасетов, offline model training и будущих execution workflows.

> Это инженерный кейс, а не инвестиционная рекомендация и не обещание торговой доходности.

## Контекст

ML-проекты в трейдинге быстро ломаются, если данные, признаки, метки, эксперименты и execution assumptions смешаны в notebooks или одноразовых скриптах. Цель проекта - построить контролируемую research-систему, где каждый этап явный, тестируемый и воспроизводимый.

## Бизнес-цель

Создать поддерживаемую платформу для strategy research под MOEX/Finam workflows:

- загружать и нормализовать рыночные данные;
- строить feature snapshots с point-in-time корректностью;
- собирать воспроизводимые training datasets;
- запускать offline model training с validation artifacts;
- подготовить систему к безопасным dry-run и paper-trading этапам.

## Инженерный контур

Репозиторий организован как Python-приложение с понятными модулями:

```text
src/trading_bot/
  api/          FastAPI service и health checks
  broker/       граница Finam client
  common/       config, logging, database helpers
  data/         ingestion, MOEX datasets, futures chains, queue workers
  execution/    execution service boundary
  features/     feature engine, artifacts, feature service
  labeling/     triple-barrier labels и trade simulation
  ml/           datasets, offline training, validation, backtesting, registry
  storage/      repositories и migrations
tests/          focused tests по всему pipeline
docs/           architecture, roadmap, pipeline и ML documentation
```

## Технические акценты

- Python 3.12 project managed with `uv`.
- FastAPI service с live и readiness health checks.
- PostgreSQL storage с migrations и repository boundaries.
- Redis и RabbitMQ для local infrastructure и ingestion queues.
- MOEX/AlgoPack-style historical ingestion workflows.
- Feature layer со schema hashes, shifted features, source timestamp tracking и leakage checks.
- Dataset artifact builder с tensors, trading targets, audit metadata, reports и sharded mode.
- Offline training CLI с PyTorch, metrics, experiment manifests, validation reports, registry entries и notebook reports.
- Optional CatBoost и LightGBM baselines за explicit flags.
- Test suite для data ingestion, storage, features, labels, datasets, training, validation, backtesting и API health.
- Quality tooling: pytest, mypy strict mode, Ruff, coverage, pre-commit, Bandit, pip-audit, MkDocs.

## Dataset Pipeline

DB dataset pipeline собирает воспроизводимый `TrainingDataset` artifact из PostgreSQL-backed market data.

Artifact содержит:

- feature tensors из versioned feature schemas;
- action labels: `FLAT`, `LONG`, `SHORT`;
- trading targets: success, expected R, result R, utility, MAE, MFE;
- sample IDs, timestamps, regimes и chronological split metadata.

Sharded dataset mode рассчитан на multi-year ranges при ограниченной памяти рабочей станции. Он записывает несколько dataset shards и общий manifest, позволяя обучаться в хронологическом порядке без загрузки всего датасета в RAM.

## Валидация и risk controls

Проект рассматривает обучение модели как gated workflow:

- dataset preflight блокирует пустые или некорректные train/validation/test splits;
- timestamps должны оставаться хронологическими;
- sample IDs не должны пересекаться между splits;
- NaN и Inf отклоняются до обучения;
- labels и trading targets валидируются перед training;
- feature scalers fit only on train split;
- validation и test data остаются chronological.

Такой дизайн намеренно консервативен, потому что trading systems требуют auditability до любой автоматизации.

## Коммерческая ценность

Кейс показывает способность:

- перевести неопределенную research-идею в структурированную software system;
- разделить data engineering, ML, API, storage и execution boundaries;
- строить repeatable pipelines вместо хрупких ручных workflows;
- проектировать safety gates для high-risk domains;
- поддерживать Python-кодовую базу с tests, docs и operational commands.

## Стек

Python, FastAPI, PostgreSQL, SQLAlchemy, Alembic, Redis, RabbitMQ, Docker, pandas, NumPy, Polars, PyArrow, PyTorch, scikit-learn, CatBoost, LightGBM, MLflow, Optuna, Evidently, pytest, mypy, Ruff, MkDocs.

## Статус

Private engineering project. Публичный профиль содержит case study и техническое резюме; видимость исходного кода можно изменить отдельно, когда репозиторий будет готов к публичному review.

