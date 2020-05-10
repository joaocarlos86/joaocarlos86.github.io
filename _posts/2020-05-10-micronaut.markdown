---
layout: post
title:  "Micronaut - the basics"
date:   2020-05-10 14:32:44 +0100
categories: microservice micronaut
---

## What is Micronaut?

"A modern, JVM-based, full-stack framework for building modular, easily testable microservice and serverless applications."

That's the Micronaut definition according to [Official Micronaut Website](https://micronaut.io), but what that means (exactly)?

My definition of Micronaut is a reactive and non-blocking, lightweight and polyglot framework used to build microservices.

# Why reactive and non-blocking?

Micronaut supports any framework that implements Reactive Streams (such as [RxJava](https://github.com/ReactiveX/RxJava) and [Reactor](https://projectreactor.io))

# Why lightweight?

Reflection-based IoC frameworks load and cache reflection data for every single field, method, and constructor in your code. Micronaut features a Dependency Injection and Aspect-Oriented Programming runtime that uses no reflection.

# Why polyglot?

Java, Groovy or Kotlin.

# Inversion of Control

For me, this is one of the biggest advantages of Micronaut. I make an extensive use of the Spring framework, it's easy, fast, reliable, has a large community and it's very active, but Spring isn't perfect, depending of the use case some of the disadvantages might make of Spring a non optimal choice. 

One of the pain points of Spring is that it relies exclusively on runtime reflection and proxies to implement dependency injection. Micronaut, on the other hand, focus on compile time data.

Injecting dependencies at runtime means that, no early verification will be made in order to ensure that all depencies are effectively available. To create an instance of a class with dependencies, the framework needs to identify the ideal candidate and then use reflection to instantiate that class. A natural consequence is if the class being instantiated has more dependencies, those dependencies needs to be created (if not yet) using reflection. If any of the dependencies can't be created or if there's multiple candidates, the application will fail.

Injecting dependencies at compile-time allows the compiler to verify that every component in the application has access to all dependencies it will need. The fact that the compiler is eagerly verifying the dependencies reduces the amount of time needed to create instances of the dependencies and, generally, reduces the usage of reflection. This also reduces the amount of tests that needs to be written.

## Use cases

Micronaut has a very extensive range of use case, the two most important for me are

# Microservices

When I wanted to write microservices in Java, I would use Spring Boot with no hesitation, but the truth is you can't really create microservices with Spring, they just aren't micro, the total of dependencies, and the ways of working of the framework are prohibitives. The Micronaut underlying mechanisms (such as the reactive and non-blocking IO and the compile time IC) make of it a good choice if you want something fast that consumes a small amount of resources if compared with the concurrency.

# GraalVM - [docs](https://docs.micronaut.io/latest/guide/index.html#graal)

[GraalVM](https://www.graalvm.org/) is a new universal virtual machine from Oracle that supports a polyglot runtime environment and the ability to compile Java applications down to native machine code.

# Serverless functions

Micronaut is lightweight, and it's low overhead compile-time DI and AOP makes this framework a good choice if you need to write funcions for serverless environemnts.