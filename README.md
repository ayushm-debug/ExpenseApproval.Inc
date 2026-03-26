# Expense Approval System

Corporate expense submission and approval with role-based access (Employee, Manager, Admin, Finance).

## Development

Prerequisites: Node.js and npm.

```sh
npm i
npm run dev
```

The app runs on Vite (see `vite.config.ts` for the exact port).

Optional: set `VITE_API_URL` (e.g. `http://localhost:4000`) in a `.env` file so the UI targets your API. If unset, the client defaults to `http://localhost:4000`.

## Backend API (Express)

From the `server/` directory:

```sh
cd server
npm install
npm start
```

Default API port: **4000**. Set environment variables:

| Variable | Purpose |
|----------|---------|
| `ORACLE_USER`, `ORACLE_PASSWORD`, `ORACLE_CONNECTION_STRING` | Oracle connection pool |
| `JWT_SECRET` | **Required in production** — signing key for access tokens |
| `JWT_EXPIRES_IN` | Optional token lifetime (default `7d`) |
| `PORT` | Optional (default `4000`) |

`POST /auth/login` returns `{ token, user }`. Authenticated routes expect `Authorization: Bearer <token>`.

