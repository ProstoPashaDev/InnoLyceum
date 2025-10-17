# Secrets Management

Our project handles sensitive information such as passwords, API keys, and configuration secrets with strong security measures to prevent accidental exposure.

- Secrets are stored primarily in a `.env` file containing sensitive configuration for services like PostgreSQL and Redis.
- Before pushing code to the repository, the `.env` file is encrypted using **SOPS** with an asymmetric encryption algorithm to ensure confidentiality.
- The **private decryption key** is securely stored in **1Password**, a trusted secrets and password management tool.
- When developers work locally, they decrypt the `.env` file using **SOPS** and the private key retrieved from **1Password**.
- This workflow guarantees that encrypted secrets are safe in version control while allowing secure local access for development.
