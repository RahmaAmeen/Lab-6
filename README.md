# Software Project I: Todos monorepo (Tutorial 5)

Two apps that run side by side:

| Folder      | What                                   | URL                    |
| ----------- | -------------------------------------- | ---------------------- |
| `backend/`  | NestJS REST API, todos kept in memory  | http://localhost:3000  |
| `frontend/` | Next.js 16 App Router routing demos    | http://localhost:3001  |

The frontend reads its data from the backend, so **start the backend first**.

## Requirements

- Node.js 20.9 or newer (`node -v`)
- npm

## Run it

Open two terminals.

**Terminal 1: backend**

```bash
cd backend
npm install
npm run start:dev        # http://localhost:3000/todos
```

**Terminal 2: frontend**

```bash
cd frontend
npm install
cp .env.example .env.local   # first time only (Windows: copy .env.example .env.local)
npm run dev                  # http://localhost:3001
```

Open http://localhost:3001. The home page links to every routing demo.

## Backend API

| Method | Path         | Result                                        |
| ------ | ------------ | --------------------------------------------- |
| GET    | `/todos`     | All todos                                     |
| GET    | `/todos/:id` | One todo, or **404** if it doesn't exist      |
| POST   | `/todos`     | Create `{ "title": "..." }`                   |
| DELETE | `/todos/:id` | Delete a todo                                 |

The data lives in memory. It starts with 3 seed todos and resets every time the
backend restarts. CORS is enabled for `http://localhost:3001` so the browser can
call the API directly from the frontend.

## More

See [`frontend/README.md`](frontend/README.md) for the folder tree, the URL-to-concept
table and the student exercises.
