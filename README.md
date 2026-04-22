# Workout Tracking System

A professional Flask-based application for tracking workouts and exercises, featuring a REST API for CRUD operations on workouts and exercises, and a seed script to populate the database with sample data.

## Project Description

This system provides a comprehensive solution for managing personal workout routines. It allows users to track exercises, The application includes a seed script to populate the database with sample exercises and workouts for testing and development purposes.

### Key Features
- **REST API**: Full CRUD operations for exercises and workouts
- **Database Seeding**: Automated population of sample workout and exercise data
- **Flask-Migrate**: Database schema versioning and migrations
- **Data Validation**: Marshmallow schemas for input validation
- **Flask Blueprints**: Blueprints for modular code


## Installation Instructions

Follow these steps to set up the project locally:

1. **Clone the repository** then navigate to the project directory.

2. **Install dependencies using Pipenv**:
   ```bash
   pipenv install or pipenv sync
   ```

3. **Activate the virtual environment**:
   ```bash
   pipenv shell
   ```

4. **Set up environment variables or use the config.py file**:
   - Create a `.env` file in the root directory.
   - Add any required environment variables, such as database URI.
   - Example:
     ```
     DATABASE_URL=sqlite:///instance/app.db
     ```

5. **Set up the database**:
   - Initialize and apply migrations:
     ```bash
     flask db init  # only use when making migrations
     flask db migrate
     flask db upgrade
     ```

6. **Populate the database with sample data**:
   ```bash
   python app/seed.py
   ```

## Run Instructions

To start the Flask development server:

1. Ensure you are in the virtual environment (`pipenv shell`).

2. Set the required environment variables:
   ```bash
   export FLASK_APP=app.py
   export FLASK_ENV=development
   ```

3. Run the application:
   ```bash
   flask run (if you already set required env in step 2) or python app.py
   ```

The server will start on `http://127.0.0.1:5000` by default.

## API Endpoints

The following REST API endpoints are available for workout and exercise management (test with postman or curl):

### Exercise CRUD Operations
- **GET /exercises** - Retrieve all exercises
- **GET /exercises/<id>** - Retrieve a specific exercise by ID
- **POST /exercises** - Create a new exercise
- **PUT /exercises/<id>** - Update an existing exercise
- **DELETE /exercises/<id>** - Delete an exercise

### Workout CRUD Operations
- **GET /workouts** - Retrieve all workouts
- **GET /workouts/<id>** - Retrieve a specific workout by ID
- **POST /workouts** - Create a new workout
- **PUT /workouts/<id>** - Update an existing workout
- **DELETE /workouts/<id>** - Delete a workout

## Project Structure

```
workout-app/
├── app.py                 # Main Flask application entry point
├── config.py              # Application configuration
├── Pipfile                # Pipenv dependency management
├── Pipfile.lock           # Pipenv lock file
├── README.md              # Project documentation
├── app/
│   ├── __init__.py        # Flask app factory
│   ├── extensions.py      # Flask extensions (e.g., SQLAlchemy, Migrate)
│   ├── models.py          # Database models (Exercise, Workout, WorkoutExercise)
│   ├── seed.py            # Database seeding script
│   ├── routes/
│   │   ├── __init__.py
│   │   ├── exercise_detail.py  # Exercise API routes
│   │   └── workout_detail.py   # Workout API routes
│   └── schemas/
│       └── tableschema.py  # Marshmallow schemas for validation
├── instance/              # Instance-specific data (e.g., SQLite database)
├── migrations/            # Flask-Migrate migration files
│   ├── alembic.ini
│   ├── env.py
│   ├── README
│   ├── script.py.mako
│   └── versions/
│       └── <migration_files>
└── .git/                  # Git repository
```

## Dependencies

All project dependencies are managed via Pipenv and listed in the `Pipfile`. Key dependencies include:

- Flask: Web framework
- Flask-SQLAlchemy: Database ORM
- Flask-Migrate: Database migrations
- Marshmallow: Data serialization and validation
- Faker: Fake data generation for seeding

To install dependencies, run `pipenv install`.

## Seed Script

The `seed.py` script populates the database with sample workout and exercise data for testing and development purposes. It creates a set of predefined exercises (e.g., Bench Press, Squat) and sample workouts with associated exercises.

To run the seed script:

```bash
python app/seed.py
```

## License

This project is licensed under the MIT License. See the `LICENSE` file for details.
  
