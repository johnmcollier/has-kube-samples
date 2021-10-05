# Create Service

This scenario covers creating a service and adding it to an application

1. A [HASServiceRequest](input-hasServiceRequest.yaml) resource is created by a client with the following fields set:

   - `spec.type` field set to `create`, telling the controller to create a new service for an application
   - `spec.serviceName` field set to the name of the service.
   - `spec.applicationUUID` field set to the UUID of the application
   - `sourceRepository.URL` field set to the git repository containing the service

2. The following is done by the HAS controller:

   - The requested registries are queryed, and it retrieves the list of matching samples

   - The status of the [HASServiceRequest](output-hasServiceRequest.yaml) resource is set to successful/unsuccessful based on whether or not the operation suceeded.
   - The application model in the [HASApplication](output-hasApplication.yaml) resource has the service added to it.