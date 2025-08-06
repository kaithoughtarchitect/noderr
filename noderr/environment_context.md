# Universal Environment Context Profile Template

<!-- 
🚨 CRITICAL ENVIRONMENT AWARENESS CHECK 🚨

Before proceeding, answer these questions:
1. Are you in a development environment? (Replit workspace, Codespaces, local machine, etc.)
2. What do you see in your current shell prompt?
3. Is there a separate deployed/production version of this app?

YOUR MISSION: Document the DEVELOPMENT environment you're currently in.
You are NOT documenting the production/deployed environment.

Remember:
- Development = Where you write and test code
- Production = Where real users access the app
- NEVER confuse these two!
-->

<!-- 
AI AGENT INSTRUCTIONS - READ THIS FIRST:

This is a UNIVERSAL TEMPLATE that adapts to ANY platform (Replit, Lovable, AWS, local, etc.).

CRITICAL: You are documenting the DEVELOPMENT environment, NOT the production/deployed environment.

WHAT TO DO:
1. Run the COMPREHENSIVE DISCOVERY SEQUENCE below to detect your platform
2. Test EVERY command in your actual environment
3. Replace ALL [bracketed] placeholders in this file with real values
4. Update this existing `environment_context.md` file directly with the completed content
5. Document platform-specific tools, limitations, and workflows
6. Verify all commands work before finalizing

CRITICAL DISCOVERY SEQUENCE:
Run these commands first to identify your platform and capabilities:
```bash
# ENVIRONMENT TYPE CHECK - RUN THIS FIRST!
echo "=== ENVIRONMENT TYPE CHECK ==="
echo "Current working directory: $(pwd)"
echo "Development environment indicators:"
env | grep -E "REPL|CLOUD|VIRTUAL|AWS|GCP|AZURE|HEROKU|VERCEL|NETLIFY|LOVABLE|CODEPEN|CODESANDBOX|GITPOD|GITHUB|CODESPACES"
echo ""
echo "⚠️ CONFIRMING: I am documenting the DEVELOPMENT workspace, not production"
echo "=== END ENVIRONMENT CHECK ==="

# Platform Detection
pwd && echo "Working directory: $(pwd)"
uname -a
echo "Shell: $SHELL"
whoami && id
env | grep -E "REPL|CLOUD|VIRTUAL|AWS|GCP|AZURE|HEROKU|VERCEL|NETLIFY|LOVABLE|CODEPEN|CODESANDBOX|GITPOD|GITHUB|CODESPACES"

# Tool Availability Check
for tool in git node npm python3 python pip pip3 yarn pnpm go rust java mvn gradle docker docker-compose kubectl helm terraform ansible; do
    which $tool >/dev/null 2>&1 && echo "✓ $tool: $(which $tool)" || echo "✗ $tool: not available"
done

# Process & Port Management Detection
lsof -i :5000 2>/dev/null && echo "✓ lsof available" || echo "✗ lsof not available"
netstat -tln 2>/dev/null | head -5 && echo "✓ netstat available" || echo "✗ netstat not available"
ss -tln 2>/dev/null | head -5 && echo "✓ ss available" || echo "✗ ss not available"

# Package Manager Detection
npm --version 2>/dev/null && echo "✓ npm: $(npm --version)" || echo "✗ npm not available"
yarn --version 2>/dev/null && echo "✓ yarn: $(yarn --version)" || echo "✗ yarn not available"
pnpm --version 2>/dev/null && echo "✓ pnpm: $(pnpm --version)" || echo "✗ pnpm not available"
pip --version 2>/dev/null && echo "✓ pip: $(pip --version)" || echo "✗ pip not available"
pip3 --version 2>/dev/null && echo "✓ pip3: $(pip3 --version)" || echo "✗ pip3 not available"

# Platform-Specific Tool Detection
# Replit
which replit 2>/dev/null && echo "✓ REPLIT DETECTED" || echo "✗ Not Replit"
# Lovable
which lovable 2>/dev/null && echo "✓ LOVABLE DETECTED" || echo "✗ Not Lovable"
# AWS
which aws 2>/dev/null && echo "✓ AWS CLI DETECTED" || echo "✗ AWS CLI not available"
# Docker
which docker 2>/dev/null && echo "✓ DOCKER DETECTED" || echo "✗ Docker not available"
# Kubernetes
which kubectl 2>/dev/null && echo "✓ KUBERNETES DETECTED" || echo "✗ Kubernetes not available"
```

