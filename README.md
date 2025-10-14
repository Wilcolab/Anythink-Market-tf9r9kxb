
# Anythink-Market: Python & Node.js Servers

This project contains two servers:

- **Python FastAPI server** (port 8000)
- **Node.js Express server** (port 8001)

The Node.js server is a migration of the Python server's routes and logic, now implemented using Express.

## Project Structure

- `python-server/`: FastAPI server implementation
- `my-express-app/`: Express server implementation
- `docker-compose.yml`: Multi-container orchestration for both servers

## Migration Details

The following routes and logic were migrated from Python (FastAPI) to Node.js (Express):

| Route         | Method | Python (FastAPI) Behavior                | Node.js (Express) Behavior         |
|---------------|--------|------------------------------------------|------------------------------------|
| `/`           | GET    | Returns "Hello World"                    | Returns "Hello World"              |
| `/tasks`      | GET    | Returns a list of tasks                  | Returns a list of tasks            |
| `/tasks`      | POST   | Adds a task to the list (JSON body)      | Adds a task to the list (JSON body)|

Both servers use an in-memory array for tasks.

## Getting Started

To run both servers using Docker Compose:

```shell
docker compose up
```

This will build and start both the FastAPI and Express servers. Access them at:

- FastAPI (Python): [http://localhost:8000](http://localhost:8000)
- Express (Node.js): [http://localhost:8001](http://localhost:8001)

## API Routes (Node.js)

- `GET /` — Returns "Hello World"
- `GET /tasks` — Returns the task list
- `POST /tasks` — Adds a task to the list. Expects JSON: `{ "text": "..." }`

## API Routes (Python)

- `GET /` — Returns "Hello World"
- `GET /tasks` — Returns the task list
- `POST /tasks` — Adds a task to the list. Expects JSON: `{ "text": "..." }`

---

See each subdirectory's README for more details on running the servers individually.
