<img src=https://github.com/user-attachments/assets/b0b2b2d4-c2ed-47b6-b59c-9da1d87514c6>
<br />
<br />

<h1>Group Policy & Managing Accounts</h1>

This section introduces Group Policy to enforce account lockout policies and demonstrates account lifecycle management, including locking, unlocking, enabling, disabling, and observing logs.<br />
<br />
<br />

<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines)
- Remote Desktop
- Active Directory Domain Services
- PowerShell
<br />
<br />

<h2>Operating Systems Used </h2>

- Windows Server 2022
- Windows 10 (21H2)
<br />
<br />

<h2>Walkthrough Steps</h2>

1. Set Up Account Lockout Policy:
  - On DC-1, open Group Policy Management Console (GPMC).
  - Create a new Group Policy Object (GPO) for account lockout with these settings:
    - Lockout after 5 failed attempts.
    - Lockout duration: 30 minutes.
    - Reset counter after 15 minutes.
  - Link the GPO to the relevant OU or domain and update Group Policy (gpupdate /force).
<br />
<br />

2. Test Account Lockout:
  - Log into Client-1 and attempt 6 incorrect logins for a user. Verify the account is locked in ADUC.
<br />
<br />

3. Unlock Accounts:
  - In ADUC, unlock the user account and reset the password.
<br />
<br />

4. Enable/Disable Accounts:
  - Disable the same account in ADUC and observe login errors from Client-1.
  - Re-enable the account and verify login functionality.
<br />
<br />

5. Observe Logs:
  - Review event logs on both DC-1 and Client-1 to understand account lockout and login activity.
<br />
<br />
