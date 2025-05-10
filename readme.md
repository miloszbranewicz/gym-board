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

## 🚀 Goals

- ✅ Prove the concept of managing classes and signups
- ✅ Deliver real value to small gyms or trainers
- ❌ Skip payments, subscriptions, mailing etc. in this phase

---

## 📜 License

MIT – Free to use and build upon.
