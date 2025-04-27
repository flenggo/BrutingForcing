
# PIN Brute-Force Script

## Project Overview

This Python script is designed to perform a brute-force attack against a server that verifies PIN codes. The goal of the script is to guess the correct PIN (from 000 to 999) by systematically trying all possible combinations.

The script simulates a brute-force attack by sending HTTP POST requests with PIN codes and analyzing the server's response. If the server responds with an indication of a valid PIN (e.g., "Access Granted"), the script terminates and outputs the correct PIN.

## Solution Process

### 1. Initial Setup
   - I set up the Python environment and ensured that all necessary modules (e.g., `socket`, `time`) were available.
   - The IP address (`HOST`) and port (`PORT`) of the server were defined as constants at the top of the script. This made it easy to configure the target server.

### 2. Brute-Force Logic
   - The script uses a loop to try all PIN combinations, from 000 to 999.
   - For each PIN, a HTTP POST request is crafted using the `create_request()` function. This request contains the PIN as part of the body.
   - The script then sends this request to the server using the `send_request()` function, which handles the socket connection.
   
### 3. Server Response Analysis
   - The server’s response is analyzed using the `check_response()` function. If the server responds with a specific string (e.g., "Access Granted"), the correct PIN is found, and the script terminates.

### 4. Error Handling
   - Timeouts and socket errors are handled to prevent the script from crashing when issues arise (e.g., connection timeouts or server unavailability).
   - A delay (`DELAY`) is introduced between each request to avoid overwhelming the server or triggering anti-bot defenses.

## How to Run

### 1. Clone the Repository
   If you haven't already, clone the repository to your local machine using:

   ```bash
   git clone https://github.com/flenggo/BrutingForcing
   ```

### 2. Install Python
   Ensure you have Python 3.x installed. You can check your version with:

   ```bash
   python --version
   ```

   If Python is not installed, download and install it from [python.org](https://www.python.org/downloads/).

### 3. Running the Script
   Navigate to the project directory and run the script:

   ```bash
   python pin_bruteforce.py
   ```

   The script will attempt to brute-force the PIN by sending HTTP requests to the specified server. It will output the status for each PIN attempt and stop once the correct PIN is found.

### 4. Modifying Configuration
   - You can modify the `HOST` and `PORT` variables in the script to point to your target server.
   - Adjust the `DELAY` constant to change the time between attempts.

## Files and Notes

### Main Files:
- **pin_bruteforce.py**: The main Python script that performs the brute-force attack, sends requests, and checks the server responses.

### Additional Notes:
- **Security Considerations**: Always obtain explicit permission before performing any brute-force or penetration testing on a server. Unauthorized access attempts can lead to legal issues.
- **Rate Limiting and Anti-Bot Measures**: This script is designed for educational purposes. In a real-world scenario, servers implement rate-limiting and CAPTCHA systems to prevent brute-force attacks.

## Lessons Learned

1. **Brute-Force Mechanics**: This project helped me understand the mechanics of brute-forcing and how it can be prevented with the right security measures.

## Improving Security

If I were tasked with securing a system against brute-force attacks, I would:
- Implement **rate-limiting** to prevent excessive login attempts.
- Change the password format to a 4 to 6 or a password using combinations of string, symbols, and intergers Project Overview
This Python script is designed to perform a brute-force attack against a server that verifies PIN codes. The goal of the script is to guess the correct PIN (from 000 to 999) by systematically trying all possible combinations.

The script simulates a brute-force attack by sending HTTP POST requests with PIN codes and analyzing the server's response. If the server responds with an indication of a valid PIN (e.g., "Access Granted"), the script terminates and outputs the correct PIN.

