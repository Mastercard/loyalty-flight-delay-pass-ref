# Flight Delay Pass Reference Application

FlightDelayPass API
- API version: v1.0
  - Build date: 2021-01-22T14:30:47.482-06:00[America/Chicago]

FlightDelayPass application


## Requirements

Building the API client library requires:
1. Java 1.7+
2. Maven/Gradle

## Installation

To install the API client library to your local Maven repository, simply execute:

```shell
mvn clean install
```

To deploy it to a remote Maven repository instead, configure the settings of the repository and execute:

```shell
mvn clean deploy
```

Refer to the [OSSRH Guide](http://central.sonatype.org/pages/ossrh-guide.html) for more information.

### Maven users

Add this dependency to your project's POM:

```xml
<dependency>
  <groupId>com.mastercard.lts.benefits</groupId>
  <artifactId>flight_delay_pass_reference</artifactId>
  <version>0.0.1-SNAPSHOT</version>
  <scope>compile</scope>
</dependency>
```

### Gradle users

Add this dependency to your project's build file:

```groovy
compile "com.mastercard.lts.benefits:flight_delay_pass_reference:0.0.1-SNAPSHOT"
```

### Others

At first generate the JAR by executing:

```shell
mvn clean package
```

Then manually install the following JARs:

* `target/flight_delay_pass_reference-0.0.1-SNAPSHOT.jar`
* `target/lib/*.jar`

## Getting Started

Please follow the [installation](#installation) instruction and execute the following Java code:

```java

import com.mastercard.developer.flight_delay_pass_reference.*;
import com.mastercard.developer.flight_delay_pass_reference.auth.*;
import com.mastercard.developer.flight_delay_pass_reference.model.*;
import com.mastercard.developer.flight_delay_pass_reference.api.FlightDelayControllerApi;

import java.io.File;
import java.util.*;

public class FlightDelayControllerApiExample {

    public static void main(String[] args) {
        
        FlightDelayControllerApi apiInstance = new FlightDelayControllerApi();
        String xOpenapiClientId = "xOpenapiClientid_example"; // String | 
        UserRequest userRequest = new UserRequest(); // UserRequest | 
        try {
            RegistrionResponse result = apiInstance.postRegistration(xOpenapiClientId, userRequest);
            System.out.println(result);
        } catch (ApiException e) {
            System.err.println("Exception when calling FlightDelayControllerApi#postRegistration");
            e.printStackTrace();
        }
    }
}

```

# Steps to run the application from command line
              
- Create a new project from Mastercard DevZone - stage.developer.mastercard.com or developer.mastercard.com
- Select "****TBD****" from Choose API dropdown and hit continue.
- Get Sandbox keys and store your .p12 certificate along with the readme/documentation.
- Please save this Sandbox Keys, .p12, key store password and alias as you are going to use these to run the application.
- Clone this repository and set up as Maven project
- Update the following keys in application.properties file
    - *mastercard.flight.delay.pass.ref.app.consumer.key*: This can be found in the project you created on developerZone
    - *mastercard.flight.delay.pass.ref.app.keystore.path*: Path where you saved your certs i.e., .p12 file you received while creating a project
    - *mastercard.flight.delay.pass.ref.app.keystore.password*: This is the password you get with Sandbox cert.
    - *mastercard.flight.delay.pass.ref.app.keystore.alias*: This is the alias you get with Sandbox cert.
    
- Example:
    - mastercard.flight.delay.pass.ref.app.url = https://stage.api.mastercard.com
    - mastercard.flight.delay.pass.ref.app.consumer.key = Abcdfefgjhilklmnopqrstuvwxyz-dxcq_zD7IiPa0df175e!22a7fddba56e800000000000000000
    - mastercard.flight.delay.pass.ref.app.keystore.path = C:\\path\\provided.p12
    - mastercard.flight.delay.pass.ref.app.keystore.password = pwd
    - mastercard.flight.delay.pass.ref.app.keystore.alias = alias

	
- Do a clean build either through IDE or command prompt, if you are doing it through command prompt then the below command should be executed in the directory which contains this repository's pom file
    Eg: mvn clean install
- Run the application using below command 
    - Example: `java -jar path of the Jar relative to the current directory/flight_delay_pass_reference-1.0.0.jar <argument>`
    - Argument: An argument which defines the feature user wants to run through command line. If you don't specify this argument, it will run all the features(registration and error) one after the other.
        - registration : Registration for flight delay mock service
        - error: An error scenario example         
               
- Command line example to run the application: 
    - `java -jar target/flight_delay_pass_reference-1.0.0.jar registration` here the application runs only registration feature. if you want to run more than one feature then specify the features with comma separated. Eg: `java -jar target/flight_delay_pass_reference-1.0.0.jar registration,error` here it executes only these 2 features.You can remove the argument to run all the features Example: `java -jar target/flight_delay_pass_reference-1.0.0.jar`. If you want to run the feature one by one then execute the command `java -jar target/flight_delay_pass_reference-1.0.0.jar registration` then again run the command with different feature `java -jar target/flight_delay_pass_reference-1.0.0.jar error` and so on.
    
# Sandbox Testing
    
If you would like to test this in Sandbox environment please contact Mastercard representative to set up you or your organization in this environment because if this does not happen the authorization fails in the Loyalty Flight Delay Pass Service API. All the URLs have a prefix `reference` in this reference application for all resources of Loyalty Flight Delay Pass Service API so that it deals with sample data. You need to remove this `reference` word from the URLs when testing against real data. Eg: `loyalty/flight-delay-pass/registrations` just for reference application. 

While testing the application with a `reference(/loyalty/flight-delay-pass/registrations)` url you need to send the exact inputs that are used in this reference app to get the desired response otherwise the mock returns an error with a message 'the request does not match'.


    
 
Client libraries can be generated for a simplified integration with the reference service, [for more details](https://developer.mastercard.com/blog/consuming-mastercard-apis-in-client-applications)


Copyright (c) 2021 Mastercard
 
Licensed under the Apache License, Version 2.0 (the "License");
you may not use this file except in compliance with the License.
You may obtain a copy of the License at
 
    http://www.apache.org/licenses/LICENSE-2.0
 
Unless required by applicable law or agreed to in writing, software
distributed under the License is distributed on an "AS IS" BASIS,
WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
See the License for the specific language governing permissions and
limitations under the License.    