ENHANCED INSTRUCTIONS:
- Do NOT guess commands - test everything
- Do NOT leave any [brackets] in the final file
- Document ALL platform-specific tools, workflows, and limitations
- If a standard tool doesn't work, find and document the platform-specific alternative
- Pay special attention to process management, package installation, and deployment workflows
- This document will be your ONLY reference for this environment
- CRITICAL: Distinguish between development preview URLs and production deployed URLs
-->

## START HERE - FILL OUT EVERYTHING BELOW THIS LINE

```yaml
# Environment Metadata
environment:
  type: "[development|testing|staging|production]"
  provider: "[local|replit|lovable|aws|gcp|azure|heroku|vercel|netlify|codespaces|gitpod|other]"
  lifecycle: "[persistent|ephemeral]"
  purpose: "[Primary purpose and project association]"
  
  # CRITICAL: Document which environment this profile represents
  environment_focus: "DEVELOPMENT - This profile documents the development workspace"
  
  # Platform-Specific Detection Results
  platform_detection:
    identified_platform: "[detected platform from env vars]"
    special_environment_vars: "[list key env vars that indicate platform]"
    available_tools: "[list detected tools]"
    missing_standard_tools: "[list missing tools and alternatives]"
    
  orchestration_hints:
    auto_seed_on_reset: [true|false]
    strict_linting: [true|false]
    backup_before_migrations: [true|false]
    uses_workflow_system: [true|false]
    uses_container_orchestration: [true|false]
    uses_serverless_deployment: [true|false]
```

**Profile Name:** [Platform-Stack-Version, e.g., Replit-NodeJS-v20, Lovable-React-v18, AWS-ECS-Python-3.11]  
**Environment ID:** [unique identifier, e.g., ENV-2024-01-15-replit-001]  
**Last Updated:** [ISO 8601 timestamp]  
**Validated By:** [Agent ID/Version]  
**Confidence Level:** [High/Medium/Low - based on testing completeness]

---

## Purpose
This document serves as the complete operational manual for AI agents working in this specific **DEVELOPMENT** environment. It translates abstract goals into concrete, tested commands. Every command listed here has been verified to work in this environment.

**Critical Rule:** ALWAYS use these exact commands. Do not rely on general knowledge about similar environments.

**Environment Focus:** This document describes the DEVELOPMENT environment, not production.

---

## 1. Critical Platform Rules & Gotchas

### 1.1 Critical Don'ts - DO NOT VIOLATE THESE RULES
```yaml
critical_donts:
  # Platform-specific restrictions that will break functionality
  process_management:
    - "NEVER manually restart servers - use platform-specific restart method"
    - "NEVER kill processes with pkill - use platform workflow system"
    - "NEVER use manual npm run dev - use platform startup method"
  
  package_management:
    - "NEVER manually npm install new packages - use platform package manager"
    - "NEVER edit package.json directly - use platform dependency system"
    - "NEVER pip install globally - use platform python package system"
  
  network_configuration:
    - "NEVER use localhost for server binding - use platform-specific host"
    - "NEVER hardcode ports - use platform-provided port configuration"
    - "NEVER ignore platform networking requirements"
    - "NEVER use production URLs for development testing"
  
  file_system:
    - "NEVER use absolute paths like /repo/ - use relative paths"
    - "NEVER assume standard Linux file permissions"
    - "NEVER write to protected directories"
  
  environment_confusion:
    - "NEVER test features on the production deployed URL"
    - "NEVER confuse the development preview with the live app"
    - "NEVER make changes thinking you're in dev but affecting production"
  
  platform_specific:
    # Fill in platform-specific critical restrictions, e.g.:
    # - "NEVER use packager_tool for Replit without language parameter"
    # - "NEVER bypass platform authentication for cloud platforms"
    # - "NEVER ignore container resource limits in containerized environments"
```

