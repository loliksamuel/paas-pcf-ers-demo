[![Build Status](https://travis-ci.org/mborges-pivotal/pcf-ers-demo1.svg?branch=master)](https://travis-ci.org/mborges-pivotal/pcf-ers-demo1)
[ ![Download](https://api.bintray.com/packages/mborges-pivotal/generic/pcf-ers-demo1/images/download.svg) ](https://bintray.com/mborges-pivotal/generic/pcf-ers-demo1/_latestVersion)

# PCF Elastic Runtime Service (ERS) Base Demo
Base application to demonstrate PCF ERS

## Credits and contributions
As you all know, we often transform other work into our own. This is all based from Andrew Ripka's [cf-workshop-spring-boot github repo](https://github.com/pivotal-cf-workshop/cf-workshop-spring-boot) with some basic modifications.

## Introduction
This base application is intended to demonstrate some of the basic functionality of PCF ERS:

* PCF api, target, login, and push
* PCF environment variables
  * Spring Cloud Profiles
* Scaling, self-healing, router and load balancing
* RDBMS service and application auto-configuration
* Blue green deployments

## Getting Started

**Prerequisites**
- [Cloud Foundry CLI](http://info.pivotal.io/p0R00I0eYJ011dAUCN06lR2)
- [Git Client](http://info.pivotal.io/i1RI0AUe6gN00C010l12J0R)
- An IDE, like [Spring Tool Suite](http://info.pivotal.io/f00RC0N0lh01eU21IAJ260R)
- [Java SE Development Kit](http://info.pivotal.io/n0I60i3021AN0JU0le10CRR)

**Building (creating jar file)**
```
$ git clone [REPO]
$ cd [REPO]
$ ./mvnw clean install
``` 


### Running on Cloud Foundry
Take a look at the manifest file for the recommended setting. Adjust them as per your environment.

 

```bash
cf login -a https://api.run.pivotal.io
cf push yourappnamexxx -p target/xxx-0.0.1-SNAPSHOT.jar
or
cf create-space spc1 -o allocation
cf target -o allocation -s spc1
cf push -n mysubdomain6
```
 

 
wait and see long logs, see the route, and browse there http://<route>



### Running on local machine
The application is set to use an embedded H2 database in non-PaaS environments, and to take advantage of Pivotal CF's auto-configuration for services. To use a MySQL Dev service in PCF, simply create and bind a service to the app and restart the app. No additional configuration is necessary when running locally or in Pivotal CF.

In Pivotal CF, it is assumed that a Pivotal MySQL service will be used.

```
$ ./mvnw spring-boot:run
```

Then go to the http://localhost:8080 in your browser

## Labs/Demo Scripts summary
We have a [Labs](https://github.com/Pivotal-Field-Engineering/pcf-ers-demo/tree/master/Labs) folder to help you learn PCF. These labs can be used for workshops or self-training.    


