# 📄 Resume Builder - MERN Stack Application

A modern, full-stack web application for creating professional resumes with AI-powered content enhancement. Built with the MERN stack (MongoDB, Express, React, Node.js), this application allows users to create, customize, and share beautiful resumes using multiple templates.

## ✨ Features

### 🎨 **Resume Creation & Customization**
- **Multiple Templates**: Choose from Classic, Modern, Minimal, and Minimal Image templates
- **Color Customization**: Personalize your resume with custom accent colors
- **Real-time Preview**: See changes instantly as you edit
- **Responsive Design**: Works seamlessly on desktop and mobile devices

### 🤖 **AI-Powered Enhancement**
- **Professional Summary Enhancement**: AI-powered suggestions to improve your professional summary
- **Job Description Optimization**: Enhance job descriptions with action verbs and quantifiable results
- **ATS-Friendly Content**: AI helps make your resume compatible with Applicant Tracking Systems

### 📋 **Resume Sections**
- Personal Information (with profile image upload via ImageKit)
- Professional Summary
- Work Experience
- Education
- Projects
- Skills

### 💾 **Management Features**
- Create multiple resumes
- Save and edit resumes
- Public/Private visibility settings
- Share resumes with unique URLs
- Download resumes as PDF
- Dashboard to manage all your resumes

### 🔐 **Authentication**
- Secure user registration and login
- JWT-based authentication
- Protected routes and user-specific data

## 🛠️ Tech Stack

### Frontend
- **React 19** - UI library
- **Redux Toolkit** - State management
- **React Router** - Navigation
- **Tailwind CSS 4** - Styling
- **Vite** - Build tool
- **Axios** - HTTP client
- **Lucide React** - Icons
- **React Hot Toast** - Notifications

### Backend
- **Node.js** - Runtime environment
- **Express 5** - Web framework
- **MongoDB** - Database
- **Mongoose** - ODM
- **OpenAI API** - AI content enhancement
- **ImageKit** - Image storage and management
- **JWT** - Authentication
- **Bcrypt** - Password hashing
- **Multer** - File uploads

## 📁 Project Structure

```
Resume-Builder/
├── client/                 # Frontend React application
│   ├── src/
│   │   ├── app/           # Redux store and slices
│   │   ├── components/    # Reusable components
│   │   ├── pages/         # Page components
│   │   ├── configs/       # API configuration
│   │   └── assets/        # Static assets
│   └── package.json
│
├── server/                # Backend Node.js application
│   ├── controllers/       # Route controllers
│   ├── models/           # Mongoose models
│   ├── routes/           # API routes
│   ├── middlewares/      # Custom middlewares
│   ├── configs/          # Configuration files
│   └── package.json
│
└── README.md
```

## 🚀 Getting Started

### Prerequisites
- Node.js (v16 or higher)
- MongoDB (local or Atlas)
- OpenAI API key
- ImageKit account

### Environment Variables

#### Backend (.env in server directory)
```env
PORT=3000
MONGODB_URI=your_mongodb_connection_string
JWT_SECRET=your_jwt_secret
OPENAI_API_KEY=your_openai_api_key
OPENAI_MODEL=gpt-4o-mini
IMAGEKIT_PUBLIC_KEY=your_imagekit_public_key
IMAGEKIT_PRIVATE_KEY=your_imagekit_private_key
IMAGEKIT_URL_ENDPOINT=your_imagekit_url_endpoint
```

#### Frontend (.env in client directory)
```env
VITE_BACKEND_URL=http://localhost:3000
```

### Installation

1. **Clone the repository**
```bash
git clone https://github.com/yourusername/resume-builder.git
cd resume-builder
```

2. **Install Backend Dependencies**
```bash
cd server
npm install
```

3. **Install Frontend Dependencies**
```bash
cd ../client
npm install
```

4. **Set up environment variables**
   - Create `.env` file in the `server` directory with the required variables
   - Create `.env` file in the `client` directory with the required variables

5. **Start MongoDB**
   - Ensure MongoDB is running locally or use MongoDB Atlas

6. **Run the Application**

   **Backend (from server directory):**
   ```bash
   npm start
   # or for development with nodemon
   npm run server
   ```

   **Frontend (from client directory):**
   ```bash
   npm run dev
   ```

7. **Access the Application**
   - Frontend: http://localhost:5173 (or the port shown in terminal)
   - Backend: http://localhost:3000

## 📖 API Endpoints

### User Routes
- `POST /api/users/register` - Register new user
- `POST /api/users/login` - Login user
- `GET /api/users/data` - Get user data (protected)

### Resume Routes
- `POST /api/resumes/create` - Create new resume (protected)
- `GET /api/resumes/get/:resumeId` - Get resume by ID (protected)
- `GET /api/resumes/all` - Get all user resumes (protected)
- `PUT /api/resumes/update` - Update resume (protected)
- `DELETE /api/resumes/delete/:resumeId` - Delete resume (protected)
- `GET /api/resumes/public/:resumeId` - Get public resume

### AI Routes
- `POST /api/ai/enhance-pro-sum` - Enhance professional summary (protected)
- `POST /api/ai/enhance-job-desc` - Enhance job description (protected)
- `POST /api/ai/enhance-skills` - Generate skills suggestions (protected)

## 🎯 Key Features Implementation

### Authentication Flow
- Users register with email and password
- Passwords are hashed using bcrypt
- JWT tokens are issued upon successful login
- Protected routes verify JWT tokens via middleware

### Resume Management
- Each resume is associated with a user ID
- Resumes can be marked as public or private
- Public resumes can be shared via unique URLs
- Resume data is stored in MongoDB with a flexible schema

### AI Enhancement
- Integration with OpenAI API for content improvement
- System prompts optimized for resume writing
- ATS-friendly suggestions
- Context-aware enhancements

### Image Upload
- Profile pictures uploaded via ImageKit
- Secure image storage and CDN delivery
- Multer for handling multipart/form-data

## 🌐 Deployment

The application is configured for deployment on Vercel:
- `vercel.json` files are included for both frontend and backend
- Separate deployments for client and server recommended
- Environment variables must be set in Vercel dashboard

## 📝 Usage

1. **Register/Login**: Create an account or log in
2. **Create Resume**: Click "Create New Resume" from dashboard
3. **Fill Information**: Add your personal info, experience, education, etc.
4. **Enhance with AI**: Use AI suggestions to improve your content
5. **Customize**: Choose template and customize colors
6. **Preview**: See real-time preview of your resume
7. **Download**: Export as PDF or share with unique URL

## 📄 License

This project is open source and available under the [MIT License](LICENSE).

**Star ⭐ this repository if you find it helpful!**
