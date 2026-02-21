# Hysteria Install Script

A simple installer script to set up **Hysteria** — a high-performance, censorship-resistant proxy/relay tool — on your Linux server.

Hysteria uses a custom UDP/QUIC-based protocol to deliver fast and reliable connectivity even on unreliable or lossy networks, with options for SOCKS5/HTTP proxying, TCP/UDP forwarding, and more.

---

## 🛠️ Install

To install Hysteria using this script, run:

```
wget https://raw.githubusercontent.com/stellawills/hysteria/refs/heads/main/hysteria.sh
chmod +x hysteria.sh
./hysteria.sh
```

This will:

* Download the install script to your server
* Make it executable
* Run the script to install or update Hysteria

---

## 📦 What This Script Does

This installer script aims to:

✅ Detect your Linux distribution
✅ Install necessary dependencies (bash, curl, etc.)
✅ Download and install the latest Hysteria release
✅ Set up Hysteria as a system service (if supported)
✅ Provide easy remove/upgrade options

---

## 📌 Requirements

Before running the script, make sure:

* You are on a **Linux server** with `bash` and network access
* You have **superuser (root) permissions**
* (Optional) You already have a domain and certificate if planning to use HTTPS with a real domain

*Hysteria itself does not have strict OS requirements, but it works best on common distros like Ubuntu, Debian, CentOS, Rocky, etc.* ([v2.hysteria.network][1])

---

## 📘 About Hysteria

Hysteria is a flexible proxy and tunnelling tool designed for performance and censorship resistance. Key features include: ([GitHub][2])

* ⚡ **Fast performance** with QUIC-based transport
* 🧠 **Censorship resistance** (masquerades as HTTP/3)
* 🌍 Supports SOCKS5, HTTP proxy, TCP/UDP forwarding
* 🔧 Cross-platform support for many OS and architectures
* 🔐 Optional authentication & traffic control

For more details and official docs, visit the upstream project: [https://github.com/apernet/hysteria](https://github.com/apernet/hysteria)

---

## 🧪 Usage

After installation, your server will be ready to run Hysteria.
You can manage Hysteria with:

```bash
sudo systemctl start hysteria-server
sudo systemctl status hysteria-server
sudo systemctl stop hysteria-server
```

Configuration files are typically located at:

```
/etc/hysteria/config.yaml
```

You should edit this file to set your domain, password, ports, authentication type, and any masquerade behaviour you want.

---

## 🚀 Contributing

If you find issues or want to improve this script:

1. Fork this repo
2. Make your changes
3. Submit a pull request

---

## ⭐ Thanks

If this script and Hysteria have helped you, please consider ⭐ the repo or contributing upstream!

---

## 📝 License

MIT License — feel free to use and modify.



---
