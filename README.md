# Drone Harness Plugin

## Drone Plugin to trigger Pipelines or Workflows in Harness using API key.

### Usage:

    - name: Harness Plugin
      image: diegokoala/drone-harness-plugin
      settings:  
        application: "Harness Demo Application"
        type: "PIPELINE"
        entityname: "CD Pipeline"
        service: "search"
        build: "v6"
        accountid:
          from_secret: harness_acctid
        apikey: 
          from_secret: harness_secret
        service_name: "order-service"
        build_number: "latest"
        artifact_source_name: "harness_todolist-sample"



Obs: 

To run this plugin outside drone, you should create this ENV variables before the container starts.

You can add to the Dockerfile

    ENV PLUGIN_ACCOUNTID "AccountID"
    ENV PLUGIN_APIKEY "4P1K3Y"
    ENV PLUGIN_APPLICATION "Harness Demo Application"
    ENV PLUGIN_ENTITYNAME "CD Pipeline"
    ENV PLUGIN_TYPE "PIPELINE"
    ENV PLUGIN_SERVICE_NAME "order-service"
    ENV PLUGIN_BUILD_NUMBER "latest"
    ENV PLUGIN_ARTIFACT_SOURCE_NAME "harness_todolist-sample"
