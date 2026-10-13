# Smart rural issue management guide

A React/Vite frontend and Express/PostgreSQL backend for reporting local issues, publishing notices, and administering users. The frontend also contains informational welfare-scheme pages.

## Correct database configuration

The current backend uses PostgreSQL through `pg`, despite the stale MongoDB setting in `backend/.env.example`. Create `backend/.env` with:

```dotenv
DATABASE_URL=postgresql://USER:PASSWORD@HOST:5432/DATABASE
JWT_SECRET=replace-with-a-long-random-development-secret
PORT=5000
FRONTEND_URL=http://localhost:3000
NODE_ENV=development
```

Use a disposable PostgreSQL database supporting TLS. `backend/src/config/database.js` currently enables TLS with certificate verification disabled; that is an implementation limitation, not a general PostgreSQL requirement. The database user needs permission to initialize the tables in `backend/src/config/schema.sql`. Startup invokes the initializer automatically.

## Run

In the backend:

```sh
cd backend
npm ci
npm run dev
```

In a second terminal at the repository root:

```sh
npm ci
npm run dev
```

Vite is explicitly configured for port 3000; the API defaults to 5000. Set root `VITE_API_URL=http://localhost:5000/api` if overriding the frontend API destination. Vite variables are bundled at build time.

## Architecture and API

`src/lib/AuthContext.tsx` manages client auth; `src/lib/api.ts` attaches Bearer tokens stored in localStorage. The backend mounts `/api/auth`, `/api/issues`, `/api/notices`, and `/api/users`. Auth routes support registration/login/profile, issues support reporting and comments, and notices/users include admin operations. Role checks are in middleware and route handlers; public list/detail routes are also present.

`/api/health` reports that the HTTP process is alive. It does not verify database readiness: the server listens even if asynchronous initialization fails. Check startup logs and a database-backed endpoint as well.

## Checks, deployment, and known mismatches

Root `npm run lint` performs TypeScript checking; `npm run build` creates `build/`; `npm run preview` previews it. Backend `npm test` is a placeholder. Use `backend/postman_collection.json` and `TESTING_GUIDE.md` for manual exercises against disposable data. `resetDb.js`, seed SQL, and admin scripts can alter stored records and should be reviewed before use.

The frontend API helper includes a user-delete operation that is not implemented in the current user router. Do not assume every helper has a matching endpoint. Deploy the Vite build and Node backend with matching frontend origin/API URL, PostgreSQL connectivity, and a configured JWT secret. A Supabase-hosted database is accessed through the backend's PostgreSQL connection; no Supabase browser key is needed for this frontend.

## More documentation

- [Source, command, and configuration reference](REFERENCE.md)
- [Contributing](../CONTRIBUTING.md)
