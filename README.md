# AzureIoTHubDeviceOperations
This is a Postman collection which allows basic device operations executed via Postman

For registering a device using Device Provisioning service:
URL: https://global.azure-devices-provisioning.net/[ID_Scope]/registrations/[registration_id]/register?api-version=2021-06-01

If using key-based authentication, a security token is passed in the HTTP Authorization request header in the following format:

SharedAccessSignature sig={signature}&se={expiry}&skn={policyName}&sr={URL-encoded-resourceURI}


The security token has the following format for retrieving the device twin:

SharedAccessSignature sig={signature}&se={expiry}&skn={policyName}&sr={URL-encoded-resourceURI}

Here are the expected values

Value	Description
{signature}	An HMAC-SHA256 signature string of the form: {URL-encoded-resourceURI} + "\n" + expiry. Important: The key is decoded from base64 and used as key to do the HMAC-SHA256 computation.
{expiry}	UTF8 strings for number of seconds since the epoch 00:00:00 UTC on 1 January 1970.
{URL-encoded-resourceURI}	Lower case URL-encoding of the lower case resource URI. URI prefix (by segment) of the endpoints that can be accessed with this token, starting with host name of the IoT Device Provisioning Service (no protocol). For example, mydps.azure-devices-provisioning.net.
{policyName}	The name of the shared access policy to which this token refers.
