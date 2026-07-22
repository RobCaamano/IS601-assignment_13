# Module 14 - Complete BREAD Functionality for Calculations

## DockerHub Repo
[DockerHub Repo](https://hub.docker.com/repository/docker/robcaamano/601_module14)

## Screenshots

|| |
|---| --- |
| Browse | <img src="screenshots/browse_calculations.png" alt="Browse" width="900"/> |
| Read | <img src="screenshots/read_calculation.png" alt="Reade" width="900"/> |
| Edit | <img src="screenshots/edit_calculation.png" alt="Edit" width="900"/> |
| Add | <img src="screenshots/add_calculation.png" alt="Add" width="900"/> |
| Delete | <img src="screenshots/delete_calculation.png" alt="Delete" width="900"/> |
| GitHub Actions Workflow | <img src="screenshots/github_actions.png" alt="GitHub Actions Workflow" width="900"/> |
| Docker Hub Deployment | <img src="screenshots/dockerhub_deployment.png" alt="Docker Hub Deployment" width="900"/> |

## How to run tests locally

### Prerequisites
- A Postgres instance matching `DATABASE_URL` (see `app/config.py`, default `postgresql://postgres:postgres@localhost:5432/fastapi_db`). The `db` service in `docker-compose.yml` provides this:
```
docker-compose up -d db
```
- Playwright browsers (needed for the UI test fixtures in `tests/conftest.py`):
```
playwright install --with-deps chromium
```

### Running tests
```
# Full test suite as defined in pytest.ini
pytest

# Specific file
pytest -s -v tests/<type>/<file>

# Keep data after tests (skip table truncation/drop)
pytest --preserve-db

# Include tests marked @pytest.mark.slow (skipped by default)
pytest --run-slow

# Run only a specific marker (slow / fast / e2e)
pytest -m e2e
```

Coverage is collected automatically (`pytest.ini` sets `--cov=app`); an HTML report is written to `htmlcov/index.html` after each run.

## How to run UI

### Prerequisites
- Docker must be running. On Windows/WSL, make sure Docker Desktop is open and its WSL integration is enabled before continuing (`docker info` should succeed without errors).

### Start the app
```
docker-compose up -d
```

### Access the UI
Open [http://localhost:8000](http://localhost:8000) in your browser.

## Reflection
