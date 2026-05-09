# GoRide — Full Stack Ride Sharing Platform

A full stack ride sharing platform that connects riders and drivers in real time, featuring live GPS tracking, automated matching, and a seamless booking experience.

---

## Features

- Real time GPS tracking powered by Socket.IO
- Live ride notifications for riders and drivers
- Automated driver rider matching system
- JWT authentication with bcrypt password hashing
- Token blacklisting for secure session management
- Google Maps API integration for dynamic geocoding and fare estimation
- 15+ RESTful API endpoints following MVC architecture
- Concurrent user session support
- MongoDB schemas via Mongoose ODM

---

## Tech Stack

**Frontend**
- React.js
- Tailwind CSS

**Backend**
- Node.js
- Express.js
- Socket.IO
- MongoDB with Mongoose

**APIs and Services**
- Google Maps API
- JWT Authentication
- Bcrypt

---

## Project Structure

```
GoRide/
├── frontend/
│   ├── src/
│   └── public/
├── backend/
│   ├── controllers/
│   ├── models/
│   ├── routes/
│   └── middlewares/
└── README.md
```

---

## Getting Started

```bash
# Clone the repository
git clone https://github.com/yourusername/GoRide.git

# Install backend dependencies
cd backend
npm install

# Install frontend dependencies
cd ../frontend
npm install

# Run backend
npm run dev

# Run frontend
npm run dev
```

---

## Environment Variables

Create a `.env` file in the backend folder and add the following:

```
PORT=5000
MONGO_URI=your_mongodb_connection_string
JWT_SECRET=your_jwt_secret
GOOGLE_MAPS_API_KEY=your_google_maps_api_key
```

---

## License

This project is open source and available under the MIT License.
