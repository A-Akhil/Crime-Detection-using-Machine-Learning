# Cross-Platform Docker Development Setup

This setup enables live code synchronization between your local directory and Docker container without platform-specific scripts.

## Prerequisites
- Docker installed on your system
- Docker Compose installed (usually comes with Docker Desktop)

## Setup Instructions

### 1. Build and Start Development Environment
```bash
docker-compose -f docker-compose.dev.yml up --build
```

### 2. For Subsequent Runs (No Rebuild Needed)
```bash
docker-compose -f docker-compose.dev.yml up
```

### 3. Stop the Environment
```bash
docker-compose -f docker-compose.dev.yml down
```

## How It Works

### Volume Mounting
- Your local project directory is mounted to `/code` in the container
- Changes made locally are immediately reflected in the container
- Changes made in the container are reflected locally

### Excluded Directories
- `venv/` - Virtual environment (container has its own)
- `__pycache__/` - Python cache files
- `.git/` - Git directory

### Live Development Benefits
- ✅ Edit code locally with your preferred IDE
- ✅ Changes automatically sync to container
- ✅ Django auto-reloads on file changes
- ✅ No rebuilds needed for code changes
- ✅ Works on Windows, Linux, and Mac

## Development Workflow

1. **Start the environment:**
   ```bash
   docker-compose -f docker-compose.dev.yml up
   ```

2. **Edit your code** in your local IDE (VS Code, PyCharm, etc.)

3. **See changes immediately** - Django will automatically reload

4. **Access your application** at `http://localhost:8000`

5. **Stop when done:**
   ```bash
   docker-compose -f docker-compose.dev.yml down
   ```

## Troubleshooting

### If you need to rebuild (only for dependency changes):
```bash
docker-compose -f docker-compose.dev.yml up --build
```

### If you need to reset the database:
```bash
docker-compose -f docker-compose.dev.yml exec web python manage.py migrate
```

### If you need to run Django commands:
```bash
docker-compose -f docker-compose.dev.yml exec web python manage.py <command>
```

## Platform-Specific Notes

### Windows
- Use PowerShell or Command Prompt
- Docker Desktop must be running
- File paths work automatically with Docker Desktop

### Linux
- Use terminal
- Ensure your user is in the docker group
- File permissions are preserved

### macOS
- Use terminal
- Docker Desktop must be running
- File paths work automatically with Docker Desktop

## When to Use Full Rebuild

You only need to rebuild when:
- Dependencies change (requirement.txt modified)
- Dockerfile changes
- New system packages needed

For code changes in Python files, HTML templates, CSS, etc., no rebuild is needed!
