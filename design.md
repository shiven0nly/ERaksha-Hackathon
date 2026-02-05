# System Design & Logic Flow

## 1. Network Topology: Transparent Bridging
Our device sits as a "Man-in-the-Middle" but in a helpful way. By using a Linux Bridge (`br0`), the devices don't know the Agentic-Box is there. This allows the Agent to "sniff" traffic without changing the user's IP settings.

## 2. The Agentic Reasoning Loop (O.P.A.L.)
The system operates on a continuous loop:
1. **Observe:** `Scapy` captures metadata (Source IP, Dest IP, Port, Payload Size).
2. **Plan:** The data is fed into a **Behavioral Threshold Formula**:
   $$Anomaly Score (S) = \sum_{i=1}^{n} (V_i - B_i)^2$$
   *(Where $V$ is current traffic volume and $B$ is the established baseline).*
3. **Act:** If $S > Threshold$, the Agent asks the LLM: *"This Smart Remote is sending 5MB of UDP traffic. Is this a hack?"*
4. **Learn:** If the user confirms it's a hack, the Agent updates its "Malicious Signature" database.

## 3. Deception Logic: The "Ghost" Network
The **Decoy Engine** maps the current network and fills "empty" IP addresses with virtual honeypots.
* **The Bait:** We expose Port 23 (Telnet) on a fake device named `Kitchen_Smart_Fridge`.
* **The Hook:** When a hacker attempts to brute-force the fake fridge, the Agent captures their IP and MAC.
* **The Sink:** The Agent instantly tells the Firewall to drop all packets from that MAC address across the **real** devices.

## 4. Autonomous Defence Layer
We use `IPTables` with `ipset` for high-speed blocking. 
* **Dynamic Micro-segmentation:** If a device is compromised (like the AC), the Agent doesn't just "kill" the internet; it restricts the AC to only talk to the internal Temperature Controller, cutting off the hacker's "Command & Control" (C2) server.
