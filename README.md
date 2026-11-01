#  Nessus Vulnerability Assessment

## Task 3 – Vulnerability Assessment and Security Scanning

### 1. Project Overview

This project demonstrates a vulnerability assessment performed using **Tenable Nessus Essentials**. The objective of the assessment was to identify potential security weaknesses in a local system, analyze the detected vulnerabilities, and document appropriate remediation recommendations.

The assessment was conducted in a controlled local environment for educational and security-testing purposes.

---

## 2. Objectives

The primary objectives of this assessment were:

- To perform a vulnerability scan using Nessus Essentials.
- To identify security vulnerabilities present on the target system.
- To analyze the severity and technical details of detected vulnerabilities.
- To understand the potential security impact of the findings.
- To provide appropriate remediation recommendations.
- To document the assessment results in a structured security report.

---

## 3. Tool Used

**Vulnerability Scanner:** Tenable Nessus Essentials

**Scan Type:** Basic Vulnerability Scan

**Target:** Localhost

**Target IP:** `127.0.0.1`

---

## 4. Assessment Summary

| Severity | Number of Vulnerabilities |
|----------|----------------------------|
| Critical | 0 |
| High | 0 |
| Medium | 3 |
| Low | 0 |
| **Total** | **3** |

The scan identified **three Medium-severity SSL/TLS certificate-related vulnerabilities**.

---

## 5. Vulnerabilities Identified

### 5.1 SSL Certificate Cannot Be Trusted

**Severity:** Medium  
**CVSS:** 6.5

#### Description

The SSL certificate presented by the service could not be validated through a trusted certificate chain. This may occur when the certificate is self-signed, issued by an unrecognized Certificate Authority, or when required intermediate certificates are missing.

#### Potential Impact

An untrusted certificate can make it difficult for users or systems to verify the authenticity of the service and may increase the risk of man-in-the-middle attacks.

#### Recommendation

Replace the untrusted certificate with a valid certificate issued by a trusted Certificate Authority and ensure that the complete certificate chain is correctly configured.

---

### 5.2 SSL Self-Signed Certificate

**Severity:** Medium  
**CVSS:** 6.5

#### Description

The SSL certificate used by the detected service is self-signed and is not signed by a recognized Certificate Authority.

#### Potential Impact

Because the certificate is not trusted by default, users and systems cannot reliably verify the identity of the service.

#### Recommendation

Use a certificate issued by a trusted Certificate Authority. For internal testing environments, ensure that the organization's trusted certificate infrastructure is properly configured.

---

### 5.3 SSL Certificate with Wrong Hostname

**Severity:** Medium  
**CVSS:** 5.3

#### Description

The hostname associated with the service does not match the hostname specified in the SSL certificate.

The Nessus scan identified the certificate Common Name (CN) as **AnyDesk Client**, while the target system identities included localhost.

#### Potential Impact

A hostname mismatch can cause certificate validation failures and may make it difficult to verify that the certificate belongs to the intended service.

#### Recommendation

Configure the service with a certificate containing the correct hostname in the certificate's Common Name (CN) or Subject Alternative Name (SAN).

---

## 6. Severity Analysis

The assessment did not identify any Critical or High-severity vulnerabilities.

The three findings were classified as Medium severity and were related to SSL/TLS certificate configuration.

These findings should be reviewed and remediated to improve the security and trustworthiness of the affected service.

---

## 7. Remediation Recommendations

The following actions are recommended:

1. Replace self-signed certificates with certificates issued by a trusted Certificate Authority where appropriate.
2. Ensure that the complete SSL/TLS certificate chain is correctly configured.
3. Verify that the certificate hostname matches the target service hostname.
4. Remove or replace expired, invalid, or untrusted certificates.
5. Regularly review SSL/TLS configurations for security weaknesses.
6. Perform a follow-up Nessus scan after remediation to verify that the vulnerabilities have been resolved.

---

## 8. Assessment Evidence

The Nessus scan results were reviewed and documented using the following evidence:

- Nessus vulnerability summary
- Vulnerability severity results
- SSL Certificate Cannot Be Trusted finding
- SSL Self-Signed Certificate finding
- SSL Certificate with Wrong Hostname finding
- Vulnerability descriptions and remediation recommendations

Screenshots of the Nessus scan results can be included in this repository as supporting evidence.

---

## 9. Conclusion

The Nessus vulnerability assessment was successfully completed against the local system.

A total of **3 Medium-severity vulnerabilities** were identified, all related to SSL/TLS certificate configuration. No Critical, High, or Low severity vulnerabilities were detected during the assessment.

The identified issues can be addressed by using trusted certificates, maintaining a valid certificate chain, and ensuring that certificate hostnames correctly match the services they protect.

This assessment demonstrates the use of Nessus for vulnerability identification, severity analysis, security documentation, and remediation planning.

---

## 10. Disclaimer

This vulnerability assessment was performed only against a local system in a controlled environment for educational and authorized security-testing purposes.

No unauthorized systems or networks were targeted.
