# Bug report: Application fails to start  
   
## Description  
I've been trying to start the application using the command line, but it doesn't seem to work. I get an error message and the app just won't start. I'm not very familiar with the technical details, but I copied the error message below for reference.  
   
## Steps to reproduce  
1. Open command line.  
2. Navigate to the directory where the application is located.  
3. Attempt to start the application by running it.  
   
## Actual result  
The application fails to start and displays the following error message:  
```  
Traceback (most recent call last):  
  File "<frozen runpy>", line 198, in _run_module_as_main  
  File "<frozen runpy>", line 88, in _run_code  
  File "C:\stuff\httpie\apps\cli\venv\Scripts\http.exe\__main__.py", line 4, in <module>  
  File "C:\stuff\httpie\apps\cli\httpie\__main__.py", line 6  
    def main()  
              ^  
SyntaxError: expected ':'  
```  
   
## Expected result  
The application should start without any errors.  
   
## Environment  
- Operating System: Windows 10  
- Command Line Interface: Command Prompt
- Application Version: dunno 
   
Let me know if you need any more information. Thank you!

<details>
   <summary>SPOILER - USE IF YOU'RE STUCK! 🤔 - BEFORE: DID YOU ASK GITHUB COPILOT 🤖 ALREADY?</summary>

*System:* Oh, you're in luck! Looks like one of your colleagues has already started to work on this bug! Here's a comment they've left. 

---
   
**Chris Colleague:** I didn't get very far with my investigations but I think that there's a problem with the `__main__.py` file. Good luck figuring out the rest, I'm going on holiday now!

</details>
