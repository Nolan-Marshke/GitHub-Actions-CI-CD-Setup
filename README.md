# Tech Quiz Application

A full-stack application featuring a quiz interface with automated CI/CD pipeline. This application uses a React frontend and Express/MongoDB backend to provide an interactive quiz experience.

## 📝 Description

Tech Quiz is an interactive web application that presents users with technology-related questions, primarily focused on Python programming. The application features a clean, responsive UI and provides immediate feedback on answers.

## 🛠️ Technologies Used

### Frontend
- React
- Cypress (for component testing)
- Bootstrap (for styling)

### Backend
- Node.js
- Express
- MongoDB with Mongoose
- TypeScript

### DevOps
- GitHub Actions (CI/CD)
- Render (Hosting)

## ✨ Features

- Interactive quiz interface with multiple-choice questions
- Score tracking and result display
- Responsive design for both desktop and mobile
- Comprehensive test coverage with Cypress component tests
- Automated CI/CD pipeline with GitHub Actions

## 🚀 Installation & Setup

### Prerequisites
- Node.js (v18 or later recommended)
- MongoDB (local instance or MongoDB Atlas)
- Git

### Local Development Setup

1. **Clone the repository:**
    ```bash
    git clone https://github.com/yourusername/tech-quiz.git
    cd tech-quiz
    ```

2. **Set up environment variables:**
    ```bash
    # Create a .env file in the server directory
    cp server/.env.EXAMPLE server/.env
    # Edit the .env file with your MongoDB connection string
    ```

3. **Install dependencies:**
    ```bash
    # Install root dependencies
    npm install

    # Install client dependencies
    cd client
    npm install

    # Install server dependencies
    cd ../server
    npm install
    ```

4. **Build the server:**
    ```bash
    npm run build
    ```

5. **Seed the database:**
    ```bash
    npm run seed
    ```

6. **Start the development servers:**
    ```bash
    # Start the server (from the server directory)
    npm run watch

    # In a separate terminal, start the client (from the client directory)
    cd ../client
    npm run dev
    ```

7. **Access the application:**
    - Frontend: http://localhost:5173
    - Backend API: http://localhost:3001/api

## 🔄 CI/CD Workflow

This project uses a Git Flow inspired branching strategy with automated CI/CD through GitHub Actions.

### Branch Structure
- `main` - Production branch, deployed to Render
- `develop` - Integration branch for features
- Feature branches - Created from develop for individual features

### Development Workflow

1. **Create a feature branch from develop:**
    ```bash
    git checkout develop
    git pull origin develop
    git checkout -b feature/your-feature-name
    ```

2. **Make changes and commit them:**
    ```bash
    git add .
    git commit -m "Descriptive message about your changes"
    ```

3. **Push your feature branch and create a Pull Request to develop:**
    ```bash
    git push -u origin feature/your-feature-name
    ```
    Then create a PR on GitHub targeting the develop branch.
    
4. GitHub Actions will automatically run Cypress component tests on your PR.
5. After review and approval, merge your PR into develop.
6. When ready to deploy, create a PR from develop to main and merge it.
7. GitHub Actions will automatically trigger deployment to Render.

### GitHub Actions Workflows
- **cypress-tests.yml** - Runs component tests on PRs to develop
- **render-deploy.yml** - Triggers deployment to Render when code is merged to main

## 📋 Usage

### Taking a Quiz
1. Navigate to the home page
2. Click "Start Quiz" to begin
3. Select an answer for each question
4. View your score at the end and choose to take another quiz if desired





📝 License
This project is licensed under the MIT License - see the LICENSE file for details.
