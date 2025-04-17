# 🔐 Security Vulnerability Reports

This repository contains detailed reports of real-world vulnerabilities discovered through responsible disclosure efforts. Each report includes a professional write-up outlining the vulnerability type, impact, affected URLs, and remediation recommendations.

---

## 📌 Table of Contents

1. [Exposure of Sensitive Information to Unauthorized Actors](#1-exposure-of-sensitive-information-to-unauthorized-actors)
2. [Web Cache Poisoning](#2-web-cache-poisoning)
3. [No Rate Limiting in Password Reset Functionality](#3-no-rate-limiting-in-password-reset-functionality)

---

## 1. Exposure of Sensitive Information to Unauthorized Actors

- **Type**: Information Disclosure  
- **Affected Domain**: Public APIs on `api.gatehub.net`  
- **Summary**: Sensitive transactional data is publicly accessible without authentication via exposed endpoints. Attackers can enumerate payment information by sending crafted requests to specific API URLs.

- **Impact**:
  - Exposure of financial transaction data
  - Privacy violation of users
  - Potential regulatory non-compliance

- **Proof of Concept (PoC)**:  
  [POC Video or Screenshot](#) *(Insert link to video or media)*

- **Recommendation**:
  - Implement strict access control to protect sensitive endpoints
  - Authenticate API requests and validate permissions
  - Apply data minimization and masking techniques

---

## 2. Web Cache Poisoning

- **Type**: Web Cache Poisoning  
- **Affected Domain**: `https://www.nwbbank.com`  
- **Summary**: Improper handling of HTTP headers allows cache manipulation. This may lead to malicious redirects or the serving of altered content from cache, impacting user security.

- **Impact**:
  - Redirection to attacker-controlled domains
  - Trust degradation and potential phishing attacks
  - Possible malware distribution via poisoned cache entries

- **Proof of Concept (PoC)**:  
  [POC Video or Screenshot](#) *(Insert link to video or media)*

- **Recommendation**:
  - Sanitize and validate user-controlled headers
  - Configure cache policies properly using `Vary` and `Cache-Control`
  - Avoid caching responses that depend on header values like `Host`

---

## 3. No Rate Limiting in Password Reset Functionality

- **Type**: Rate Limiting Misconfiguration  
- **Affected Domain**: `https://app.achievable.me/auth/forgot-password`  
- **Summary**: Lack of rate limiting allows attackers to send a flood of password reset emails, potentially overwhelming user inboxes and creating a nuisance.

- **Impact**:
  - Email flooding (DoS vector)
  - Annoyance and service disruption for users
  - Opens a window for phishing/social engineering

- **Proof of Concept (PoC)**:  
  [POC Video or Screenshot](#) *(Insert link to video or media)*

- **Recommendation**:
  - Implement request throttling and IP-based rate limits
  - Add CAPTCHA to password reset forms
  - Alert users after repeated reset requests

---

## 📝 Disclosure Notes

All vulnerabilities were responsibly disclosed to the respective organizations. This repository is maintained for educational and demonstration purposes only. Sensitive information has been redacted or anonymized where appropriate.

---

