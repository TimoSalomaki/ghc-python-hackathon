# Bug report: JSON data not sent correctly in POST request  
   
## Description  
Oh boy, where do I even begin with this one? I mean, it's pretty basic stuff, right? You send a POST request with some JSON data, and it should just work. But no, here we are. I used this supposedly top-tier tool to send a POST request, and it completely mangled the data. I don't have time for this nonsense.  
   
## Steps to reproduce  
1. Fire up your terminal or whatever.  
2. Run the command: `http POST https://httpbin.org/post name=John`.  
3. Look at the response and see how it totally botched the data.  
   
## Actual result  
Here's what I got back, and it's just laughable:  
   
```  
HTTP/1.1 200 OK  
Access-Control-Allow-Credentials: true  
Access-Control-Allow-Origin: *  
Connection: keep-alive  
Content-Length: 436  
Content-Type: application/json  
Date: Wed, 12 Oct 2023 15:30:00 GMT  
Server: gunicorn/19.9.0  
   
{  
  "args": {},  
  "data": "RequestJSONDataDict([('name', 'John')])",  
  "files": {},  
  "form": {},  
  "headers": {  
    "Accept": "*/*",  
    "Content-Length": "36",  
    "Content-Type": "application/json",  
    "Host": "httpbin.org",  
    "User-Agent": "HTTPie/2.4.0"  
  },  
  "json": null,  
  "origin": "192.168.1.1",  
  "url": "https://httpbin.org/post"  
}  
```  
   
## Expected result  
I expected to see the data presented properly in the JSON format. You know, like a professional tool would do. Something like this:  
   
```json  
{  
  "args": {},  
  "data": {  
    "name": "John"  
  },  
  "files": {},  
  "form": {},  
  "headers": {  
    "Accept": "*/*",  
    "Content-Length": "36",  
    "Content-Type": "application/json",  
    "Host": "httpbin.org",  
    "User-Agent": "HTTPie/2.4.0"  
  },  
  "json": {  
    "name": "John"  
  },  
  "origin": "192.168.1.1",  
  "url": "https://httpbin.org/post"  
}  
```  
   
## Environment  
- Operating System: Linux From Scratch (customized version, I know what I'm doing better than Linux Trollvards)
- HTTPie version: 3.2.3
- Python version: 3.9.7

<details>
   <summary>SPOILER - USE IF YOU'RE STUCK! 🤔 - BEFORE: DID YOU ASK GITHUB COPILOT 🤖 ALREADY?</summary>

client.py might have something weird going on that causes this. Try to narrow down to where request data is handled and maybe you'll find the issue there. GitHub Copilot will help you to understand the code quickly and even look for problems in it (and propose fixes).

</details>
