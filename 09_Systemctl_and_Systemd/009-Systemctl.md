# Systemctl and Its Relation to Packages and Applications

systemd is the default init system and service manager for most modern Linux distributions. It manages system startup, services, and system states, providing a unified way to control processes and resources.

## What is systemctl?
- `systemctl` is a command-line tool to control the systemd system and service manager.
- It is used to start, stop, enable, disable, and check the status of system services (daemons).

## How systemctl Relates to Packages and Applications
- Many software packages (like web servers, databases, etc.) install system services that are managed by systemd.
- When you install a package that provides a service (e.g., `nginx`, `apache2`, `mysql`), it usually creates a corresponding systemd service unit file (e.g., `nginx.service`).
- You use `systemctl` to manage these services:
  - Start a service: `sudo systemctl start nginx`
  - Stop a service: `sudo systemctl stop nginx`
  - Enable a service to start at boot: `sudo systemctl enable nginx`
  - Check status: `systemctl status nginx`
- Removing a package with a service (e.g., `sudo apt remove nginx`) will also remove its service unit file, so you can no longer manage it with `systemctl`.

## Example Workflow
1. Install a package that provides a service:
   ```bash
   sudo apt install nginx
   ```
2. Start and enable the service:
   ```bash
   sudo systemctl start nginx
   sudo systemctl enable nginx
   ```
3. Check the status:
   ```bash
   systemctl status nginx
   ```
4. Remove the package and its service:
   ```bash
   sudo apt remove nginx
   ```

## Summary
- `systemctl` manages services provided by installed packages.
- Not all packages have services, but those that do (like servers and background daemons) are controlled via systemd and `systemctl`.
- Always use your package manager to install/remove software, and `systemctl` to manage their running state.
