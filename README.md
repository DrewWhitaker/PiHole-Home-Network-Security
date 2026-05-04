# PiHole-Home-Network-Security
Network-wide ad blocker and DNS sinkhole deployed on Raspberry Pi 4B using Pi-hole to block ads, trackers, and malware across all home network devices.

# Pi-hole Home Network Security System
A network-wide DNS sinkhole deployed on a Raspberry Pi 4B to block ads, 
trackers, and malware domains across all devices on the home network.

## Hardware Used
- Raspberry Pi 4B (8GB RAM)
- MicroSD card with Raspberry Pi OS (64-bit)
- Spectrum home network

## What it Does
- Blocks ads, trackers, and malware at the DNS level before they reach any device
- Monitors and logs all DNS queries across the entire network in real time
- Protects every device on the network including phones, laptops, and smart TVs
- Runs 24/7 as a headless Linux server requiring no user interaction

## How it Works
Pi-hole acts as a DNS sinkhole. When any device on the network makes a DNS 
request, it goes through Pi-hole first. Pi-hole checks the requested domain 
against its blocklists — if the domain is a known ad network, tracker, or 
malware domain, Pi-hole blocks it before it ever reaches the device.

## Skills Demonstrated
- Linux server administration (Raspberry Pi OS)
- DNS configuration and network administration
- Network security and traffic analysis
- Hardware setup and configuration
- Headless server deployment

## Results
![Dashboard](screenshots/dashboard.png)
![Query Log](screenshots/querylog.png)
![Top Blocked Domains](screenshots/topblocked.png)

## Example Blocked Query Analysis
| Domain | Type | Reason Blocked |
|--------|------|----------------|
| ca.iadsdk.apple.com | Ad Network | Apple iAd advertising SDK tracking device behavior |
| doubleclick.net | Ad Network | Google's ad serving and tracking network |
| googlesyndication.com | Ad Network | Google AdSense ad delivery network |
| facebook.com/tr | Tracker | Facebook cross-site tracking pixel |
| google-analytics.com | Tracker | Google behavior tracking across websites |

## What the Query Log Shows
Every DNS request made by every device on the network is logged including:
- Which device made the request
- What domain was requested
- Whether it was blocked or allowed
- Exact timestamp of the request

This reveals how frequently devices phone home to ad networks and telemetry 
servers completely in the background without user knowledge.

## Technologies Used
- Raspberry Pi OS (Debian-based Linux)
- Pi-hole v6
- DNS (Domain Name System)
- Linux command line

## Future Improvements
- Set up PiVPN for VPN access when on public WiFi
- Add Unbound for recursive DNS resolution for enhanced privacy
- Expand blocklists to include additional malware and phishing domains
- Configure static IP reservation on router
