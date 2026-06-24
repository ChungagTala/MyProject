# PropSpace - Property Listing Platform

PropSpace is a modern web application that makes it easy to browse, list, and manage properties for rent or sale.

## Features
- **User Authentication**: Secure sign up and log in system.
- **Property Management**: Easily create, view, make changes to, and remove real estate listings.
- **Account Dashboard**: A personal space to manage your profile and account settings.
- **Search & Filter**: Find the exact properties you want by filtering by city, price, or type.
- **Secure Architecture**: Specialized protections to guarantee only you can edit your own listings.
- **Premium UI**: A sleek, dark-mode design that works perfectly on both desktop and mobile devices.

## Tech Stack
- **Frontend**: React (Vite), Axios, Lucide React, and standard CSS.
- **Backend**: Node.js and Express.
- **Database**: MongoDB (Mongoose).
- **Security**: JWT for authentication and BcryptJS for password hashing.

## Project Structure
- `frontend/`: The React client interface.
- `backend/`: The Node/Express server application.

## Getting Started

### Prerequisites
- Node.js installed on your machine.
- A local or remote MongoDB database (like MongoDB Atlas).

### Installation
1. **Clone or download** this repository.
2. **Start the Backend**:
   - Navigate to the backend folder: `cd backend`
   - Install dependencies: `npm install`
   - Create a `.env` file and add your `PORT`, `MONGO_URI`, and `JWT_SECRET`.
   - Run the backend: `node index.js`
3. **Start the Frontend**:
   - Navigate to the frontend folder: `cd frontend`
   - Install dependencies: `npm install`
   - Start the development server: `npm run dev`

## API Endpoints Overview

### Authentication
- `POST /api/users/register`: Create a new user account.
- `POST /api/users/login`: Log into an account.
- `GET /api/users/profile`: Fetch the current user's profile.
- `PUT /api/users/profile`: Update profile details.

### Properties
- `GET /api/properties`: Get all properties (supports filtering by city, type, and price).
- `GET /api/properties/detail/:id`: Get a specific property's details.
- `GET /api/properties/mine`: View properties listed by the logged-in user.
- `POST /api/properties`: Create a new listing.
- `PUT /api/properties/:id`: Edit a specific listing.
- `DELETE /api/properties/:id`: Remove a listing.

## API Testing Reference

If you are using Postman or a similar tool to test the API locally (`http://localhost:5001/api`), you can expect the following responses based on your requests:

- **201 Created**: Sent after successfully registering a new user (`POST /api/users/register`).
- **200 OK**: Sent for successful data fetches, like getting all properties (`GET /api/properties`).
- **400 Bad Request**: Happens if required fields are missing when creating a listing.
- **401 Unauthorized**: Shows up when trying to access a protected route without a valid token.
- **403 Forbidden**: Occurs if you try to edit or delete a listing you didn't create.
- **404 Not Found**: Happens if you try to view a property that doesn't exist in the database.
