# Secure Software Development Project: Artemis Financial (CS-305)

## Project Summary

This project was developed for a client, **Artemis Financial**, a financial consulting firm specializing in savings, retirement, investment, and insurance planning. Artemis Financial wanted to modernize their operations by securing their web application and client data. Specifically, they requested the implementation of secure communication protocols and data integrity verification mechanisms, such as checksums, to ensure that data transfers are protected from tampering.

## Key Actions and Reflections

**What was the issue, and what did Artemis Financial need?**  
The company was concerned about vulnerabilities in its existing software and requested enhancements to improve data security. I was tasked with refactoring the application to support HTTPS, generate and implement secure hash functions for checksum verification, and use digital certificates to secure communication channels.

**What did I do well when addressing security vulnerabilities?**  
I successfully identified the lack of encrypted communications and added HTTPS by generating a self-signed certificate using Java Keytool and configuring Spring Boot to use it. I also implemented a SHA-256 cryptographic hash algorithm to verify data integrity. Secure coding is essential because it protects sensitive information from interception, forgery, or tampering — ultimately strengthening the company’s trustworthiness and compliance with industry standards.

**What challenges or insights did I gain from the vulnerability assessment?**  
A challenge I encountered was Spring Boot’s behavior when misconfigured — such as silent shutdowns due to incorrect keystore paths or missing controller mappings. This helped me better understand how application context and runtime dependencies work in Spring Boot. It also emphasized the importance of carefully testing SSL configurations and keystore loading.

**How did I increase layers of security, and how would I assess vulnerabilities in the future?**  
I added multiple layers of security: HTTPS communication, certificate-based encryption, SHA-256 hashing, and checksum validation. In the future, I would use tools like OWASP Dependency-Check and SonarQube to identify vulnerabilities earlier and apply secure design patterns like input validation, access control, and principle of least privilege.

**How did I ensure the application remained functional and secure?**  
After refactoring, I tested the `/hash` endpoint over HTTPS and validated the checksum output manually in the browser. I verified the self-signed certificate was working by exporting a `.cer` file and reviewing the certificate details. I also used static analysis (OWASP Dependency-Check) to confirm that no additional vulnerabilities were introduced during the process.

**What tools or practices helped, and how will they be useful in future work?**  
Key tools included:
- Java Keytool for generating and managing SSL certificates
- Spring Boot for creating RESTful services and managing secure properties
- OWASP Dependency-Check for static vulnerability testing
- Maven for building and managing dependencies

Practices like separating configuration from logic, maintaining proper keystore locations, and testing in small increments helped reduce errors and improved maintainability.

**What can I showcase to future employers from this project?**  
This project demonstrates my ability to secure a live Java application with HTTPS, implement cryptographic integrity checks (SHA-256), and apply industry tools for vulnerability detection. It shows I can handle real-world security tasks in Java-based enterprise applications — including certificate management, secure configuration, and RESTful endpoint development.

