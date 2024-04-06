# Project Setup, Environment Variables, CRUD with DynamoDB

## TLDR

## Setup

Test

## AWS SAM

## Architecture Overview

### Services Used

### Architecture 

## Project Structure



```bash
.
├── Makefile
├── README.md
├── cmd
│   └── handlers
│       ├── create_todo
│       │   ├── create_todo.go
│       │   ├── create_todo_helper.go
│       │   └── create_todo_helper_test.go
│       ├── get_todo
│       │   ├── get_todo.go
│       │   ├── get_todo_helper.go
│       │   └── get_todo_helper_test.go
│       ├── update_todo
│       │   ├── update_todo.go
│       │   ├── update_todo_helper.go
│       │   └── update_todo_helper_test.go
│       ├── delete_todo
│       │   ├── delete_todo.go
│       │   ├── delete_todo_helper.go
│       │   └── delete_todo_helper_test.go
│       └── get_all_todos
│           ├── get_all_todos.go
│           ├── get_all_todos_helper.go
│           └── geT_all_todos_helper_test.go
├── internal
│   ├── database
│   │   └── dynamo_client.go
│   ├── services
│   │   ├── user_service.go
│   │   └── store
│   │       ├── user.go
│   │       └── store.go
│   └── transport
│       └── lambda
│           ├── response.go
│           └── error.go
├── go.mod
├── go.sum
└── template.yaml
```

## Handlers

##