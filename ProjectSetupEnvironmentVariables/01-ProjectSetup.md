# Project Setup

## TLDR

Really quick summary of how I'd setup a Go AWS Project. 

## Project Structure

Most of the ideas outlined below have been taken and adapted from [Leonard Q Marcq](https://leonardqmarcq.com/posts/go-project-structure-for-api-gateway-lambda-with-aws-sam)'s idea of a Modular Monolith. Each Microservice has it's own Go Module which could contain lambda functions, databases, queues... They are self contained modules which contain everything they might need to operate correctly rather than having each lambda being in it's go module.

```bash
.
├── Makefile
├── README.md
├── cmd
│   └── lambdas
│       ├── create_todo
│       │   ├── create_todo.go
│       │   └── create_todo_test.go # Integration Tests
│       └── ...
├── internal
│   ├── databases
│   │   ├── dynamo.go
│   │   └── dynamo_test.go # Unit Tests
│   ├── structs
│   │   └── todo.go
│   └── utils
│       ├── lambda
│       │   ├── response.go
│       │   ├── response_test.go # Unit Tests
│       │   ├── error.go
│       │   └── error_test.go # Unit Tests
│       └── utils
│          ├── response.go
│          └── response.go
├── go.mod
├── go.sum
└── template.yaml 
```

### cmd

Following [Golang Project Standards](https://github.com/golang-standards/project-layout/tree/master/internal), CMD is for main applications for this project.

For now this will contain the handlers for our Lambda functions. If we were to add containers, this will be where they'd go.

#### Tests

Tests inside cmd will all be integration tests. They'll be invoking lambdas and/or making HTTP requests to check everything is working as expected.

### Internal

Again, following [Golang Project Standards](https://github.com/golang-standards/project-layout/tree/master/internal), Internal is for private application and library code. To maintain sanity, the tests will cover the green cases and any 4XX responses.

#### Databases

Code which handles all the interactions with Databases. Initially this will have a dynamodb container but if we were to add RDS, we'd add that here too.

### Structs

Home for all the structs and types. Gives them an easy to find place to live.

### Utils

Functions which can be shared accross many functions. Response.go will have the

### Tests

All of the tests inside /internal will be the unit tests. No calls to AWS or other services will be made. Everything will be mocked through dependency injection or other means. Compared to the integration tests, these will be more thorough. 

