# Create Customer Interaction

These file will provide you instructions on how to reuse existing code for create customer interaction in seibel.


## Getting Started

These instructions will get you a copy of the project up and running on your local machine for development and testing purposes. See deployment for notes on how to deploy the project on a live system.  


### Prerequisites

Python
Code editor (i.e vscode etc)

### Installing

Clone repository on your local  

Create Virtual Environment , name "venv"  

pip install -r requirements.txt  

 
### EP for Rest Call:
#local host :http://localhost:8001/createinteraction/api/v1/createci  

#Dev :http://cadlaut01/createinteraction/api/v1/createci  

#Prod :http://caplaut01/createinteraction/api/v1/createci  


#Input Parameters : 

{
        "transactionId": "%s",(transaction id from your code)
        "contextentity":"Account",
        "customernumber": "%s",(Customer number on which CI needs to be created)
        "accountnumber": "%s",(Account number on which CI needs to be created)
        "description":"Customer Opted out from Bill Reminder (updated by Optie bot)",(Change this according to your requirement)
        "contactmedium":"Notification - SMS",(Change this according to your requirement)
        "citype":"Billing",(Change this according to your requirement)
        "cisubtype":"Billing",(Change this according to your requirement)
        "ciordernumber":"",
        "ciservicename":"DeliveryMode",
        "ciserviceoptionvalue":"Asynchronous"
        }

Example data set:

data = '''{
        "transactionId": "%s",
        "contextentity":"Account",
        "customernumber": "%s",
        "accountnumber": "%s",
        "description":"Customer Opted out from Bill Reminder (updated by Optie bot)",
        "contactmedium":"Notification - SMS",
        "citype":"Billing",
        "cisubtype":"Billing",
        "ciordernumber":"",
        "ciservicename":"DeliveryMode",
        "ciserviceoptionvalue":"Asynchronous"
        }'''%(transactionID,customernumber,accountnumber)
        #print (data)
        url = restcreateinteractionConfig['getAPI']
        headers = {
                'content-type': "application/json",
                'cache-control': "no-cache",
                'charset': "utf-8"
                    }             
        
        response = requests.post(url, headers=headers, allow_redirects=False, verify=False, data=data, proxies=proxy)

#Output Parameters : 

Success Response:
{"success":"Y","reason":"submitted successfully"}

Failure Response:

{"success":"N","reason":"Create interaction failed with {}".format(response.status_code)}  




## Deployment

The code is located on Docker production env (caplaut01), location :

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



## Contributing



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




