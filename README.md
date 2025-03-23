# MERN Blog Platform

A personal blog platform built with the MERN stack (MongoDB, Express.js, React, Node.js) with comprehensive DevOps practices.

## Features

- User authentication (register, login, logout)
- Create, read, update, and delete blog posts
- Markdown support for blog content
- Responsive design
- Admin dashboard for content management
- CI/CD pipeline for automated testing and deployment
- Error monitoring and logging

## Tech Stack

### Backend
- Node.js with Express
- MongoDB with Mongoose
- JWT for authentication
- Winston and Morgan for logging
- PM2 for process management

### Frontend
- React.js
- React Router for navigation
- Axios for API requests
- React Markdown for content rendering
- Sentry for error tracking

### DevOps
- GitHub Actions for CI/CD
- Render for backend hosting
- Vercel for frontend hosting
- Environment variables for configuration
- HTTPS for secure communication

## Getting Started

### Prerequisites
- Node.js (v14+)
- MongoDB Atlas account or local MongoDB installation
- Git

### Local Development Setup

1. Clone the repository
```bash
git clone https://github.com/your-username/mern-blog-platform.git
cd mern-blog-platform
```

2. Install backend dependencies
```bash
cd backend
npm install
cp .env.example .env
# Update .env with your MongoDB URI and JWT secret
```

3. Install frontend dependencies
```bash
cd ../frontend
npm install
cp .env.example .env.local
# Update .env.local with your backend API URL
```

4. Run development servers
```bash
# In the backend directory
npm run dev

# In the frontend directory (open a new terminal)
npm start
```

## Deployment

### Backend Deployment (Render)

1. Create a new Web Service on Render
2. Connect your GitHub repository
3. Configure build settings:
   - Environment: Node
   - Build Command: `cd backend && npm install`
   - Start Command: `cd backend && npm start`
4. Add environment variables:
   - MONGODB_URI
   - JWT_SECRET
   - NODE_ENV=production

### Frontend Deployment (Vercel)

1. Sign up for Vercel and connect your GitHub repository
2. Configure project settings:
   - Framework Preset: Create React App
   - Root Directory: frontend
3. Add environment variables:
   - REACT_APP_API_URL (pointing to your Render backend URL)

## CI/CD Pipeline

This project uses GitHub Actions for continuous integration and deployment:

1. On every push or pull request to the main branch:
   - Backend and frontend tests are run
   - Build is verified
   - Contributors are notified of failed builds

2. On successful merge to main:
   - Changes are automatically deployed to staging environments
   - Production deployment requires manual approval

## Monitoring and Logging

### Backend Monitoring
- Winston for structured logging
- Morgan for HTTP request logging
- Render dashboard for server metrics

### Frontend Monitoring
- Sentry for real-time error tracking and monitoring
- Performance monitoring with Lighthouse

## Security Measures

- HTTPS enabled for all communications
- JWT authentication with secure storage
- Environment variables for sensitive credentials
- Password hashing with bcrypt
- Helmet.js for secure HTTP headers
- CORS configuration to restrict unauthorized domains

## Project Structure

```
mern-blog-platform/
├── backend/             # Express.js server
│   ├── config/          # Configuration files
│   ├── controllers/     # Route controllers
│   ├── middleware/      # Custom middleware
│   ├── models/          # Mongoose models
│   ├── routes/          # API routes
│   └── server.js        # Server entry point
├── frontend/            # React application
│   ├── public/          # Static files
│   └── src/             # React components and logic
├── .github/             # GitHub Actions workflows
└── README.md            # Project documentation
```

## Contributing

1. Fork the repository
2. Create a feature branch: `git checkout -b feature-name`
3. Commit your changes: `git commit -m 'Add some feature'`
4. Push to the branch: `git push origin feature-name`
5. Open a pull request

## License

This project is licensed under the MIT License - see the LICENSE file for details.