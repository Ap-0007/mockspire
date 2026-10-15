# Mockspire

> AI-powered mock interviews to help you practice, analyze, and improve your interview performance.

[![CI](https://github.com/anujsharma8d/mockspire/actions/workflows/ci.yml/badge.svg)](https://github.com/anujsharma8d/mockspire/actions/workflows/ci.yml)
[![License: MIT](https://img.shields.io/badge/License-MIT-green.svg)](LICENSE)
[![PRs Welcome](https://img.shields.io/badge/PRs-welcome-brightgreen.svg)](CONTRIBUTING.md)

Mockspire is an AI-powered interview preparation platform that simulates realistic interviews and delivers personalized feedback on your performance. It helps you practice interview questions, understand your strengths, identify areas for improvement, and build confidence before real interviews.

**Live demo:** [mockspire.vercel.app](https://mockspire.vercel.app/)

> The backend runs on a free hosting tier. If nobody has used the app for a while, the first request can take up to a minute to wake the server up. After that it responds normally.

---

## Screenshots

![Mockspire Landing Page](client/src/assets/Landing.png)

![Mockspire Dashboard](client/src/assets/MockspireDashboard.png)

---

## Table of Contents

- [Features](#features)
- [Tech Stack](#tech-stack)
- [Architecture](#architecture)
- [How It Works](#how-it-works)
- [Project Structure](#project-structure)
- [Getting Started](#getting-started)
- [Environment Variables](#environment-variables)
- [Running the Application](#running-the-application)
- [Interview Insights](#interview-insights)
- [Who Is Mockspire For?](#who-is-mockspire-for)
- [Roadmap](#roadmap)
- [Contributing](#contributing)
- [License](#license)
- [Author](#author)

---

## Features

### AI-Powered Interviews
Generate personalized interview questions based on:
- Job role
- Interview type
- Difficulty level

### Realistic Interview Practice
Practice in a structured environment designed to simulate a real interview.

### Speech-to-Text
Answer questions out loud. Your spoken responses are converted into text using the browser's Web Speech API.

> Speech recognition works best in Chromium-based browsers such as Chrome and Edge. Support varies in other browsers.

### Performance Analysis
Get detailed feedback after each interview, including a performance score and insights.

### Core Strengths
See the areas where you performed well.

### Focus Areas
Find out what needs improvement and what to work on next.

### Performance Tracking
Review previous interview results and track your progress over time.

### User Authentication
Secure account management with:
- Sign up and login
- Protected routes
- JWT authentication

### Responsive UI
Works across desktop, tablet, and mobile.

---

## Tech Stack

**Frontend**
- React
- React Router
- Tailwind CSS
- Lucide React
- Axios
- Web Speech API

**Backend**
- Node.js
- Express.js
- MongoDB with Mongoose
- JWT authentication

**AI**
- Google Gemini API for question generation, answer evaluation, and feedback

---

## Architecture

```text
                    ┌───────────────────┐
                    │      React        │
                    │     Frontend      │
                    └─────────┬─────────┘
                              │
                              │ REST API
                              ▼
                    ┌───────────────────┐
                    │     Express.js    │
                    │      Backend      │
                    └───────┬─────┬─────┘
                            │     │
                ┌───────────┘     └───────────┐
                ▼                             ▼
       ┌─────────────────┐          ┌─────────────────┐
       │     MongoDB     │          │       AI        │
       │     Database    │          │     Services    │
       └─────────────────┘          └─────────────────┘
```

---

## How It Works

1. Create an account
2. Choose an interview
3. AI generates questions
4. Take the interview
5. AI analyzes your responses
6. View your results
7. Review Core Strengths and Focus Areas
8. Improve and practice again

---

## Project Structure

```text
mockspire/
├── .github/
│   ├── ISSUE_TEMPLATE/       # Bug report and feature request templates
│   └── workflows/            # CI
│
├── client/                   # React frontend
│   ├── src/
│   │   ├── api/              # API calls
│   │   ├── assets/
│   │   ├── components/       # Reusable UI components
│   │   ├── pages/            # Route-level pages
│   │   ├── App.jsx
│   │   └── main.jsx
│   ├── .env.example
│   └── package.json
│
├── server/                   # Express backend
│   ├── controllers/          # Request handlers
│   ├── middleware/           # Auth and other middleware
│   ├── models/               # Mongoose models
│   ├── routes/               # API routes
│   ├── services/             # Business logic and AI calls
│   ├── .env.example
│   ├── server.js
│   └── package.json
│
├── CODE_OF_CONDUCT.md
├── CONTRIBUTING.md
├── LICENSE
└── README.md
```

---

## Getting Started

### Prerequisites

- [Node.js](https://nodejs.org/) and npm
- A MongoDB database: [MongoDB](https://www.mongodb.com/) installed locally, or a free [MongoDB Atlas](https://www.mongodb.com/atlas) cluster
- A Gemini API key from [Google AI Studio](https://aistudio.google.com/)

### Clone the Repository

```bash
git clone https://github.com/anujsharma8d/mockspire.git
cd mockspire
```

### Install Dependencies

**Frontend**
```bash
cd client
npm install
```

**Backend** (in a second terminal)
```bash
cd server
npm install
```

---

## Environment Variables

Each folder has a `.env.example` file. Copy it to `.env` and fill in your own values.

**macOS / Linux**
```bash
cp client/.env.example client/.env
cp server/.env.example server/.env
```

**Windows (PowerShell)**
```powershell
Copy-Item client/.env.example client/.env
Copy-Item server/.env.example server/.env
```

**`client/.env`**
```env
VITE_API_URL=http://localhost:5000
```

**`server/.env`**
```env
PORT=5000
MONGO_URI=your_mongodb_connection_string
JWT_SECRET=your_jwt_secret
GEMINI_API_KEY=your_gemini_api_key
```

> **Never commit `.env` files or real keys to GitHub.**

---

## Running the Application

**Start the backend**
```bash
cd server
npm run dev
```
The backend runs on `http://localhost:5000`.

**Start the frontend** (in another terminal)
```bash
cd client
npm run dev
```
The frontend runs on the Vite dev server. Open the URL printed in your terminal.

---

## Interview Insights

After each interview, Mockspire gives you a performance breakdown:

| Insight | Description |
|---|---|
| Performance Score | Your overall interview performance. |
| Core Strengths | The areas where you performed strongly. |
| Focus Areas | Specific areas that need more practice. |
| Detailed Feedback | What you did well and what could be improved. |

---

## Who Is Mockspire For?

People preparing for:
- Technical interviews
- HR interviews
- Behavioral interviews
- Software engineering interviews
- Job placements
- Career transitions

---

## Roadmap

Planned improvements. Many of these are good places to contribute.

- [ ] AI voice for interview questions
- [ ] Speech analysis
- [ ] Video interview practice
- [ ] Resume-based interview generation
- [ ] More detailed performance analytics
- [ ] Personalized preparation plans
- [ ] Multiple interview languages

---

## Contributing

Contributions are welcome, from bug fixes and docs to new features.

1. Read the [Contributing Guide](CONTRIBUTING.md) and the [Code of Conduct](CODE_OF_CONDUCT.md).
2. Pick an issue, ideally one labeled [`good first issue`](https://github.com/anujsharma8d/mockspire/issues?q=is%3Aopen+label%3A%22good+first+issue%22), and comment on it so others know you're working on it.
3. Fork the repository, create a branch, and open a pull request.

Found a bug or have an idea? [Open an issue](https://github.com/anujsharma8d/mockspire/issues/new/choose).

---

## License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.

---

## Author

**Anuj Sharma**

Built with the MERN stack.

---

If you find Mockspire useful, consider giving the repository a ⭐.