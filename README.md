# Hysteria Server Installer

This repository contains a Bash installer for deploying a Hysteria server on Ubuntu or Debian.

The script:
- downloads and installs the Hysteria binary
- writes a server config to `/etc/hysteria/config.json`
- creates a dedicated `hysteria` system user
- generates local TLS files under `/etc/hysteria`
- installs a `systemd` service
- configures persistent firewall rules with `iptables-persistent`
- prompts for `DOMAIN`, `OBFS`, and `PASSWORD` during interactive installs

## Requirements

- Ubuntu or Debian with `systemd`
- Root access, or a user with `sudo`
- A valid domain name if you plan to replace the default domain value

## Quick Start

```bash
wget https://raw.githubusercontent.com/stellawills/hysteria/main/hysteria.sh
chmod +x hysteria.sh
sudo ./hysteria.sh
```

## Configuration

During an interactive install, the script asks for:

- `DOMAIN`
- `OBFS`
- `PASSWORD`

If you press Enter at the password prompt on a fresh install, the installer generates a random password and prints it at the end.

For non-interactive runs, you can still predefine values through environment variables before running the script.

`PROTOCOL` and `UDP_PORT` still come from the values defined at the top of `hysteria.sh` unless you override them through the environment.

The active server config is written to:

```text
/etc/hysteria/config.json
```

## Service Management

```bash
sudo systemctl status hysteria-server.service
sudo systemctl restart hysteria-server.service
sudo systemctl stop hysteria-server.service
```

## Notes

- The current script generates local TLS materials with `openssl`.
- Firewall rules are saved to `/etc/iptables/rules.v4` and `/etc/iptables/rules.v6`.
- The installer is currently built around the package flow used on Ubuntu and Debian.

## Remove

```bash
sudo ./hysteria.sh --remove
```

## License

MIT
