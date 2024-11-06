# HTTPie Debugging Challenge
Welcome to the HTTPie Debugging Challenge! In this exercise, you'll work with a modified version of the HTTPie command-line HTTP client. Your mission is to identify and fix several critical issues to restore the tool's full functionality.

## Introduction
### Table of Contents
- About the Challenge
- Objectives
- Prerequisites
- Setup Instructions
- The Challenge
  - Known Issues
  - Tasks
- Submission Guidelines
- Resources
- License

### About the Challenge
HTTPie is a user-friendly command-line HTTP client for interacting with web services. It offers a simple and intuitive syntax for making HTTP requests and displaying responses.

In this challenge, you'll debug and fix a forked version of HTTPie that contains several deliberate issues. This will help you enhance your debugging skills and experience how AI-assisted tools like GitHub Copilot can aid in the development process.

### Prerequisites
- Python version 3.7 or higher installed.
- Visual Studio Code on Windows, Mac or Linux
- GitHub Copilot

### Setup Instructions
1. Clone the challenge repository to your machine from https://github.com/TimoSalomaki/httpie_cli
2. Follow the local [development setup guidance](https://github.com/httpie/cli/blob/master/CONTRIBUTING.md#development-environment) to get the dev environment up and running. If you have trouble getting Make to run, follow this [Windows specific guidance](https://github.com/httpie/cli/blob/master/CONTRIBUTING.md#windows).

3. Verify the Installation
Check the HTTPie version:

```bash
http --version
```

4. Oh no, it's broken! Let's fix it!

## The Challenge
Wow, the application really seems broken. It doesn't even run! Luckily, we have a bunch of issue reports from users in our bare-bones issue tracker. Let's start by fixing the first error, then the next one, and hopefully getting the application to run as intended once all are fixed.

- [Bug 1](tickets/bug-1-app-startup-fails.md): App startup fails
- [Bug 2](tickets/bug-2-no-output.md): No output when running HTTPie command
- [Bug 3](tickets/bug-3-the-never-ending-story.md): The Never-Ending Story of HTTPie
- [Bug 4](tickets/bug-4-something-extra-not-working.md): Something extra not working, I think
- [Bug 5](tickets/bug-5-json-data-not-sent-correctly.md): JSON data not sent correctly in POST request
- [Bug 6](tickets/bug-6-laughable-timeout-handling.md): HTTPie CLI Timeout Handling is Laughable
- [Bug 7](tickets/bug-7-unexpected-terminal-output.md): Unexpected Terminal Output for HTTPie CLI

Phew, that was tough but everything is now fixed! However, there are now feature requests from the customers to be worked on... The work never ends!

- [Feature Request 1](tickets/feature-request-1-CBOR-format.md): Support for CBOR Response Formatting
- [Feature Request 2](tickets/feature-request-2-caching.md): Add Caching Capability with a Flag
- [Feature Request 3](tickets/feature-request-3-metrics.md): Enhanced Resource Utilization Metrics for HTTPie CLI

## Resources
- HTTPie Documentation: [Official Docs](https://httpie.io/docs/cli)
- Python Documentation: [Python 3 Docs](https://docs.python.org/3/index.html)
- GitHub Copilot: [Copilot Information](https://docs.github.com/en/copilot)
- Git Basics: *Use GitHub Copilot Chat's `@terminal` extension for help.*
- Pytest Documentation: [Pytest Docs](https://docs.pytest.org/en/stable/)
- PEP 8 Style Guide: [PEP 8 Docs](https://peps.python.org/pep-0008/)

## Tips and Best Practices
- Use GitHub Copilot as much as possible, even if you think it won't be of help (you might be surprised!)
- Understand the code before fixing, so that you can determine whether GitHub Copilot is suggesting the right changes.
- Regularly test the application after changes to catch new issues early.
- **If you're stuck, don't hesitate to seek assistance from peers or mentors.**

Good luck, and happy debugging!
