# HW #1 - Provisioning Servers

Automatically provisioning a computational resource will be one of the most important skills for you to master in your career.  You have gained experience using [digitalocean](https://developers.digitalocean.com/v2/) to automatically create virtual images on a cloud platform and perform simple tasks with the droplets. As part of any risk management strategy, it is also important to be able to have access to a variety of platforms to avoid vender lock-in and systematic failures.

In this homework assignment, you will complete the following tasks:

* Be able to automatically provision using a code api from **two cloud providers**. Logically, you should complete the provision workshop, to have digitalocean count as one. Choose one additional cloud provider below.

* The provisioning code needs to be able to perform the following:
  - create a new VM, with a registered ssh key. *This will allow you ssh directly into your account without being emailed a temporary root password.*
  - print out the ip address of the new server.

* You are free to choose which technology/framework you like for your implementation. You might consider something like the [node aws-sdk package](https://www.npmjs.com/package/aws-sdk), or [boto for Python](https://aws.amazon.com/sdk-for-python/).

* Use proper and source control and configuration management practices e.g., using package managers and their associated files (package.json/requirements.txt) to declare software dependencies. Remember, someone else should be able to run your code.

* Depending on your cloud provider, there may be some manual one-time configuration you need to perform, such as setting up security groups, firewall rules, etc. For this assignment, this can be manually configured.

## Cloud Providers

See the github education pack for many free promotions: https://education.github.com/pack

### DigitalOcean

DigitalOcean is one of the cheapest and simpliest cloud providers available. If using digitalocean, you must be able to obtain your [own api key](https://www.digitalocean.com/docs/api/create-personal-access-token/) after creating an account.

To create and register a ssh key, you can first create your ssh key locally, then [add your public key to DO](https://www.digitalocean.com/docs/droplets/how-to/add-ssh-keys/).

In your createDroplet code, you will need to change the `"ssh_keys":null,` entry to add the id associated with your ssh key.

You can retrieve the associated id using the api:

```bash
curl -X GET -H 'Content-Type: application/json' -H "Authorization: Bearer $DOTOKEN" "https://api.digitalocean.com/v2/account/keys"
```

Finally, you can change the code to use the id: `"ssh_keys":[12345...],`.


### Amazon Web Services (AWS)

AWS is a rich computation platform for supporting many services. 

AWS provides a [free tier plan](http://aws.amazon.com/free/), for 12 months, which is appropriate for learning the platform.

### Azure

You can use obtain a free student account through dreamspark for azure.

### Google Cloud Platform
Google has its own set of cloud solutions on its platform. It offers a [free tier](https://cloud.google.com/free/) and (as of January 2019) 300$ free credit on signup. Documentation for Compute Engine can be found [here](https://cloud.google.com/compute/docs/).


### Scaleway
Scaleway is a European based cloud provider with very afforadable small servers, perfect for a project like this or hosting a small website. While there is no free tier or trial, the cheapest server comes in at €0.004/hr. Check out their website [here](https://www.scaleway.com/) and their API documentation [here](https://developer.scaleway.com).

### VCL

You can connect to VCL over XML-RPC:
https://arjie.com/2014/04/10/using-the-vcl-xml-rpc-interface-with-python/

### OpenStack

Is a platform that attempts to provide a open source implementation of cloud components and infrastructure, which has various venders that implement the standard. See here: https://www.openstack.org/marketplace/public-clouds/

### Other platforms

In general, for this assignment, we will not be using Platform as a Service providers such as Heroku. If you identify another platform you'd like to try, bring it to the attention of the professor first.

## Screencast

In your screencast, demonstrate running your code that provisions the two servers across the different platforms, including the cloud provider interface before and after running the code. Demonstrate being able to ssh into your box with your registered ssh key.

## Submission

Please [submit your repo here](https://docs.google.com/forms/d/e/1FAIpQLScg8aTK_GBSlwGEjAarQXFi037M77KJ9cJj9IfiOWWOn27WiQ/viewform?usp=sf_link).

In your repository, have your code, link to a screencast.

The assignment is due Friday, Jan 25th before midnight.

## Evaluation

You will receive a **ZERO** if a security token is found to be checked into your repository.

- 50%: Code for provisioning from two platforms.
- 25%: Quality of source repository, configuration management practices.
- 25%: Screencast and following instructions.
