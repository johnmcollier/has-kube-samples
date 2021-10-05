# Update Service

This scenario covers deleting a service from an application

1. A [HASServiceRequest](input-hasServiceRequest.yaml) resource is created by a client with the following fields set:

   - `spec.type` field set to `delete`, telling the controller to create a new service for an application
   - `spec.serviceName` field set to the name of the service being updated.
   - `spec.applicationUUID` field set to the UUID of the application.

2. The following is done by the HAS controller:

   - The application model in the [HASApplication](output-hasApplication.yaml) resource has the service removed from it.
   - The status of the [HASServiceRequest](output-hasServiceRequest.yaml) resource is set to successful/unsuccessful based on whether or not the operation suceeded.
