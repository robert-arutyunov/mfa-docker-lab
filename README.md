# MFA Docker Lab

A containerized lab project to learn and demonstrate multi-factor authentication (MFA) concepts using Keycloak (TOTP) and Docker Compose.

## What this lab includes
- Keycloak + Postgres running in Docker
- Realm export committed to the repo for repeatable setup
- Auto-import of the realm on startup

## Quick start (Windows PowerShell)
1. Copy the example env file:
   ```powershell
   copy .env.example .env
