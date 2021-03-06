# Java Client Library for IBM Watson IoT Platform

[![Build Status](https://travis-ci.org/ibm-watson-iot/iot-java.svg?branch=master)](https://travis-ci.org/ibm-watson-iot/iot-java)
[![GitHub issues](https://img.shields.io/github/issues/ibm-watson-iot/iot-java.svg)](https://github.com/ibm-watson-iot/iot-java/issues)
[![GitHub](https://img.shields.io/github/license/ibm-watson-iot/iot-java.svg)](https://github.com/ibm-watson-iot/iot-java/blob/master/LICENSE)

Introduction
============

This repository contains the Java Client Library to simplify interactions with [IBM Watson IoT Platform] (https://internetofthings.ibmcloud.com).

The following documentation is provided to help you to get started:

- The [Device section](https://console.ng.bluemix.net/docs/services/IoT/devices/libraries/java.html) contains information on how devices publish events and handle commands using the Java ibmiotf Client Library.
- The [Managed Device section](docs/java_cli_for_manageddevice.rst) contains information on how devices can connect to the Watson IoT Platform Device Management service using Java ibmiotf Client Library and perform device management operations like firmware update, location update, and diagnostics update.
- The [Gateway section](https://console.ng.bluemix.net/docs/services/IoT/gateways/libraries/java_cli_gw.html) contains information on how gateways publish events and handle commands for itself and for the attached devices using the Java ibmiotf Client Library.
- The [Gateway Management section](https://console.ng.bluemix.net/docs/services/IoT/gateways/libraries/java_cli_managed_gw.html) contains information on how to connect the gateway as Managed Gateway to IBM Watson IoT Platform and manage the attached devices.
- The [Application section](https://console.ng.bluemix.net/docs/services/IoT/applications/libraries/java.html) details how applications can use the Java ibmiotf Client Library to interact with devices.
- The [API section](docs/java_cli_for_api.rst)  contains information on how applications can use the Java ibmiotf Client Library to interact with the organization in the Watson IoT Platform through REST APIs
- The [Data management section](https://github.com/ibm-watson-iot/iot-platform-apiv2-samples/blob/master/java/api-samples-v2/src/main/java/com/ibm/iotf/sample/client/application/api/SampleDataManagementAPIOperations.java)contains information on how applications can use the Java ibmiotf Client Library to interact with the organization in the Watson IoT Platform Data management APIs



----

How to use the Watson IoT Client Library for Java
=================================================

The client library can be used by both Application Developers, as well as, Device Developers.


Setup your development environment
----------------------------------
This section explains how to set up your development environment to use the Watson IoT Platform Client Library for Java and needs  

*  Java  
The Java Client Library requires either of the following versions of Java:

    *  [Java 7](http://www.oracle.com/technetwork/java/javase/downloads/jdk7-downloads-1880260.html)  

    *  [Java 8](https://java.com/en/download/)

* [Maven 3](https://maven.apache.org/download.cgi)

* [Watson IoT Client Library for Java](https://github.com/ibm-watson-iot/iot-java)

* [Samples](https://github.com/amitmangalvedkar/iot-platform-apiv2-samples/tree/master/java/api-samples-v2)

* Optionally [Eclipse IDE](https://www.eclipse.org)

Maven support
--------------------------------------------------------------------

The library artifact is pushed to the maven. Use the following maven dependency to include this library in your Java application.

    <dependency>
        <groupId>com.ibm.messaging</groupId>
        <artifactId>watson-iot</artifactId>
        <version>0.2.6</version>
    </dependency>


However, if you want to build the library by yourself, use the following maven command:

    mvn clean package -Dmaven.test.skip=true

The above command quickly builds the library by skipping the test and the `target` directory contains the output jar files. However, if you also want to run the tests, modify the property files that are in the directory `src/test/resources`, and then run the following maven command:

    mvn clean package

Development using Eclipse
-------------------------



----

Supported Features
==================

| Feature   |      Supported?      | Description |
|----------|:-------------:|:-------------|
| [Device connectivity](https://console.ng.bluemix.net/docs/services/IoT/devices/libraries/java.html) |  &#10004; | Connect your device(s) to Watson IoT Platform with ease using this library. [Click here](https://console.ng.bluemix.net/docs/services/IoT/devices/libraries/java.html) for detailed information on how devices can publish events and handle commands.|
| [Gateway connectivity](https://console.ng.bluemix.net/docs/services/IoT/gateways/libraries/java_cli_gw.html) |    &#10004;   | Connect your gateway(s) to Watson IoT Platform with ease using this library. [Click here](https://console.ng.bluemix.net/docs/services/IoT/gateways/libraries/java_cli_gw.html) for detailed information on how gateways can publish events and handle commands for itself and for the attached devices. |
| [Application connectivity](https://console.ng.bluemix.net/docs/services/IoT/applications/libraries/java.html) | &#10004; | Connect your application(s) to Watson IoT Platform with ease using this library. [Click here](https://console.ng.bluemix.net/docs/services/IoT/applications/libraries/java.html) for detailed information on how applications can subscribe to device events and publish commands to devices. |
| [Watson IoT API](https://console.ng.bluemix.net/docs/services/IoT/reference/api.html) | &#10004; | Shows how applications can use this library to interact with the Watson IoT Platform through REST APIs. [Click here](docs/java_cli_for_api.rst) for more information. |
| [SSL/TLS support](https://console.ng.bluemix.net/docs/services/IoT/reference/security/index.html) | &#10004; | By default, this library connects your devices, gateways and applications **securely** to Watson IoT Platform registered service. Ports 8883(default one) and 443 support secure connections using TLS with the MQTT and HTTP protocol. Developers can use the [port setting](https://console.ng.bluemix.net/docs/services/IoT/devices/libraries/java.html#constructor) to change the port number to 443 incase port 8883 is blocked. Also, use the [WebSocket setting]((https://console.ng.bluemix.net/docs/services/IoT/devices/libraries/java.html#constructor)) in order to connect your device/gateway/application over WebSockets. <br> Also, note that the library uses port 1883(unsecured) to connect to the Quickstart service.|
| [Client side Certificate based authentication](https://console.ng.bluemix.net/docs/services/IoT/reference/security/RM_security.html) | &#10004; | Support for [Client side Certificate based authentication](https://console.ng.bluemix.net/docs/services/IoT/reference/security/RM_security.html) is provided by Watson IoT Platform. For information about how to configure certificates, see [Configuring certificates](https://console.bluemix.net/docs/services/IoT/reference/security/set_up_certificates.html#custom_domains).|
| [Device Management](https://console.ng.bluemix.net/docs/services/IoT/devices/device_mgmt/index.html) | &#10004; | Connects your device/gateway as managed device/gateway to Watson IoT Platform.<br> 1. [Click here](docs/java_cli_for_manageddevice.rst) for more information on how to perform device management operations like firmware update, reboot, location update and diagnostics update for a device.<br> 2. [Click here](https://console.ng.bluemix.net/docs/services/IoT/gateways/libraries/java_cli_managed_gw.html) for more information about managing the devices behind gateway.<br> 3. [Click here](https://github.com/ibm-watson-iot/iot-java/blob/master/docs/java_cli_for_api.rst#device-management-request-operations) for information about how to initiate a DM operation from the application.|
| [Device Management Extension(DME)](https://console.ng.bluemix.net/docs/services/IoT/devices/device_mgmt/custom_actions.html) | &#10004; | Provides support for custom device management actions.<br>1. [Click here](https://github.com/ibm-watson-iot/iot-java/blob/master/docs/java_cli_for_manageddevice.rst#device-management-extension-dme-packages) for more information about DME support for a Device. <br> 2. [Click here](https://github.com/ibm-watson-iot/iot-java/blob/master/docs/java_cli_for_api.rst#device-management-extensiondme) to know how to create and initiate a DME request from the application.|
| [Scalable Application](https://console.ng.bluemix.net/docs/services/IoT/applications/mqtt.html) | &#10004; | Provides support for load balancing for applications. [Click here](https://console.ng.bluemix.net/docs/services/IoT/applications/libraries/java.html#constructor) for more information about how to enable scalable application support using this library. |
| [Auto reconnect](https://github.com/eclipse/paho.mqtt.java/issues/9) | &#10004; | Enables device/gateway/application to automatically reconnect to Watson IoT Platform while they are in a disconnected state. To enable this feature, set [Automatic-Reconnect](https://console.ng.bluemix.net/docs/services/IoT/devices/libraries/java.html#constructor) option to true. |
| Websocket | &#10004; | Enables device/gateway/application to connect to Watson IoT Platform using WebSockets. To enable this feature, set [WebSocket](https://console.ng.bluemix.net/docs/services/IoT/devices/libraries/java.html#constructor) option to true. |
| [Event/Command publish using MQTT](https://console.ng.bluemix.net/docs/services/IoT/reference/mqtt/index.html)| &#10004; | Enables device/gateway/application to publish messages using MQTT. Refer to [Device](https://console.ng.bluemix.net/docs/services/IoT/devices/libraries/java.html#publishing_events), [Gateway](https://console.ng.bluemix.net/docs/services/IoT/gateways/libraries/java_cli_gw.html#publishing_events) and [Application](https://console.ng.bluemix.net/docs/services/IoT/applications/libraries/java.html#publishing_events_devices) section for more information. |
| [Event/Command publish using HTTP](https://console.ng.bluemix.net/docs/services/IoT/devices/api.html)| &#10004; |Enables device/gateway/application to publish messages using HTTP. Refer to [Device](https://console.ng.bluemix.net/docs/services/IoT/devices/libraries/java.html#publishing_events), [Gateway](https://console.ng.bluemix.net/docs/services/IoT/gateways/libraries/java_cli_gw.html#publishing_events) and [Application](https://console.ng.bluemix.net/docs/services/IoT/applications/libraries/java.html#publishing_events_devices) section for more information. |
| [Data management](https://console.bluemix.net/docs/services/IoT/information_management/im_index.html)| &#10004; |help you to simplify your applications by decoupling them from the complexities of how specific devices are connected. Refer to [Data management](https://console.bluemix.net/docs/services/IoT/information_management/im_index.html) section for more information. |

Migration from release 0.1.5 to 0.2.1
---------------------------------------

Starting from release **0.2.1**, the library doesn't add parent JSON Element "d" in front of the actual event that is published, as outlined in the following example:

    {"temp":56,"hum":70}


If you need to revert back to the previous behavior, run the application with the property **com.ibm.iotf.enableCustomFormat** set to false as follows:

    java -Dcom.ibm.iotf.enableCustomFormat=false <...>

This will publish the message in old format as follows:

    {"d":{"temp":56,"hum":70}}

----

Key additions to v0.2.5
-------------------------------------------------------------------------------

Version 0.2.5 of the Watson IoT Java Client Library extends the authentication mechanism by adding support for Client side Certificate based authentication. The enhanced security policies enable organizations to determine how they want devices to connect to and be authenticated to the platform. The extended security options that are available to an organization depend on the plan type. Lite, Standard or Advanced Security Plan (ASP) types are available.

Network failure tests that help ascertain network disconnectivity between the Client and the Server while data events are in transit, have been added to the test suite. Leverage the existing setup to build on top of it, various network failure simulations, that suit the needs of your environment. [Further documentation on how one can simulate the conditions are mentioned here](https://github.com/amprasanna/iot-java/blob/master/docs/Steps_to_simulate_Network_Failure_Conditions.md).

----

Key additions to v0.2.6
-------------------------------------------------------------------------------

Version 0.2.6 of the Watson IoT Java Client Library adds on Data management capabilities. Imagine you have many different types, makes, or models of device that you want to connect, and these devices publish data in differing formats.  As a developer you would probably prefer to work with these devices using a simple, common RESTful interface.  Well now you can! You can use the powerful mapping features of Data management to normalize incoming data into a consistent form ready for use in application, dashboards and analytics.

----

Download
-------------------------------------------------------------------------------

Refer to the maven secion for how to use this library in your project. Also, you can download the library manually from the [maven repository](https://repo1.maven.org/maven2/com/ibm/messaging/watson-iot/0.2.6/watson-iot-0.2.6.jar).

When you use maven, the dependencies are downloaded automatically.

----

Samples
-------------------------------------------------------------------------------
You can find samples in each of the corresponding repositories as follows:

* [Device samples](https://github.com/ibm-watson-iot/iot-java/blob/master/samples/device-samples) - Repository contains all device (also device management) related samples in Java. Information and instructions regarding the use of these samples can be found in their respective directories.
* [Gateway Samples](https://github.com/ibm-watson-iot/iot-java/blob/master/samples/gateway-samples) - Repository contains all Gateway (also gateway management) related samples in Java.
* [Watson IoT Platform API V002 samples](https://github.com/ibm-watson-iot/iot-java/blob/master/samples/api) - Repository contains samples that interacts with IBM Watson IoT Platform using the platform API Version 2.
* [Scalable Application samples](https://github.com/ibm-watson-iot/iot-java/blob/master/samples/shared-subscription-sample) - Repository contains sample(s) for building scalable applications, using shared subscription support in IBM Watson IoT Platform.
* [Backup-restore sample](https://github.com/ibm-watson-iot/iot-java/blob/master/samples/backup-restore) - The sample in the repository shows how to backup the device configuration in Cloudant NoSQL DB and restore the same later.
* [Data management sample](https://github.com/amitmangalvedkar/iot-platform-apiv2-samples/blob/master/java/api-samples-v2/src/main/java/com/ibm/iotf/sample/client/application/api/SampleDataManagementAPIOperations.java) - The sample in the repository creates all the artifacts needed for getting a working Data Management sample that converts values from Fahrenhiet to Celcius.

Dependencies
------------------------------------------------------------------------------

-  [Paho MQTT Java Client](https://repo.eclipse.org/content/repositories/paho-releases/org/eclipse/paho/org.eclipse.paho.client.mqttv3/1.1.0/org.eclipse.paho.client.mqttv3-1.1.0.jar) - Provides a client class that enables applications to connect to an MQTT broker.
-  [google-gson](https://code.google.com/p/google-gson/) - A library for interacting with JSON objects.
-  [Apache Commons Logging](http://commons.apache.org/proper/commons-logging/download_logging.cgi) - A library for logging various types of information.
-  [Apache Commons Codec](https://commons.apache.org/proper/commons-codec/download_codec.cgi) - Provides common encoder and decoder functionalities, for example, Base64.
-  [Apache Commons Lang](https://commons.apache.org/proper/commons-lang/download_lang.cgi) - Provides methods for manipulating core Java classes.
-  [Apache Commons Net](https://commons.apache.org/proper/commons-net/download_net.cgi) - Provides methods for client side Internet protocols.
-  [Apache Ant](http://ant.apache.org/) - A build tool for automated builds.
-  [Apache HttpClient](https://hc.apache.org/downloads.cgi) - HTTP Client library.
-  [Apache HttpCore](https://hc.apache.org/downloads.cgi)  - HTTP Core library.
-  [Apache HttpMime](https://hc.apache.org/httpcomponents-client-ga/httpmime/dependency-info.html)  - HTTP Mime library.
-  [Joda-Time](http://www.joda.org/joda-time/download.html) - The date and time library for Java.
-  [Bouncy Castle's PEMReader](https://www.bouncycastle.org/latest_releases.html) - Provides methods to read Client side Certificates

----

License
-----------------------

The library is shipped with Eclipse Public License. For more information about the public licensing, see the [License file](LICENSE).
