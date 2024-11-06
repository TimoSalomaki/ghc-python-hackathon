# Feature Request: Enhanced Resource Utilization Metrics for HTTPie CLI  
## Description:  
Hello HTTPie Team!  
   
First off, let me just say, I am a HUGE fan of HTTPie. It's my go-to tool for all things HTTP-related, and it has made my development workflow so much more efficient. However, as someone who is always looking to optimize and understand the performance characteristics of my tools, I have a feature request that I think would be an absolute game-changer!  
   
I often find myself needing to capture detailed metrics about the resource utilization of the HTTPie CLI itself while making HTTP requests. Specifically, I would love to capture memory usage, CPU usage, and network usage stats for each request. This data would be invaluable for performance tuning, debugging, and ensuring that my scripts and applications are as efficient as possible.  
   
## Request:  
I would like HTTPie CLI to have built-in functionality to capture and display memory, CPU, and network usage statistics for each HTTP request made. This could be an optional feature that can be enabled via a command-line flag or configuration setting.  
   
## Expected Behavior:  
When this feature is enabled, HTTPie CLI should:  
1. Measure and display the amount of memory used by the process during the request.  
2. Measure and display the CPU utilization during the request.  
3. Measure and display the network usage statistics, including bytes sent and received.  
   
This information should be presented in a clear and concise manner alongside the usual HTTPie output, either in the console or as part of a detailed report.  
   
## Example:  
Here's a conceptual example of what the output might look like when this feature is enabled:  
   
```sh  
$ http --metrics GET http://example.com  
   
HTTP/1.1 200 OK  
Content-Type: application/json  
...  
   
{  
    "key": "value"  
}  
   
# Resource Utilization Metrics  
Memory Usage: 10MB  
CPU Usage: 15%  
Network Sent: 512 bytes  
Network Received: 2048 bytes  
```  
   
I imagine this would involve integrating some system-level monitoring tools or libraries to gather the stats, but I think it would be well worth the effort. The ability to see these metrics would provide deep insights and help us developers make more informed decisions about optimizing our tools and applications.  
   
Thank you so much for considering this feature request! Keep up the amazing work with HTTPie!  
   
Best regards,  
Danny Developer
