# Mergington High School Activities API

A super simple FastAPI application that allows students to view and sign up for extracurricular activities.

## Features

- View all available extracurricular activities
- Sign up for activities
- Unregister participants from activities

## Getting Started

From the repository root, install the dependencies:

```bash
pip install -r requirements.txt
```

Run the application:

```bash
python -m uvicorn src.app:app --reload
```

Open http://localhost:8000/docs for the API documentation, or
http://localhost:8000/redoc for the alternative documentation.

## Running Tests

Install the project dependencies, including pytest, then run the backend tests
from the repository root:

```bash
python -m pytest
```

## API Endpoints

| Method | Endpoint                                                          | Description                                                         |
| ------ | ----------------------------------------------------------------- | ------------------------------------------------------------------- |
| GET    | `/activities`                                                     | Get all activities with their details and current participant count |
| POST   | `/activities/{activity_name}/signup?email=student@mergington.edu` | Sign up for an activity                                             |
| DELETE | `/activities/{activity_name}/participants?email=student@mergington.edu` | Unregister a student from an activity                               |

## Data Model

The application uses a simple data model with meaningful identifiers:

1. **Activities** - Uses activity name as identifier:

   - Description
   - Schedule
   - Maximum number of participants allowed
   - List of student emails who are signed up

2. **Students** - Uses email as identifier:
   - Name
   - Grade level

All data is stored in memory, which means data will be reset when the server restarts.
