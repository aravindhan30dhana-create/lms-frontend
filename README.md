LMS Frontend

This repository contains the frontend for the Learning Management System (LMS). It is built using React (Vite), TypeScript, Tailwind CSS, and integrates with your backend APIs for courses, users, authentication, and more.

🚀 Live Demo

Visit the production build here:
https://lms-frontend-two-olive.vercel.app/

📂 Project Structure
src/
 ├── components/          # UI components
 ├── contexts/            # React context providers (AuthContext, etc.)
 ├── hooks/               # Custom hooks (useToast, etc.)
 ├── pages/               # Route pages (Home, Courses, Dashboard, Signup, Login)
 ├── lib/                 # API utilities (axios instance, etc.)
 ├── styles/              # Tailwind + custom styles
 └── App.tsx              # Application entry point with router


Other important files:

.env.example — Shows which environment variables to provide

vite.config.ts — Vite configuration

package.json — Dependencies & scripts

tailwind.config.ts — Tailwind CSS configuration

🛠️ Technologies Used

React + TypeScript

Vite (fast build tooling)

Tailwind CSS (utility-first styling)

React Router (navigation)

Axios (HTTP requests)

Context API for authentication & global state

Vercel for deployment

⚙️ Configuration
Environment Variables

Create a .env file in the project root (copy from .env.example) and provide the following:

VITE_API_URL=https://lms-backend-production-c5d8.up.railway.app/api


This variable points to your backend APIs in production.
For local development you might set:

VITE_API_URL=http://localhost:8080/api

▶️ Running Locally

Clone the repository

git clone https://github.com/aravindhan30dhana-create/lms-frontend.git
cd lms-frontend


Install dependencies

npm install


Start the dev server

npm run dev


Open http://localhost:5173
 (or whichever port Vite shows) in your browser.

Build for production

npm run build


Preview the production build locally

npm run preview

🔐 Authentication Flow

Users sign up via /auth/signup endpoint (via backend)

On signup or login, the JWT token and user info are stored in localStorage and React Context

Once authenticated, the UI redirects based on user.role (e.g., /student/dashboard, /instructor/dashboard)

Protected routes only render when isAuthenticated is true

🧪 API Usage

Below are some key endpoints (backend) you’ll consume from the frontend:

Feature	HTTP Method	Endpoint
Get all courses	GET	/courses
Get course by ID	GET	/courses/{id}
Enroll in course	POST	/student/enroll/{courseId}
Mark lesson complete	PUT	/student/enrollments/{enrollId}/complete-lesson
User signup	POST	/auth/signup
User login	POST	/auth/login

Note: These endpoints are relative to VITE_API_URL defined in your .env.

🧩 Key Features & Pages

Home / Course list page

Course detail page (view lessons, enroll, mark progress)

Student dashboard (view enrolled courses, progress stats)

Instructor dashboard (if implemented)

Authentication pages (Login, Signup)

Dynamic routing & role-based UI

🗂️ Deployment

This frontend is deployed to Vercel:

Push commits to GitHub → Vercel automatically builds & deploys

Environment variable VITE_API_URL configured in Vercel dashboard

Live site: https://lms-frontend-two-olive.vercel.app/

🤝 Contributing

Contributions are welcome!

Fork the repository

Create a new branch (git checkout -b feature/YourFeature)

Commit your changes (git commit -m 'Add YourFeature')

Push to your fork (git push origin feature/YourFeature)

Open a Pull Request

📄 License

This project is open-source under the MIT License.
