# Farmly App

A mobile application connecting farmers directly with customers, built with React Native and Node.js.

## Overview

Farmly is a marketplace platform that enables farmers to list their produce and connect with local customers. The app features real-time messaging, location-based farm discovery, and separate interfaces for farmers and customers.

### Key Features
- 📍 Location-based farm discovery with distance calculation
- 💬 Real-time messaging between farmers and customers
- 📱 Role-based interfaces (Farmer vs Customer views)
- 🖼️ Image upload support for farms and produce
- 🔐 Firebase Authentication integration
- 📊 Produce inventory management

## Project Structure

- **Farmly-Project-FE/** - React Native frontend application
- **Farmly-backend/** - Node.js/Express backend API

## Features

### For Farmers
- Create and manage farm profiles
- List produce with details and pricing
- Chat directly with customers
- Manage produce inventory

### For Customers
- Browse local farms
- View available produce
- Direct messaging with farmers
- Location-based farm discovery

## Tech Stack

### Frontend
- React Native (Expo)
- Firebase Authentication
- React Navigation
- React Native Gifted Chat
- Axios for API calls
- Expo Location API
- AsyncStorage for local data

### Backend
- Node.js + Express
- MongoDB/Mongoose
- Firebase Admin SDK
- JWT Authentication
- Multer for file uploads
- Express middleware for authentication

## Installation

### Prerequisites
- Node.js (v14 or higher)
- npm or yarn
- Expo CLI
- iOS Simulator (for Mac) or Android Studio (for Android development)

### Frontend Setup

1. Navigate to the frontend directory:
   ```bash
   cd Farmly-Project-FE
   ```

2. Install dependencies:
   ```bash
   npm install
   ```

3. Start the development server:
   ```bash
   npm start
   ```

4. Run on iOS:
   ```bash
   npm run ios
   ```

5. Run on Android:
   ```bash
   npm run android
   ```

### Backend Setup

1. Navigate to the backend directory:
   ```bash
   cd Farmly-backend
   ```

2. Install dependencies:
   ```bash
   npm install
   ```

3. Create a `.env` file with your environment variables:
   ```env
   PORT=3000
   MONGODB_URI=your_mongodb_connection_string
   JWT_SECRET=your_jwt_secret
   ```

4. Set up the database with seed data (optional):
   ```bash
   npm run seed
   ```

5. Start the server:
   ```bash
   npm start
   ```

   For development with auto-reload:
   ```bash
   npm run dev
   ```

## Configuration

### Firebase Setup
1. Create a Firebase project
2. Add your Firebase configuration to `Farmly-Project-FE/firebase.js`
3. Set up Firebase Authentication
4. Configure Firestore rules in `firestore.rules`

### Environment Variables
Configure the following environment variables in your backend:
- `MONGODB_URI` - MongoDB connection string
- `JWT_SECRET` - Secret key for JWT tokens
- `PORT` - Server port (default: 3000)

## API Endpoints

### Authentication
- `POST /users` - Create new user account
- `GET /users` - Get all users
- `PATCH /users/:id` - Update user by ID

### Farm Management
- `GET /farms` - Get all farms
- `POST /farms` - Create new farm (requires farmer authentication)
- `GET /farms/:id` - Get farm by ID
- `PATCH /farms/:id` - Update farm by ID
- `DELETE /farms/:id` - Delete farm by ID

### Produce Management
- `GET /produce` - Get all produce from all farms
- `POST /produce` - Add produce to a farm
- `GET /produce/:id` - Get produce by ID
- `PATCH /produce/:id` - Update produce by ID
- `DELETE /produce/:id` - Delete produce by ID

### File Upload
- `POST /upload` - Upload images (supports JPEG, JPG, PNG, GIF)

## Contributing

1. Fork the repository
2. Create your feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

## Project Architecture

### Frontend Structure
- `screens/` - Main application screens (Login, Signup, Farm lists, etc.)
  - `farmer/` - Farmer-specific screens
  - `user/` - Customer-specific screens
- `navigation/` - React Navigation setup and routing
- `utils/` - API calls and helper functions
- `styles/` - Shared styling components
- `constants/` - App-wide constants and configuration

### Backend Structure
- `model/` - Mongoose schemas (Farm, User models)
- `routes/` - Express route definitions
- `middleware/` - Authentication and upload middleware
- `config/` - Configuration files (Firebase setup)
- `db/` - Database seeds and utilities
- `uploads/` - Uploaded images directory

## Development Notes

### Image Handling
- Images are uploaded to the backend's `uploads/` folder
- Maximum file size: 10MB
- Supported formats: JPEG, JPG, PNG, GIF
- Images are served statically from the backend

### Authentication Flow
1. Users register/login through Firebase Authentication
2. Firebase token is exchanged for JWT token from backend
3. JWT token is used for protected API endpoints
4. Role-based access (Farmer vs Customer) is enforced

## License

This project is proprietary software. All rights reserved.

## Contact

For questions or support, please contact the development team.