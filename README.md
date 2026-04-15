# Workout Tracking API

A professional Flask RESTful API designed to track gym workouts and exercises. This application uses a Many-to-Many relationship with an association class to record specific performance metrics (reps, sets, and duration) for every exercise performed within a workout.

## Features
- **Many-to-Many Architecture**: Connects Workouts and Exercises via a `WorkoutExercise` association model.
- **Data Validation**: Comprehensive input checking using Marshmallow.
- **Automated Seeding**: Populate the database instantly with realistic gym data using Faker.
- **Database Management**: Schema versioning with Flask-Migrate.

---

## Installation & Setup

1. **Clone the Project**
   ```bash
   git clone <your-repository-url>
   cd workout-app

## Database Initialization
   
Apply migrations to create your local SQLite database:

    
   flask db upgrade

  
 ## Seeding the Database

     
   python -m app.seed

## Execution

Start the local development server:

    
  flask run

## 📚 Core Dependencies

- **Flask** → Web framework  
- **Flask-SQLAlchemy** → ORM  
- **Flask-Migrate** → Database migrations  
- **Marshmallow** → Serialization & validation  
- **Faker** → Mock data generation  
- **python-dotenv** → Environment variables  
