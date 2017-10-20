# HW #3 Proxies, Queues, Cache Fluency.

Understanding the basic building blocks that form complex infrastructure is an important precedent to being able to construct and deploy it.

### Building Infrastructure

In our [redis workshop](https://github.com/CSC-DevOps/Queues), we worked with server-side web technologies combined with redis to demonstrate concepts related to caches and queues.

Your assignment is to complete the workshop assignment with the following additional considerations:

* Implement a new route `catfact/:num` which will retrieve the nth cat fact from the catfacts.txt. Use the provided `get_line` function.
* Modify the catfact route to create a key, e.g., `catfact:13`, whenever a catfact is retrieved. Have the catfact key expire in 10 seconds. Next, retrieve the key from redis if it is available, otherwise, retrieve it from disk. Finally, in addition to returning the catfact, also return the time in ms to retrieve the key.
* Implement a new route, "toggleCacheFeature", which will turn on and off the catfact caching feature.

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
- Complete catfact route and caching: 60%
- Demonstrate toggleCacheFeature: 80%
- Complete conceptual questions 100%

### Submission

[Submit link](https://docs.google.com/forms/d/e/1FAIpQLSchUA_qNl7t7VlWlwIdKJMXvNfFA63UZipVqs_SGWo4_SWoWA/viewform?usp=sf_link) to your repository, including your code, README, and screencast.

The assignment is due Monday, Oct 29th at midnight.
