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

In general, for this assignment, we will not be using Platform as a Service providers such as Heroku. If you identify another platform you'd like to try, bring it to the attention of the professor first as a pull request to this assignment.