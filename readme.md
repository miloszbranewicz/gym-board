# 🏋️ GymBoard – Gym Management MVP

GymBoard is a minimal, focused MVP application for small gyms or personal trainers who want to digitize class signups and schedules without expensive or bloated platforms.

This is **not a full SaaS platform**. It's an experimental MVP to validate whether this kind of system can be useful in a real-world gym setting.

---

## ✨ Features in MVP

- Public class schedule (day, time, trainer)
- User sign-up and login
- Clients can enroll/unenroll in classes
- Admin panel to add classes
- Admin can see a list of attendees per class

---

## 🛠 Tech Stack

| Layer      | Tech                        |
|------------|-----------------------------|
| Backend    | Laravel, Sanctum, PostgreSQL |
| Frontend   | React, TypeScript, Vite     |
| UI         | TailwindCSS                 |
| Testing    | Pest (PHP), Vitest (TS)     |

---

## 🚀 Installation & Running

### Prerequisites
- Docker
- Docker Compose
- Git

### Setup Steps

1. Clone the repository:
```bash
git clone <repository-url>
cd gym-board
```

2. Create Laravel project:
```bash
composer create-project laravel/laravel backend
```

3. Create React project:
```bash
npm create vite@latest frontend -- --template react-ts
cd frontend
npm install
cd ..
```

4. Start the containers:
```bash
docker-compose up -d
```

5. Initialize Laravel:
```bash
# Generate application key
docker-compose exec app php artisan key:generate

# Run migrations
docker-compose exec app php artisan migrate
```

### Accessing the Application

- Frontend: http://localhost:5173
- Backend API: http://localhost:8000
- Database (pgAdmin): http://localhost:5050
  - Email: admin@gymboard.com
  - Password: admin

### Database Management

To connect to the database through pgAdmin:
1. Open http://localhost:5050
2. Login with credentials above
3. Add new server:
   - Name: GymBoard DB
   - Host: db
   - Port: 5432
   - Database: gymboard
   - Username: gymboard
   - Password: secret

### Development Commands

```bash
# View logs
docker-compose logs -f

# Stop containers
docker-compose down

# Rebuild containers
docker-compose up -d --build

# Access backend container
docker-compose exec app bash

# Access frontend container
docker-compose exec frontend sh
```

---

## 👥 Getting Started for New Developers

### Prerequisites Check
Before starting, ensure you have:
- Docker Desktop installed and running
- Git installed
- Node.js (v18 or later) installed
- Composer installed (for local development)

### First-time Setup

1. Clone the repository:
```bash
git clone <repository-url>
cd gym-board
```

2. Create `.env` files:
```bash
# Backend
cp backend/.env.example backend/.env

# Frontend
cp frontend/.env.example frontend/.env
```

3. Start the development environment:
```bash
docker-compose up -d
```

4. Install dependencies and initialize the project:
```bash
# Backend setup
docker-compose exec app composer install
docker-compose exec app php artisan key:generate
docker-compose exec app php artisan migrate
docker-compose exec app php artisan db:seed

# Frontend setup
docker-compose exec frontend npm install
```

5. Verify the setup:
- Frontend should be running at http://localhost:5173
- Backend API should be accessible at http://localhost:8000
- Database should be accessible through pgAdmin at http://localhost:5050

### Common Issues & Solutions

1. **Port conflicts**: If you see port conflicts, check if you have other services running on ports 5173, 8000, or 5432.

2. **Database connection issues**: 
   - Ensure PostgreSQL container is running: `docker-compose ps`
   - Check database logs: `docker-compose logs db`

3. **Permission issues**:
   - On Linux/Mac: `chmod -R 777 storage bootstrap/cache`
   - On Windows: Ensure Docker Desktop has proper permissions

4. **Container not starting**:
   - Try rebuilding: `docker-compose up -d --build`
   - Check logs: `docker-compose logs -f`

### Development Workflow

1. Always create a new branch for your work:
```bash
git checkout -b feature/your-feature-name
```

2. After making changes:
```bash
git add .
git commit -m "Description of your changes"
git push origin feature/your-feature-name
```

3. Create a Pull Request on GitHub to merge your changes into the main branch.

---

## 🚀 Goals

- ✅ Prove the concept of managing classes and signups
- ✅ Deliver real value to small gyms or trainers
- ❌ Skip payments, subscriptions, mailing etc. in this phase

---

## 📜 License

MIT – Free to use and build upon.
