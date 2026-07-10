# AIT506 — Team Project

Shared workspace for AIT506 coursework. Notebooks are organized by week (`Week 1/`, `Week 2/`, ...).

## Prerequisites

- **Python 3.14** (this project was built against 3.14.6)
  - macOS: `brew install python@3.14`
- **git**

## Setup

The virtual environment is **not** committed to git (it's ~1.2 GB). Each teammate rebuilds it locally from `requirements.txt`.

```bash
# 1. Clone the repo and enter it
git clone <repo-url> AIT506-Team
cd AIT506-Team

# 2. Create the virtual environment
python3.14 -m venv .venv

# 3. Activate it
source .venv/bin/activate          # macOS / Linux
# .venv\Scripts\activate           # Windows (PowerShell)

# 4. Install dependencies
pip install -r requirements.txt
```

## Running JupyterLab

```bash
source .venv/bin/activate
jupyter lab
```

Then open the notebook for the week you're working on.

## Using the venv in PyCharm

Open the folder in PyCharm and set the project interpreter to `.venv/bin/python`
(Settings → Project → Python Interpreter → Add → Existing environment).

## Working together

- **Create a branch** for your work instead of committing straight to `main`:
  ```bash
  git checkout -b week3-yourname
  ```
  Open a pull request (or merge) when it's ready.
- **Notebooks & merge conflicts:** `.ipynb` files are JSON and conflict easily.
  Before committing, clear outputs (Kernel → Restart & Clear Outputs) to keep diffs small,
  and try not to edit the same notebook cell at the same time.
- **If you add a package,** update the shared list so teammates stay in sync:
  ```bash
  pip freeze > requirements.txt
  ```
  Commit the updated `requirements.txt`.
- **Never commit `.venv/`, `.idea/`, or `.env`** — they're already in `.gitignore`.

## Layout

```
AIT506-Team/
├── Week 1/          # notebooks for week 1
├── Week 2/          # notebooks for week 2
├── requirements.txt # pinned dependencies (rebuild the venv from this)
├── .gitignore
└── README.md
```
