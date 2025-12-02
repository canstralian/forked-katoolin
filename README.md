![katoolin](https://cloud.githubusercontent.com/assets/8742190/9415562/83397aae-4840-11e5-8f72-28dfffcc70a9.png)

# katoolin (Forked)

Automatically install Kali Linux security tools on Ubuntu/Debian-based systems.

This is a maintained fork of the original [katoolin](https://github.com/LionSec/katoolin) project by LionSec.

## Features

- Add and manage Kali Linux repositories
- Install 300+ security tools organized by category
- Remove Kali Linux repositories safely
- Interactive menu-based interface
- Tool search functionality

## Categories

| Category | Description |
|----------|-------------|
| Information Gathering | Reconnaissance and OSINT tools |
| Vulnerability Analysis | Vulnerability scanners and assessment |
| Wireless Attacks | WiFi and Bluetooth security tools |
| Web Applications | Web app security testing |
| Sniffing & Spoofing | Network traffic analysis |
| Maintaining Access | Persistence and backdoor tools |
| Reporting Tools | Documentation and reporting |
| Exploitation Tools | Exploit frameworks and tools |
| Forensics Tools | Digital forensics and analysis |
| Stress Testing | Load and stress testing tools |
| Password Attacks | Password cracking and auditing |
| Reverse Engineering | Binary analysis and debugging |
| Hardware Hacking | Hardware security testing |
| Extra | Additional tools and meta-packages |

## Requirements

- Python 2.7+ (Python 3.x recommended)
- Ubuntu, Debian, or compatible Linux distribution
- Root/sudo privileges

## Installation

```bash
# Clone the repository
git clone https://github.com/canstralian/forked-katoolin.git

# Copy to system path
sudo cp forked-katoolin/katoolin.py /usr/bin/katoolin

# Make executable
sudo chmod +x /usr/bin/katoolin

# Run katoolin
sudo katoolin
```

## Usage

### Basic Commands

| Command | Description |
|---------|-------------|
| `<number>` | Install the tool with that number |
| `0` or `99` | Install all tools in the category |
| `back` | Return to previous menu |
| `gohome` | Return to main menu |
| `show` | Show available tools |
| `help` | Display help information |

### Example Session

```
1) View Categories
2) Update Katoolin
3) Help
4) Exit

: katoolin > 1
:: Categories:

 1) Information Gathering  2) Vulnerability Analysis
 3) Wireless Attacks       4) Web Applications
...
```

## ⚠️ Warning

Before updating your system, **always remove all Kali Linux repositories** to avoid package conflicts:

```bash
sudo rm /etc/apt/sources.list.d/katoolin.list
sudo apt update
```

## Roadmap & New Features

See [FEATURES.md](FEATURES.md) for:
- Proposed new features
- Repurposing ideas
- Technical modernization plans
- Implementation roadmap

## Contributing

We welcome contributions! See [CONTRIBUTING.md](CONTRIBUTING.md) for:
- How to report bugs
- How to suggest features
- Development setup
- Coding standards
- Pull request process

## Related Projects

- [katoolin3](https://github.com/s-h-3-l-l/katoolin3) - Python 3 rewrite
- [Kali Linux](https://www.kali.org/) - Official Kali distribution

## License

This project is licensed under the GNU General Public License v2.0 - see [LICENCE](LICENCE) for details.

## Acknowledgments

- Original project by [LionSec](https://github.com/LionSec/katoolin)
- Kali Linux team for maintaining the security tools repository

## Disclaimer

This tool is intended for legal security testing and educational purposes only. Users are responsible for ensuring they have proper authorization before using any security tools. Misuse of these tools may violate local, state, or federal laws.
