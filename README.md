# Agentic-IoT-Guard: The Future Of Home Security 🛡️
[PPT Link](https://docs.google.com/presentation/d/1Y4odsqUE003ysN60uuqUX-CiHBanp7Ai8DOSZALeqBU/edit?usp=sharing)

## 1. Project Vision
As home IoT ecosystems grow, traditional security fails because smart devices (ACs, TVs, Bulbs) lack the compute power to defend themselves. **Agentic-IoT-Guard** is a student-led prototype of a "Self-Thinking" security appliance. Unlike a passive firewall, this system acts as an **Active Agent** with a specific goal: *Identify, Deceive, and Neutralize* threats within the home network.

## 2. The Problem We are Solving
* **Shadow IoT:** Most users don't know what devices are on their network.
* **Protocol Weakness:** Embedded systems use insecure protocols (Telnet, UPnP) that are easily hijacked.
* **The "Spy" Scenario:** Hackers can turn on microphones in smart remotes or disable AC compressors, causing physical discomfort or privacy leaks.

## 3. Core Functional Modules
### A. The Surveyor Agent (Discovery & Profiling)
Automatically fingerprints every device using MAC OUI analysis and Nmap service detection. It assigns a "Risk Score" based on open ports and firmware age.

### B. The Decoy Engine (Deceptive Defence)
Instead of just blocking hackers, we waste their time. The system spins up **Virtual Honeypots**—fake vulnerable cameras and NAS drives—to trap attackers the moment they enter the network.

### C. The Guardian Agent (Autonomous Response)
Powered by a Local LLM, this agent monitors traffic patterns. If your Smart TV starts sending 1GB of data to an unknown server at 2 AM, the Guardian recognizes the anomaly and dynamically rewrites the firewall rules to isolate the TV.

## 4. How to Use
1. Connect the **Agentic-Box** between your ISP Modem and your Home Router.
2. Power on the Raspberry Pi.
3. Access the Local Dashboard via `http://agent-guard.local`.
4. The Agent begins "Learning Mode" for 24 hours to establish a behavior baseline.
