# specialties-service

specialties-service — domain: providers

- **Port:** 8203
- **Language:** Python 3.11 + Flask
- **Database:** `providers` (Postgres, table `specialties`)
- **Event bus:** Kafka

## API

| Method    | Path                       |
|-----------|----------------------------|
| GET       | `/api/specialties/`          |
| POST      | `/api/specialties/`          |
| GET       | `/api/specialties/<id>`      |
| PUT/PATCH | `/api/specialties/<id>`      |
| DELETE    | `/api/specialties/<id>`      |
| GET       | `/health`                  |
| GET       | `/ready`                   |

## Events

**Publishes:** (none)
**Subscribes:** (none)

## HTTP peer dependencies

- `providers-service`
- `audit-log-service`

## Local dev

```bash
pip install -e ../../libs/py-healthcare-common
pip install -r requirements.txt
cp .env.example .env
(cd ../../infra && docker compose up -d postgres kafka kafka-init)
python -m app.main
```

## Tests

```bash
pytest
```
