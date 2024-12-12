# Context
This code is me learning how to do Oauth2 in FastAPI


# Create the development environment

The code has been developed and tested on Python 3.13.0.

```
git clone git@github.com:peterhoward42/work-ex-fastapi.git
cd work-ex-fastapi
python3 -m venv .venv
source .venv/bin/activate
python -m pip install --upgrade pip
pip install -r requirements.txt
python migrate_db.py

```

# Run the automated tests

The development environment does not set the DATABASE_URL environment variable,
so the tests will create amd use an SQLite file-based database at ./database.db

```
make test
```

# Configuring the API to use an external database

By default the API creates and interacts with a local SQLite database - which lives
in a local `./database.db` file.

You can alternatively specify an external (pre-existing) database connection URL using the `DATABASE_URL` environment variable.

For example:

```export DATABASE_URL="postgresql+psycopg2://user:password@hostname/database_name'"```

# Launching the service locally and interacting with it

```
fastapi dev main.py
```

The fastAPI CLI output will include something like this:

```
Serving at: http://127.0.0.1:8000
API docs: http://127.0.0.1:8000/docs
```

Point your browser to the API docs URL (a SwaggerUI) to try out the API.

