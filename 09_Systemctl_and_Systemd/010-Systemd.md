# Systemd: The Modern Linux Init System

## What is systemd?
- systemd is the default init system and service manager for most modern Linux distributions (e.g., Ubuntu, Fedora, CentOS, Debian).
- It is responsible for booting the system, managing services (daemons), and handling system states.

## Key Features
- Parallel service startup for faster boot times
- Service dependency management
- Logging with `journald`
- Socket and device activation
- Resource control (cgroups)
- Timers (as a replacement for cron)

## Common systemd Components
- **systemctl**: Command-line tool to manage systemd services
- **journalctl**: View logs collected by systemd
- **unit files**: Configuration files describing services, sockets, targets, etc.

## Basic systemctl Commands
- Start a service:
  ```bash
  sudo systemctl start service_name
  ```
- Stop a service:
  ```bash
  sudo systemctl stop service_name
  ```
- Enable a service at boot:
  ```bash
  sudo systemctl enable service_name
  ```
- Check service status:
  ```bash
  systemctl status service_name
  ```
- List all services:
  ```bash
  systemctl list-units --type=service
  ```

## Example: Manage nginx Service
```bash
sudo systemctl start nginx
sudo systemctl enable nginx
systemctl status nginx
sudo systemctl stop nginx
```

## Viewing Logs
- Use `journalctl` to view logs:
  ```bash
  journalctl -u nginx
  journalctl -b    # Logs since last boot
  ```

## Summary
- systemd is a powerful and flexible init system.
- Use `systemctl` to manage services and `journalctl` to view logs.
- Understanding systemd is essential for Linux system administration.
