# ✅ GymBoard – MVP Scope

## 🎯 Goal
Provide a simple web app for small gyms or personal trainers to manage fitness class scheduling and allow client signups.

---

## 🚪 User: Client

- [ ] Register and login
- [ ] View all available classes (with time, date, trainer)
- [ ] Enroll and unenroll from a class

## 🔐 User: Admin

- [ ] Add/edit/delete classes (title, description, trainer, limit)
- [ ] View list of enrolled clients for any class

---

## 🔧 API Endpoints (example)

- POST `/api/register` – User registration
- POST `/api/login` – User login
- GET `/api/classes` – Fetch public class list
- POST `/api/classes/{id}/enroll` – Enroll in class
- DELETE `/api/classes/{id}/unenroll` – Cancel enrollment
- Admin only:
    - POST `/api/admin/classes`
    - GET `/api/admin/classes/{id}/attendees`

---

## 🚫 Out of Scope (future only)

- Payments / subscriptions
- Email / SMS notifications
- Coach panel
- Advanced reporting

---

## ⏱ Estimated Time

💡 Around 15–20 hours of focused development, spread over 1–2 weeks.

---

## 🧪 Testing

- API: Pest
- Frontend: Vitest + React Testing Library
