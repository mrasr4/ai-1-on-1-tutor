# Adaptive Language Learning System

Welcome to the Adaptive Language Learning System! This project is an interactive platform designed to provide a personalized language learning experience, aligned with CEFR standards, and optimized for the Replit IDE.

## Project Overview

This system aims to deliver:
*   **Proficiency Assessment:** To gauge user's current language level.
*   **Adaptive Learning Paths:** Personalized lesson plans based on assessment results and progress.
*   **Interactive Practice Modules:** Including a code editor for syntax/grammar, audio recorder for pronunciation, and an interactive terminal for conversation simulation.
*   **Comprehensive Feedback:** Detailed analysis of errors and targeted suggestions.
*   **Progress Tracking:** Monitoring user development across various skills.
*   **Cultural Sensitivity:** Content designed to be culturally appropriate and inclusive.

(More details can be found in the `memory-bank/` directory, particularly `projectRequirementsDocument.md`.)

## Tech Stack

*   **Frontend:** React, Tailwind CSS, `react-router-dom`, Clerk (for auth)
*   **Backend:** Node.js, Express.js, Pino (logger), Clerk (for auth)
*   **Database:** SQLite (via `better-sqlite3`)
*   **Development Environment:** Replit IDE

(Full details in `memory-bank/techStackDocument.md`.)

## Getting Started

### Prerequisites

*   A Replit account.
*   Node.js and npm (usually pre-installed on Replit Node.js templates).

### Setup Instructions

1.  **Clone/Fork the Repl:** Get a copy of this project in your Replit workspace.

2.  **Environment Variables:**
    *   This project uses Clerk for authentication. You will need to sign up at [Clerk.com](https://clerk.com), create an application, and get your Publishable Key and Secret Key.
    *   **IMPORTANT:** The file `.env.example` lists the required environment variables. Due to a system restriction during automated setup, this file might not have been created. If it's missing, please create it manually by copying the content below into a new file named `.env.example` at the root of the project:
        ```env
        # Clerk Authentication - Get these from your Clerk Dashboard
        # Frontend (React - name might change based on build tool, e.g., VITE_CLERK_PUBLISHABLE_KEY)
        NEXT_PUBLIC_CLERK_PUBLISHABLE_KEY="pk_test_YOUR_PUBLISHABLE_KEY"
        CLERK_SECRET_KEY="sk_test_YOUR_SECRET_KEY"

        # Backend Configuration
        LOG_LEVEL="info"

        # Database (SQLite - filename or path relative to project root)
        DATABASE_URL="./database/app.db" # Path used by initDb.js

        # Application specific
        # APP_BASE_URL="http://localhost:3000" # Adjust if needed
        ```
    *   Once you have `.env.example`, copy it to a new file named `.env` (this file is ignored by Git):
        ```bash
        cp .env.example .env
        ```
    *   Open the `.env` file and replace the placeholder values (especially for Clerk keys) with your actual credentials. In Replit, it's highly recommended to use **Replit Secrets** for these values instead of directly editing the `.env` file for production/shared Repls. The application code (e.g., `src/frontend/main.jsx`, `src/backend/server.js`) expects these environment variables to be available via `process.env` or `import.meta.env` (for Vite frontend).

3.  **Install Dependencies:**
    Open the Replit Shell/Console and run:
    ```bash
    npm install
    ```

4.  **Initialize the Database:**
    This will create the SQLite database file and set up the necessary tables.
    ```bash
    npm run db:init
    ```

5.  **(Optional) Git Initialization:**
    If you haven't already and want to track changes with Git:
    ```bash
    git init
    git add .
    git commit -m "Initial project setup"
    ```
    You can then connect this to a remote repository (e.g., on GitHub) using Replit's Git integration or command line.

### Running the Application (Development Mode)

To start the development servers for both frontend and backend concurrently:

```bash
npm run dev
```

This command (using `npm-run-all`) will typically:
*   Start the backend server (e.g., using `nodemon` on `src/backend/server.js`).
*   Start the frontend development server (e.g., Vite, once configured in `package.json` script `dev:frontend`).

Look for output in the console indicating the ports on which the frontend and backend are running. Replit should automatically provide a URL to access the running application.

**Note on Frontend Dev Script:** The `dev:frontend` script in `package.json` is currently a placeholder (`echo "TODO: Implement frontend development script (e.g., vite)" && exit 1`). You will need to replace this with the actual command to start your React frontend development server (e.g., `vite`, `react-scripts start` if using Create React App, etc.) based on your chosen React setup within Replit.

## Linting and Formatting

*   To check for linting issues:
    ```bash
    npm run lint
    ```
*   To automatically fix linting issues:
    ```bash
    npm run lint:fix
    ```
*   To check formatting with Prettier:
    ```bash
    npm run format:check
    ```
*   To automatically format files with Prettier:
    ```bash
    npm run format
    ```

## Project Structure

A brief overview of the main directories:

*   `memory-bank/`: Contains all project planning and documentation.
*   `public/`: Static assets for the frontend.
*   `src/`: Main application source code.
    *   `frontend/`: React frontend application.
    *   `backend/`: Node.js/Express backend application.
    *   `common/`: Code shared between frontend and backend (e.g., types - if using TypeScript).
*   `database/`: SQLite database file (`app.db`) and related scripts.
*   `scripts/`: Utility scripts (currently none).
*   `tests/`: Automated tests (to be developed).

(Full details in `memory-bank/projectStructure.md`.)

## Contributing

(Details to be added later, e.g., branching strategy, PR process if this becomes a collaborative project.)

## License

This project is currently UNLICENSED. 
