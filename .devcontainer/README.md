# Dev Container Configuration

This repository includes a minimal Dev Container configuration optimized for code reviews and quick fixes in web-based VS Code environments (GitHub Codespaces, VS Code for the Web).

## What's Included

### Base Environment
- **PHP 8.2** (matching project requirements)
- **Node.js 18** (for frontend tooling)
- **Git** (pre-installed in base image)

### VS Code Extensions
- **PHP Development**: Intelephense for PHP IntelliSense
- **Symfony Framework**: Symfony for VS Code with Twig support
- **JavaScript & TypeScript**: TypeScript support, Prettier, ESLint
- **Angular**: Angular Language Service
- **Configuration Files**: XML, YAML, CSV support
- **EditorConfig**: Consistent code formatting

### Optimizations
- Minimal extension set for fast startup
- Composer cache volume for faster dependency management
- No automatic dependency installation (keeps startup fast)
- Configured for code review workflow

## Usage

### GitHub Codespaces
1. Click "Code" → "Codespaces" → "Create codespace on [branch]"
2. Wait for the container to build and start
3. Begin code review or make quick fixes

### VS Code for the Web
1. Navigate to `github.dev/[repository-url]`
2. The dev container will be automatically detected and suggested

### Local VS Code with Dev Containers Extension
1. Install the "Dev Containers" extension
2. Open command palette (Ctrl/Cmd + Shift + P)
3. Run "Dev Containers: Reopen in Container"

## Manual Setup (if needed)
If you need to install dependencies manually:
```bash
# Install PHP dependencies (lightweight)
composer install --no-dev --optimize-autoloader

# Install Node.js dependencies
npm install
```

## File Associations
The configuration includes automatic file associations for:
- `.twig` files → HTML (for Symfony templates)
- `.yml` files → YAML
- `.neon` files → YAML (for PHPStan configuration)

## Performance Notes
This configuration is optimized for:
- **Fast startup** (minimal features and extensions)
- **Low resource usage** (no development servers or watchers)
- **Code review workflow** (IntelliSense and syntax highlighting)
- **Quick fixes** (linting and formatting tools)

For full development, consider using the project's Docker setup or local development environment.