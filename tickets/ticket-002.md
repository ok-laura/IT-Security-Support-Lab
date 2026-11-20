# Ticket 002: File Permissions & Access Control

## Ticket Information
- Ticket ID: 002
- Category: Access Management
- Priority: Medium
- Status: Resolved
- Environment: Ubuntu Linux (VirtualBox)

## Issue Description
An employee, Amy, requires access to a restricted
company directory. Access must be granted securely
without providing unnecessary admin privileges.

## Actions Taken
1. Created a company directory under /srv.
2. Restricted directory access to the root user.
3. Tested unauthorized access using Amy's account.
4. Confirmed that access was denied.
5. Added Amy to the company_staff security group.
6. Assigned group ownership of the directory.
7. Configured permissions to allow authorized access.
8. Verified Amy could access the directory.
9. Confirmed Amy did not have administrator privileges.

## Commands Used
sudo mkdir -p /srv/company_files
sudo chmod 700 /srv/company_files
sudo -u amy ls /srv/company_files
sudo usermod -aG company_staff amy
sudo chown root:company_staff /srv/company_files
sudo chmod 770 /srv/company_files
groups amy
ls -ld /srv/company_files
sudo -l -U amy

## Resolution
Successfully configured group-based access control.

Amy can now access the company directory through
membership in the company_staff group without
receiving administrator privileges.

## Security Considerations
Applied the principle of least privilege by restricting
directory access to authorized users.

Used Linux group membership to manage access
without granting unnecessary system privileges.

## Evidence
- Unauthorized access recording:
  recordings/ticket-002-access-control.cast

- Authorized access recording:
  recordings/ticket-002-authorized-access.cast
