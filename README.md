# Pyrat Brute-Force Script

## Use Conditions:
### Designed specifically for pyrat CTF room - THM
### Designed for a TCP connections with interactive authentication, where the server: 
  1. prompts for a password following a username input
  2. responds with a specific fail message to wrong passwords.

## Parameter Input: 
Accepts command-line argument: 
```syntax
script <IP> <PORT> <USERNAME> <WORDLIST> <FAIL_RESPONSE> [-v]
```

## Mechanism of Action:
  1 Connects to a specified IP and port using Netcat.
  
  2 Sends the username to the server
  
  3 Iterates passwords from the provided wordlist
  
  4 Waits for the fail response before attempting to log in with _each password (including first one?, idk.. you check).
     If the fail response is detected, it sends the next password and logs the attempt
  
  5 Analyzes the server's response:
    If server responce doesnt match the fail response, it outputs the correct password and exits.

Output:
Minimal output by default(not so minimal); verbosity can be enabled with -v for detailed logging.
Uses color coding for clear differentiation between fail responses and successful logins.
