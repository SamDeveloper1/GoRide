<div align="center">

# 🚗 GoRide

### Full Stack Ride Sharing Platform

*Connecting riders and drivers in real time — fast, secure, and seamless.*

[![Node.js](https://img.shields.io/badge/Node.js-339933?style=for-the-badge&logo=nodedotjs&logoColor=white)](https://nodejs.org)
[![React](https://img.shields.io/badge/React-20232A?style=for-the-badge&logo=react&logoColor=61DAFB)](https://reactjs.org)
[![MongoDB](https://img.shields.io/badge/MongoDB-4EA94B?style=for-the-badge&logo=mongodb&logoColor=white)](https://mongodb.com)
[![Express](https://img.shields.io/badge/Express.js-000000?style=for-the-badge&logo=express&logoColor=white)](https://expressjs.com)
[![Socket.io](https://img.shields.io/badge/Socket.io-010101?style=for-the-badge&logo=socketdotio&logoColor=white)](https://socket.io)
[![TailwindCSS](https://img.shields.io/badge/Tailwind_CSS-38B2AC?style=for-the-badge&logo=tailwind-css&logoColor=white)](https://tailwindcss.com)

![License](https://img.shields.io/badge/License-MIT-blue?style=flat-square)
![Status](https://img.shields.io/badge/Status-Active-success?style=flat-square)
![PRs](https://img.shields.io/badge/PRs-Welcome-brightgreen?style=flat-square)

</div>

---

## 📖 About

**GoRide** is a full stack ride sharing platform that connects riders and drivers in real time. Built with a modern tech stack, it features live GPS tracking, automated driver-rider matching, and a secure authentication system — delivering a smooth and reliable ride booking experience.

---

## ✨ Features

| Feature | Description |
|---|---|
| 📍 **Real Time GPS Tracking** | Live location tracking powered by Socket.IO |
| 🔔 **Live Notifications** | Instant ride updates for both riders and drivers |
| 🤝 **Auto Matching** | Automated driver-rider matching algorithm |
| 🔐 **JWT Authentication** | Secure login with bcrypt password hashing |
| 🚫 **Token Blacklisting** | Secure logout and session invalidation |
| 🗺️ **Google Maps API** | Dynamic geocoding and real time fare estimation |
| 🌐 **RESTful APIs** | 15+ endpoints following clean MVC architecture |
| 👥 **Concurrent Sessions** | Supports multiple users simultaneously |
| 🗄️ **MongoDB Atlas** | Cloud database with Mongoose ODM |

---

## 🛠️ Tech Stack

### Frontend
![React](https://img.shields.io/badge/React-20232A?style=flat-square&logo=react&logoColor=61DAFB)
![TailwindCSS](https://img.shields.io/badge/Tailwind_CSS-38B2AC?style=flat-square&logo=tailwind-css&logoColor=white)
![JavaScript](https://img.shields.io/badge/JavaScript-F7DF1E?style=flat-square&logo=javascript&logoColor=black)

### Backend
![Node.js](https://img.shields.io/badge/Node.js-339933?style=flat-square&logo=nodedotjs&logoColor=white)
![Express](https://img.shields.io/badge/Express.js-000000?style=flat-square&logo=express&logoColor=white)
![Socket.io](https://img.shields.io/badge/Socket.io-010101?style=flat-square&logo=socketdotio&logoColor=white)
![MongoDB](https://img.shields.io/badge/MongoDB-4EA94B?style=flat-square&logo=mongodb&logoColor=white)

### APIs & Services
![Google Maps](https://img.shields.io/badge/Google_Maps-4285F4?style=flat-square&logo=googlemaps&logoColor=white)
![JWT](https://img.shields.io/badge/JWT-000000?style=flat-square&logo=jsonwebtokens&logoColor=white)
![Bcrypt](https://img.shields.io/badge/Bcrypt-003A70?style=flat-square&logo=letsencrypt&logoColor=white)

---

## 📁 Project Structure

```
GoRide/
│
├── 📂 frontend/
│   ├── 📂 src/
│   │   ├── 📂 components/
│   │   ├── 📂 pages/
│   │   ├── 📂 context/
│   │   └── 📂 utils/
│   └── 📂 public/
│
├── 📂 backend/
│   ├── 📂 controllers/
│   ├── 📂 models/
│   ├── 📂 routes/
│   ├── 📂 middlewares/
│   └── 📂 utils/
│
└── 📄 README.md
```

---

## 🚀 Getting Started

### Prerequisites

Make sure you have the following installed:

- ![Node](https://img.shields.io/badge/Node.js-v18+-339933?style=flat-square&logo=nodedotjs&logoColor=white)
- ![npm](https://img.shields.io/badge/npm-v9+-CB3837?style=flat-square&logo=npm&logoColor=white)
- ![MongoDB](https://img.shields.io/badge/MongoDB_Atlas-Account-4EA94B?style=flat-square&logo=mongodb&logoColor=white)

### Installation

```bash
# 1. Clone the repository
git clone https://github.com/yourusername/GoRide.git
cd GoRide

# 2. Install backend dependencies
cd backend
npm install

# 3. Install frontend dependencies
cd ../frontend
npm install
```

### Running the App

```bash
# Run backend (from /backend)
npm run dev

# Run frontend (from /frontend)
npm run dev
```

---

## 🔑 Environment Variables

Create a `.env` file inside the `/backend` folder:

```env
PORT=5000
MONGO_URI=your_mongodb_connection_string
JWT_SECRET=your_jwt_secret
GOOGLE_MAPS_API_KEY=your_google_maps_api_key
```

---

## 🔗 API Overview

| Method | Endpoint | Description |
|---|---|---|
| POST | `/api/auth/register` | Register a new user |
| POST | `/api/auth/login` | Login and get token |
| POST | `/api/auth/logout` | Logout and blacklist token |
| GET | `/api/rides` | Get all rides |
| POST | `/api/rides/book` | Book a new ride |
| PUT | `/api/rides/:id` | Update ride status |
| GET | `/api/drivers/nearby` | Get nearby drivers |

---

## 🤝 Contributing

Contributions are always welcome!

1. Fork the repository
2. Create your feature branch `git checkout -b feature/AmazingFeature`
3. Commit your changes `git commit -m 'Add some AmazingFeature'`
4. Push to the branch `git push origin feature/AmazingFeature`
5. Open a Pull Request

---

## 📄 License

This project is licensed under the **MIT License** — see the [LICENSE](LICENSE) file for details.

---

<div align="center">

Made with ❤️ by [Your Name](https://github.com/yourusername)

⭐ Star this repo if you found it helpful!

</div>
