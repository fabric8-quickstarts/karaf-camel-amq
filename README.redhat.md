# Camel AMQ QuickStart

This quickstart demonstrates how to connect to EnMasse (MaaS) and use JMS messaging between two Camel routes.

This quickstart requires EnMasse to have been deployed and running first. Follow the directions at

http://enmasse.io/documentation

to install EnMasse into OpenShift or Kubernetes. There is a `deploy.sh` script that will help you install EnMasse. Once EnMasse is installed, please create an incomingOrders queue using the EnMasse console.

### Configuration

The quickstart must run on a Openshift project different from the one where EnMasse is deployed.

Before running the quickstart, you need to configure the `src/main/fabric8/deployment.yml` file in order to 
use the correct remote instance of AMQ EnMasse.
The `AMQP_SERVICE_NAME` environment variable must point to the hostname of the external "messaging" route exposed by EnMasse.

### Building

The example can be built with:

    mvn clean install

### Running the example in OpenShift

The example can be built and deployed using:

    mvn fabric8:deploy

When the example runs in OpenShift, you can use the OpenShift client tool to inspect the status, e.g.:

- To list all the running pods:
    ```
    $ oc get pods
    ```

- Then find the name of the pod that runs this example, and output the logs from the running pod with:
    ```
    $ oc logs <name of pod>
    ```
