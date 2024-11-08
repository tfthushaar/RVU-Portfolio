# RVU-Portfolio

**RVU-Portfolio** is a portfolio management and presentation platform designed for students and staff at RV University. It allows users to register, log in, upload content, and view portfolios in an organized, visually appealing manner. The app leverages Firebase for authentication, real-time database storage, file management, and hosting, creating a streamlined and scalable backend solution.

---

## Table of Contents

- [Features](#features)
- [Project Structure](#project-structure)
- [Tech Stack](#tech-stack)
- [Getting Started](#getting-started)
- [Running the Project Locally](#running-the-project-locally)
- [Deployment](#deployment)
- [Firebase Rules](#firebase-rules)
- [Contributing](#contributing)
- [License](#license)

---

## Features

- **User Authentication**: Secure login using Firebase Authentication.
- **Portfolio Management**: CRUD operations for portfolio items.
- **File Upload**: Upload and display media files, managed with Firebase Storage.
- **Real-Time Updates**: Real-time data synchronization using Firebase Firestore.
- **Analytics**: User engagement insights provided by Firebase Analytics.

---

## Project Structure

RVU-Portfolio/
├── frontend/
│   ├── public/
│   │   ├── index.html         # Main HTML file for the frontend
│   │   └── assets/            # Folder for static assets (images, etc.)
│   ├── src/
│   │   ├── components/        # Reusable UI components
│   │   │   ├── AuthForm.js    # Authentication form component
│   │   │   ├── PortfolioItem.js # Component to display each portfolio item
│   │   │   └── UploadForm.js  # Form component for uploading media
│   │   ├── pages/             # Pages in the app (Home, Login, etc.)
│   │   │   ├── Home.js        # Home page
│   │   │   ├── Login.js       # Login page
│   │   │   └── Profile.js     # User profile/portfolio page
│   │   ├── services/          # Firebase services for auth, db, storage
│   │   │   ├── firebase.js    # Firebase configuration and initialization
│   │   │   └── auth.js        # Authentication-related functions
│   │   ├── App.js             # Main App component
│   │   ├── index.js           # Entry point for React app
│   │   └── styles/            # CSS/SCSS files for styling components
│   │       └── main.css       # Main stylesheet
│   └── package.json           # Frontend dependencies and scripts
├── backend/
│   ├── controllers/           # Logic for handling API requests
│   │   └── portfolioController.js
│   ├── models/                # Database schemas (if needed, e.g., NoSQL models)
│   │   └── portfolioItem.js   # Structure for portfolio items
│   ├── routes/                # API routes
│   │   ├── authRoutes.js      # Routes for authentication
│   │   └── portfolioRoutes.js # Routes for portfolio management
│   ├── services/              # Firebase service modules
│   │   ├── firebaseConfig.js  # Firebase setup and configuration
│   │   └── storageService.js  # Functions for file upload/download
│   ├── server.js              # Entry point for backend server
│   ├── package.json           # Backend dependencies and scripts
│   └── .env                   # Environment variables for Firebase and secrets
├── firebase.json              # Firebase configuration file for deployment
├── .gitignore                 # Ignored files (e.g., node_modules, .env)
└── README.md                  # Project documentation

---

### Key Directories

- **frontend**: Contains the React frontend application.
- **backend**: Contains Firebase Functions backend files for managing portfolio data and file uploads.
- **firebase.json**: Firebase configuration file for hosting, database, and function settings.

---

## Tech Stack

- **Frontend**: React, Firebase Authentication, Firebase Storage
- **Backend**: Firebase Functions, Firestore Database
- **Hosting**: Firebase Hosting

---

## Getting Started

### Prerequisites

- [Node.js](https://nodejs.org/) (v14+)
- [Firebase CLI](https://firebase.google.com/docs/cli) (for deployment)

### Firebase Setup

1. Create a Firebase project at [Firebase Console](https://console.firebase.google.com/).
2. Set up Firebase Authentication, Firestore, and Firebase Storage.
3. Copy your Firebase configuration and add it to `frontend/src/services/firebase.js`.

### Installation

1. Clone the repository:

   git clone https://github.com/yourusername/RVU-Portfolio.git
   cd RVU-Portfolio

2. Install dependencies for both frontend and backend:

  cd frontend
  npm install
  cd ../backend
  npm install

### Running the Project Locally

Start Frontend:
    cd frontend
    npm start

Start Backend:
     cd backend
    firebase emulators:start
    
The app should now be accessible on http://localhost:3000, with the backend emulated on Firebase emulators.

## Deployment

Build Frontend:
cd frontend
npm run build

Deploy to Firebase:
firebase deploy

Firebase will deploy both the frontend (Firebase Hosting) and backend (Firebase Functions) based on your firebase.json settings.

## Firebase Rules

Firestore Rules
In firestore.rules, ensure that users can only access their own data
