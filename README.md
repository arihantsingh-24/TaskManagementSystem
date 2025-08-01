# Task Management System 
🚀 [Live here](https://task-management-system01.netlify.app)

A full-stack web application for managing tasks with user authentication, file uploads, and real-time updates.

## Features

### Authentication
- User registration and login with JWT
- Secure password hashing with bcrypt
- Protected routes and middleware

### Task Management
- Create, read, update, and delete (CRUD) tasks
- Task status tracking (pending, in-progress, completed, cancelled)
- Priority levels (low, medium, high, urgent)
- Due date management
- File attachments (up to 3 documents per task)
- Search and filter functionality
- Sort by due date, priority, or title

### User Management
- CRUD operations for users
- Role-based access control (user/admin)
- User assignment to tasks

### File Upload
- Support for PDF, DOC, DOCX, JPG, PNG, GIF files
- Maximum 3 files per task
- 5MB file size limit per file
- File deletion functionality

## Tech Stack

### Backend
- **Node.js** - Runtime environment
- **Express.js** - Web framework
- **MongoDB** - Database
- **Mongoose** - ODM for MongoDB
- **JWT** - Authentication
- **bcryptjs** - Password hashing
- **multer** - File upload handling
- **express-validator** - Input validation

### Frontend
- **React** - UI library
- **React Router** - Client-side routing
- **Context API** - State management
- **Axios** - HTTP client
- **Tailwind CSS** - Styling
- **Lucide React** - Icons
- **React Hook Form** - Form handling
- **React Hot Toast** - Notifications
- **date-fns** - Date utilities

## Prerequisites

- Node.js (v14 or higher)
- MongoDB (local installation or MongoDB Atlas)
- npm or yarn

## Installation

### 1. Clone the repository
```bash
git clone <repository-url>
cd TaskManagementSystem
```

### 2. Install backend dependencies
```bash
cd server
npm install
```

### 3. Install frontend dependencies
```bash
cd ../client
npm install --legacy-peer-deps
```

### 4. Set up MongoDB
Make sure MongoDB is running on your system. The application will connect to `mongodb://localhost:27017/task-management` by default.

### 5. Start the backend server
```bash
cd ../server
npm run dev
```
The server will start on `http://localhost:5000`

### 6. Start the frontend development server
```bash
cd ../client
npm run dev
```
The client will start on `http://localhost:5173`

## Usage

### Registration
1. Navigate to `http://localhost:5173/register`
2. Fill in your name, email, and password
3. Click "Create account"

### Login
1. Navigate to `http://localhost:5173/login`
2. Enter your email and password
3. Click "Sign in"

### Creating Tasks
1. After logging in, you'll be redirected to the dashboard
2. Click "New Task" button
3. Fill in the task details:
   - Title and description
   - Assign to a user
   - Set status and priority
   - Choose due date
   - Upload documents (optional)
4. Click "Create Task"

### Managing Tasks
- **View**: All tasks are displayed on the dashboard
- **Edit**: Click the edit icon on any task card
- **Delete**: Click the delete icon on any task card
- **Filter**: Use the status filter to view specific task types
- **Search**: Use the search bar to find tasks by title or description
- **Sort**: Choose sorting options (due date, priority, title)

### File Management
- Upload up to 3 files per task
- Supported formats: PDF, DOC, DOCX, JPG, PNG, GIF
- Maximum file size: 5MB per file
- Remove files by clicking the trash icon

## API Endpoints

### Authentication
- `POST /api/auth/register` - Register a new user
- `POST /api/auth/login` - Login user
- `GET /api/auth/user` - Get current user data

### Users
- `GET /api/users` - Get all users
- `GET /api/users/:id` - Get user by ID
- `PUT /api/users/:id` - Update user
- `DELETE /api/users/:id` - Delete user

### Tasks
- `GET /api/tasks` - Get user's tasks
- `GET /api/tasks/all` - Get all tasks (admin only)
- `GET /api/tasks/:id` - Get task by ID
- `POST /api/tasks` - Create new task
- `PUT /api/tasks/:id` - Update task
- `DELETE /api/tasks/:id` - Delete task
- `DELETE /api/tasks/:id/documents/:docId` - Delete document from task

## Project Structure

```
TaskManagementSystem/
├── server/
│   ├── config/
│   │   └── db.js
│   ├── middleware/
│   │   ├── auth.js
│   │   └── upload.js
│   ├── models/
│   │   ├── User.js
│   │   └── Task.js
│   ├── routes/
│   │   ├── auth.js
│   │   ├── users.js
│   │   └── tasks.js
│   ├── uploads/
│   ├── index.js
│   └── package.json
├── client/
│   ├── src/
│   │   ├── components/
│   │   │   ├── Dashboard.jsx
│   │   │   ├── Login.jsx
│   │   │   ├── Navbar.jsx
│   │   │   ├── PrivateRoute.jsx
│   │   │   ├── Register.jsx
│   │   │   └── TaskModal.jsx
│   │   ├── context/
│   │   │   └── AuthContext.jsx
│   │   ├── App.jsx
│   │   ├── index.css
│   │   └── main.jsx
│   ├── package.json
│   └── tailwind.config.js
└── README.md
```

## Security Features

- JWT-based authentication
- Password hashing with bcrypt
- Input validation with express-validator
- File type and size validation
- CORS enabled for cross-origin requests
- Protected routes with middleware

## Contributing

1. Fork the repository
2. Create a feature branch
3. Make your changes
4. Test thoroughly
5. Submit a pull request

## License

This project is licensed under the MIT License.

## Support

For support, please open an issue in the repository or contact the development team. 
