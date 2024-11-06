# Bug report: No output when running HTTPie command  
   
## Description  
When I run the command `http www.google.com`, nothing is printed in the terminal. There are no errors, no successes, absolutely nothing. I even tried running it with `http azure.microsoft.com`, and since that didn't work either, I am convinced this is a bug.  
   
## Steps to reproduce  
1. Open terminal.  
2. Run the command `http azure.microsoft.com`.  
3. Observe the output.  
   
## Actual result  
No output is displayed in the terminal. The command seems to execute but there are no messages, errors, or any form of feedback.  
   
## Expected result  
The expected result is that the terminal should display the output of the HTTP request to `azure.microsoft.com`, including status codes, headers, and body content.  
   
## Environment  
- HTTPie CLI version: 3.2.3 
- Operating System: Windows 12 Beta Ultimate
- Terminal: vscode's terminal, or what do you mean? 
- Other relevant environment details: I'm worried about global warming :(

<details>
   <summary>SPOILER - USE IF YOU'RE STUCK! 🤔 - BEFORE: DID YOU ASK GITHUB COPILOT 🤖 ALREADY?</summary>
   
**Chris Colleague:** I already took up this issue but I'm afraid my skills are not good enough to figure out how to fix everything! I have a strong feeling that everything is ok with the code itself but that there's some misconfiguration in the default parameters. Perhaps, a silent mode is on by default or something?

</details>
