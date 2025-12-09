# Setup-for-Home-Security-Lab

**OVERVIEW**

This repo tracks the setup of a lightweight Ubuntu-based analysis VM meant for hands-on security practice. Stage 1 covers the initial system prep: updates, essential packages, and baseline tools.

**Table of Contents**

1. Project Goals
2. Prerequisites
3. Stage 1 — Base System Setup
4. Stage 2 — Networking & Visibility Layer 
5. Commands
6. Next Steps
7. License

**Project Goals**

 - Build a stable, minimal VM for SOC / malware / security analysis tasks.
 - Keep the setup lightweight and easy to rebuild.
 - Document each stage clearly for repeatability.

**Prerequisites**

 - 8 GB RAM - This is entirely based on my system specs. 
 - At least 37 GB free disk. I kept the allocated disk at 20 GB due to the space available on disk C.
 - VirtualBox.
 - Ubuntu v24.04 LTS ISO image.

**Stage 1 — Base System Setup**

I began by doing a system prep and system updates to make sue the base OS isn't outdated.
  **command: sudo apt update && sudo apt upgrade -y** 

I also carried the installation of the following foundational tools, using this **command: sudo apt install -y vim net-tools curl wget git htop ufw**

 - vim — A lightweight, in‑terminal text editor. Perfect for quickly editing configuration files without leaving the shell. 
 - net-tools — A package that provides classic networking commands like ifconfig, netstat, and route. While newer tools like ip are common, net-tools is still useful for troubleshooting and legacy scripts.
 - curl — A command‑line tool used to fetch files form the internet.
 - wget — Similar to curl, but designed for downloading files and entire directories.
 - git — This is a distributed version control system. It is used to store and track changes to configuration files, scripts, and documentation. This makes it easy to roll back changes or collaborate with others.
 - htop — An interactive process viewer that’s more user‑friendly. It shows CPU, memory, and process usage in real time, with color coding and easy navigation.
 - ufw — “Uncomplicated Firewall,” a simple front‑end for managing iptables. It is used to define firewall rules with straightforward commands and to secure my lab once I start exposing services.

**Stage 2 — Networking & Visibility Layer**

In Stage 1, my VM just had the basics: it could run, edit configs, and do simple tasks. But it didn’t really know what was happening on the network or inside itself.
In this stage I “gave my VM a sense of what’s going on around it”, this involves giving te VM awareness and visibility. 

It’s still lightweight based on my system's resources, but I had tools that let me see traffic, processes, and connections in a clear way.

The following are the tools that I installed for this stage:
 - tcpdump — Packet capture for traffic inspection that captures packets enable me peek at the actual traffic moving through the interfaces.
 - nmap — Port scanning tool that scans ports and services to display what’s open and reachable.
 - traceroute — Maps the path that packets take across the network.
 - whois — Pulls domain registration info, handy when checking out unfamiliar hosts.
 - netcat (ncat) — A flexible tool for testing ports, setting up listeners, or moving data around.
 - sysstat — Collects stats on CPU, I/O, and processes to enable me to see system activity over time.
 - fail2ban — This is a small log‑based security monitor that watches logs for repeated failed login attempts and can block offenders automatically.

**Install Commands**
sudo apt update
sudo apt install -y tcpdump nmap traceroute whois netcat-openbsd sysstat fail2ban                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                          
