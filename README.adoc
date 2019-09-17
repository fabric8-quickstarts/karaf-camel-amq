# Camel AMQ QuickStart

This quickstart demonstrates how to connect to EnMasse (MaaS) and use JMS messaging between two Camel routes.

This quickstart requires EnMasse to have been deployed and running first. To install EnMasse into OpenShift or Kubernetes follow [documentation](https://enmasse.io/documentation/master/openshift/#installing-messaging).

### Configuration

The quickstart must run on a Openshift project different from the one where EnMasse is deployed.

Log in as a user with cluster-admin privileges:

```
oc login -u system:admin
```

Before running the quickstart, you need to configure EnMasse (create user and queue). Run the following commands to create new project and apply configuration files:

```
oc new-project MY_PROJECT_NAME
oc apply -f src/main/resources/k8s
```

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
