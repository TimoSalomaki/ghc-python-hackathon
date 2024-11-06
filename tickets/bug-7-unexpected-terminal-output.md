# Bug report: Unexpected Terminal Output for HTTPie CLI  
   
## Description  
Hi wonderful developers,  
   
First of all, I want to thank you for all the hard work you do. I have been using your amazing tool, HTTPie CLI, and I was so excited to try it out after seeing all the fantastic features and beautiful output in the YouTube videos. However, when I use the tool, I don't get the colorful, pretty printouts that I've seen in the videos. Instead, all I see is white text on a black terminal screen. I'm really sorry if this is a user error, but I thought it might be worth reporting. I appreciate your understanding and patience with me.  
   
## Steps to reproduce  
1. Open the terminal.  
2. Run HTTPie CLI with a basic request, e.g., `http GET https://httpbin.org/get`.  
   
## Actual result  
```  
$ http GET https://httpbin.org/get  
HTTP/1.1 200 OK  
Access-Control-Allow-Credentials: true  
Access-Control-Allow-Origin: *  
Content-Length: 426  
Content-Type: application/json  
Date: Mon, 01 Jan 2023 00:00:00 GMT  
Server: gunicorn/19.9.0  
   
{  
    "args": {},  
    "headers": {  
        "Accept": "*/*",  
        "Accept-Encoding": "gzip, deflate",  
        "Host": "httpbin.org",  
        "User-Agent": "HTTPie/2.4.0"  
    },  
    "origin": "123.123.123.123",  
    "url": "https://httpbin.org/get"  
}  
```  
All the text appears in white on a black terminal screen.  
   
## Expected result  
I was expecting the output to be colorful and visually appealing as shown in the YouTube videos. The headers, JSON structure, and other components should be color-coded to make it easier to read and understand.  
   
## Environment  
- **HTTPie CLI version:** ƸӜƷ
- **Operating System:** (͡ ° ͜ʖ ͡ °)
- **Terminal:** ¯\(°_o)/¯
- **Python version:** ٩(^‿^)۶  
   
Thank you so much for your time and help. I hope this feedback is helpful, and I apologize for any inconvenience I may have caused. You're doing an amazing job!  
   
Warm regards,  
A very grateful user
