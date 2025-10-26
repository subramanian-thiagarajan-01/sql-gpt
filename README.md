# sql-gpt: AI-Powered SQL Generation

This repository serves as the umbrella project for an AI-powered application that generates SQL queries from natural language prompts. It uses Git submodules to manage the separate backend (API) and frontend (user interface) repositories.

## 🚀 Getting Started

Follow these steps to set up and run the entire application locally.

### Prerequisites

You'll need the following installed on your system:

- **Git**: For cloning the repository and managing submodules.
- **Python (3.13 or newer)**: For the backend API and its dependencies (managed by `uv`).
- **Node.js (LTS recommended)**: For the frontend application and its dependencies (managed by `npm`/`yarn`/`pnpm`).
- **`uv` (Ultrafast Python package installer and resolver)**: Used to manage the backend's virtual environment and dependencies.
  - Installation: `pip install uv` (or follow the official `uv` documentation).

### Setup Instructions

#### 1. Clone the Repository

Clone the parent repository and recursively initialize its submodules:

```bash
git clone --recurse-submodules https://github.com/your-username/sql-gpt.git
cd sql-gpt
```

If you cloned without `--recurse-submodules`, run this:

```bash
git submodule update --init --recursive
```

#### 2. Configure Environment Variables

Both the backend and frontend will require configuration. Typically, you'll need to set an OpenAI API Key or similar credentials for the AI model.

- Create a `.env` file in the `backend/` directory (see the `backend/README.md` for specifics).
- Create an `.env.local` file in the `frontend/` directory (see the `frontend/README.md` for specifics).

#### 3. Set up the Backend

Navigate to the backend directory and follow its setup instructions:

```bash
cd backend
# Follow instructions in backend/README.md
uv venv      # Creates a virtual environment
uv sync      # Installs dependencies
cd ..        # Return to the root
```

#### 4. Set up the Frontend

Navigate to the frontend directory and follow its setup instructions:

```bash
cd frontend
# Follow instructions in frontend/README.md
npm install  # Or yarn/pnpm install
cd ..        # Return to the root
```

## 🏃 Running the Application

Once both components are set up, you can start them independently.

### 1. Start the Backend API

Navigate to the `backend` folder and run:

```bash
cd backend
source .venv/bin/activate  # Activate the virtual environment (Linux/macOS)
# or .venv\Scripts\activate (Windows)
uvicorn main:app --reload --port 8000
cd ..
```

The API should be available at `http://localhost:8000`.

### 2. Start the Frontend

Navigate to the `frontend` folder and run:

```bash
cd frontend
npm run dev
cd ..
```

The application should open in your browser, typically at `http://localhost:3000`.

---

## 📁 Project Structure

```
sql-gpt/
├── backend/          # Backend API (submodule)
├── frontend/         # Frontend UI (submodule)
└── README.md         # This file
```

## 🤝 Contributing

Contributions are welcome! Please refer to the individual repository READMEs for contribution guidelines.

## 📄 License

See LICENSE file for details.
