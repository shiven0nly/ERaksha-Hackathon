# Detailed System Requirements

## 1. Hardware Specification
* **Compute Unit:** Raspberry Pi 5 (8GB RAM) - Required for running local AI inference (Ollama).
* **Storage:** 64GB UHS-I MicroSD (High endurance) for logging and Docker images.
* **Network Interface Card (NIC):** * Primary: Built-in Gigabit Ethernet.
    * Secondary: TP-Link USB 3.0 to Gigabit Ethernet Adapter (to create the 'Bridge').
* **Cooling:** Active heat-sink (required as AI processing generates significant heat).

## 2. Software & Libraries
* **Operating System:** Ubuntu Server 22.04 LTS (Optimized for headless performance).
* **Language Environment:** Python 3.11+.
* **Networking Stack:**
    * `Scapy`: For deep packet inspection (DPI) and packet crafting.
    * `Bridge-utils`: To create a Layer-2 transparent bridge.
    * `Nmap`: For active network reconnaissance.
* **Agent Intelligence:**
    * `Ollama`: To run **Llama-3 (8B)** or **Mistral-7B** locally for threat reasoning.
    * `Pandas/NumPy`: For real-time traffic anomaly calculations.
* **Virtualization:** `Docker` & `Docker-Compose` to deploy lightweight honeypot containers (Cowrie, HoneyPy).

## 3. Performance Benchmarks (Project Goals)
* **Detection Latency:** Identify new devices in < 30 seconds.
* **Mitigation Speed:** Execute firewall block in < 1 second after threat confirmation.
* **False Positive Rate:** < 2% through continuous baseline refinement.
