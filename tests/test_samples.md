# Test Results

**Project:** EWB Phishing URL Awareness Checker  
**Author:** Ahmed Shakir  
**Python version:** 3.13.5 *(verify on your Windows computer)*  
**Operating system:** Windows *(confirm this matches your environment)*  
**Test date:** 2026-10-28 *(update if you run tests on another date)*

## Five Workbook Sample Tests

| # | Input URL | Expected result | Actual result | Pass/Fail |
|---|---|---|---|---|
| 1 | `https://www.example.com/login` | No listed warning signs; do not claim the URL is safe. | No listed warning signs found. This does NOT prove safety. | PASS* |
| 2 | `http://192.0.2.10/account` | Flag IP-address hostname and HTTP. | Uses an IP address instead of a familiar domain. Uses HTTP. HTTPS alone does not prove trust. | PASS* |
| 3 | `http://example.com@sample.invalid/login` | Flag the `@` symbol and HTTP. | Contains an @ symbol; inspect carefully. Uses HTTP. HTTPS alone does not prove trust. | PASS* |
| 4 | `https://a.b.c.d.e.example.invalid/path` | Flag many hostname segments/subdomains. | Contains many hostname segments/subdomains. | PASS* |
| 5 | `https://xn--example.invalid/` | Flag punycode-style hostname. | Contains a punycode-style hostname. | PASS* |

\* These are expected outputs from the initial project checks. Run every test on your Windows computer and replace each status with PASS or FAIL according to the output you personally observe.

## Additional Improvement Check: Malformed URL

| Input | Expected result | Actual result | Pass/Fail |
|---|---|---|---|
| `http://[bad` | Display a clear invalid-URL message rather than crashing. | This text is not a valid URL format. | PASS* |

\* Verify this by entering the malformed sample into your running program.

## Additional Improvement Checks

- **Repeat-check loop:** The program should accept multiple URLs without restarting and exit when the user enters `q`, `quit`, or `exit`. Verify this interactively.
- **Warning summary:** When warning signs are found, the program should display `REVIEW CAREFULLY` and the number of warning signs.
- **Safety reminder:** The program should remind the user never to enter passwords from unexpected links.

## Test Notes

This checker examines URL text only. It does not visit websites, query reputation services, or prove that a URL is safe or malicious. A result with no listed warning signs is not proof of safety.

Before submitting:
1. Run all five sample URLs on your Windows computer.
2. Run the malformed-URL check.
3. Confirm the Python version with `python --version`.
4. Make sure the operating system field says Windows if that matches your environment.
5. Replace each `PASS*` with PASS or FAIL based on the output you personally observed.
6. Save genuine screenshots of your own test runs in the project's `screenshots` folder.
