# HW #3 Proxies, Queues, Cache Fluency.

Understanding the basic building blocks that form complex infrastructure is an important precedent to being able to construct and deploy it.

### 100% Branch and Statement Coverage

In our [redis workshop](https://github.com/CSC-DevOps/Queues), we worked with server-side web technologies combined with redis to demonstrate concepts related to caches and queues.

Your assignment is 


##### Option 1:

Build a simple three tier web application (front-end/service/storage) with the following additional considerations:

* Introduce a cache mechanism for read requests from storage.
* Introduce a queue mechanism for servicing a batch write requests to storage.
* Have more than one service instance.
* Introduce a proxy mechanism for directing requests to multiple service instances.

##### Evaluation

- Demonstrate: Simple three tier web app: 50%
- Demonstrate caching: 75%
- Demonstrate queue: 85%
- Demonstrate more than one service instance running: 90%
- Demonstrate proxy: 95%

**--OR--**

#### Option 2   

Complete the workshop assignment with the following additional considerations:

* Run an additional instance of the service layer (main.js) on a different port (e.g., 3001).
* Create a proxy that will uniformly deliver requests to localhost/ to localhost:3000, localhost:3001, etc.  It is suggested you use redis to look up which host to resolve to.

##### Evaluation

- Complete set/get 50%
- Complete recent 75%
- Complete upload/meow 85%
- Additional service instance running: 90%
- Demonstrate proxy: 100%

### Submission

Create a github repository (on github proper or NCSU), with a basic report in the README.md file and your code in your repository.

Please email your TA with the link to your repository in order to submit.

The assignment is due Tuesday, March 24th at midnight.

