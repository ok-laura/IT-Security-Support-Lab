# Ticket 004: Firewall Configuration & System Updates

## Ticket Information
- **Ticket ID:** 004
- **Category:** System Security & Maintenance
- **Priority:** Medium
- **Status:** Resolved
- **Environment:** Ubuntu Linux (Oracle VirtualBox)

## Issue Description

During a simulated workstation security assessment, the Ubuntu firewall was found to be inactive.

Additionally, the operating system had pending software updates.

The objective was to improve system security by configuring the firewall, installing available updates, and verifying the changes.

## Initial Findings

- UFW version 0.36.2 was installed.
- The firewall was inactive.
- The UFW service was enabled.
- Ubuntu reported packages available for upgrading.

## Actions Taken

1. Investigated the existing firewall configuration.
2. Configured UFW to deny incoming connections by default.
3. Configured UFW to allow outgoing connections by default.
4. Enabled the firewall.
5. Verified the firewall configuration.
6. Refreshed Ubuntu's package information.
7. Identified available software updates.
8. Installed available package upgrades.
9. Checked for remaining updates.
10. Restarted Ubuntu to complete the update process.
11. Verified that the firewall remained active after restarting.
12. Confirmed that Ubuntu no longer required a reboot.

## Commands Used

```bash
sudo ufw version
sudo ufw status verbose
sudo systemctl is-enabled ufw
sudo ufw default deny incoming
sudo ufw default allow outgoing
sudo ufw enable
sudo apt update
apt list --upgradable
sudo apt upgrade
sudo reboot
```

## Resolution

Successfully enabled and configured the Ubuntu firewall.

The firewall now uses the following default policies:

- Incoming connections: Denied
- Outgoing connections: Allowed

Available system updates were installed.

After restarting Ubuntu, the firewall remained active, and the system no longer reported that a reboot was required.

## Security Considerations

Firewalls help reduce exposure to unauthorized network connections.

Regular software updates help address known vulnerabilities and improve system stability.

Verifying security configurations after restarting ensures that protective settings remain active.

## Evidence

Terminal recording:

`recordings/ticket-004-security-verification.cast`
