# Smart Urban Rental Assistance Platform

A minimal rental platform for students and bachelors: verified listings, transparent info, and secure communication.

## Tech stack

- **Frontend:** React (Vite) + React Router
- **Backend:** Node.js + Express
- **Database:** SQLite (single file, no server)

## Modules (current)

| Module | Status |
|--------|--------|
| 21. AI-Based Rental Recommendation | Basic: area match + rent sort |
| 22. Authentication & Authorization | Login, signup, JWT, tenant/owner roles |
| 23. Smart Location & Proximity | Preferred area (e.g. near college) used in recommendations |
| 24. Intelligent Search & Ranking | Recommendations sorted by area + rent |
| 25. Tenant–Owner Trust Score | Placeholder (default score 5.0) |
| 26. Automated Rental Agreement | Placeholder |
| 27. Digital Rent Payment | Placeholder |

## How to run

### Backend

```bash
cd backend
npm install
npm start
```

Runs at **http://localhost:5000**

### Frontend

```bash
cd frontend
npm install
npm run dev
```

Runs at **http://localhost:3000** and proxies `/api` to the backend.

### First use

1. Open http://localhost:3000
2. **Sign up** as Tenant (student/bachelor) or Owner (landlord)
3. Tenants: set “Preferred area” (e.g. Downtown, Near ABC College) for recommendations
4. Owners: add listings (title, address, area, rent)
5. **For You** (recommendations): logged-in users see listings ranked by preferred area and rent
6. **Trust · Agreement · Payment** page shows placeholders for future features

## API overview

- `POST /api/auth/signup` – Sign up (tenant/owner)
- `POST /api/auth/login` – Login
- `GET /api/listings` – List all listings (public)
- `GET /api/listings/:id` – Get one listing (public)
- `POST /api/listings` – Create listing (owner, auth)
- `GET /api/recommendations` – Recommended listings (auth; area + rent)
- `GET /api/trust/:userId` – Trust score (placeholder)
- `POST /api/agreement/generate` – Agreement (placeholder)
- `POST /api/payment/pay` – Payment (placeholder)

## Project structure

```
backend/          # Express API
  db.js           # SQLite + schema
  server.js       # App entry
  middleware/     # JWT auth
  routes/         # auth, listings, recommendation, trust, agreement, payment

frontend/         # React (Vite)
  src/
    api.js        # API client
    AuthContext.jsx
    App.jsx, Nav.jsx
    pages/        # Login, Signup, Listings, ListingDetail, CreateListing, Recommendations, Placeholders
```

Keep backend running while using the frontend.
