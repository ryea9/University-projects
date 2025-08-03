# Cryptography Projects

This section showcases practical projects completed for the Cryptography (41900) course. These projects provided hands-on experience with both foundational and modern cryptographic concepts, from securing web traffic with a Public Key Infrastructure (PKI) to deploying a private blockchain network.

---

## Summary of Skills & Tools

### Key Skills Learned
*   **Public Key Infrastructure (PKI):** Full lifecycle management, including creating a Root Certificate Authority (CA), generating key pairs, and issuing/signing X.509 digital certificates.
*   **Blockchain & Distributed Ledger Technology:** Deep understanding of blockchain fundamentals, including Proof-of-Work (PoW) consensus, genesis block configuration, and transaction validation.
*   **Cryptographic Protocols:** Practical implementation and analysis of protocols that secure modern communication, including TLS/SSL and SSH.
*   **Digital Wallets & Accounts:** Management of cryptographic keys for account creation, mining, and secure asset transfer on a blockchain.
*   **Command-Line Security Tools:** Proficiency with industry-standard CLI tools for cryptographic operations and network deployment.

### Tools Used
*   **OpenSSL:** For all PKI-related tasks, including key generation, Certificate Signing Request (CSR) creation, certificate signing, and running a test TLS server.
*   **Geth (Go Ethereum):** Used as the primary client for initializing and running a private Ethereum blockchain network.
*   **Ubuntu (Linux VM):** The operating environment for deploying servers, running clients, and executing all commands.
*   **Mozilla Firefox:** For verifying the TLS certificate chain of trust and confirming the secure connection to the web server.

---

## Projects

Below are summaries of the two major projects completed for this subject. Each project is contained in its own submodule within this directory. Clicking a link will take you to its dedicated repository.

### 1. Secure HTTPS Server (PKI) Project

This project involved building a complete Public Key Infrastructure from the ground up to secure a web server with TLS. Acting as my own self-managed Root Certificate Authority (CA), I issued and signed a valid X.509 certificate for a web server, demonstrating a full, practical understanding of the chain of trust that underpins modern internet security.

➡️ **[View the full project here](https://github.com/ryea9/Secure-https-server-pki)**

### 2. Private Ethereum Blockchain Project

This project involved deploying a private, custom Proof-of-Work Ethereum blockchain from scratch. This provided foundational experience in blockchain technology and decentralized systems. The process included creating a custom genesis block, generating and managing user accounts (wallets), initiating a miner to secure the network, and executing transactions between accounts on the private network.

➡️ **[View the full project here](https://github.com/ryea9/private-ethereum-blockchain)**
