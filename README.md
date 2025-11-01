# Personal Travel Diary App

A full-stack web application for creating and managing your personal travel stories. Share your adventures, add photos, tag locations, and keep track of your favorite travel memories.

## Features

- 🔐 **User Authentication**: Secure sign-up and login system with JWT-based authentication
- 📝 **Create & Edit Stories**: Add detailed travel stories with titles, descriptions, and dates
- 📸 **Image Upload**: Upload and attach images to your travel stories
- 🏷️ **Location Tags**: Tag multiple visited locations for each travel story
- ⭐ **Favorites**: Mark your favorite travel stories
- 🔍 **Search**: Search through your travel stories by title or content
- 📅 **Date Filtering**: Filter stories by date range
- 🎨 **Modern UI**: Beautiful, responsive design built with React and Tailwind CSS
- 👤 **User Profile**: Manage your account and view your travel statistics

## Tech Stack

### Frontend

- **React 19** - UI library
- **Vite** - Build tool and dev server
- **Tailwind CSS** - Utility-first CSS framework
- **Redux Toolkit** - State management
- **React Router** - Client-side routing
- **Axios** - HTTP client
- **React Icons** - Icon library
- **React Toastify** - Toast notifications
- **React Modal** - Modal component
- **React Day Picker** - Date picker component
- **Moment.js** - Date manipulation

### Backend

- **Node.js** - Runtime environment
- **Express.js** - Web framework
- **MongoDB** - NoSQL database
- **Mongoose** - MongoDB object modeling
- **JWT** - Authentication tokens
- **Bcrypt** - Password hashing
- **Multer** - File upload handling
- **CORS** - Cross-origin resource sharing
- **Cookie Parser** - Cookie parsing middleware

## Prerequisites

Before you begin, ensure you have the following installed:

- **Node.js** (v16 or higher)
- **npm** or **yarn**
- **MongoDB** (local installation or MongoDB Atlas account)

## Installation

### 1. Clone the repository

```bash
git clone https://github.com/poojavengala/Travel-Diary-App
cd Personal-Travel-Diary-App-main
```

### 2. Backend Setup

```bash
cd backend

# Install dependencies
npm install

# Create a .env file in the backend directory
# Add the following environment variables:
```

Create a `.env` file in the `backend` directory with the following content:

```env
MONGO_URI=your_mongodb_connection_string
JWT_SECRET=your_jwt_secret_key
```

**Example:**

```env
MONGO_URI=mongodb://localhost:27017/travel-diary
# OR for MongoDB Atlas:
# MONGO_URI=mongodb+srv://username:password@cluster.mongodb.net/travel-diary

JWT_SECRET=your_super_secret_jwt_key_here
```

### 3. Frontend Setup

```bash
cd ../frontend

# Install dependencies
npm install
```

## Running the Application

### Development Mode

1. **Start the backend server:**

   ```bash
   cd backend
   npm run dev
   ```

   The backend server will run on `http://localhost:3000`

2. **Start the frontend development server:**
   ```bash
   cd frontend
   npm run dev
   ```
   The frontend will run on `http://localhost:5173`

### Production Mode

1. **Build the frontend:**

   ```bash
   cd frontend
   npm run build
   ```

2. **Start the backend server:**
   ```bash
   cd backend
   npm start
   ```

## Project Structure

```
Personal-Travel-Diary-App-main/
├── backend/
│   ├── assets/              # Static assets
│   ├── controllers/         # Route controllers
│   │   ├── auth.controller.js
│   │   ├── travelStory.controller.js
│   │   └── user.controller.js
│   ├── models/              # Mongoose models
│   │   ├── travelStory.model.js
│   │   └── user.model.js
│   ├── routes/              # API routes
│   │   ├── auth.route.js
│   │   ├── travelStory.route.js
│   │   └── user.route.js
│   ├── uploads/             # Uploaded images
│   ├── utils/               # Utility functions
│   │   ├── error.js
│   │   └── verifyUser.js
│   ├── index.js             # Backend entry point
│   ├── multer.js            # File upload configuration
│   └── package.json
│
├── frontend/
│   ├── public/              # Static public assets
│   ├── src/
│   │   ├── components/      # React components
│   │   │   ├── AddEditTravelStory.jsx
│   │   │   ├── DateSelector.jsx
│   │   │   ├── EmptyCard.jsx
│   │   │   ├── FilterInfoTitle.jsx
│   │   │   ├── ImageSelector.jsx
│   │   │   ├── Navbar.jsx
│   │   │   ├── PasswordInput.jsx
│   │   │   ├── PrivateRoute.jsx
│   │   │   ├── Profile.jsx
│   │   │   ├── SearchBar.jsx
│   │   │   ├── TagInput.jsx
│   │   │   └── TravelStoryCard.jsx
│   │   ├── pages/           # Page components
│   │   │   ├── Auth/
│   │   │   │   ├── Login.jsx
│   │   │   │   └── SignUp.jsx
│   │   │   └── Home/
│   │   │       ├── Home.jsx
│   │   │       └── ViewTravelStory.jsx
│   │   ├── redux/           # Redux store and slices
│   │   │   ├── slice/
│   │   │   │   └── userSlice.js
│   │   │   └── store.js
│   │   ├── utils/           # Utility functions
│   │   │   ├── axiosInstance.js
│   │   │   ├── helper.js
│   │   │   └── uploadImage.js
│   │   ├── App.jsx          # Main App component
│   │   ├── main.jsx         # React entry point
│   │   └── index.css        # Global styles
│   ├── index.html
│   ├── package.json
│   └── vite.config.js
│
└── README.md
```

## API Endpoints

### Authentication

- `POST /api/auth/signup` - Register a new user
- `POST /api/auth/signin` - Login user
- `POST /api/auth/signout` - Logout user

### User

- `GET /api/user/get` - Get current user profile
- `PUT /api/user/update` - Update user profile

### Travel Stories

- `GET /api/travel-story/get-all` - Get all travel stories for the authenticated user
- `GET /api/travel-story/get/:id` - Get a specific travel story
- `POST /api/travel-story/create` - Create a new travel story
- `PUT /api/travel-story/update/:id` - Update a travel story
- `DELETE /api/travel-story/delete/:id` - Delete a travel story

### Static Files

- `GET /uploads/:filename` - Access uploaded images
- `GET /assets/:filename` - Access static assets

## Usage

1. **Sign Up**: Create a new account with username, email, and password
2. **Login**: Sign in with your credentials
3. **Create Story**: Click the "+" button to add a new travel story
   - Add a title and story description
   - Upload an image
   - Select the visited date
   - Add location tags
   - Mark as favorite (optional)
4. **View Stories**: Browse all your travel stories on the home page
5. **Search**: Use the search bar to find specific stories
6. **Filter**: Filter stories by date range or favorite status
7. **Edit/Delete**: Click on a story card to view, edit, or delete it
8. **Profile**: Access your profile to view account information

## Environment Variables

### Backend (.env)

- `MONGO_URI` - MongoDB connection string
- `JWT_SECRET` - Secret key for JWT token generation

## Security Features

- Password hashing using bcryptjs
- JWT-based authentication
- Protected routes with middleware
- CORS configuration for secure cross-origin requests
- Input validation and error handling

## Contributing

Contributions are welcome! Please feel free to submit a Pull Request.

**Note**: Make sure to configure your MongoDB connection string and JWT secret in the `.env` file before running the application.
