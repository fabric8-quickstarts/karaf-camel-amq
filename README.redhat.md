# Camel AMQ QuickStart

This quickstart demonstrates how to connect to EnMasse (MaaS) and use JMS messaging between two Camel routes.

This quickstart requires EnMasse to have been deployed and running first. Follow the directions at

http://enmasse.io/documentation

to install EnMasse into OpenShift or Kubernetes.    There is a deploy-openshift.sh script and a deploy-kubernetes.sh script that will help you install EnMasse.    Once EnMasse is installed, please create an incomingOrders queue using the EnMasse console.

To install this quickstart from the command line type

The example can be built with:

    mvn clean install

This requires you have [setup your local computer](http://fabric8.io/guide/getStarted/develop.html) to work with docker and kubernetes.




