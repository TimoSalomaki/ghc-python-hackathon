# Bug report: HTTPie CLI Timeout Handling is Laughable  
   
## Description  
   
Honestly, I can't believe I have to write this up. I mean, you would think that in 2024, handling a timeout properly wouldn't be rocket science. But here we are. I'm trying to make an API call that SHOULD timeout, but instead, I'm getting a ridiculous HTTP 5XX error. I've seen better error handling in first-year coding projects.   
  
## Steps to reproduce  
   
1. Open your terminal. This assumes you know what that is.  
2. Run the following command with HTTPie CLI:  
   ```
   Do I really have to spoon feed everything to you? Figure out a way to make a call that timeouts.
   ```  
3. Wait for the inevitable failure.  
   
## Actual result  
   
Instead of the expected timeout, I get this absurd HTTP 5XX error. Here, feast your eyes on this mess:  
   
```  
HTTP/1.1 500 Internal Server Error  
Content-Type: application/json  
Date: Thu, 12 Oct 2023 10:00:00 GMT  
Server: ExampleServer/1.0  
   
{  
  "error": "Server Error",  
  "message": "An unexpected error occurred."  
}  
```  
   
## Expected result  
   
Seriously? I have to spell this out? When a request times out, I expect a TIMEOUT. Something like:  
   
```  
http: error: Request timed out (HTTP timeout)  
```  
   
Not some generic, unhelpful HTTP 5XX error. Is that really too much to ask?  
   
## Environment  
   
- Every environment imaginable on our dear planet Earth.
- Network: Stable, because I know someone will blame it on my network  
   
Fix this. I'm losing brain cells just writing this report.
