# Todo App Fullstack

A modern, full-stack todo application built with React, Node.js, Express, and MongoDB. Features user authentication, JWT tokens, email notifications, and a beautiful responsive UI.

## 🚀 Features

- **User Authentication**: Secure registration and login with JWT tokens
- **Password Management**: Forgot password and reset password functionality
- **Email Notifications**: Password reset emails via Gmail SMTP
- **Todo Management**: Create, read, update, and delete todos
- **Protected Routes**: Authentication middleware for secure access
- **Responsive Design**: Modern UI built with Tailwind CSS and Radix UI
- **Real-time Updates**: Hot reload development experience
- **Database Integration**: MongoDB Atlas for data persistence

## 🛠️ Tech Stack

### Backend
- **Node.js** - Runtime environment
- **Express.js** - Web framework
- **MongoDB** - NoSQL database
- **Mongoose** - ODM for MongoDB
- **JWT** - JSON Web Tokens for authentication
- **bcrypt** - Password hashing
- **Nodemailer** - Email service
- **CORS** - Cross-origin resource sharing

### Frontend
- **React 18** - UI library
- **Vite** - Build tool and dev server
- **React Router** - Client-side routing
- **Tailwind CSS** - Utility-first CSS framework
- **Radix UI** - Accessible UI components
- **Axios** - HTTP client
- **React Hot Toast** - Toast notifications
- **GSAP** - Animation library
- **Lucide React** - Icon library

## 📋 Prerequisites

Before running this application, make sure you have the following installed:

- **Node.js** (v16 or higher)
- **npm** or **yarn**
- **MongoDB Atlas** account (or local MongoDB)
- **Gmail** account (for email functionality)

## 🔧 Installation

1. **Clone the repository:**
   ```bash
   git clone <repository-url>
   cd todoAppFullstack-main
   ```

2. **Install backend dependencies:**
   ```bash
   npm install
   ```

3. **Install frontend dependencies:**
   ```bash
   cd frontend
   npm install
   cd ..
   ```

4. **Environment Setup:**
   Create a `.env` file in the root directory with the following variables:
   ```env
   PORT=5000
   MONGO_URL=mongodb+srv://your-username:your-password@cluster.mongodb.net/database-name
   SECRET_KEY=your-jwt-secret-key
   GMAIL=your-gmail@gmail.com
   GMAIL_PASS=your-gmail-app-password
   ```

## 🚀 Running the Application

### Development Mode

1. **Start the backend server:**
   ```bash
   npm run server
   ```

2. **Start the frontend (in a new terminal):**
   ```bash
   cd frontend
   npm run dev
   ```

3. **Access the application:**
   - Frontend: `http://localhost:5173`
   - Backend API: `http://localhost:5000`

### Production Mode

1. **Build and start the application:**
   ```bash
   npm run build
   npm run server
   ```

2. **Access the application:**
   - Application: `http://localhost:5000`

## 📡 API Endpoints

### Authentication Routes (`/api/users`)

| Method | Endpoint | Description | Auth Required |
|--------|----------|-------------|---------------|
| POST | `/register` | User registration | ❌ |
| POST | `/login` | User login | ❌ |
| GET | `/logout` | User logout | ✅ |
| POST | `/forgot-password` | Request password reset | ❌ |
| POST | `/reset-password` | Reset password with token | ❌ |
| POST | `/verify-reset-token` | Verify reset token | ❌ |

### Todo Routes (`/api/todo`)

| Method | Endpoint | Description | Auth Required |
|--------|----------|-------------|---------------|
| POST | `/create` | Create new todo | ✅ |
| GET | `/getAllTodo` | Get all user todos | ✅ |
| GET | `/getOne/:id` | Get single todo | ✅ |
| PUT | `/update/:id` | Update todo | ✅ |
| DELETE | `/delete/:id` | Delete todo | ✅ |

## 🗂️ Project Structure

```
todoAppFullstack-main/
├── controllers/          # Request handlers
│   ├── userControllers.js
│   └── todoControllers.js
├── db/                   # Database configuration
│   └── dbConnect.js
├── frontend/             # React frontend
│   ├── src/
│   │   ├── components/   # Reusable components
│   │   ├── pages/        # Page components
│   │   ├── utils/        # Utility functions
│   │   └── varibles.jsx  # API base URL
│   ├── public/           # Static assets
│   └── dist/             # Build output
├── middleware/           # Express middleware
│   └── authMiddleware.js
├── models/               # Mongoose schemas
│   ├── userSchema.js
│   └── todoSchema.js
├── routes/               # API routes
│   ├── userRoutes.js
│   └── todoRoutes.js
├── .env                  # Environment variables
├── index.js              # Express server entry point
├── package.json          # Backend dependencies
└── README.md             # Project documentation
```

## 🔐 Environment Variables

| Variable | Description | Required |
|----------|-------------|----------|
| `PORT` | Server port (default: 5000) | ❌ |
| `MONGO_URL` | MongoDB connection string | ✅ |
| `SECRET_KEY` | JWT secret key | ✅ |
| `GMAIL` | Gmail address for notifications | ✅ |
| `GMAIL_PASS` | Gmail app password | ✅ |

## 📜 Available Scripts

### Backend Scripts
- `npm run server` - Start development server with nodemon
- `npm run build` - Install frontend deps, build frontend, install backend deps

### Frontend Scripts
- `npm run dev` - Start development server
- `npm run build` - Build for production
- `npm run preview` - Preview production build
- `npm run lint` - Run ESLint

## 🔒 Security Features

- **Password Hashing**: bcrypt for secure password storage
- **JWT Authentication**: Stateless authentication with tokens
- **CORS Protection**: Configured for specific origins
- **Input Validation**: Request validation middleware
- **Protected Routes**: Authentication middleware for sensitive endpoints

## 📧 Email Configuration

To enable password reset functionality:

1. Enable 2-factor authentication on your Gmail account
2. Generate an App Password: [Google App Passwords](https://support.google.com/accounts/answer/185833)
3. Use the App Password in the `GMAIL_PASS` environment variable

## 🤝 Contributing

1. Fork the repository
2. Create a feature branch: `git checkout -b feature-name`
3. Commit your changes: `git commit -am 'Add feature'`
4. Push to the branch: `git push origin feature-name`
5. Submit a pull request

## 📄 License

This project is licensed under the ISC License.

## 👥 Author

Built with ❤️ using modern web technologies.

---

**Note**: Make sure to set up your environment variables and MongoDB connection before running the application. The frontend will automatically proxy API requests to the backend in development mode.