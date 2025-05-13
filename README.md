# MCP Task Manager Server

A simple task management server built using the Model Context Protocol (MCP). This server allows you to create, list, and complete tasks through MCP tools and HTTP API endpoints.

## Features

- Create tasks with title and description
- List all tasks
- Mark tasks as completed
- In-memory storage (tasks are lost when the server restarts)
- HTTP API for integration with web applications
- MCP compatibility for AI assistants

## Installation

```bash
# Install dependencies
npm install
```

## Building and Running

```bash
# Build the TypeScript code
npm run build

# Run the MCP server (stdio mode for AI assistants)
npm start

# Run the HTTP server (for web applications)
npm run http
```

## HTTP API Endpoints

### Create a Task

```
POST /api/tasks
```

Request body:
```json
{
  "title": "Task title",
  "description": "Task description"
}
```

### List All Tasks

```
GET /api/tasks?status=[all|pending|completed]
```

### List Pending Tasks

```
GET /api/tasks/pending
```

### Complete a Task

```
PATCH /api/tasks/:id/complete
```

### Execute MCP Tool Directly

```
POST /api/mcp/execute
```

Request body:
```json
{
  "tool": "tool-name",
  "params": {
    "param1": "value1",
    "param2": "value2"
  }
}
```

## Available Tools

### 1. create-task

Creates a new task with a title and description.

Parameters:
- `title`: String (required) - The title of the task
- `description`: String (required) - The description of the task

### 2. list-tasks

Lists all tasks currently stored in memory.

Parameters: None

### 3. complete-task

Marks a specific task as completed.

Parameters:
- `id`: String (required) - The ID of the task to mark as completed

## Connecting to the Server

### MCP Mode

The MCP server runs on stdio, making it compatible with MCP clients like Claude for Desktop.

### HTTP Mode

The HTTP server runs on port 3000 by default. You can access it at `http://localhost:3000`.

You can customize the port by setting the `PORT` environment variable:  

```bash
PORT=8080 npm run http
```

## Example Usage

1. Start the server: `npm start`
2. Connect to the server using an MCP client
3. Use the tools to manage your tasks:
   - Create a task: `create-task` with title and description
   - List all tasks: `list-tasks`
   - Complete a task: `complete-task` with the task ID
# mcp-server-example
