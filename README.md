# late-show-API
# Late Show API - Flask RESTful Service

![Flask](https://img.shields.io/badge/Flask-2.2.2-blue)
![SQLAlchemy](https://img.shields.io/badge/SQLAlchemy-2.0-green)
![JWT](https://img.shields.io/badge/JWT_Authentication-Implemented-success)

A production-ready REST API for managing a late night TV show's episodes, guests, and appearances with full JWT authentication.

## Features

Token-based authentication (JWT)
CRUD operations for episodes, guests, and appearances
PostgreSQL database with SQLAlchemy ORM
Flask-Migrate for database migrations
Request validation and error handling
Postman test collection included

## Project Structure
late-show-api/
├── server/
│ ├── app.py 
│ ├── config.py 
│ ├── seed.py 
│ ├── models/ 
│ │ ├── user.py 
│ │ ├── guest.py 
│ │ ├── episode.py 
│ │ └── appearance.py 
│ ├── controllers/ 
│ │ ├── auth.py 
│ │ ├── guests.py 
│ │ ├── episodes.py
│ │ └── appearances.py 
├── migrations/ 
├── tests/ 
└── requirements.txt 

text

## Setup Instructions

### 1. Prerequisites
- Python 3.9+
- PostgreSQL 12+
- Pipenv

### 2. Installation

# Clone repository
git clone https://github.com/almasi89/late-show-api.git
cd late-show-api

# Install dependencies
pipenv install
pipenv shell

# Set environment variables

3. Database Setup
# Create PostgreSQL database
createdb late_show_db

# Run migrations
flask db upgrade

# Seed initial data
python server/seed.py
API Documentation
Authentication
Endpoint	Method	Description
/register	POST	Register new user
/login	POST	Login and get JWT token
Episodes
Endpoint	Method	Auth	Description
/episodes	GET	No	List all episodes
/episodes/<id>	GET	No	Get episode details
/episodes/<id>	DELETE	Yes	Delete an episode
Guests
Endpoint	Method	Auth	Description
/guests	GET	No	List all guests
Appearances
Endpoint	Method	Auth	Description
/appearances	POST	Yes	Create new appearance
Running the Server
bash
export FLASK_APP=server.app
export FLASK_ENV=development
flask run --port 5555
Testing
Import challenge-4-lateshow.postman_collection.json into Postman

Test endpoints in this order:

Register user

Login to get token

Access protected routes with token

Technologies Used
Backend: Flask, Flask-RESTful

Database: PostgreSQL, SQLAlchemy

Authentication: Flask-JWT-Extended

Migrations: Flask-Migrate

Environment: python-dotenv