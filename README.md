# Spring Boot Thymeleaf Demo Application - Cloud

<img src="https://user-images.githubusercontent.com/30971809/34328614-dc67a4c0-e8e3-11e7-9492-273ae1892526.jpg"></img>

Please ensure you have the following development tools.

    JDK 1.7 or later
    Maven 3 or later
    spring-boot 1.3.5.RELEASE

Run

    mvn spring-boot:run

    http://localhost:8080

## How to deploy the spring boot demo application in cloud environment ?

## Step 1 : Install cloud foundry client tool 

Please refer https://docs.cloudfoundry.org/cf-cli/install-go-cli.html for installing cli tool.
```
cf version
cf version 6.26.0+9c9a261fd.2017-04-06
```
## Step 2 : Login to cloud foundry -> cf login -a api.run.pivotal.io
```
spring-boot-application-in-cloud > cf login -a api.run.pivotal.io

API endpoint: api.run.pivotal.io

Email> emailaddress@domain.com

Password>
Authenticating...
OK

Targeted org <yourorganization>

Targeted space development

API endpoint:   https://api.run.pivotal.io (API version: 2.101.0)
User:           emailaddress@domain.com
Org:            <yourorganization>
Space:          development
```
## Step 3 : cd to spring application working directory  [Note : where the manifest.yml resides]
```
spring-boot-application-in-cloud > ls
README.md
manifest.yml
src
SpringBoot-Thymeleaf-Example.iml
pom.xml
target
```
## Step 4 : cf push
```
spring-boot-application-in-cloud > cf push
Using manifest file /Users/user/workspace/createvalue/spring-boot-application-in-cloud/manifest.yml

Updating app spring-boot-demo-app-cloud in org <yourorganization> / space development as emailaddress@domain.com..
OK

Using route spring-boot-demo-app-cloud.cfapps.io
Uploading spring-boot-demo-app-cloud...
Uploading app files from: /var/folders/_z/jzxb5_m17wj8ygf92z9vvv4h0000gn/T/unzipped-app713090882
Uploading 347.6K, 94 files
Done uploading
OK

Stopping app spring-boot-demo-app-cloud in org <yourorganization>  / space development as emailaddress@domain.com...
OK

Starting app spring-boot-demo-app-cloud in org <yourorganization>  / space development as emailaddress@domain.com...
Downloading binary_buildpack...
Downloading php_buildpack...
Downloading go_buildpack...
..

0 of 1 instances running, 1 starting
1 of 1 instances running

state     since                    cpu      memory         disk           details
#0   running   2017-12-24 06:44:35 PM   162.0%   319.1M of 1G   143.2M of 1G
```
## Step 5 : cf apps
```
spring-boot-application-in-cloud > cf apps
name                         requested state   instances   memory   disk   urls
spring-boot-demo-app-cloud   started           1/1         1G       1G     spring-boot-demo-app-cloud.cfapps.io
```
## Congratulations - you have deployed your first spring boot application in cloud environment !!!

click here to access the spring boot application in cloud : 

https://spring-boot-demo-app-cloud.cfapps.io/

