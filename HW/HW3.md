# HW #3 Proxies, Queues, Cache Fluency.

Understanding the basic building blocks that form complex infrastructure is an important precedent to being able to construct and deploy it.

### Building Infrastructure

In our [redis workshop](https://github.com/CSC-DevOps/Queues), we worked with server-side web technologies combined with redis to demonstrate concepts related to caches and queues.

Your assignment is to complete the workshop assignment with the following additional considerations:

* Implement a new command `spawn`, which will create a new app server running on another port. Correspondingly, implement a new command `destroy`, which will destroy a random server. Available servers should be stored in redis, which can be seen by `listservers` command. Destroying all servers is undefined behavior.
* Create a proxy that will uniformly deliver requests to available servers. E.g., if a visit happens to `/` then toggle between `localhost:3000`, `localhost:3001`, etc.  Use redis to look up which server to resolve to.

### Conceptual Questions

1. Describe some benefits and issues related to using Feature Flags.
2. What are some reasons for keeping servers in seperate availability zones?
3. Describe the Circuit Breaker pattern and its relation to operation toggles.
4. What are some ways you can help speed up an application that has
   - a) traffic that peaks on Monday evenings
   - b) real time and concurrent connections with peers
   - c) heavy upload traffic

##### Evaluation

- Complete set/get 30%
- Complete recent 40%
- Complete upload/meow 50%
- Complete spawn/destory/listservers: 60%
- Demonstrate proxy: 80%
- Complete conceptual questions 100%

### Submission

[Submit link](https://docs.google.com/a/ncsu.edu/forms/d/e/1FAIpQLSfDVxEvErclx8MT_vrJdIMOdKtnbwf-tGZU0oOdJyfkFrKHJQ/viewform?usp=sf_link) to your repository, including your code, README, and screencast.

The assignment is due Wednesday, April 5th at midnight.