### 1.2 Lessons Learned - Debugging Gotchas
```yaml
debugging_gotchas:
  # Platform-specific behaviors that affect development workflow
  console_behavior:
    - "Console logs appear in [platform-specific location], not terminal"
    - "Error messages may be filtered or formatted differently"
    - "Debug output routing varies by platform"
  
  development_workflow:
    - "File changes trigger automatic rebuilds/restarts"
    - "Hot reload behavior differs from standard development"
    - "Build processes may have platform-specific timing"
  
  network_behavior:
    - "WebSocket connections require specific URL patterns"
    - "Proxy behavior affects API calls and static assets"
    - "Port forwarding may have platform-specific requirements"
    - "Development preview URL is different from deployed URL"
  
  resource_management:
    - "Memory limits may cause unexpected termination"
    - "CPU throttling affects performance characteristics"
    - "Storage persistence varies by platform type"
  
  platform_ui:
    - "Platform-specific UI panels contain critical information"
    - "Workflow status indicators show actual system state"
    - "Error notifications may appear in unexpected locations"
  
  environment_separation:
    - "Development changes appear in preview, not production"
    - "Production deployment requires explicit action"
    - "Preview and production have different URLs and states"
  
  platform_specific:
    # Fill in platform-specific gotchas, e.g.:
    # - "Replit console logs appear in bottom panel workflow view"
    # - "Lovable deployments auto-trigger on file changes"
    # - "AWS container logs require specific CloudWatch configuration"
```

---

## 2. Environment Discovery & Validation

### 2.1 System Information
```bash
# Operating System Details
[Actual command that works, e.g.:]
# uname -a
# Returns: [actual output]

# Shell Information
[Actual command, e.g.:]
# echo $SHELL && $SHELL --version
# Returns: [actual output]

# Current User & Permissions
[Actual command, e.g.:]
# whoami && id
# Returns: [actual output]

# Environment Type Confirmation
# echo "This profile documents: DEVELOPMENT environment"
# Returns: DEVELOPMENT environment
```

### 2.2 Platform-Specific Detection
```bash
# Platform Detection Results
[Document detected platform, e.g.:]
# env | grep -E "REPL|CLOUD|VIRTUAL|AWS|GCP|AZURE|HEROKU|VERCEL|NETLIFY|LOVABLE|CODEPEN|CODESANDBOX|GITPOD|GITHUB|CODESPACES"
# Returns: [actual env vars that indicate platform]

# Available Platform-Specific Tools
[List platform-specific tools, e.g.:]
# which replit aws lovable docker kubectl
# Returns: [actual tool paths or "not found"]

# Development vs Production Indicators
# [Document how to tell if you're in dev vs prod]
# Example: "REPL_ID present = development workspace"
```

### 2.3 Available Commands Check
```bash
# Core utilities availability
[Document which essential commands exist, e.g.:]
# for cmd in git node npm python3 curl wget nc lsof netstat ss tree; do which $cmd && echo "✓ $cmd" || echo "✗ $cmd"; done
# Returns: [actual availability results]

# Package managers available
[Document available package managers, e.g.:]
# for pm in npm yarn pnpm pip pip3 gem bundle cargo; do which $pm && echo "✓ $pm: $($pm --version)" || echo "✗ $pm"; done
# Returns: [actual package manager availability]
```

