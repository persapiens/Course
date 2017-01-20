# HW #1 - A Provisioning Servers

Automatically provisioning a computational resource will be one of the most important skills for you to master in your career.  You have gained experience using [digitalocean](https://developers.digitalocean.com/v2/) to automatically create virtual images on a hosted server. As part of any risk management strategy, it is also important to be able to have access to a variety of platforms to avoid vender lock-in and systematic failures.

In this homework assignment, you will complete the following tasks:

* Be able to automatically provision using a code api from **2 service providers**. Have the code request a new VM and then save or print out the ip address of the new server.
* Use configuration management to be able to build your repo, e.g., use package managers such as npm, maven, etc. to declare and manage your software dependencies.
* Answer conceptual questions.
 
## Service Providers

See the github education pack for many free promotions: https://education.github.com/pack

### DigitialOcean

DigitialOcean is one of the cheapest and lowest image providers.
If using digitalocean, I will keep the api key open for testing, but by submission, you must be able to obtain your own api key.

To get your ssh key, you can upload under security and then get the id this way:

```bash
curl -X GET -H 'Content-Type: application/json' -H 'Authorization: Bearer $TOKEN' "https://api.digitalocean.com/v2/account/keys"
```

### Amazon Web Services (AWS)

AWS is a rich computation platform for supporting many services. The goal of your homework assignment is to create  account with AWS, learn how to use its API, and perform a simple task with the service.

AWS provides a [free tier plan](http://aws.amazon.com/free/), for 12 months, which is appropriate for learning the platform.

### Azure

You can use obtain a free student account through dreamspark for azure.

### VCL

You can connect to VCL over XML-RPC:
https://arjie.com/2014/04/10/using-the-vcl-xml-rpc-interface-with-python/

### OpenStack

Is a platform that attempts to provide a open source implementation of cloud components and infrastructure, which has various venders that implement the standard. See here: https://www.openstack.org/marketplace/public-clouds/

### Other platforms

In general, for this assignment, we will not be using Platform as a Service providers such as heroku. If you identify another platform you'd like to try, bring it to the attention of the professor first.

## Concepts

Answer in your own words the following questions:

1. Define idempotency. Give two examples of an idempotent operation and non-idempotent operation.
2. Describe several issues related to management of your inventory.
3. Describe two configuration models. What are disadvantages and advantages of each model?
4. What are some of the consquences of not having proper configuration management?

## Submission

Please [submit your repo here](https://docs.google.com/a/ncsu.edu/forms/d/e/1FAIpQLSePzXXObpSBIF0L_3fId9lFoZaqffbHCPTUlhrSgFe0EuNksQ/viewform).

In your repository, have your code, link to a screencast.

The assignment is due Thursday, January 26th at midnight.

## Evaluation

You will receive a ZERO if a security token is found to be checked into your repository.

- 40% Code for provisioning from two platforms.
- 20% Configuration management of repo.
- 20% Concepts
- 20% Screencast and following instructions.

