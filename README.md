Study Buddy AI – Docker Deployment

Overview

Study Buddy AI is a Node.js, Express, EJS and MongoDB application containerised with Docker for SIT725 8.2HD.

Main functions:

Register / Login / Logout

Add Subjects

Add Tasks

Store data in MongoDB

/api/student endpoint

Requirements

Install:

Git

Docker Desktop

No separate Node.js or MongoDB installation is required.

Run the Application

1. Clone the repository

git clone <GITHUB_REPO_URL>
cd <YOUR_REPOSITORY_FOLDER>

2. Create .env

Create a .env file in the project root:

PORT=3000
SESSION_SECRET=replace_with_a_long_random_secret
MONGO_URI=mongodb://127.0.0.1:27017/studybuddy

The .env file is not committed because it contains runtime configuration.

3. Build and start

docker compose up -d --build

4. Open the application

http://localhost:3000

The application runs on port 3000.

Test the App

Use this flow:

Register → Login → Add Subject → Add Task → Logout

The created users, subjects and tasks are stored in MongoDB.

Student API

Open:

http://localhost:3000/api/student

Expected response:

{
  "name": "Juhar Rafid",
  "studentId": "s225654261"
}

Useful Commands

Check running containers:

docker compose ps

Stop the app:

docker compose down

View app logs:

docker compose logs app

View MongoDB logs:

docker compose logs mongo