### 2.4 Environment Constraints
```bash
# Disk Space
[Command and threshold, e.g.:]
# df -h /
# Returns: [actual disk usage]

# Memory
[Command and limits, e.g.:]
# free -m
# Returns: [actual memory info]

# Process/File Limits
[Command, e.g.:]
# ulimit -a
# Returns: [actual limits]

# Network Connectivity
[Test external connectivity, e.g.:]
# curl -s https://api.ipify.org
# Returns: [actual IP or connectivity status]
```

---

## 3. Platform-Specific Workflow Management

### 3.1 Process Management System
```bash
# How to start/stop/restart processes in this DEVELOPMENT environment
[Document platform-specific process management, e.g.:]

# For Replit:
# restart_workflow name="Start application"  # NOT manual npm run dev

# For Docker:
# docker-compose restart service_name

# For Kubernetes:
# kubectl rollout restart deployment/app-name

# For Standard Linux:
# systemctl restart service_name
# OR: pm2 restart app_name
# OR: pkill -f "process_name" && npm run dev &

# Current Platform Method:
[Actual method for this platform]
```

### 3.2 Package Management System
```bash
# How to install dependencies in this DEVELOPMENT environment
[Document platform-specific package management, e.g.:]

# For Replit:
# Use packager_tool(install_or_uninstall="install", language_or_system="nodejs", dependency_list=["package"])
# NOT direct npm install

# For Docker:
# Edit Dockerfile, then docker-compose build

# For Standard environments:
# npm install package_name
# OR: yarn add package_name
# OR: pip install package_name

# Current Platform Method:
[Actual method for this platform]
```

### 3.3 Deployment System
```bash
# How to deploy FROM this development environment TO production
# CRITICAL: This describes how to DEPLOY, not how to develop
[Document platform-specific deployment, e.g.:]

# For Replit:
# Built-in deployment via UI - click "Deploy" button
# Creates SEPARATE production instance at .repl.app

# For Vercel:
# vercel --prod
# Deploys FROM development TO production

# For Heroku:
# git push heroku main

# For AWS:
# aws deploy or terraform apply

# For Docker:
# docker build -t app . && docker push

# Current Platform Method:
[Actual method for this platform]

# REMEMBER: Deployment creates/updates PRODUCTION, not development
```

---

## 4. File System Operations

### 4.1 Working Directory Structure
```bash
# Get current directory
pwd
# Returns: [actual path in DEVELOPMENT environment]

# Project root identification
[Document how to identify project root, e.g.:]
# ls -la | grep -E "package.json|requirements.txt|Dockerfile|.git"
# Project root: [actual project root path]

# File system type and permissions
[Document file system characteristics, e.g.:]
# mount | grep "$(pwd)" | head -1
# Returns: [actual mount info]
```

### 4.2 Directory Listing
```bash
# Primary method (with hidden files)
ls -la

# Recursive tree view
[Working command or note if unavailable, e.g.:]
# tree -L 3 -a
# OR: find . -type d -name ".*" -prune -o -print | head -50
# Current method: [actual working command]
```

### 4.3 File Reading & Writing
```bash
# Read entire file
cat [filepath]

# Read with line numbers (for debugging)
cat -n [filepath]

# Check if file exists first
[[ -f [filepath] ]] && cat [filepath] || echo "File not found: [filepath]"

# Platform-specific file writing method
[Document safe file writing method, e.g.:]
# Standard: cat << 'EOF' > [filepath]
# OR: echo "content" > [filepath]
# OR: platform-specific editor commands
# Current method: [actual method that works]

# NOTE: File changes in development may auto-sync to preview
```

---

## 5. Network & Port Management

### 5.1 Network Configuration
```bash
# Network interfaces
[Working command, e.g.:]
# ip addr show
# OR: ifconfig
# OR: platform-specific network command
# Current method: [actual working command]

# Public IP detection (if applicable to dev environment)
[Working command, e.g.:]
# curl -s https://api.ipify.org
# OR: platform-specific IP detection
# Current method: [actual working command]

# DNS resolution test
[Working command, e.g.:]
# nslookup google.com
# OR: dig google.com +short
# OR: platform-specific DNS test
# Current method: [actual working command]
```

