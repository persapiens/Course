# HW #3 Proxies, Queues, Cache Fluency.

Understanding the basic building blocks that form complex infrastructure is an important precedent to being able to construct and deploy it.

### Building Infrastructure

In our [redis workshop](https://github.com/CSC-DevOps/Queues), we worked with server-side web technologies combined with redis to demonstrate concepts related to caches and queues.

Your assignment is to complete the workshop assignment with the following additional considerations:

* Implement a new command `spawn`, which will create a new app server running on another port. Correspondingly, implement a new command `destroy`, which will destroy a random server. Available servers should be stored in redis can be seen by `listservers` command. Destroying all servers is undefined behavior.
* Create a proxy that will uniformly deliver requests to available servers. E.g., if a visit happens to `/` then toggle between `localhost:3000`, `localhost:3001`, etc.  Use redis to look up which server to resolve to.

##### Evaluation

- Complete set/get 50%
- Complete recent 60%
- Complete upload/meow 70%
- Complete spawn/destory/listservers: 90%
- Demonstrate proxy: 100%

### Submission

[Submit link](https://goo.gl/forms/3hsFEb0WC5DrbKlj2) to your repository, including your code, README, and screencast.

The assignment is due Thursday, November 3rd at midnight.
