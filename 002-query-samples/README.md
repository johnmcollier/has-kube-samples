# Create Application

This scenario covers query a list of devfile samples from a Devfile Registry

1. A [DevfileSampleRequest](input-hasDevfileSampleRequest.yaml) resource is created by a client with the following fields set:

   - `spec.registries` array with list of registries
   - Optional list of tags and architectures to filter on

2. The following is done by the HAS controller:

   - The requested registries are queryed, and it retrieves the list of matching samples

   - The [DevfileSampleRequest](input-hasDevfileSampleRequest.yaml)'s `status.Data` field is set to the returned samples.