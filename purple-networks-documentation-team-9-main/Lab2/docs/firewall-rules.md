# Firewall Rules & NAT Table - Team 09

## NAT Port Forwarding
| Interface | Protocol | Source | Destination | Port | Redirect Target |
| :--- | :--- | :--- | :--- | :--- | :--- |
| **WAN** | TCP | Any | WAN address | 80 | 10.31.9.135:80 |

## Interface Rules
| Interface | Action | Source | Destination | Port | Purpose |
| :--- | :--- | :--- | :--- | :--- | :--- |
| **WAN** | Pass | Any | 10.31.9.135 | 80 | Allow HTTP traffic to Web Server |
| **WAN** | Block | Any | Any | 22 | Prevent external SSH access |
| **LAN**| Pass | Blue net | 10.31.9.135 | 22 | Internal SSH management |
| **LAN**| Pass | Blue net | 10.31.9.75 | 445 | Internal Samba file sharing |
| **redlan** | Block | redlan net | 10.31.9.75 | Any | Block attacker access to File Server |
| **redlan** | Pass | redlan net | Any | Any | Allow attacker testing traffic |

*Note* - LAN is our bluelan

