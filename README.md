Capitalism

Capitalism is a MERN stack web platform designed to facilitate collaborative learning and skill development through peer-to-peer guidance. The platform focuses on creating a dynamic learning environment with secure authentication, user-friendly interfaces, and real-time communication features.

Motivation

In today's fast-paced world, acquiring new skills is essential for both personal and professional growth. Traditional learning methods often lack interaction and practical guidance. Capitalism bridges this gap by enabling users to exchange knowledge through collaborative, supportive peer-to-peer learning.

Features

Peer Connection: Real-time chat interface allows direct communication after connection requests and acceptance, enabling hands-on guidance.
Robust Security: Implements Google OAuth 2.0 authentication and JSON Web Tokens (JWT) to ensure database and session security.
Rating & Feedback: Users can rate and provide feedback on guidance sessions to build credibility and trust within the community.
Responsive Design: Optimized layout for seamless use across devices, enhancing user experience.
Technologies Used

Frontend: React.js, React Router, Context API, React-Bootstrap, Axios, React-Toastify, Socket.io-client
Backend: Node.js, Express.js, MongoDB (MongoDB Atlas), Mongoose, Socket.io, JWT, Passport.js
Deployment & Tools: Docker, Docker Compose, Google Cloud Console (OAuth), MongoDB Compass, Postman, VSCode, Git, GitHub
Screenshots

Refer to the screenshots folder for visuals of the application interface.

Installation

Follow these steps to run Capitalism locally on your machine.

Prerequisites
Google OAuth credentials configured in Google Cloud Console.
MongoDB Atlas connection string.
Nodemailer app password for email notifications.
Basic knowledge of Node.js and React projects.
Clone the Repository
git clone https://github.com/vyshuJanu/Capitalism.git
cd Capitalism
Frontend Setup
cd Frontend
npm install
Create a .env file in the Frontend directory with:

VITE_LOCALHOST=http://localhost:8000
VITE_SERVER_URL=<your-deployment-link>
Run the frontend:

npm run dev
Frontend will be accessible at http://localhost:5173.

Backend Setup
cd ../Backend
npm install
Create a .env file in the Backend directory with:

PORT=8000
CORS_ORIGIN=*
MONGODB_URI=mongodb+srv://<username>:<password>@cluster0.<your-project>.mongodb.net
CLOUDINARY_CLOUD_NAME=<your-cloudinary-cloud-name>
CLOUDINARY_API_KEY=<your-cloudinary-api-key>
CLOUDINARY_API_SECRET=<your-cloudinary-api-secret>
GOOGLE_CLIENT_ID=<your-google-client-id>
GOOGLE_CLIENT_SECRET=<your-google-client-secret>
GOOGLE_CALLBACK_URL=http://localhost:8000/auth/google/callback
JWT_SECRET=<your-jwt-secret>
EMAIL_ID=<your-email-id>
APP_PASSWORD=<your-app-password>
Run the backend:

npm run dev
Backend will be running at http://localhost:8000.

Running with Docker (Optional)
Create a docker-compose.yml file in the root Capitalism folder:

version: '3'

services:
  backend:
    build:
      context: .
      dockerfile: Dockerfile.backend
      args:
        PORT: 8000
        CORS_ORIGIN: "*"
        MONGODB_URI: "mongodb+srv://<username>:<password>@cluster0.<your-project>.mongodb.net"
        CLOUDINARY_CLOUD_NAME: "<your-cloudinary-cloud-name>"
        CLOUDINARY_API_KEY: "<your-cloudinary-api-key>"
        CLOUDINARY_API_SECRET: "<your-cloudinary-api-secret>"
        GOOGLE_CLIENT_ID: "<your-google-client-id>"
        GOOGLE_CLIENT_SECRET: "<your-google-client-secret>"
        GOOGLE_CALLBACK_URL: "http://localhost:8000/auth/google/callback"
        JWT_SECRET: "<your-jwt-secret>"
    ports:
      - "8000:8000"

  frontend:
    build:
      context: .
      dockerfile: Dockerfile.frontend
      args:
        VITE_LOCALHOST: "http://localhost:8000"
        VITE_SERVER_URL: "<your-deployment-link>"
    ports:
      - "5173:5173"
To run the app using Docker Compose:

sudo docker-compose up
To stop and remove images:

sudo docker-compose down --rmi all
Access the app at http://localhost:5173.

