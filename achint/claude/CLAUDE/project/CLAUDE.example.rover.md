# CLAUDE.md
<!-- This is to be placed at the project level -->
<!-- This specific example works well for the CarverRover project -->

This file provides guidance when working with code in this repository.

## Core Development Rules

### JavaScript/HTML5 Best Practices

#### Code Organization
- **Modular Structure**: Use ES6 modules (`import`/`export`) to organize code into logical components
- **Separation of Concerns**: Keep HTML (structure), CSS (styling), and JavaScript (behavior) separate
- **File Naming**: Use kebab-case for files (`user-profile.js`) and camelCase for variables/functions

#### JavaScript Fundamentals
- **Strict Mode**: Always use `'use strict';` or ES6 modules (implicit strict mode)
- **Variable Declarations**: Prefer `const` > `let` > avoid `var`
- **Arrow Functions**: Use for callbacks and short functions: `array.map(item => item.id)`
- **Async/Await**: Prefer over Promises chains for better readability
- **Error Handling**: Always wrap async operations in try-catch blocks

#### HTML5 Standards
- **Semantic HTML**: Use proper elements (`<header>`, `<nav>`, `<main>`, `<article>`, `<section>`)
- **Meta Tags**: Include viewport, charset, and description meta tags
- **Forms**: Use proper input types (`email`, `tel`, `date`) and validation attributes

#### Performance & Security
- **Script Loading**: Use `defer` or `async` attributes, place scripts before closing `</body>`
- **Input Validation**: Validate and sanitize all user inputs on both client and server

### Python Backend Best Practices

#### Code Organization & Structure
- **Package Structure**: Use `__init__.py` files to create proper packages and control imports
- **Dependency Injection**: Use FastAPI's dependency injection system for database sessions and config
- **Layer Separation**: Keep API routes, business logic, and data access layers separate
- **Configuration**: Use Pydantic models for configuration and environment variable management

#### Code Style
- PEP 8 naming (snake_case for functions/variables)
- Class names in PascalCase
- Constants in UPPER_SNAKE_CASE
- Document with docstrings
- Use f-strings for formatting

#### Package Management
- ONLY use pip for package management

#### FastAPI Specific
- **Type Hints**: Always use type hints for function parameters and return values
- **Pydantic Models**: Define request/response models using Pydantic for automatic validation
- **Error Handling**: Use HTTPException for API errors and custom exception handlers
- **Async Operations**: Use `async/await` for I/O operations (database, external APIs)
- **Dependency Management**: Use `Depends()` for shared dependencies like database sessions

#### Database & SQLAlchemy
- **Session Management**: Use context managers or FastAPI dependencies for database sessions
- **Query Optimization**: Use `select()` with `joinedload()` or `selectinload()` to avoid N+1 queries
- **Migrations**: Use Alembic for database schema migrations in production
- **Connection Pooling**: Configure proper connection pools for concurrent requests

#### Security & Validation
- **Input Validation**: Validate all inputs using Pydantic models and custom validators
- **SQL Injection**: Use SQLAlchemy ORM queries instead of raw SQL
- **API Authentication**: Implement proper authentication/authorization for sensitive endpoints
- **Environment Variables**: Store secrets in environment variables, never in code
- **CORS Configuration**: Configure CORS properly for frontend-backend communication


## Project Overview

Carver Rover is a compliance pain point identification tool that analyzes social media content (Reddit, X, YouTube, etc.) to identify compliance-related issues and pain points. It uses OpenAI's LLM for content analysis and provides both a REST API and web interface for exploring results.

## Architecture & Structure

**Core Components:**
- `src/cppit/api/` - FastAPI backend (port 8000) with REST endpoints
- `src/cppit/web_ui/` - Flask frontend (port 5000) with Jinja2 templates  
- `src/cppit/collectors/` - Data collection modules (Reddit, YouTube APIs)
- `src/cppit/analyzers/` - Content analysis using OpenAI LLM and ML clustering
- `src/cppit/database/` - SQLAlchemy ORM with SQLite databases
- `src/cppit/scheduler/` - APScheduler for automated data collection
- `src/cppit/processors/` - Data processing and transformation logic

**Configuration System:**
- YAML config files in `configs/` directory define data sources, keywords, and collection parameters
- Environment variables in `.env` for API keys (OpenAI, Reddit, YouTube)
- Each config creates its own SQLite database in `data/` directory

## Development Commands

**Start/Stop Services:**
```bash
./control.sh start    # Start FastAPI backend + Flask frontend
./control.sh stop     # Stop all services
./control.sh restart  # Restart all services
./control.sh status   # Check service health
./control.sh logs     # View recent logs
```

**Testing:**
```bash
pytest                        # Run all tests
pytest tests/test_*.py        # Run specific test files
```

**Code Quality:**
```bash
black .                       # Code formatting
isort .                       # Import sorting  
flake8 .                      # Linting
mypy .                        # Type checking
```

**Virtual Environment Setup:**
```bash
python3.10 -m venv carver-rover-venv
source carver-rover-venv/bin/activate  # macOS/Linux
pip install -r requirements.txt
```

**CRITICAL: Virtual Environment Location**
- **ALWAYS activate the correct virtual environment before any pip operations**
- **Virtual environment path**: `./venvs/carver-rover`
- **Activation command**: `source ./venvs/carver-rover/bin/activate`
- **Verify activation**: Check with `which python` - should show `./venvs/carver-rover/bin/python`

## Key Technical Details

**Database Architecture:**
- Each YAML config creates a separate SQLite database
- Database name comes from `run_name` field in config
- Tables: complaints, contacts, complaint_embeddings, cluster_info
- Use `?db_name=<config_name>` query param to access specific databases via API

**LLM Integration:**
- OpenAI GPT-4o-mini for content analysis
- Sentence transformers for embeddings
- Temperature=0 for consistent analysis results

**Service URLs:**
- Frontend: http://127.0.0.1:5000
- Backend API: http://127.0.0.1:8000  
- API Docs: http://127.0.0.1:8000/docs

**Log Files:**
- Backend: `logs/backend.log`
- Frontend: `logs/frontend.log`
- Scheduler: `logs/scheduler_run_*.log`
