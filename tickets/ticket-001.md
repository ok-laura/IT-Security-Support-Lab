# Ticket 001: New Employee Account Creation

## Ticket Information
- Ticket ID: 001
- Category: User Account Management
- Priority: Low
- Status: Resolved
- Environment: Ubuntu Linux (VirtualBox)

## Issue Description
A new employee named Amy, needs an account
to access company systems.

## Actions Taken
1. Created a new Linux user account using adduser.
2. Disabled password authentication during initial setup.
3. Verified the account using the id command.
4. Checked group memberships using groups.
5. Checked sudo permissions to confirm the account
   was not granted admin privileges.

## Commands Used
sudo adduser --disabled-password --gecos "" amy
id amy
groups amy
sudo -l -U amy

## Resolution
Successfully created Amy's account with standard
user permissions and no admin access.

## Security Considerations
Applied the principle of least privilege by ensuring
the employee account was not granted unnecessary
admin permissions.

## Evidence
Terminal recording: recordings/ticket-001-amy.cast
