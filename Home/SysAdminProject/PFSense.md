# Pre-Reqs
* Two NICs (virtual)
* One WAN bound (hitting level 1 NAT)
* One Virtual internal NIC, binded to physical output NIC
* VM Server 
  * 4 vCPUs
  * 8G RAM (Overkill, probably will move it down to 4G when needed)
  * 70G Disk (Hella overkill, really need like 20G tops)
# Install
Install like normal using PFSense ISO
Bind NAT NIC to WAN interface
Bind Internal virt NIC to LAN interface
Hostname set to "pfSense"
Domain set to "virtnet.internal"

# Extra Packages
* Lightsquid
* Open-VM-Tools
* openvpn-client-export
  *  can be removed after VPN server is standing, just needed to bounce around the internal network
  *  also not required if this was on the same network as working computer
* snort
* squid

# Routing table notes

## Default Gateways

* GW_WAN(default) GATEWAY: 192.168.10.1 , Monitor: 192.168.10.1
* WAN_DHCP GaATEWAY: 192.168.l1.l , Monitor: 192.168.1.1

## WAN IP
Set statically via Layer 1 NAT router config
## LAN Config

IPV4 Range: 10.5.0.1/16

## DNS Resolver
* Enable
* Register DHCP leases in DNS Resolver: enabled
* Register DHCP static mappings in the DNS resolver: enabled

What this does: auto adds a DNS entry on the internal DNS router.  This allows things checking for their dns name to resolve to their proper IP address. (Namely Katello/Foreman and OpenVPN