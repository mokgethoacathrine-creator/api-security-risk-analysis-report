# API Security Risk Analysis Report

## Project Overview

This repository contains an API security risk assessment conducted as part of the **Future Interns Cybersecurity Program - Task 3 (API Security Risk Analysis)**.

The assessment follows the **OWASP API Security Top 10 (2023)** framework and demonstrates real-world API security auditing skills used by SaaS security consultants and AppSec engineers.

---

## Target API

| Property | Value |
|----------|-------|
| **Name** | JSONPlaceholder |
| **URL** | https://jsonplaceholder.typicode.com |
| **Type** | Public REST API (Read-only testing) |
| **Purpose** | Demo and testing API |

---

## Tools Used

| Tool | Purpose |
|------|---------|
| **Postman v11** | API request testing, response inspection |
| **Browser DevTools** | Header and error message analysis |

---

## Methodology

The assessment followed a structured approach based on OWASP API Security Top 10:

1. **Authentication Assessment** - Tested access without credentials
2. **Authorization Testing (BOLA/IDOR)** - ID manipulation to access other users' data
3. **Data Exposure Analysis** - Reviewed response fields for sensitive data leakage
4. **Input Validation** - Boundary testing with XSS and SQL injection payloads
5. **Rate Limiting** - Rapid sequential request testing
6. **Information Disclosure** - Header and error message inspection

---

## Key Findings Summary

| Severity | Count | Findings |
|----------|-------|----------|
| **CRITICAL** | 1 | No Authentication Required |
| **HIGH** | 2 | Broken Object Level Authorization, Excessive Data Exposure |
| **MEDIUM** | 2 | Missing Rate Limiting, No Input Validation |
| **LOW** | 1 | Information Disclosure via Headers |
| **TOTAL** | 6 | |

---

## Risk Heat Map

| Risk | Severity |
|------|----------|
| No Authentication | ████████████████████ CRITICAL |
| Broken Object Level Authorization | ████████████████████ HIGH |
| Excessive Data Exposure | ████████████████████ HIGH |
| Missing Rate Limiting | ████████████████████ MEDIUM |
| No Input Validation | ████████████████████ MEDIUM |
| Information Disclosure | ████████████████████ LOW |

---

## Report Contents

The full security assessment report includes:

- Executive Summary
- Scope & Methodology
- Risk Summary Table
- 6 Detailed Findings with:
  - Description of each vulnerability
  - Attack scenarios (business impact)
  - Remediation suggestions with code examples
- Remediation Roadmap (Priorities P0-P3)
- Test Cases Executed (Appendix)
- Conclusion

---

## Evidence

Screenshots of all test cases are available in the `/screenshots` directory:

| Screenshot | Finding |
|------------|---------|
| image1.jpeg | No authentication - GET /posts returns 200 OK |
| image2.jpeg | BOLA - Accessing /users/1 |
| image3.jpeg | BOLA - Accessing /users/2 |
| image4.jpeg | Excessive data exposure - Response fields (part 1) |
| image5.jpeg | Excessive data exposure - Response fields (part 2) |
| image6.jpeg | Missing rate limiting - Multiple rapid requests |
| image7.jpeg | No input validation - XSS payload accepted (201 Created) |

---

## Repository Structure
