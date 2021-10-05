# Create Application

This scenario covers creating an application using HAS' Kubernetes API.

1. A [HASApplicationRequest](input-hasApplicationRequest.yaml) resource is created with the following fields set:

   - applicationName
   - GitOps repo URL
   - `spec.type` set to `create`

2. The following is done by the HAS controller:

   - A [HASApplication](output-hasApplication.yaml) resource is created, with the application model generated under `status.data

   - The [HASApplicationRequest](output-hasApplicationRequest.yaml)'s status is set to Successful if the operation succeeded, and unsuccessful if it failed.