# MCP Task Manager Server

A simple task management server built using the Model Context Protocol (MCP). This server allows you to create, list, and complete tasks through MCP tools.

## Features

- Create tasks with title and description
- List all tasks
- Mark tasks as completed
- In-memory storage (tasks are lost when the server restarts)

## Installation

```bash
# Install dependencies
npm install
```

## Building and Running

```bash
# Build the TypeScript code
npm run build

# Run the server
npm start
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

This MCP server runs on stdio, making it compatible with MCP clients like Claude for Desktop.

## Example Usage

1. Start the server: `npm start`
2. Connect to the server using an MCP client
3. Use the tools to manage your tasks:
   - Create a task: `create-task` with title and description
   - List all tasks: `list-tasks`
   - Complete a task: `complete-task` with the task ID
# mcp-server-example