### 5.2 Port Management
```bash
# Check port availability IN DEVELOPMENT
[Working command, e.g.:]
# lsof -i :[port]
# OR: netstat -tln | grep :[port]
# OR: ss -tln | grep :[port]
# OR: platform-specific port check
# Current method: [actual working command]

# Test port connectivity
[Working command, e.g.:]
# nc -zv localhost [port]
# OR: curl -s -o /dev/null -w "%{http_code}" http://localhost:[port]
# OR: platform-specific connectivity test
# Current method: [actual working command]
```

### 5.3 Application Access Configuration
```yaml
# CRITICAL: Distinguish between development preview and production deployment
development_server:
  bind_host: "[0.0.0.0|localhost|platform-specific]"
  default_port: [port number]
  alternative_ports: [list of ports]
  
  access_urls:
    # DEVELOPMENT PREVIEW - Use this for ALL development testing
    local_dev_preview: 
      url: "[actual preview URL - e.g., localhost:3000, Replit webview URL]"
      description: "Primary development testing URL"
      how_to_access: "[e.g., 'Visible in Replit preview pane', 'Open browser to localhost:3000']"
      
    # PRODUCTION DEPLOYMENT - Reference only, DO NOT use for testing
    public_deployed_app: 
      url: "[deployed URL if exists, otherwise 'Not deployed yet']"
      description: "Live production app - DO NOT MODIFY during development"
      warning: "⚠️ Changes here affect real users!"
      how_to_deploy: "[e.g., 'Click Deploy button', 'Run deployment command']"
    
  # Platform-specific URL patterns
  platform_url_examples:
    # Replit: preview = [project].[user].repl.co, production = [app].repl.app
    # Vercel: preview = localhost:3000, production = [app].vercel.app
    # Railway: preview = localhost:[port], production = [app].railway.app
    development_pattern: "[platform's dev URL pattern]"
    production_pattern: "[platform's production URL pattern]"
    
  platform_specific_config:
    websocket_url: "[websocket URL pattern if applicable]"
    proxy_requirements: "[any proxy requirements]"
    firewall_rules: "[any firewall considerations]"
```

---

## 6. Version Control & Collaboration

### 6.1 Git Configuration
```bash
# Check git user (in development environment)
git config user.name && git config user.email
# Returns: [actual git config]

# Platform-specific git setup
[Document any platform-specific git requirements, e.g.:]
# For cloud platforms: automatic git config
# For local: manual setup required
# Current setup: [actual configuration method]
```

### 6.2 Collaboration Tools
```bash
# Platform-specific collaboration features
[Document collaboration tools, e.g.:]
# For Replit: built-in multiplayer (development only)
# For Codespaces: GitHub integration
# For local: manual git workflow
# Current platform: [actual collaboration method]

# NOTE: Collaboration typically happens in development, not production
```

---

## 7. Language & Runtime Management

### 7.1 Runtime Detection
```bash
# Node.js
[Test and document, e.g.:]
# node -v && npm -v
# Returns: [actual versions in development environment]

# Python
[Test and document, e.g.:]
# python3 --version && pip3 --version
# Returns: [actual versions in development environment]

# Other runtimes
[Test and document other runtimes, e.g.:]
# go version
# rustc --version
# java -version
# Returns: [actual versions or "not available"]
```

### 7.2 Package Management
```bash
# Primary package manager for this DEVELOPMENT environment
[Document the correct method, e.g.:]
# For Node.js: npm install / yarn add / pnpm add
# For Python: pip install / pip3 install
# For platform-specific: use platform tools
# Current method: [actual method that works]

# Platform-specific package installation
[Document platform-specific requirements, e.g.:]
# For Replit: use packager_tool
# For Docker: modify Dockerfile
# For cloud platforms: use platform package manager
# Current requirement: [actual requirement]
```

