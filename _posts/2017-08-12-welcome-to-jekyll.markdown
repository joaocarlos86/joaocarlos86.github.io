---
layout: post
title:  "Polyglot persistence"
date:   2017-08-12 19:44:44 -0300
categories: persistence databases
---

What is the best kind of database available? It's MongoDB with the schemaless and high flexibility? It's a relational database with his keys, integrity and many years of evolution? Well it can be a Redis and the speed of a key-value storage! I can spend days talking about the databases available, but we will never find the best one.

But, what if I told you that we dont need to use only one database? We can use as much as we need! If you want to use a cache in your application, use a key-value database! Need to develop a fucntion where the data model is constantly changing? Use a schemaless database (like MongoDB or CouchDB)! You need to save series of data (IoT sensor data over the time)? Why not to use a database like Cassandra?

It's a crime to use a single one database to solve all the problems, different kinds of problems need diferents aproachs.

Maybe I talk about those databases in next posts.
