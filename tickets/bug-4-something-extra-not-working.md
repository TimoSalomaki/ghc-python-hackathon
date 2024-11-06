# Bug report: Something extra not working, I think
   
## Description  
I tried to use the tool to do something but it's not doing it right. I was supposed to add something extra to my call but it seems like it's ignoring it or something. I don't really know, but it should work and it's not. It’s like when you ask for a sandwich with extra cheese and they just give you a plain sandwich.  
   
## Steps to reproduce  
1. Open the tool.  
2. Run the command `http https://httpbin.org/headers My-Custom-Header:HelloWorld`.  
3. Look at what comes back.  
   
## Actual result  
I got this weird thing back:  
   
```  
HTTP/1.1 200 OK  
Access-Control-Allow-Credentials: true  
Access-Control-Allow-Origin: *  
Connection: keep-alive  
Content-Length: 218  
Content-Type: application/json  
Date: Wed, 12 Oct 2023 14:48:00 GMT  
Server: gunicorn/19.9.0  
   
{  
  "headers": {  
    "Accept": "*/*",  
    "Host": "httpbin.org",  
    "User-Agent": "HTTPie/2.4.0"  
  }  
}  
```  
   
## Expected result  
I thought it should show the extra thing I added, like the custom thing I mentioned in the command. But it’s not there.  
   
## Environment  
- Operating System: Windows
- HTTPie version: 2.4.0  
- Python version: 5.1.0

<details>
   <summary>SPOILER - USE IF YOU'RE STUCK! 🤔 - BEFORE: DID YOU ASK GITHUB COPILOT 🤖 ALREADY?</summary>

*System:* At this point you should be pretty comfortable with the `@workspace` extension. Can you find the code where headers are finalized? Maybe something's wrong there.

</details>
