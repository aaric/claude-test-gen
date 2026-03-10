# Todo Application

A web-based todo application built with Python, FastAPI, and vanilla JavaScript.

## Features

- Create, read, update, and delete todos
- Mark todos as complete/incomplete
- Priority levels (low, medium, high)
- Filter todos by status (All, Active, Completed)
- Clean, responsive web interface
- Auto-generated API documentation

## Technology Stack

- **Backend**: FastAPI + Uvicorn
- **Frontend**: Vanilla HTML/CSS/JavaScript
- **Data Validation**: Pydantic
- **Storage**: In-memory (data is lost on restart)

## Project Setup

- **Python Version**: 3.12+
- **Virtual Environment**: `.venv/`
- **Package Manager**: `uv`

## Running the Application

```bash
# Install dependencies
uv sync

# Start the server
uv run python main.py
```

The application will be available at:
- **Frontend**: http://localhost:8000
- **API Documentation (Swagger)**: http://localhost:8000/docs
- **API Documentation (ReDoc)**: http://localhost:8000/redoc

## API Endpoints

| Method | Endpoint | Description |
|--------|----------|-------------|
| GET | `/` | Serve frontend HTML |
| GET | `/api/todos` | List all todos |
| GET | `/api/todos/{id}` | Get specific todo |
| POST | `/api/todos` | Create new todo |
| PUT | `/api/todos/{id}` | Update todo |
| DELETE | `/api/todos/{id}` | Delete todo |
| PATCH | `/api/todos/{id}/toggle` | Toggle completed status |
| DELETE | `/api/todos` | Clear all todos |

## Project Structure

```
.
├── .venv/              # Virtual environment
├── app/                # Application package
│   ├── __init__.py
│   ├── main.py         # FastAPI app and routes
│   ├── models.py       # Pydantic models
│   └── storage.py      # In-memory storage
├── static/             # Frontend assets
│   ├── index.html      # Main HTML page
│   ├── styles.css      # Styling
│   └── app.js          # Frontend JavaScript
├── main.py             # Entry point (starts server)
├── pyproject.toml      # Project configuration
├── .gitignore          # Git ignore rules
├── .python-version     # Python version specification
└── CLAUDE.md           # Claude Code guidance
```

## Data Model

```python
class TodoItem:
    id: str              # UUID
    title: str           # Required (1-200 chars)
    description: str     # Optional (max 1000 chars)
    completed: bool      # Default: False
    created_at: datetime
    updated_at: datetime
    priority: Literal["low", "medium", "high"]  # Default: "medium"
```

## Usage

1. **Add a todo**: Enter a title, optional description, select priority, and click "Add"
2. **Complete a todo**: Click the checkbox next to a todo
3. **Edit a todo**: Click the ✏️ icon to edit
4. **Delete a todo**: Click the 🗑️ icon to delete
5. **Filter todos**: Use "All", "Active", or "Completed" buttons
6. **Clear completed**: Click "Clear Completed" to remove all completed todos

## Development

The server runs with auto-reload enabled by default. Any changes to Python files will automatically restart the server.

For production deployment, disable reload:
```python
# In main.py, change reload=True to reload=False
```
