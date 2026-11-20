# Ticket 003: Failed Login Attempts & Security Logs

## Ticket Information
- **Ticket ID:** 003
- **Category:** Security Incident Investigation
- **Priority:** Medium
- **Status:** Resolved
- **Environment:** Ubuntu Linux (VirtualBox)

## Issue Description
An employee, Amy, reported difficulty logging into her account. An authentication failure was simulated to investigate how Ubuntu records unsuccessful login attempts.

## Actions Taken
1. Configured a password for Amy's account.
2. Simulated an unsuccessful login attempt using an incorrect password.
3. Examined Ubuntu's authentication logs.
4. Searched for authentication failure events.
5. Investigated authentication events associated with Amy's account.
6. Checked Amy's password status.
7. Recorded the investigation for documentation.

## Commands Used

```bash
sudo passwd amy
su - amy
sudo grep 'authentication failure' /var/log/auth.log | tail -n 5
sudo grep 'su:' /var/log/auth.log | grep 'amy' | tail -n 10
sudo passwd -S amy
```

## Investigation Findings
- An unsuccessful authentication attempt was generated during testing.
- Ubuntu's authentication logs recorded the failed login.
- Log entries were examined to identify the affected account and authentication activity.
- Amy's account was checked to verify its password status.

## Resolution
The investigation identified an unsuccessful authentication attempt associated with the simulated login test.

The account remained accessible using the correct password, indicating that the simulated failure was caused by incorrect credentials rather than a confirmed account restriction.

## Security Considerations
Authentication logs provide important evidence when investigating account access issues.

Repeated unsuccessful login attempts may indicate forgotten credentials, account misuse, or attempted unauthorized access.

Reviewing authentication events helps IT security personnel distinguish routine login problems from potentially suspicious activity.

## Evidence
- Authentication investigation recording:
  `recordings/ticket-003-login-investigation.cast`

## Lab Disclaimer
This ticket documents a simulated security investigation conducted in a controlled Ubuntu virtual machine.
