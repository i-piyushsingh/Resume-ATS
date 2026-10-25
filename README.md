# Resumely (Resume ATS)

**Your next role starts with a sharper story.** Resumely is a full-stack web app that turns a good resume into a confident application. Upload your resume, run a free resume signal check, and see what recruiters and ATS systems notice first.

![Resumely login page](screenshots/login.png)

## Features

- Sign up and sign in with your own account
- Personal dashboard for your resume checks
- Upload a resume and run an analysis
- Results page with feedback on your resume
- Secure file uploads, with optional Cloudinary storage

## Tech stack

| Layer | Technology |
|---|---|
| Frontend | React (JSX components), Redux state management with slices, CSS |
| Backend | Node.js with routes, controllers, middlewares and services |
| Database | MongoDB |
| File storage | Cloudinary (when configured) |
| Testing | Test files for both frontend and backend |

## Project structure

```
.
├── backEnd/
│   ├── config/          Cloudinary, database, environment and security setup
│   ├── controllers/     Auth and analysis request handlers
│   ├── middlewares/     Auth, error handling and file upload
│   ├── models/          User and analysis models
│   ├── routes/          API routes
│   ├── services/        Auth, analysis and file storage logic
│   ├── utils/           Validation helpers
│   ├── tests/
│   └── index.js         Server entry point
│
├── frontEnd/
│   ├── public/
│   └── src/
│       ├── components/  Analyzer, AuthScreen, Dashboard, Results
│       ├── constants/   Sample data
│       ├── services/    API calls
│       ├── store/       Redux slices for auth and analysis
│       ├── tests/
│       └── App.jsx
│
└── screenshots/
```

## Getting started

### Prerequisites

- Node.js 18 or newer
- A MongoDB database (local or hosted)
- Optional: a Cloudinary account for file storage

### 1. Clone the repository

```bash
git clone <repo-url>
cd <repo-folder>
```

### 2. Set up the backend

```bash
cd backEnd
npm install
```

Create a `.env` file inside `backEnd/` with your own values. The exact variable names are in `backEnd/config/env.config.js`. For Cloudinary they are:

```
CLOUDINARY_CLOUD_NAME=your_cloud_name
CLOUDINARY_API_KEY=your_api_key
CLOUDINARY_API_SECRET=your_api_secret
```

Never commit your `.env` file. Then start the server:

```bash
npm start
```

The server runs on port `8080` and prints `MongoDB Connected` once the database is reachable.

### 3. Set up the frontend

In a new terminal:

```bash
cd frontEnd
npm install
npm start
```

Check `frontEnd/package.json` for the exact scripts. Open the URL it prints to see the app.

## Running the tests

```bash
cd backEnd
npm test
```

## Notes

- This project was built and tested on SandboxPro, then published to GitHub.
- Keep API keys and database credentials in `.env` only. They must never appear in the code or in commits.
