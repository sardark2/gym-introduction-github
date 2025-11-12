OctoFit Tracker — quick dev README

This README shows how to create and use the Python virtual environment used by the OctoFit backend and how to run the dev environment.

Important notes
- When running automated agent commands in this repository, do not change directories; instead point commands at the target paths (e.g. `python3 -m venv octofit-tracker/backend/venv`).
- Forwarded ports used by the project (do not change): 8000 (public), 3000 (public), 27017 (private).

Create the virtual environment

```bash
python3 -m venv octofit-tracker/backend/venv
```

Install dependencies into the venv

```bash
# use the venv's pip directly (no global activation required):
./octofit-tracker/backend/venv/bin/python -m pip install --upgrade pip setuptools wheel
./octofit-tracker/backend/venv/bin/pip install -r octofit-tracker/backend/requirements.txt
```

Run the Django development server (example)

```bash
# from repository root; use the venv python and point to the backend project path
./octofit-tracker/backend/venv/bin/python -m django runserver 0.0.0.0:8000
```

Troubleshooting
- If you see permission errors, ensure the venv was created with the same Python interpreter and that you have network access to download packages.
- For MongoDB-related features follow the project notes; use Django ORM where possible (do not run raw MongoDB scripts unless necessary).

Next steps
- Scaffold a Django project into `octofit-tracker/backend/` (I can do this for you and commit the scaffold to `build-octofit-app`).
- Add frontend startup docs for the React app in `octofit-tracker/frontend/`.
