# wgconfig
A simple bash script to output wireguard configurations with public and private key.

```bash
[vpnuser@mypc]~$ wgconfig

Enter values for any or all fields or none to generate keypair only

Filename (example client01) = client02
Address (example: 10.0.0.2/30) = 10.0.0.3/24
ListenPort (return for dynamic endpoint) =
DNS servers separated by comma (return for none) = 9.9.9.9
PresharedKey (return for none) =
Remote peer PublicKey = oqDuysTcgUDrFrUMZI75CXEzgg4/d0uTaOFbvr6QzjM=
AllowedIPs (separated by comma, 0.0.0.0/0 for default) = 0.0.0.0/0
Endpoint (hostname or IP address) = vpn.vpn.org
Endpoint listenport = 51820

### configuration saved as client02.conf

[vpnuser@mypc]~$ cat client02.conf

# Name = client02
[Interface]
PrivateKey = iN92rSS26TJqOfXsUmWOoRxYV2NgzKauu81Z0DsffGI=
# Publickey = NIQUfUiIbA/1Daw/SELmGoSHHBS+iPYTrcQ255ipS0U=
Address = 10.0.0.3/24
DNS = 9.9.9.9
# MTU = 1420

[Peer]
PublicKey = oqDuysTcgUDrFrUMZI75CXEzgg4/d0uTaOFbvr6QzjM=
AllowedIPs = 0.0.0.0/0
Endpoint = vpn.vpn.dev:51820
# PersistentKeepalive = 25
```

## Installation and usage

Clone the repo or copy the script.<br>
Make the script executable `chmod +x wgconfig`.<br>
Place it somewhere in your path `~/bin` `~/.local/bin` `/usr/local/bin`.<br>

There are no command line flags or options, just execute the script and follow the prompts.

## Requirements

- wireguard-tools
  - Linux (debian based)
    - `apt install wireguard-tools`
  - macOS Macports and Homebrew
    - `port install wireguard-tools`
    - `brew install wireguard-tools`
  - FreeBSD
    - `pkg install wireguard-tools`

For additional operating systems: [Wireguard Installation](https://www.wireguard.com/install/)

## Further Information

- [WireGuard](https://www.wireguard.com/)
- [Unofficial WireGuard Documentation](https://github.com/pirate/wireguard-docs)
