# Serverless Go 

## Who am I? Why am I doing this? 
I am a developer who mostly uses Node. Recently, I have been learning Go. I've Struggled to find good learning resources which demo how to write and unit test serverless apps written in Go.

So, I'm sharing what I've found to help other developers learning Go. 

## What will be covered?

This will cover how to:

- setup a Go project with AWS SAM
- write code testable, including: 
    - unit tests, mocking the SDK calls through dependency injection
    - integration tests
    - contract testing

The project will start off with a straight forward synchronous REST API written with Api Gateway, Lambda and DynamoDB. The plan is to then further develop this app to authenticate user requests and refactor the app to use a more event-driven architecture - possibly following the CQRS and Event Sourcing Design Patterns.

But for now, it'll be a straight forward, fully tested CRUD app written in GO, deployed with AWS SAM.

### Links

- [Go With Tests](https://quii.gitbook.io/learn-go-with-tests)
- [Go and AWS - Code and Deploy a Serverless API, freeCodeCamp](https://www.youtube.com/watch?v=zHcef4eHOc8&t=808s)

## Testing with Dependency Injection

Dependency Injection is a programming technique where could is decoupled so that code receives its dependents (other objects or functions that it requires to run), as opposed to creating them internally. 

There's three types:

- Constructor Injection
- Setter Injection (also known as Property Injection)
- Method Injection

Having a google, Method injection seems to be the prefered way to injected dependencies. This will be the way we'll do things.

### Links

- [Dependency Injection, The Best Pattern - CodeAesthetic ](https://www.youtube.com/watch?v=J1f5b4vcxCQ)



