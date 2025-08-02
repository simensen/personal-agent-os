# Tech Stack

## Context

Global tech stack defaults for Agent OS projects, overridable in project-specific `.agent-os/product/tech-stack.md`.

- App Framework: Symfony 7.3, Laravel 12.x
- Language: PHP 8.4+
- Primary Database: MySQL
- JavaScript Framework: Vue 3.5
- Build Tool: Vite
- Import Strategy: Node.js modules
- Package Manager: npm, pnpm
- Node Version: 22 LTS
- CSS Framework: TailwindCSS 4.0+
- UI Components: Tailwind UI
- Font Provider: Google Fonts
- Font Loading: Self-hosted for performance
- Icons: Lucide Vue Next components
- Application Hosting: Digital Ocean App Platform/Droplets
- Hosting Region: Primary region based on user base
- Database Hosting: Digital Ocean Managed MySQL
- Database Backups: Daily automated
- Asset Access: Private with signed URLs
- CI/CD Platform: GitHub Actions
- CI/CD Trigger: Push to main/staging branches
- Tests: Run before deployment
- Production Environment: main branch
- Staging Environment: staging branch
