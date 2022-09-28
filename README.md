# Git Hub action to run Postman Collection integration tests

- https://octopus.com/blog/githubactions-running-endtoend-tests

Reference: https://github.com/OctopusSamples/junit-newman-test/blob/main/GitHubTree.json

# Azure IoTHub Device Operations
This is a Postman collection which allows basic device operations executed via Postman using javascript.
&nbsp;
Operations:
- Register a device throught Azure Device Provisioning Service.
- Retrive device twin properties throght Azure IoT Hub.

# Registering a device using Device Provisioning service:

URL: https://global.azure-devices-provisioning.net/[ID_Scope]/registrations/[registration_id]/register?api-version=2021-06-01

<b>HTTP Method:PUT</b>

Request Headers:

-  Authorization: sasToken
-  Content-type: application/json

If using key-based authentication, a security token is passed in the HTTP Authorization request header in the following format:

SharedAccessSignature sig={signature}&se={expiry}&skn={policyName}&sr={URL-encoded-resourceURI}


Request Body:
```
{
  "registrationId": "cXdlX3F3ZV9xX3F3ZQ"
}
```

SasToken example:
```
 SharedAccessSignature sr=0ne002ee24e%2Fregistrations%2Fcxdlx3f3zv9xx3f3zq&sig=mM%2F%2BCl4qA8zrjhG3gBC%2Fbgw6xqftBf3eL6%2BgPQ%2FaPu8%3D&se=1660075663
```
&nbsp;
How sas tokens are generated:

Link to official documentation: https://docs.microsoft.com/en-us/azure/iot-dps/how-to-control-access


# Retrieve device twin from Azure IoT Hub

URL: https://{{hubName}}.azure-devices.net/twins/{{deviceId}}?api-version=2016-11-14

<b>HTTP Method: GET</b>

Request Headers:

- Authorization: sasToken

The security token has the following format for retrieving the device twin:
```
 SharedAccessSignature sig={signature}&se={expiry}&skn={policyName}&sr={URL-encoded-resourceURI}
```

SasToken example:
```
SharedAccessSignature sr=iothub-iomt-iothub-v1-dev-westeurope.azure-devices.net&sig=H92FehA0llWjbHYSYAxqMp4M3fOQH%2Fy%2F73%2FV3%2BWz0TA%3D&se=1660075777&skn=iothubowner
```
&nbsp;
How sas tokens for retrieving device twin are generated:

Link to official documentation: https://docs.microsoft.com/en-us/azure/iot-hub/iot-hub-dev-guide-sas?tabs=java

