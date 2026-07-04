<!-- GitHub profile README for YurGusev -->

<h1 align="center">Юрий Гусев</h1>

<p align="center">
  Python / ML Engineer: data pipelines, trading research infrastructure,
  backend automation и production-подход к инженерным задачам.
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

## Обо мне

Я занимаюсь практической разработкой на стыке Python, данных, машинного обучения и автоматизации. Основной фокус - надежные инженерные системы: загрузка и нормализация данных, подготовка датасетов, feature engineering, offline training, API, тесты и документация, с которой можно работать в команде.

Сейчас развиваю направление ML-first trading infrastructure: пайплайны рыночных данных, воспроизводимые обучающие выборки, offline-обучение моделей, валидация, backend-сервисы и подготовка к безопасным dry-run / paper-trading сценариям.

Что для меня важно в разработке:

- понятные границы между data engineering, ML, backend и execution-логикой;
- воспроизводимые пайплайны вместо разрозненных ручных скриптов;
- тесты, типизация, линтеры, миграции и документация как часть продукта;
- осторожный подход к рискованным доменам: preflight-gates, audit metadata, dry-run, validation first.

Также изучаю Data Science в SENATOROVAI и использую GitHub как портфолио инженерной практики, исследовательских заметок и проектной работы.

---

## Стек

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

## Избранные проекты

| Проект | Что показывает | Стек |
|---|---|---|
| [AI Trading Bot](portfolio/ai-trading-bot.md) | Private engineering project для trading research: ingestion, feature pipelines, dataset artifacts, offline training, validation и backend API. | Python, FastAPI, PostgreSQL, Redis, RabbitMQ, PyTorch, pandas |

Production-style работа оформлена в виде кейсов, потому что часть репозиториев приватная или связана с коммерческим контекстом.

---

## Кейс: AI Trading Bot

**Цель:** создать поддерживаемую инженерную основу для trading research и будущей автоматизации на российском рынке.

**Проблема:** ML-задачи в трейдинге быстро становятся хаотичными без чистых исторических данных, воспроизводимых датасетов, leakage-aware признаков, валидации моделей и операционных safety-gates.

**Что реализовано:**

- загрузка рыночных данных для MOEX/AlgoPack-style workflows;
- PostgreSQL-хранилище для raw и normalized market data;
- feature snapshots со schema hash и no-leakage audit metadata;
- pipeline сборки dataset artifacts для offline ML;
- sharded datasets для многолетних диапазонов и ограниченной памяти рабочей станции;
- PyTorch offline training CLI с experiment manifests, metrics, registry metadata и отчетными артефактами;
- FastAPI health endpoints и Docker-based local infrastructure;
- тесты вокруг data ingestion, storage, features, labels, datasets, training, validation, backtesting и API health.

**Результат:** проект переводит trading model research из набора ad hoc scripts в воспроизводимый инженерный workflow с явной lineage-информацией, повторяемыми командами обучения и safety gates перед model promotion.

[Читать полный кейс](portfolio/ai-trading-bot.md)

---

## Инженерные принципы

- Документировать решения и операционные команды, а не только код.
- Строить воспроизводимые пайплайны вместо ручных notebook-only процессов.
- Разделять исследовательскую, backend, storage, ML и execution-логику.
- Не пропускать рискованные изменения без dry-run, validation, tests и preflight checks.
- Поддерживать проект так, чтобы его мог быстро понять другой разработчик.

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

## Материалы портфолио

- [Кейс AI Trading Bot](portfolio/ai-trading-bot.md)
- [План оформления репозиториев](portfolio/repository-descriptions.md)
- [Шаблон README для репозитория](templates/repository-readme-template.md)
