# Spendly — Flask Expense Tracker

A full-stack personal finance web app built with Flask and SQLite. Users register, log in, and track daily expenses across categories — with a dashboard showing spending summaries, category breakdowns, and date-range filters.

![Spendly preview](preview.webp)

## Features

- User registration and login with hashed passwords (Werkzeug)
- Add, edit, and delete expense entries
- Category breakdown: Food, Transport, Bills, Health, Entertainment, Shopping, Other
- Date-range filtering with quick presets (this month, last 3 months, last 6 months)
- Summary stats: total spent, average per day, top category
- Persistent SQLite storage via a simple query layer (`database/queries.py`)
- Responsive UI with Jinja2 templates

## Tech Stack

- **Backend**: Python 3, Flask
- **Database**: SQLite (via `sqlite3` stdlib)
- **Auth**: Werkzeug password hashing
- **Frontend**: Jinja2 templates, vanilla CSS/JS
- **Testing**: pytest

## Getting Started

```bash
# 1. Clone and enter the project
git clone https://github.com/Vighnesh1045/-flask-expense-tracker
cd -flask-expense-tracker

# 2. Create a virtual environment
python3 -m venv venv
source venv/bin/activate      # Windows: venv\Scripts\activate

# 3. Install dependencies
pip install -r requirements.txt

# 4. Set a secret key (required for session security)
export SECRET_KEY="your-strong-random-secret"

# 5. Run the app
python app.py
```

Then open `http://localhost:5001` in your browser. The database is created automatically on first run.

## Running Tests

```bash
pytest
```

## Project Structure

```
├── app.py                  # Flask routes and app factory
├── database/
│   ├── db.py               # DB init, seed, and user helpers
│   └── queries.py          # All SQL query functions
├── templates/              # Jinja2 HTML templates
├── static/                 # CSS and JS assets
├── tests/                  # pytest test suite
└── requirements.txt
```

## Configuration

| Environment Variable | Default | Description |
|---|---|---|
| `SECRET_KEY` | random bytes (ephemeral) | Flask session signing key — set a stable value in production |

> **Note:** If `SECRET_KEY` is not set, Flask generates a random key each restart, which invalidates all existing sessions. Set it explicitly in any persistent deployment.