---

## 8. Database & Storage Operations

### 8.1 Database System Detection
```yaml
database_system: "[PostgreSQL|MySQL|MongoDB|SQLite|Redis|None]"
connection_method: "[Direct|ORM|ODM|Platform-specific]"
orm_tool: "[Prisma|TypeORM|Sequelize|Drizzle|SQLAlchemy|Mongoose|None]"
connection_source: "[DATABASE_URL env var|Config file|Platform-provided]"

# CRITICAL: Document if database is shared between dev and prod
database_environment:
  development_db: "[separate dev database|shared with production|local only]"
  production_db: "[separate production database|not accessible from dev]"
  data_isolation: "[complete|partial|none]"

platform_specific_database:
  provider: "[Neon|Supabase|AWS RDS|GCP SQL|Azure SQL|Platform-integrated]"
  access_method: "[Direct connection|Platform proxy|Service mesh]"
  management_tools: "[Platform-specific database tools]"
```

### 8.2 Database Operations
```bash
# Database connection test (IN DEVELOPMENT)
[Platform-specific database testing, e.g.:]
# For ORM: npx prisma db pull
# For direct: psql $DATABASE_URL -c "SELECT 1"
# For platform: platform-specific connection test
# Current method: [actual working method]

# Schema management
[Platform-specific schema management, e.g.:]
# For Prisma: npx prisma migrate deploy
# For Drizzle: npx drizzle-kit push
# For platform: platform-specific migration tool
# Current method: [actual working method]

# WARNING: Document if migrations affect production
```

---

## 9. Testing & Quality Assurance

### 9.1 Testing Framework
```bash
# Test execution IN DEVELOPMENT
[Document testing approach, e.g.:]
# npm test
# OR: yarn test
# OR: python -m pytest
# OR: platform-specific test runner
# Current method: [actual working method]

# Code quality tools
[Document linting/formatting, e.g.:]
# npm run lint
# OR: npx eslint .
# OR: flake8 .
# OR: platform-specific linting
# Current method: [actual working method]
```

### 9.2 Build Process
```bash
# Build command (for development)
[Document build process, e.g.:]
# npm run build
# OR: yarn build
# OR: python setup.py build
# OR: platform-specific build
# Current method: [actual working method]

# Build verification
[Document build verification, e.g.:]
# [[ -d "dist" ]] && echo "✓ Build successful"
# OR: platform-specific build verification
# Current method: [actual working method]

# NOTE: Production builds may use different process
```

---

## 10. Debugging & Monitoring

### 10.1 Log Access
```yaml
log_system:
  # Logs in DEVELOPMENT environment
  application_logs: "[location or access method in dev]"
  system_logs: "[location or access method in dev]"
  platform_logs: "[platform-specific log access in dev]"
  
  # How development logs differ from production
  dev_vs_prod_logs:
    development: "[e.g., 'console output in preview pane']"
    production: "[e.g., 'CloudWatch logs', 'platform log viewer']"
  
  real_time_monitoring: "[how to monitor in real-time during development]"
  log_aggregation: "[log aggregation system if available]"
```

### 10.2 Debugging Tools
```bash
# Debug mode activation IN DEVELOPMENT
[Document debugging approach, e.g.:]
# NODE_ENV=development npm run dev
# OR: platform-specific debug mode
# Current method: [actual method]

# Process monitoring
[Document process monitoring, e.g.:]
# ps aux | grep [process]
# OR: platform-specific process monitoring
# Current method: [actual method]
```

---

## 11. Security & Secrets Management

