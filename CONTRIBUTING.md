# Contributing to Mockspire

Thanks for your interest in Mockspire! This project is an AI-powered mock interview platform built with the MERN stack, and contributions of every size are welcome: bug fixes, new features, documentation, tests, and ideas.

This guide explains how to set up the project, pick something to work on, and get your changes merged.

## Table of Contents

- [Ways to contribute](#ways-to-contribute)
- [Getting started](#getting-started)
- [Project structure](#project-structure)
- [Finding something to work on](#finding-something-to-work-on)
- [Branches and commits](#branches-and-commits)
- [Code guidelines](#code-guidelines)
- [Opening a pull request](#opening-a-pull-request)
- [Reporting bugs](#reporting-bugs)
- [Suggesting features](#suggesting-features)
- [Reporting security issues](#reporting-security-issues)
- [License](#license)

## Ways to contribute

- Fix bugs or improve error handling
- Add features from the "Future Improvements" list in the README
- Improve the UI and accessibility
- Write or improve tests
- Improve documentation, setup instructions, and examples
- Add interview question types and categories
- Review open pull requests and help triage issues

Please be respectful and constructive in every issue, pull request, and discussion. Assume good intent, give specific feedback, and help newcomers.

## Getting started

### Prerequisites

- [Node.js](https://nodejs.org/) and npm
- A MongoDB database: either [MongoDB](https://www.mongodb.com/) installed locally, or a free MongoDB Atlas cluster
- A Gemini API key (create one in Google AI Studio)

### 1. Fork and clone

Fork the repository on GitHub, then clone your fork:

```bash
git clone https://github.com/<your-username>/mockspire.git
cd mockspire
git remote add upstream https://github.com/anujsharma8d/mockspire.git
```

### 2. Install dependencies

```bash
# Frontend
cd client
npm install

# Backend (in a second terminal)
cd server
npm install
```

### 3. Set up environment variables

Create a `.env` file in `client/`:

```
VITE_API_URL=http://localhost:5000
```

Create a `.env` file in `server/`:

```
PORT=5000
MONGO_URI=your_mongodb_connection_string
JWT_SECRET=your_jwt_secret
GEMINI_API_KEY=your_gemini_api_key
```

**Never commit `.env` files or real keys.** If you accidentally commit a secret, rotate it immediately and tell a maintainer.

### 4. Run the app

```bash
# Backend
cd server
npm run dev

# Frontend (separate terminal)
cd client
npm run dev
```

The backend runs on `http://localhost:5000`. The frontend runs on the Vite dev server URL printed in your terminal.

### 5. Keep your fork up to date

```bash
git fetch upstream
git checkout main
git merge upstream/main
```

## Project structure

```
mockspire/
├── client/                 # React frontend (Vite, Tailwind CSS)
│   └── src/
│       ├── api/            # Axios API calls
│       ├── assets/
│       ├── components/     # Reusable UI components
│       └── pages/          # Route-level pages
└── server/                 # Express backend
    ├── controllers/        # Request handlers
    ├── middleware/         # Auth and other middleware
    ├── models/             # Mongoose models
    ├── routes/             # API routes
    └── services/           # Business logic and AI calls
```

## Finding something to work on

1. Browse the [issues](https://github.com/anujsharma8d/mockspire/issues) and look for the `good first issue` and `help wanted` labels.
2. Comment on the issue to say you'd like to take it, and wait for a maintainer to confirm before you start. This avoids two people doing the same work.
3. If you have an idea that has no issue yet, open one first and describe what you want to change. This saves you from building something that doesn't fit the project.

Work on one issue per pull request.

## Branches and commits

Create a branch from an up-to-date `main`:

```bash
git checkout -b feat/short-description
```

Use a prefix that matches the kind of change:

| Prefix | Use for |
| --- | --- |
| `feat/` | New features |
| `fix/` | Bug fixes |
| `docs/` | Documentation only |
| `refactor/` | Code changes that don't alter behavior |
| `test/` | Adding or improving tests |
| `chore/` | Tooling, dependencies, config |

Write commit messages in the [Conventional Commits](https://www.conventionalcommits.org/) style:

```
feat: add session history page
fix: handle empty answer in scoring service
docs: clarify MongoDB Atlas setup
```

Keep each commit focused and the message short and specific.

## Code guidelines

- **Match the existing style.** Follow the naming, formatting, and file organization already used in the folder you're editing.
- **Keep changes small and focused.** Avoid unrelated reformatting or refactors in the same pull request.
- **Frontend:** keep components small and reusable, put API calls in `client/src/api/`, and make sure new UI works on desktop, tablet, and mobile.
- **Backend:** keep route handlers thin. Put business logic and AI calls in `server/services/`, validate request input, and return clear error messages with the right status codes.
- **AI features:** keep prompts and model calls inside the services layer, never hardcode API keys, and handle failed or malformed model responses gracefully.
- **Secrets and config:** read configuration from environment variables. Don't hardcode URLs, keys, or secrets.
- **Dependencies:** don't add a new package unless it's needed, and mention why in your pull request.
- **Tests and linting:** if the package you're changing has lint or test scripts, run them and make sure they pass before opening a pull request. When you fix a bug or add logic, add a test if the project has a test setup for that area.

## Opening a pull request

Before you open it:

- [ ] The app runs locally and your change works as intended
- [ ] No console errors or warnings introduced by your change
- [ ] No secrets, `.env` files, or unrelated files are included
- [ ] Lint and tests pass, if available
- [ ] Your branch is up to date with `main`

Then:

1. Push your branch to your fork and open a pull request against `main`.
2. Give it a clear title, following the commit style above.
3. Describe **what** you changed and **why**, and link the issue with `Closes #<issue-number>`.
4. For UI changes, include before and after screenshots or a short screen recording.
5. Mark the pull request as a draft if it isn't ready for review yet.

A maintainer will review your pull request, usually within a few days. Reviews are about the code, not the person. Expect questions and suggestions, and push follow-up commits to the same branch to address them. Once approved, a maintainer will merge it.

## Reporting bugs

Open an issue and include:

- A clear description of the problem
- Steps to reproduce it
- What you expected to happen and what actually happened
- Your environment (OS, browser, Node.js version)
- Screenshots, console output, or server logs if they help

Please remove any API keys, tokens, or personal data from logs before pasting them.

## Suggesting features

Open an issue describing:

- The problem you want to solve
- Your proposed solution
- Any alternatives you considered

Discussing an idea before writing code helps make sure it fits the project's direction.

## Reporting security issues

Please do not open a public issue for security vulnerabilities. Use GitHub's private vulnerability reporting on the repository's Security tab if it is enabled, or contact the maintainer through their GitHub profile.

## License

By contributing to Mockspire, you agree that your contributions will be licensed under the project's [MIT License](LICENSE).