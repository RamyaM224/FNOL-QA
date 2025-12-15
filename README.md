# FNOL Portal — Development

This repository contains the FNOL (First Notice Of Loss) portal.

Quick start in Codespaces:
1. Open this repo in GitHub Codespaces (or open locally).
2. Codespace will use .devcontainer/devcontainer.json to install tools, forward ports and run postCreateCommand.
3. After codespace initialization:
   - Backend: http://localhost:8080
   - Frontend: http://localhost:3000
4. To run locally with docker-compose:
   - cp .env.example .env
   - docker-compose up --build
   - ./scripts/bootstrap.sh

What's here:
- .devcontainer/ — Codespace config
- docker-compose.yml — local services (db, mock-policy)
- scripts/ — helper scripts (migrations, seed)
- seed-data/ — fixture data (policies, work items)
- docs/ — architecture, onboarding

Recommended workflow:
- Create a branch per story
- Add unit and e2e tests for new features
- Open PR, CI will run tests and lint

If you want these files tailored to your stack (React/Node, Angular/Java, .NET), tell me the stack and I’ll create them.