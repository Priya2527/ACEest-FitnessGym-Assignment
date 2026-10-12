# ACEest Fitness & Gym — DevOps Assignment

A starter Flask API demonstrating Git/GitHub, Pytest, Docker, GitHub Actions, and Jenkins.

## Features

- `GET /` — welcome message
- `GET /health` — health check
- `GET /members` — list members
- `POST /members` — add a member

**Demo limitation:** Member data is stored in memory and resets when the application restarts.

## Requirements

- Python 3.12 (Python 3.10+ should also work)
- Git
- Docker Desktop on Windows
- GitHub account
- Jenkins server/agent with Python 3, Git, and Docker available

## Local setup (VS Code PowerShell)

```powershell
python -m venv .venv
.\.venv\Scripts\Activate.ps1
python -m pip install --upgrade pip
pip install -r requirements.txt
```

If PowerShell blocks activation, use the environment's Python directly:

```powershell
.\.venv\Scripts\python.exe -m pip install -r requirements.txt
```

## Run the app

```powershell
python app.py
```

Open <http://127.0.0.1:5000/>. Stop with `Ctrl+C`.

## Run tests

```powershell
python -m pytest -v
```

## Docker

Make sure Docker Desktop is running:

```powershell
docker build -t aceest-fitness .
docker run --rm -p 5000:5000 aceest-fitness
```

Open <http://127.0.0.1:5000/>.

## GitHub Actions

`.github/workflows/main.yml` runs on every push and pull request. It checks syntax, runs Ruff linting and Pytest, and builds the Docker image. Check the repository's Actions tab for results.

## Jenkins

The `Jenkinsfile` checks out the repository, installs dependencies, validates syntax, runs tests, and builds a Docker image. Configure a Jenkins Pipeline job to use this repository and `Jenkinsfile`.

This Jenkinsfile uses Unix shell steps (`sh`) and is intended for a Linux Jenkins agent with Python 3, Git, and Docker available. Adapt it if your instructor provides a different environment.

## Git workflow

The project is maintained in a public GitHub repository.

Repository: https://github.com/Priya2527/ACEest-FitnessGym-Assignment

To download the project:

```bash
git clone https://github.com/Priya2527/ACEest-FitnessGym-Assignment.git
cd ACEest-FitnessGym-Assignment
```

To submit future changes:

```bash
git add .
git commit -m "Describe the changes"
git push origin main
```

## Screenshots to collect

1. Flask app running in the browser
2. Successful Pytest output
3. Docker image build and running container
4. Repository files on GitHub
5. Successful GitHub Actions run
6. Successful Jenkins build

## Limitations

This is a learning starter project, not a production membership system. It has no database, authentication, or persistent storage.