### 11.1 Secret Storage
```yaml
secrets_management:
  method: "[environment_variables|platform_secrets|vault|config_files]"
  access_pattern: "[how to access secrets in code]"
  storage_location: "[where secrets are stored]"
  
  # CRITICAL: Document secret handling differences
  dev_vs_prod_secrets:
    development: "[e.g., '.env file', 'platform dev secrets']"
    production: "[e.g., 'platform prod secrets', 'different values']"
    isolation: "[complete|partial|shared]"
  
  platform_specific:
    secret_ui: "[platform secret management UI if available]"
    secret_injection: "[how secrets are injected]"
    secret_rotation: "[secret rotation capabilities]"
```

### 11.2 Security Best Practices
```bash
# Security scanning IN DEVELOPMENT
[Document security tools, e.g.:]
# npm audit
# OR: platform-specific security scanning
# Current method: [actual method]

# Secret detection
[Document secret detection, e.g.:]
# grep -r "password\|secret\|key" . --exclude-dir=node_modules
# OR: platform-specific secret detection
# Current method: [actual method]
```

---

## 12. Platform-Specific Features & Limitations

### 12.1 Platform Features
```yaml
platform_features:
  # Development environment features
  multiplayer_editing: [true|false]
  real_time_collaboration: [true|false]
  integrated_terminal: [true|false]
  preview_pane: [true|false]
  hot_reload: [true|false]
  
  # Deployment features (separate from development)
  built_in_deployment: [true|false]
  automatic_https: [true|false - for production]
  custom_domains: [true|false - for production]
  
  # Platform integration
  database_integration: [true|false]
  ai_assistance: [true|false]
  
  unique_features:
    - "[list unique platform features]"
```

### 12.2 Platform Limitations
```yaml
platform_limitations:
  # Development environment limitations
  no_sudo_access: [true|false]
  limited_system_tools: [true|false]
  restricted_network_access: [true|false]
  ephemeral_storage: [true|false]
  process_limits: [true|false]
  memory_constraints: [true|false]
  
  # Important distinctions
  dev_prod_separation:
    separate_urls: [true|false]
    separate_databases: [true|false]
    separate_configs: [true|false]
  
  specific_restrictions:
    - "[list specific restrictions]"
```

### 12.3 Platform-Specific Workflows
```bash
# Development workflow
[Document platform-specific development workflow, e.g.:]
# 1. Start development server: [platform-specific command]
# 2. Make changes: [platform-specific file editing]
# 3. Test changes: [use local_dev_preview URL]
# 4. Deploy to production: [platform-specific deployment]

# Emergency procedures
[Document emergency procedures, e.g.:]
# 1. Service restart: [platform-specific restart method]
# 2. Rollback: [platform-specific rollback method]
# 3. Debug: [platform-specific debugging method]

# CRITICAL: Always test in development before deploying
```

---

## 13. Performance & Resource Monitoring

### 13.1 Resource Monitoring
```bash
# CPU & Memory monitoring IN DEVELOPMENT
[Document monitoring approach, e.g.:]
# top -b -n 1 | head -20
# OR: platform-specific monitoring
# Current method: [actual method]

# Network monitoring
[Document network monitoring, e.g.:]
# netstat -s | grep -i error
# OR: platform-specific network monitoring
# Current method: [actual method]
```

### 13.2 Performance Optimization
```bash
# Performance testing IN DEVELOPMENT
[Document performance testing, e.g.:]
# time curl -s http://localhost:5000/health
# OR: time curl -s [local_dev_preview_url]/health
# OR: platform-specific performance testing
# Current method: [actual method]

# NOTE: Production performance may differ significantly
```

---

## 14. Error Recovery & Troubleshooting

### 14.1 Common Platform-Specific Errors
```yaml
common_errors:
  dependency_issues:
    detection: "[how to detect dependency issues]"
    solution: "[platform-specific solution]"
    
  process_management:
    detection: "[how to detect process issues]"
    solution: "[platform-specific solution]"
    
  network_connectivity:
    detection: "[how to detect network issues]"
    solution: "[platform-specific solution]"
    
  storage_issues:
    detection: "[how to detect storage issues]"
    solution: "[platform-specific solution]"
    
  environment_confusion:
    detection: "Testing on wrong URL (prod instead of dev)"
    solution: "Always use local_dev_preview URL for testing"
```

