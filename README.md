<div align="center">

# 🚗 Uber Clone

### A Full-Stack Ride-Sharing Application

[![React](https://img.shields.io/badge/React-19.2.0-61DAFB?style=for-the-badge&logo=react&logoColor=white)](https://reactjs.org/)
[![Node.js](https://img.shields.io/badge/Node.js-Express-339933?style=for-the-badge&logo=node.js&logoColor=white)](https://nodejs.org/)
[![MongoDB](https://img.shields.io/badge/MongoDB-Mongoose-47A248?style=for-the-badge&logo=mongodb&logoColor=white)](https://www.mongodb.com/)
[![Socket.IO](https://img.shields.io/badge/Socket.IO-Real--time-010101?style=for-the-badge&logo=socket.io&logoColor=white)](https://socket.io/)
[![TailwindCSS](https://img.shields.io/badge/Tailwind_CSS-4.1-38B2AC?style=for-the-badge&logo=tailwind-css&logoColor=white)](https://tailwindcss.com/)

<p align="center">
  <strong>A real-time ride-booking platform connecting riders with drivers, featuring live tracking, fare calculation, and seamless authentication.</strong>
</p>

[Features](#-features) • [Tech Stack](#-tech-stack) • [Architecture](#-architecture) • [Installation](#-installation) • [API Reference](#-api-reference) • [Screenshots](#-screenshots)

</div>

---

## ✨ Features

### 👤 User Features
- **User Authentication** - Secure registration & login with JWT
- **Real-time Location Search** - Google Maps autocomplete integration
- **Ride Booking** - Select pickup & destination with vehicle type options
- **Live Ride Tracking** - Real-time GPS tracking during rides
- **Fare Estimation** - Dynamic fare calculation before booking
- **OTP Verification** - Secure ride start verification

### 🚕 Captain (Driver) Features
- **Captain Registration** - Register with vehicle details
- **Ride Requests** - Receive real-time ride notifications
- **Ride Management** - Accept, start, and complete rides
- **Earnings Dashboard** - Track ride history and earnings

### 🔐 Security Features
- JWT-based authentication
- Password hashing with bcrypt
- Token blacklisting for logout
- Protected routes for authenticated users

---

## 🛠 Tech Stack

<table>
<tr>
<td valign="top" width="50%">

### Frontend
| Technology | Purpose |
|------------|---------|
| ![React](https://img.shields.io/badge/-React_19-61DAFB?style=flat-square&logo=react&logoColor=black) | UI Library |
| ![Vite](https://img.shields.io/badge/-Vite-646CFF?style=flat-square&logo=vite&logoColor=white) | Build Tool |
| ![TailwindCSS](https://img.shields.io/badge/-TailwindCSS-38B2AC?style=flat-square&logo=tailwind-css&logoColor=white) | Styling |
| ![React Router](https://img.shields.io/badge/-React_Router-CA4245?style=flat-square&logo=react-router&logoColor=white) | Navigation |
| ![GSAP](https://img.shields.io/badge/-GSAP-88CE02?style=flat-square&logo=greensock&logoColor=black) | Animations |
| ![Google Maps](https://img.shields.io/badge/-Google_Maps_API-4285F4?style=flat-square&logo=google-maps&logoColor=white) | Maps Integration |
| ![Socket.IO](https://img.shields.io/badge/-Socket.IO_Client-010101?style=flat-square&logo=socket.io&logoColor=white) | Real-time Communication |

</td>
<td valign="top" width="50%">

### Backend
| Technology | Purpose |
|------------|---------|
| ![Node.js](https://img.shields.io/badge/-Node.js-339933?style=flat-square&logo=node.js&logoColor=white) | Runtime |
| ![Express](https://img.shields.io/badge/-Express-000000?style=flat-square&logo=express&logoColor=white) | Web Framework |
| ![MongoDB](https://img.shields.io/badge/-MongoDB-47A248?style=flat-square&logo=mongodb&logoColor=white) | Database |
| ![Mongoose](https://img.shields.io/badge/-Mongoose-880000?style=flat-square&logoColor=white) | ODM |
| ![JWT](https://img.shields.io/badge/-JWT-000000?style=flat-square&logo=json-web-tokens&logoColor=white) | Authentication |
| ![Socket.IO](https://img.shields.io/badge/-Socket.IO-010101?style=flat-square&logo=socket.io&logoColor=white) | WebSocket Server |

</td>
</tr>
</table>

---

## 🏗 Architecture

```
┌─────────────────────────────────────────────────────────────────────────────┐
│                              CLIENT (React + Vite)                          │
│  ┌─────────────┐  ┌─────────────┐  ┌─────────────┐  ┌─────────────────────┐ │
│  │    Pages    │  │ Components  │  │   Context   │  │   Socket.IO Client  │ │
│  │ • Home      │  │ • VehiclePanel│ │ • UserCtx   │  │ • Live Updates      │ │
│  │ • Riding    │  │ • LiveTracking│ │ • CaptainCtx│  │ • Location Sync     │ │
│  │ • Captain   │  │ • ConfirmRide │ │ • SocketCtx │  │                     │ │
│  └─────────────┘  └─────────────┘  └─────────────┘  └─────────────────────┘ │
└─────────────────────────────────────┬───────────────────────────────────────┘
                                      │ HTTP/WebSocket
                                      ▼
┌─────────────────────────────────────────────────────────────────────────────┐
│                           SERVER (Node.js + Express)                        │
│  ┌─────────────┐  ┌─────────────┐  ┌─────────────┐  ┌─────────────────────┐ │
│  │   Routes    │  │ Controllers │  │  Services   │  │   Socket.IO Server  │ │
│  │ • /users    │  │ • user.ctrl │  │ • maps.svc  │  │ • Real-time events  │ │
│  │ • /captains │  │ • captain   │  │ • ride.svc  │  │ • Room management   │ │
│  │ • /rides    │  │ • ride.ctrl │  │             │  │                     │ │
│  │ • /maps     │  │ • map.ctrl  │  │             │  │                     │ │
│  └─────────────┘  └─────────────┘  └─────────────┘  └─────────────────────┘ │
│                                      │                                       │
│  ┌─────────────┐  ┌─────────────┐   │                                       │
│  │ Middlewares │  │   Models    │◄──┘                                       │
│  │ • Auth      │  │ • User      │                                           │
│  │ • Validation│  │ • Captain   │                                           │
│  │             │  │ • Ride      │                                           │
│  └─────────────┘  └─────────────┘                                           │
└─────────────────────────────────────┬───────────────────────────────────────┘
                                      │
                                      ▼
                        ┌───────────────────────────┐
                        │     MongoDB Database      │
                        │   • Users Collection      │
                        │   • Captains Collection   │
                        │   • Rides Collection      │
                        │   • Blacklist Tokens      │
                        └───────────────────────────┘
```

### 📁 Project Structure

```
uber-clone/
├── 📂 Backend/
│   ├── 📂 controllers/        # Request handlers
│   │   ├── user.controller.js
│   │   ├── captain.controller.js
│   │   ├── ride.controller.js
│   │   └── map.controller.js
│   ├── 📂 models/             # MongoDB schemas
│   │   ├── user.model.js
│   │   ├── captain.model.js
│   │   ├── ride.model.js
│   │   └── blacklistToken.model.js
│   ├── 📂 routes/             # API routes
│   ├── 📂 services/           # Business logic
│   ├── 📂 middlewares/        # Auth & validation
│   ├── 📂 db/                 # Database connection
│   ├── socket.js              # WebSocket setup
│   ├── app.js                 # Express app config
│   └── server.js              # Server entry point
│
├── 📂 frontend/
│   ├── 📂 src/
│   │   ├── 📂 pages/          # Page components
│   │   │   ├── Home.jsx
│   │   │   ├── UserLogin.jsx
│   │   │   ├── CaptainHome.jsx
│   │   │   └── Riding.jsx
│   │   ├── 📂 components/     # Reusable components
│   │   │   ├── VehiclePanel.jsx
│   │   │   ├── LiveTracking.jsx
│   │   │   └── ConfirmRide.jsx
│   │   ├── 📂 context/        # React Context
│   │   └── 📂 assets/         # Static assets
│   └── vite.config.js
│
└── README.md
```

---

## 🚀 Installation

### Prerequisites

- **Node.js** (v18 or higher)
- **MongoDB** (local or Atlas)
- **Google Maps API Key**

### 1️⃣ Clone the Repository

```bash
git clone https://github.com/yourusername/uber-clone.git
cd uber-clone
```

### 2️⃣ Backend Setup

```bash
cd Backend
npm install
```

Create `.env` file:
```env
PORT=3000
MONGODB_URI=mongodb://localhost:27017/uber-clone
JWT_SECRET=your_jwt_secret_key
GOOGLE_MAPS_API_KEY=your_google_maps_api_key
```

Start the server:
```bash
npm run dev     # Development with nodemon
npm start       # Production
```

### 3️⃣ Frontend Setup

```bash
cd frontend
npm install
```

Create `.env` file:
```env
VITE_BASE_URL=http://localhost:3000
VITE_GOOGLE_MAPS_API_KEY=your_google_maps_api_key
```

Start the development server:
```bash
npm run dev
```

---

## 📚 API Reference

### Authentication Endpoints

<details>
<summary><code>POST</code> <code>/users/register</code> - Register new user</summary>

**Request Body:**
```json
{
  "fullName": {
    "firstName": "John",
    "lastName": "Doe"
  },
  "email": "john@example.com",
  "password": "password123"
}
```

**Response:** `201 Created`
```json
{
  "token": "<JWT_TOKEN>",
  "user": { "_id": "...", "fullName": {...}, "email": "..." }
}
```
</details>

<details>
<summary><code>POST</code> <code>/users/login</code> - User login</summary>

**Request Body:**
```json
{
  "email": "john@example.com",
  "password": "password123"
}
```

**Response:** `200 OK` with JWT token
</details>

<details>
<summary><code>GET</code> <code>/users/profile</code> - Get user profile (Protected)</summary>

**Headers:** `Authorization: Bearer <token>`

**Response:** `200 OK` with user details
</details>

<details>
<summary><code>GET</code> <code>/users/logout</code> - Logout user (Protected)</summary>

**Response:** `200 OK` - Token invalidated
</details>

### Captain Endpoints

<details>
<summary><code>POST</code> <code>/captains/register</code> - Register new captain</summary>

**Request Body:**
```json
{
  "fullName": { "firstName": "Jane", "lastName": "Doe" },
  "email": "jane@example.com",
  "password": "securepassword",
  "vehicle": {
    "color": "Red",
    "plate": "XYZ123",
    "capacity": 4,
    "vehicleType": "car"
  }
}
```

**Response:** `201 Created` with captain details
</details>

<details>
<summary><code>POST</code> <code>/captains/login</code> - Captain login</summary>

**Response:** `200 OK` with JWT token and captain details
</details>

### Ride Endpoints

<details>
<summary><code>POST</code> <code>/rides/create</code> - Create ride request</summary>

**Request Body:**
```json
{
  "pickup": "123 Main St",
  "destination": "456 Oak Ave",
  "vehicleType": "car"
}
```

**Response:** `201 Created` with ride details
</details>

<details>
<summary><code>GET</code> <code>/rides/get-fare</code> - Get fare estimate</summary>

**Query Params:** `pickup`, `destination`

**Response:** `200 OK` with fare amount
</details>

<details>
<summary><code>POST</code> <code>/rides/confirm</code> - Captain confirms ride</summary>
</details>

<details>
<summary><code>GET</code> <code>/rides/start-ride</code> - Start ride with OTP</summary>
</details>

<details>
<summary><code>POST</code> <code>/rides/end-ride</code> - Complete the ride</summary>
</details>

### Maps Endpoints

<details>
<summary><code>GET</code> <code>/maps/get-coordinates</code> - Get location coordinates</summary>

**Query:** `?address=New Delhi`

**Response:** `{ "lat": 28.6139, "lng": 77.2090 }`
</details>

<details>
<summary><code>GET</code> <code>/maps/get-distance-time</code> - Calculate distance & ETA</summary>

**Query:** `?origin=...&destination=...`
</details>

<details>
<summary><code>GET</code> <code>/maps/get-suggestions</code> - Location autocomplete</summary>

**Query:** `?input=New`

**Response:** `["New Delhi, India", "New York, USA", ...]`
</details>

---

## 🔄 Real-time Features (Socket.IO)

| Event | Direction | Description |
|-------|-----------|-------------|
| `join` | Client → Server | User/Captain joins their room |
| `update-location-captain` | Client → Server | Captain sends location update |
| `new-ride` | Server → Captain | New ride request notification |
| `ride-confirmed` | Server → User | Captain accepted the ride |
| `ride-started` | Server → User | Ride has begun |
| `ride-ended` | Server → Both | Ride completed |

---

## 🎯 User Flow

```
┌─────────────────────────────────────────────────────────────────┐
│                        USER JOURNEY                             │
├─────────────────────────────────────────────────────────────────┤
│                                                                 │
│   📱 Open App → 🔐 Login/Register → 📍 Enter Destination        │
│                                                                 │
│   💰 View Fare → 🚗 Select Vehicle → ⏳ Wait for Captain         │
│                                                                 │
│   ✅ Captain Accepts → 🔢 Share OTP → 🚀 Ride Starts            │
│                                                                 │
│   📍 Live Tracking → 🏁 Arrive at Destination → 💳 Payment      │
│                                                                 │
└─────────────────────────────────────────────────────────────────┘

┌─────────────────────────────────────────────────────────────────┐
│                       CAPTAIN JOURNEY                           │
├─────────────────────────────────────────────────────────────────┤
│                                                                 │
│   📱 Open App → 🔐 Login → 📍 Go Online (Share Location)        │
│                                                                 │
│   🔔 Receive Ride Request → ✅ Accept Ride → 🚗 Navigate to User│
│                                                                 │
│   🔢 Verify OTP → 🚀 Start Ride → 🏁 Complete Ride → 💰 Earn    │
│                                                                 │
└─────────────────────────────────────────────────────────────────┘
```

---

## 🎨 Screenshots

> Add your screenshots here

| Home Screen | Ride Booking | Live Tracking |
|:-----------:|:------------:|:-------------:|
| ![Home](https://via.placeholder.com/250x500/1a1a2e/ffffff?text=Home+Screen) | ![Booking](https://via.placeholder.com/250x500/1a1a2e/ffffff?text=Ride+Booking) | ![Tracking](https://via.placeholder.com/250x500/1a1a2e/ffffff?text=Live+Tracking) |

| Captain Dashboard | Ride Request | Earnings |
|:-----------------:|:------------:|:--------:|
| ![Dashboard](https://via.placeholder.com/250x500/1a1a2e/ffffff?text=Captain+Dashboard) | ![Request](https://via.placeholder.com/250x500/1a1a2e/ffffff?text=Ride+Request) | ![Earnings](https://via.placeholder.com/250x500/1a1a2e/ffffff?text=Earnings) |

---

## 🧪 Testing the APIs

### Using cURL

```bash
# Register a new user
curl -X POST http://localhost:3000/users/register \
  -H "Content-Type: application/json" \
  -d '{"fullName":{"firstName":"John","lastName":"Doe"},"email":"john@test.com","password":"password123"}'

# Login
curl -X POST http://localhost:3000/users/login \
  -H "Content-Type: application/json" \
  -d '{"email":"john@test.com","password":"password123"}'

# Get fare estimate
curl "http://localhost:3000/rides/get-fare?pickup=Location1&destination=Location2" \
  -H "Authorization: Bearer <your_token>"
```

---

## 🔮 Future Enhancements

- [ ] Payment gateway integration (Stripe/Razorpay)
- [ ] Push notifications
- [ ] Ride scheduling
- [ ] Driver ratings & reviews
- [ ] Ride history & receipts
- [ ] Multi-language support
- [ ] Dark mode

---

## 🤝 Contributing

Contributions are welcome! Please feel free to submit a Pull Request.

1. Fork the repository
2. Create your feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

---

## 📄 License

This project is open source and available under the [MIT License](LICENSE).

---

<div align="center">

### ⭐ Star this repo if you found it helpful!

Made with ❤️ by [Samarth](https://github.com/yourusername)

</div>
