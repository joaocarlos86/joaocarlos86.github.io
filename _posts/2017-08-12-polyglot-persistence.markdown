---
layout: post
title:  "Polyglot persistence"
date:   2017-08-12 19:44:44 -0300
categories: persistence databases
---

What is the best kind of database available? It's MongoDB with the schemaless and high flexibility? It's a relational database with his keys, integrity and many years of evolution? Well it can be a Redis and the speed of a key-value storage! I can spend days talking about the databases available, but we will never find the best one.

But, what if I told you that we dont need to use only one database? We can use as much as we need! If you want to use a cache in your application, use a key-value database! Need to develop a fucntion where the data model is constantly changing? Use a schemaless database (like MongoDB or CouchDB)! You need to save series of data (IoT sensor data over the time)? Why not to use a database like Cassandra?

It's a crime to use a single one database to solve all the problems, different kinds of problems need diferents aproachs.
Martin Folwer has [written about it years ago](https://martinfowler.com/bliki/PolyglotPersistence.html) but in many companies, when I talk about polyglot persistence they seems to now know it or refuse to use because it is "more complex".

If you want to know more about polyglot persistecy I recomend a nice, short but amazing book: ["NoSQL Distilled: A Brief Guide to the Emerging World of Polyglot Persistence"](https://www.amazon.com/NoSQL-Distilled-Emerging-Polyglot-Persistence/dp/0321826620/ref=sr_1_1?ie=UTF8&qid=1502581056&sr=8-1&keywords=nosql).

So, what do you think about to use multiples databases systems in your application? 
