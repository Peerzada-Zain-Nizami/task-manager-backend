# Task Manager Project

This is a task manager application built with a **Laravel backend** and a **React.js frontend**. The project uses **Laravel Passport** for API authentication and provides task management functionality.

## Setup Instructions

### Prerequisites

- PHP 8.x
- Composer
- Node.js & npm
- MySQL or any other database

### Backend Setup (Laravel)

1. Clone the repository:
   git clone https://github.com/your-username/task-manager-project.git
   cd task-manager-project
Navigate to the backend folder:

Copy code
cd backend
Install dependencies:

composer install
Set up the .env file:

Copy .env.example to .env:

cp .env.example .env
Set up your database and other environment variables in the .env file.
Run migrations:

php artisan migrate
Install Passport:

php artisan passport:install
Run the server:

php artisan serve

API Endpoints
All API requests require an authorization token, which can be obtained after logging in using the Passport authentication.

Authentication
Register: POST /api/register

Request Body: { name, email, password }
Response: { user, token }
Login: POST /api/login

Request Body: { email, password }
Response: { user, token }
Task Management
List Tasks: GET /api/tasks

Requires Bearer token in the header.
Create Task: POST /api/tasks

Request Body: { title }
Requires Bearer token in the header.
Update Task: PUT /api/tasks/{id}

Request Body: { title }
Requires Bearer token in the header.
Delete Task: DELETE /api/tasks/{id}

Requires Bearer token in the header.
Environment Variables
Ensure the following variables are set in your .env file:

plaintext
Copy code
APP_NAME=Laravel
APP_ENV=local
APP_KEY=base64:xxxxxxxxxxxxxx
APP_DEBUG=true
APP_URL=http://localhost

DB_CONNECTION=mysql
DB_HOST=127.0.0.1
DB_PORT=3306
DB_DATABASE=your_db_name
DB_USERNAME=your_db_user
DB_PASSWORD=your_db_password

# Laravel Passport Settings
PASSPORT_CLIENT_ID=client_id_here
PASSPORT_CLIENT_SECRET=client_secret_here
