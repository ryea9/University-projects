# System Security: Broken Access Control (IDOR) Attack Simulation

This project is a practical security assessment focusing on one of the most critical web application vulnerabilities: **Broken Access Control (BAC)**. As outlined in the **OWASP Top 10 (A01:2021)**, BAC flaws occur when restrictions on what authenticated users are allowed to do are not properly enforced.

This assessment was a collaborative project where my role focused on the offensive security aspect: planning and executing an attack to demonstrate the vulnerability. The defense and mitigation strategies were handled by my project partner.

The target for this assessment was **WebGoat**, a deliberately insecure web application designed for educational purposes. The primary tool used for the attack was **Burp Suite**.

---

## My Role: The Attacker

My responsibility was to simulate a real-world attack by exploiting an **Insecure Direct Object Reference (IDOR)** vulnerability—a common type of Broken Access Control. The goal was to authenticate as a low-privilege user and escalate access to view the private data of another user on the system.

The attack methodology was executed in five distinct phases:

1.  **Authentication and Reconnaissance:**
    *   Logged into the WebGoat application with the provided standard user credentials ("tom").
    *   Used Burp Suite's proxy to intercept the HTTP traffic generated while browsing the user profile page to understand how the application fetches user data.

2.  **Traffic Interception and Analysis:**
    *   Captured the GET request for the user's profile and sent it to **Burp Repeater**.
    *   Analyzed the server's response and discovered that it contained hidden fields not displayed on the web page, including a numeric `userId`.

3.  **Pattern Identification:**
    *   Identified that the application used a predictable RESTful pattern to access user profiles (e.g., `/WebGoat/IDOR/profile/{userId}`). This suggested that any user's profile could be accessed directly if their `userId` was known.

4.  **Automated Brute-Force Attack:**
    *   Sent the request to **Burp Intruder** and targeted the `userId` parameter in the URL.
    *   Configured a numeric payload in Intruder to rapidly test a range of `userId`s close to the original user's ID.

5.  **Exploitation and Data Exfiltration:**
    *   Monitored the Intruder attack results and identified a request that returned a different HTTP status code and response length, indicating a valid, active user ID.
    *   Examined the response for this request, successfully retrieving the private profile information of another user ("Buffalo Bill"), confirming the IDOR vulnerability.

---

## Key Skills Learned

This project provided hands-on experience and solidified my skills in several key areas of offensive security:

*   **Vulnerability Analysis:** Deepened my understanding of the OWASP Top 10, specifically Broken Access Control and Insecure Direct Object References.
*   **Penetration Testing Tools:** Gained practical proficiency with industry-standard tools like **Burp Suite**, utilizing its Proxy, Repeater, and Intruder modules for a real-world scenario.
*   **HTTP Traffic Manipulation:** Mastered the ability to intercept, analyze, and modify HTTP requests to probe for weaknesses in a web application.
*   **Ethical Hacking Methodology:** Applied a structured attack methodology, from initial reconnaissance and analysis to final exploitation and reporting.
*   **Automation of Attacks:** Learned to use Burp Intruder to automate discovery and brute-force attacks, a critical skill for efficient security testing.

---

## Full Project Report

The complete project report, which includes both the detailed attack walkthrough and the proposed defense mechanisms, can be viewed by clicking the link below.

➡️ **[View the full project report here](./System%20security-%20IDOR-BAC.pdf)**
