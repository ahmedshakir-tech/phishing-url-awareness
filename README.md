# EWB Phishing URL Awareness Checker

## Overview
Phishing uses deceptive messages or links to persuade people to reveal information such as passwords or OTPs. This beginner Python project checks URL text for six selected warning signs. It does not open the URL, connect to a website, or decide conclusively whether a link is safe.

## Features
- Detects an `@` symbol.
- Flags URLs longer than 100 characters.
- Flags IPv4-style IP-address hostnames.
- Flags hostnames with five or more dot-separated segments.
- Flags punycode-style hostnames containing `xn--`.
- Flags the HTTP scheme.
- Handles empty and malformed input.
- Repeats checks until the user enters `q`, `quit`, or `exit`.
- Prints a “REVIEW CAREFULLY” summary when warning signs are found.

## Requirements
Python 3.10 or later. No extra packages are required.

## How to Run
Windows: `python phishing_checker.py`
macOS/Linux: `python3 phishing_checker.py`

Enter a sample URL from the workbook. Type `q` to quit.

## Example Output
```text
EWB Phishing URL Awareness Checker
Text checks only - this program does not open URLs.

Enter a sample URL (or type q to quit): http://192.0.2.10/account

Result:
- Uses an IP address instead of a familiar domain.
- Uses HTTP. HTTPS alone does not prove trust.

REVIEW CAREFULLY: 2 warning sign(s) found.
Never enter passwords from unexpected links.
```

## Testing
See [`tests/test_samples.md`](tests/test_samples.md). Run the program on your own computer and verify the results before submission.

## Screenshots
Save genuine screenshots from your own computer as:
- `screenshots/sample_run.png`
- `screenshots/test_results.png`

## Improvements
1. **Loop with quit command:** inspect multiple strings without restarting.
2. **Malformed URL handling:** invalid input such as `http://[bad` returns a message instead of stopping with a parsing error.
3. **Review summary:** warning results include a count.

## Limitations
This is an educational tool that only checks selected URL-text patterns. It does not visit URLs, scan for malware, query reputation services, or prove that a URL is safe or malicious. “No listed warning signs found” does **not** mean a URL is safe.

## Ethical Use
Use workbook sample strings or harmless examples only. Do not collect credentials, send phishing messages, open suspicious links to test them, or scan websites without written authorisation. Never upload passwords, API keys, tokens, or private information to GitHub.

## Author
- Name: Ahmed Shakir
- Batch/Course: [Fill in your assigned batch/course]
- Internship: AI-Powered Cybersecurity Internship, EWB Courses
