# Database & Migrations

**Purpose:** This guide explains how Django migrations build and update a local SQLite development database. It uses the Django Portfolio Application as its project context.

## Prerequisites

- Django is installed in your project's Python environment.
- The project contains `manage.py`.
- `portfolio_app` is registered in `INSTALLED_APPS` in the project's `settings.py`.
- The application's models are defined in `portfolio_app/models.py`.

Run all commands below in a terminal from the directory containing `manage.py`, with the project's environment activated. If your system uses `python3` instead of `python`, substitute it in each command.

## Key terms

| Term | Meaning |
| --- | --- |
| Database | Stores the application's records. |
| Schema | Defines the database's tables, columns, and relationships. |
| Model | A Python class that describes data Django will store. |
| Migration | A versioned set of instructions for changing the database. |
| SQLite | A database engine that stores a database in a local file without a separate database server. |

## How Migrations Work

The Django application defines `Student`, `Portfolio`, and `Project` models. Migrations translate those definitions into database structure, including the relationships between students and portfolios, and between portfolios and their projects.

The workflow is:

1. Define or change a model in `models.py`.
2. Generate a migration file.
3. Review the generated instructions.
4. Apply the migration to the database.

Changing `models.py` alone does not update the database.

### 1. Generate migration files

```bash
python manage.py makemigrations portfolio_app
```

Django compares the current models with the model history recorded in existing migration files. When it detects changes, it writes a new file under `portfolio_app/migrations/`.

Migration files contain instructions such as creating a model's table or adding a field. They do not contain the application's saved student or project records.

### 2. Review the changes

Open the newly generated file and confirm that its operations match the intended model changes. Carefully review removals and required new fields: removing a field can discard stored values, and adding a required field may require a value for existing rows.

### 3. Apply migrations

```bash
python manage.py migrate
```

Django applies pending migrations to the configured database in dependency order.

Applying a schema migration creates or changes database structure. It does not automatically populate the student portfolio tables with example records.

## Files to recognize

| File or directory | Role |
| --- | --- |
| `portfolio_app/models.py` | Defines the application's models. |
| `portfolio_app/migrations/` | Stores the ordered migration history. |
| Project `settings.py` | Selects the database backend and file location. |
| `db.sqlite3` | Stores local tables, records, and applied migration tracking. |

Keep model changes and their migration files together in version control. For typical development workflows, exclude the local `db.sqlite3` file: each developer applies the shared migrations to their own database. Migrations reproduce structure, not another developer's local records.

## Troubleshooting

| Symptom | What to check |
| --- | --- |
| `No changes detected` | Save `models.py` and confirm the app is installed. This message does not mean all existing migrations have been applied; check `showmigrations`. |
| `no such table` | Check migration status and run `migrate`. Confirm the settings point to the intended database. |
| Unapplied migrations warning | Run `python manage.py migrate` in the project's environment. |
| A new required field prompts for a default | Existing rows need a value. Choose one that makes sense for the data, or reconsider whether the field should allow missing values. |
| `database is locked` | Close database editors or other processes holding write access, then retry. |

Do not delete `db.sqlite3` or migration files as a routine fix. Deleting the database removes local records; deleting migrations removes shared schema history. Back up important data before potentially destructive changes.
