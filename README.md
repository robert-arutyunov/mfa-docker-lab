# MFA Docker Lab

A containerized lab project to learn and demonstrate multi-factor authentication (MFA) concepts using Keycloak (TOTP) and Docker Compose.

> This is a local Docker lab. To run it, you’ll need Docker Desktop (or Docker Engine) on your machine.

## What this lab includes
- Keycloak + Postgres running in Docker
- Realm export committed to the repo for repeatable setup
- Auto-import of the realm on startup



## Quick start (Windows PowerShell)
1.  Get the project:
    ```powershell
    git clone https://github.com/robert-arutyunov/mfa-docker-lab.git
    cd mfa-docker-lab
    ```
2.  Create your local `.env` file:
   ```powershell
   copy .env.example .env
   notepad .env
   ```
   Replace the `change-me` values, save, and close Notepad.

3. Start the lab (powershell): 
    ```powershell
    docker compose up -d
    ```
4. Open Keycloak:
   - http://localhost:8080

To stop the lab:
```powershell
docker compose down
```

## Verify MFA (TOTP) is enforced
1. Log into the Keycloak Admin Console:
   - http://localhost:8080
2. Select the `mfa-lab` realm.
3. Create a user (or use an existing one) and set a password.
4. Add required action `Configure OTP` to the user.
5. In a private/incognito browser window, visit:
   - http://localhost:8080/realms/mfa-lab/account
6. Log in as that user and complete the OTP enrollment (scan the QR code in an authenticator app).
7. Log out and log in again — you should be prompted for the OTP code.

## Security notes
- `.env` is intentionally ignored by Git to avoid committing passwords/secrets.
- The values in `.env.example` are placeholders—change them before running.
- This is a learning lab and uses Keycloak `start-dev` (not production hardening).
