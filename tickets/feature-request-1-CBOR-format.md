# Feature Request: Support for CBOR Response Formatting

## Description:
Hello team,

I have been using your HTTPie CLI for a while now, and I must say it has significantly improved my workflow. However, I recently encountered a limitation that I hope you can address.

Currently, the tool supports response formatting in JSON and XML, which is great, but I need the ability to format responses in CBOR (Concise Binary Object Representation). CBOR is more efficient for my use case, especially when dealing with large data sets and constrained environments.

## Request:  
Could you please add an option to format responses in CBOR? This would involve adding a new flag or option to the existing command structure to specify CBOR as the desired response format.

## Expected Behavior:  
When I make a request using HTTPie and specify the CBOR option, the response should be formatted in CBOR instead of the default JSON or XML formats.

## Example:
```sh
http --cbor GET http://api.example.com/resource
```
