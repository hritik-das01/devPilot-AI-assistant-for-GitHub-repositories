# devPilot

An AI assistant for exploring GitHub repositories. devPilot indexes a repository’s source code so you can ask questions about it and get streamed answers with links to relevant files.

## Features

- Sign in with GitHub and view your repositories.
- Index repository code for search.
- Ask questions about an indexed repository in a chat.
- Get AI-generated answers with citations linking to source files.
- View indexing progress and previous chat sessions.

## How it works

1. Sign in with GitHub and select a repository.
2. devPilot retrieves eligible code files and splits them into smaller chunks.
3. The chunks are stored as vector embeddings in PostgreSQL with pgvector.
4. When you ask a question, devPilot searches for relevant code and sends that context to the AI model.
5. The answer streams to the chat, with citations to the relevant files.

## Tech stack

**Frontend:** Next.js, React, TypeScript  
**Backend:** Java 21, Spring Boot, Spring AI  
**Database and vector search:** PostgreSQL, pgvector  
**Integrations:** GitHub OAuth and API, OpenAI

## Project structure

```text
devPilot/
├── backend/              # Spring Boot API
├── client/               # Next.js web app
├── docker/
│   └── postgres/         # PostgreSQL initialization
└── docker-compose.yml    # pgvector database service

Prerequisites
- Java 21
- Node.js and npm
- Docker Desktop or Docker Engine
- GitHub OAuth app credentials
- OpenAI API key
