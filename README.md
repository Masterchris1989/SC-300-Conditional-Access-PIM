<img width="3840" height="1677" alt="2026-08-14 18 Sign On-Microsoft Entra - Microsoft Entra admin center" src="https://github.com/user-attachments/assets/64d1c6e6-82ea-4b5d-8c1e-5cd6ab46ee8d" />
# SC-300 Project #2 — Conditional Access & Privileged Identity Management (PIM)

**Author:** Christian  
**Certification:** SC‑300 Identity & Access Administrator  
**Location:** Bronx, NY  
**Date Completed:** August 14, 2026  

---

## 📌 Project Summary

This project demonstrates the full implementation of **Conditional Access** and **Privileged Identity Management (PIM)** inside the Microsoft Entra admin center.  
The goal is to enforce secure authentication, least‑privilege access, and identity governance controls — all core SC‑300 exam objectives.

This repository contains:

- Full step‑by‑step admin center instructions  
- Conditional Access policy configurations  
- PIM role settings and activation workflow  
- Access reviews  
- Screenshots and logs  
- Identity governance documentation  
- JSON policy exports (optional)  

This is the complete write‑up for my **2nd SC‑300 project**.

---

# 1. Sign in

Sign in to **https://entra.microsoft.com** using an account with administrative privileges.

<img width="3840" height="1677" alt="2026-08-14 18 Sign On-Microsoft Entra - Microsoft Entra admin center" src="https://github.com/user-attachments/assets/d4e622ac-5432-4dbd-9759-b660793cca99" />


# 2. Conditional Access Configuration

## 2.1 Open Conditional Access

Navigate to:  
**Protection → Conditional Access**

---

## 2.2 Baseline MFA Policy

- **New policy**  
- Name: **Baseline – Require MFA for all users**  
- Users: **All users**  
- Exclude: Break‑glass account  
- Cloud apps: **All cloud apps**  
- Grant: **Require MFA**  
- Enable: **On**  
- Save

---

## 2.3 High‑Risk User Policy

- **New policy**  
- Name: **High‑risk users – Require password reset**  
- Users: All or test group  
- Conditions → User risk: **High**  
- Cloud apps: **All cloud apps**  
- Grant: **Require password change**  
- Enable: **On**  
- Save

---

## 2.4 Compliant Device Policy

- **New policy**  
- Name: **Require compliant device**  
- Users: Target users  
- Cloud apps: Key apps  
- Conditions → Device state: **Compliant**  
- Grant: **Require device to be marked compliant**  
- Enable: **On**  
- Save

---

## 2.5 App‑Specific Policy

- **New policy**  
- Name: **Admin apps – Strong access**  
- Users: Admins  
- Cloud apps:  
  - Microsoft Azure Management  
  - Microsoft 365 Admin Center  
- Grant:  
  - Require **MFA**  
  - Block **legacy authentication** (optional)  
- Enable: **On**  
- Save

---

## 2.6 Testing & Evidence

- Sign in with test accounts  
- Trigger MFA, password reset, or blocked access  
- Navigate to **Monitoring → Sign‑in logs**  
- Capture screenshots of:  
  - Policy configuration  
  - Sign‑in logs showing enforcement  

<img width="3840" height="1677" alt="2026-08-14-Conditional Access- Microsoft Entra admin center" src="https://github.com/user-attachments/assets/a50eaaef-785a-49e8-a771-688d81afb542" />

<img width="3840" height="1677" alt="2026-08-14 Conditional Access - Microsoft Entra admin center" src="https://github.com/user-attachments/assets/ab55da9d-cc86-4535-9930-f2be2f930966" />

# 3. Privileged Identity Management (PIM)

## 3.1 Open PIM

Navigate to:  
**Identity Governance → Privileged Identity Management**

---

## 3.2 Assign Eligible Roles

- Select **Microsoft Entra roles**  
- Choose a role (Security Administrator, Privileged Role Administrator, etc.)  
- Click **Add assignments**  
- Select your user  
- Set **Assignment type: Eligible**  
- Save

---

## 3.3 Configure Role Settings

- Go to **Settings**  
- Select the role  
- Configure:  
  - Require **MFA**  
  - Require **Justification**  
  - Set **Activation duration**  
  - Optional: Require **Approval**  
- Save

---

## 3.4 Activate the Role

- Go to **My roles**  
- Find the eligible role  
- Click **Activate**  
- Enter justification  
- Complete MFA  
- Select duration  
- Confirm activation  
- Capture screenshots

---

## 3.5 Configure PIM Alerts

- Go to **Settings → Alerts**  
- Enable alerts for:  
  - Permanent role assignments  
  - Activation failures  
  - Unusual activation patterns  
- Save

---

## 3.6 Create Access Review

- Navigate to **Identity Governance → Access reviews**  
- Click **+ New access review**  
- Scope: **Microsoft Entra roles**  
- Select privileged roles  
- Assign reviewers  
- Set duration  
- Start review  
- Complete review  
- Capture screenshots

<img width="3840" height="1677" alt="2026-08-14-Edit role setting - Global Administrator - Microsoft Entra admin center" src="https://github.com/user-attachments/assets/425b239f-b73b-4d90-acdd-07614fa4ec0b" />

# 4. Logs & Documentation

## 4.1 Sign‑in Logs

- Navigate to **Monitoring → Sign‑in logs**  
- Filter by test users  
- Export or screenshot entries

## 4.2 PIM Activity Logs

- Capture activation events  
- Capture access review actions

## 4.3 Governance Documentation

Document:

- Purpose of each Conditional Access policy  
- How PIM enforces least privilege  
- How MFA reduces risk  
- Summary of sign‑in logs  
- Summary of PIM activation logs  

[AuditLogs_2026-08-14.csv](https://github.com/user-attachments/files/31089205/AuditLogs_2026-08-14.csv)


# 5. GitHub Project Structure

