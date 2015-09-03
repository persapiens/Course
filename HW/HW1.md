# HW #1 Provisioning and Configuring Servers

Automatically provisioning a computational resource will be one of the most important skills for you to master in your career.  You have gained experience using [digitalocean](https://developers.digitalocean.com/v2/) to automatically create virtual images on a hosted server.

As part of any risk management strategy, it is also important to be able to have access to a variety of platforms to avoid vender lock-in and systematic failures.

Finally, you need the ability to be able to configure systems so they can suitably host components of your deployment pipeline and production environments.

In this homework assignment, you will complete the following tasks:

* Be able to automatically provision, from **2 service providers**. If using digitalocean, I will keep the api key open for testing, but by submission, you must be able to obtain your own api key.
* Be able to automatically create an inventory file (consumable by ansible) that describes the allocated servers.
* Write an ansible playbook that will deploy a simple nginx webserver.
* Use configuration management to be able to build your repo, e.g., package managers such as npm, maven, etc.
 
## Service Providers

### DigitialOcean

You should be able to get free credits using the following code: `DROPLET10`.

### Amazon Web Services (AWS)

AWS is a rich computation platform for supporting many services. The goal of your homework assignment is to create  account with AWS, learn how to use its API, and perform a simple task with the service.

AWS provides a [free tier plan](http://aws.amazon.com/free/), for 12 months, which is appropriate for learning the platform.

After creating an account, please read [this guide](https://d36cz9buwru1tt.cloudfront.net/AWS_Overview.pdf), in order to get an overview of the platform provided.  After reading this document (or others that you find), prepare a simple paragraph describing a service that you learned about. Next, please review the different ways of interfacing with the [AWS API](http://docs.aws.amazon.com/AWSEC2/latest/APIReference/making-api-requests.html).  It is possible to use simple http requests, or you can also use language binding for the API (e.g. Java, .NET, ruby, javascript, etc.).

### Azure

You can use obtain a free student account through dreamspark for azure.

### Other platforms

In general, for this assignment, we will not be using Platform as a Service providers such as heroku. Later in the semester, you make use of these services.
If you identify another platform you'd like to try, bring it to the attention of the professor first.

## Submission

Please [submit your repo here](https://docs.google.com/a/ncsu.edu/forms/d/1jz9p1xAKg0-yuHhqQF0hUEhhFqy_2F3jju-mKvTszsk/viewform?usp=send_form).

In your repository, have your code, playbook, and link to a screen.

Record a screencast of the entire process, from provisioning servers, creating inventory, running ansible, to finally seeing webserver in browser.

The assignment is due Wednesday, Sept 16th at midnight.

## Evaluation

- 40% Code for provisioning from two platforms.
- 20% Automatically generating inventory file from code.
- 20% Ansible Playbook.
- 10% Configuration management of repo.
- 10% Screencast and following instructions.
