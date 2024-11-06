# Feature Request: Add Caching Capability with a Flag

## Description:
As a user of HTTPie CLI, I frequently make repeated API calls to the same endpoints, and it would greatly improve efficiency if I could cache the responses for a specified amount of time. This would help reduce load times and minimize redundant requests to the server.

## Request:
Please add a feature that allows users to cache API responses for a specified number of minutes. This can be implemented by introducing a caching flag in the CLI call that accepts a time value in minutes. When this flag is used, HTTPie should store the response locally and reuse it for subsequent requests within the specified time frame.

## Expected Behavior:
When the caching flag is used with an API call, the first request should be sent to the server and the response should be cached locally. For any subsequent requests to the same endpoint within the specified cache duration, the cached response should be returned instead of making a new request to the server. After the cache duration expires, the next request should go to the server again and refresh the cache.

## Example:
```sh
# Caching the response for 10 minutes
http --cache=10 GET https://api.example.com/data

# Subsequent requests within 10 minutes will use the cached response
http --cache=10 GET https://api.example.com/data
```

In this example, the first request to `https://api.example.com/data` will fetch the data from the server and cache the response for 10 minutes. Any subsequent request to the same URL within 10 minutes will return the cached response instead of hitting the server again.