### 14.2 Recovery Procedures
```bash
# Full DEVELOPMENT environment reset
[Document full reset procedure, e.g.:]
# For Replit: use restart button (affects dev only)
# For Docker: docker-compose down && docker-compose up
# For local: manual cleanup and restart
# Current method: [actual method]

# Partial recovery
[Document partial recovery, e.g.:]
# Clear cache: [platform-specific cache clearing]
# Restart services: [platform-specific service restart]
# Current method: [actual method]

# NOTE: These procedures affect DEVELOPMENT only
```

---

## 15. Quick Reference Card

```bash
# DEVELOPMENT Environment Quick Commands:
[List the most important commands for this platform]

# Essential workflow:
1. Always work in DEVELOPMENT environment
2. Test using local_dev_preview URL: [actual URL]
3. Deploy to production using: [deployment method]
4. Production URL (DO NOT use for testing): [prod URL]

# Emergency commands:
[Document emergency procedures]

# Platform-specific reminders:
[List critical platform-specific rules]

# Environment check:
echo "Current environment: DEVELOPMENT"
echo "Preview URL: [local_dev_preview]"
echo "Production URL (DO NOT USE): [public_deployed_app]"
```

---

## 16. Environment Verification

Run this final check to confirm correct environment documentation:

```bash
echo "=== FINAL ENVIRONMENT VERIFICATION ==="
echo "Environment type: DEVELOPMENT"
echo "Preview/test URL: [local_dev_preview URL]"
echo "Production URL (reference only): [public_deployed_app URL or 'Not deployed']"
echo ""
echo "✓ I will use [local_dev_preview URL] for ALL testing"
echo "✓ I understand [public_deployed_app URL] is production"
echo "✓ This profile documents the DEVELOPMENT environment"
echo "=== VERIFICATION COMPLETE ==="
```

---

## Validation Checklist

Before considering this profile complete, verify:

- [ ] Environment type clearly marked as DEVELOPMENT
- [ ] Platform correctly identified and documented
- [ ] All commands tested and working in development
- [ ] Both local_dev_preview and public_deployed_app URLs documented
- [ ] Clear distinction between development and production
- [ ] Platform-specific tools and workflows documented
- [ ] Limitations and constraints clearly stated
- [ ] Error recovery procedures tested
- [ ] Security considerations addressed
- [ ] Performance baselines documented
- [ ] All placeholders replaced with actual values
- [ ] Final verification confirms development focus

---

_End of Universal Environment Context Profile_

<!-- 
FINAL CHECKLIST FOR AI AGENT:
- [ ] Updated existing `environment_context.md` file in place
- [ ] Ran comprehensive discovery sequence
- [ ] Clearly identified this as DEVELOPMENT environment
- [ ] Tested every single command
- [ ] Replaced ALL [bracketed] placeholders
- [ ] Documented BOTH development and production URLs
- [ ] Made clear which URL to use for testing
- [ ] Documented platform-specific features and limitations
- [ ] Verified file updated correctly in original location
- [ ] No [brackets] remain in document
- [ ] All commands produce expected output
- [ ] Platform-specific workflows documented
- [ ] Error recovery procedures tested

SUCCESS INDICATORS:
✅ Platform correctly identified and documented
✅ Development vs production clearly distinguished
✅ Both URLs documented with clear usage instructions
✅ All platform-specific tools and workflows captured
✅ No generic assumptions - everything tested
✅ Another AI agent could operate effectively using this profile
✅ Emergency procedures documented and tested
✅ Agent knows to use local_dev_preview for ALL testing

This profile now serves as the definitive reference for this specific DEVELOPMENT environment.
-->
