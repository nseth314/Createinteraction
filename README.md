# Create Customer Interaction

These file will provide you instructions on how to reuse existing code for create customer interaction in seibel.


## Getting Started

These instructions will get you a copy of the project up and running on your local machine for development and testing purposes. See deployment for notes on how to deploy the project on a live system.

### Prerequisites

What things you need to install the software and how to install them

```
Give examples
```

### Installing

A step by step series of examples that tell you how to get a development env running

Say what the step will be

```
Give the example
```

And repeat

```
until finished
```

End with an example of getting some data out of the system or using it for a little demo

## Running the tests

Explain how to run the automated tests for this system

### Break down into end to end tests

Explain what these tests test and why

```
Give an example
```

### EP for Rest Call:

http://caplaut01/createinteraction/api/v1/createci

Input Parameters : Account number and Customer number
Output: Success or failure message

## Deployment

The code is located on Docker production (caplaut01), location :

Image name:
File path:


Please follow following commands if you wish to make any changes :

Build : docker build -t customerinteraction .
Deploy Image:docker run -it --restart=unless-stopped --name=customerinteraction -v /appl/automation/customerinteraction/app:/app customerinteraction
[automation@cadlaut01 ~]$ docker ps -a|grep customerinteraction
165e39812197        customerinteraction                      "/entrypoint.sh /s..."   2 days ago          Up 35 hours                 80/tcp, 443/tcp, 5000/tcp                                                customerinteraction

Connect to Container:

docker  exec -it 165e39812197 bash
root@165e39812197:/app# 

Also, update customerinteraction conf entry in nginx conf file.



## Built With

* [Dropwizard](http://www.dropwizard.io/1.0.2/docs/) - The web framework used
* [Maven](https://maven.apache.org/) - Dependency Management
* [ROME](https://rometools.github.io/rome/) - Used to generate RSS Feeds

## Contributing

Please read [CONTRIBUTING.md](https://gist.github.com/PurpleBooth/b24679402957c63ec426) for details on our code of conduct, and the process for submitting pull requests to us.

## Versioning

Version:1

## Authors

**Rajesh Babu** - *Initial work* - Soap call and Template for create customer interaction
**Naresh Seth** - *Dockerization* - Move to docker dev to make code reusable
**Naresh Seth** - *Testing* - Testing code fuctionalitity with Rest calls
**Naresh Seth** - *Productionization* - Made code available for anyone in organisation
**Pareen Kunia** - *Reviewer* - Reviewed code and guided throughout the project


## License

NA

## Acknowledgments

* Pawan Kumar - Helped in containerization of code




