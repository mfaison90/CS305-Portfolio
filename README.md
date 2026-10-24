# CS 305 Portfolio: Artemis Financial Secure Software Project

## 1. Client Summary

**Briefly summarize your client, Artemis Financial, and its software requirements. Who was the client? What issue did the company want you to address?**

Artemis Financial is a consulting firm that builds personalized financial plans for its clients. The company wanted to modernize its public web application while better protecting sensitive customer information. To meet that goal, Artemis asked Global Rain to add secure communication and a checksum verification process to help ensure data integrity in the application.

## 2. Strengths and the Value of Secure Coding

**What did you do well when you found your client's software security vulnerabilities? Why is it important to code securely? What value does software security add to a company's overall well-being?**

What I did well was break the project into smaller tasks that matched what Artemis asked for. Since the client needed both secure communication and checksum verification, I handled each one separately: choosing the cipher, generating a certificate, adding the checksum functionality, and configuring the server to use HTTPS. I tested each change before moving on, which helped me catch problems early.

Secure coding matters because a small oversight, such as a password stored in a configuration file, can expose sensitive financial data. Building security in from the start costs far less than responding to a breach after it happens. Strong security also protects the trust clients place in the company.

## 3. Challenges and Helpful Resources

**Which part of the vulnerability assessment was challenging or helpful to you?**

The hardest part at first was pinning down exactly what Artemis Financial expected. The project guidelines helped the most because they spelled out the requirements, including the checksum step and secure communication. That gave me a clear starting point and a plan for implementation.

## 4. Layers of Security

**How did you increase layers of security? In the future, what would you use to assess vulnerabilities and decide which mitigation techniques to use?**

I added layers of security by starting with strong, current standards. I chose AES-256 for encryption and SHA-256 for checksums, since both are widely trusted. I then added a checksum route so the data can be checked for changes. I ran the OWASP Dependency-Check scanner to find known vulnerabilities in the project's libraries, and I reviewed the code by hand for syntax, logic, and security problems.

In future projects, I would use OWASP Dependency-Check to find vulnerabilities and NIST standards to choose encryption methods and mitigation techniques.

## 5. Verifying Functionality and Security

**How did you make certain the code and software application were functional and secure? After refactoring the code, how did you check to see whether you introduced new vulnerabilities?**

I checked that the application ran by starting it in Eclipse and confirming in the console that it was running on port 8443 without errors. I then opened the HTTPS checksum page in Chrome and confirmed the checksum appeared. After the changes, I ran the OWASP Dependency-Check scan. It reported 292 issues, all in existing framework libraries. Since I didn't add any new libraries, the scan showed no new dependency-related vulnerabilities from my code. I also reviewed the code by hand and fixed a paste error that broke the build.

## 6. Tools and Practices

**What resources, tools, or coding practices did you use that might be helpful in future assignments or tasks?**

The tools and practices I'd use again include Eclipse with Maven, Spring Boot's HTTPS settings, Java Keytool, OWASP Dependency-Check, and environment variables to keep passwords out of project files. NIST publications were a reliable source of security guidance, and the course guidelines and GitHub portfolio tutorial helped with the requirements and submission.

## 7. Portfolio Artifacts

**Employers sometimes ask for examples of work that you have successfully completed to show your skills, knowledge, and experience. What might you show future employers from this assignment?**

I would show the Practices for Secure Software Report, which explains how I assessed the client's needs and chose security standards. I'd also include the HTTPS setup, the checksum route, the dependency scan results, and the Algorithm Cipher section. Together they show that I can assess requirements, explain encryption choices, and configure a secure application.
