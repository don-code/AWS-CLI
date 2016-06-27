# AWS-CLI via Okta


We have built a simple Java application that generates temporary AWS credentials using AWS STS Assume roles, this enables AWS customers to seamlessly gain access to AWS resources using Okta to as a Single-Sign-On source.

###Setup###

Use ```git clone https://github.com/nshobayo/AWS-CLI.git``` to clone the repository locally

###Configuring the application###
  It is essential that ```oktaAWSCLI.config``` be in the same directory as the ```OktaAWSCLI-VERSION-jar-with-dependencies.jar``` file. The oktaAWSCLi config file holds information specific to each org and needs to be configured on an org to org basis. 

  Your Okta Org and AWS application url need to be added to your configuration file.
  - ```OKTA_ORG``` which is the url of your Okta org.
  - ```OKTA_AWS_APP_URL``` is the url link of your Okta AWS application url
  - **Obtaining an AWS app url**
    - Navigate to the ```Admin Dashboard``` of you Okta org 
    - Select the ```Application``` tab and click you AWS Application 
    - Under the ```General``` menu, scroll down to find the ```App Imbed Link``` section 
    - Your link is located under ```Embed Link``` 
  - Replace the example values in ```oktaAWSCLI.config``` with your values

###Running the application###
  - To run the application use the following command while in the directory containing the ```.jar``` and `.config` file

  ```java -jar OktaAWSCLI-VERSION-jar-with-dependencies.jar```

  - To specify proxy settings, you can pass in using system properties, which may be set through -D command line option.

  ```java -Dhttp.proxyHost=proxy.com -Dhttp.proxyPort=80 -Dhttp.proxyUser=username -Dhttp.proxyPassword=password -jar OktaAWSCLI-VERSION-jar-with-dependencies.jar```

###Compiling the application###
This project builds using Maven. To build a new JAR, run the following:

```
mvn clean package
```
