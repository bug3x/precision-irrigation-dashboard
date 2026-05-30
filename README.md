```
precision-irrigation-dashboard/
├── .github/
│   ├── workflows/              # GitHub Actions CI/CD pipeline YAML files
│   │   ├── ci.yml              # runs on every push / PR: lint + test
│   │   └── deploy.yml          # runs on merge to main: build + deploy
│   ├── ISSUE_TEMPLATE/
│   │   ├── bug_report.md
│   │   └── feature_request.md
│   └── pull_request_template.md
├── firmware/                   # Sprint 1 — ESP32 C++ PlatformIO project
│   ├── src/
│   │   └── main.cpp
│   ├── include/
│   │   └── config.h
│   ├── test/
│   │   └── test_calibration.cpp
│   └── platformio.ini
├── backend/                    # Sprint 2 — Python FastAPI service
│   ├── app/
│   │   ├── api/                # HTTP route handlers only
│   │   │   ├── __init__.py
│   │   │   ├── sensor_readings.py
│   │   │   ├── fields.py
│   │   │   └── irrigation.py
│   │   ├── services/           # business logic (ET calc, decision engine)
│   │   │   ├── __init__.py
│   │   │   ├── et_calculator.py
│   │   │   ├── irrigation_engine.py
│   │   │   ├── mqtt_listener.py
│   │   │   └── weather_client.py
│   │   ├── db/                 # database models and session management
│   │   │   ├── __init__.py
│   │   │   ├── models.py
│   │   │   ├── session.py
│   │   │   └── migrations/     # Alembic migration files
│   │   ├── schemas/            # Pydantic request/response schemas
│   │   │   ├── __init__.py
│   │   │   ├── sensor.py
│   │   │   └── irrigation.py
│   │   ├── core/               # config, logging, startup
│   │   │   ├── __init__.py
│   │   │   ├── config.py
│   │   │   └── logging.py
│   │   └── main.py             # FastAPI app factory
│   ├── tests/
│   │   ├── conftest.py         # shared pytest fixtures
│   │   ├── unit/
│   │   │   ├── test_et_calculator.py
│   │   │   └── test_irrigation_engine.py
│   │   └── integration/
│   │       ├── test_sensor_api.py
│   │       └── test_mqtt_pipeline.py
│   ├── Dockerfile
│   └── requirements.txt
├── frontend/                   # Sprint 3 — React Vite dashboard
│   ├── src/
│   │   ├── components/         # reusable UI components
│   │   │   ├── gauges/
│   │   │   ├── charts/
│   │   │   └── map/
│   │   ├── pages/              # full page components
│   │   ├── hooks/              # custom React hooks
│   │   ├── lib/                # API client, utility functions
│   │   └── main.jsx
│   ├── tests/
│   ├── Dockerfile
│   └── package.json
├── simulation/                 # Sprint 4 — PCSE + EnKF module
│   ├── pcse_runner.py
│   ├── enkf.py
│   └── tests/
├── infra/                      # Docker Compose + deployment configs
│   ├── docker-compose.yml
│   ├── docker-compose.prod.yml
│   └── mosquitto.conf
├── docs/                       # Architecture diagrams, ADRs, API docs
│   ├── architecture.md
│   └── decisions/              # Architecture Decision Records
├── scripts/                    # Developer utility scripts
│   ├── seed_db.py
│   └── validate_et.py
├── .gitignore
├── .env.example                # Template for environment variables
├── README.md
└── CONTRIBUTING.md
```
