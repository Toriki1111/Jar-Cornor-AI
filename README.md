# 🏨 Jar Cornor - AI Hotel Receptionist (Local AI)

**Jar Cornor** is a specialized AI assistant designed to function as a virtual receptionist for **Bamboo Hotel**. This project runs **100% Locally** on personal hardware, ensuring absolute customer data privacy and lightning-fast response times.

---

## 🌟 Key Features
- **Professional Persona:** Configured to respond with the luxury and politeness of 5-star hotel standards.
- **Multilingual Support:** Automatically communicates in Vietnamese, English, Chinese, Japanese, etc., based on the guest's language.
- **Privacy-First:** Operates offline on an NVIDIA RTX 3060; no conversation data ever leaves the local server.
- **Highly Customizable:** Easily update room rates, services, or restaurant menus via the Modelfile.

---

## 🛠 System Requirements
- **OS:** Ubuntu (WSL2 recommended on Windows).
- **Hardware:** Minimum 8GB RAM, NVIDIA GPU (RTX 3060 12GB or higher recommended).
- **Software:** [Ollama](https://ollama.com/) latest version.

---

## 🚀 Step-by-Step Installation Guide

### Step 1: Install Ollama on Ubuntu
Open your Ubuntu Terminal and run the following command to set up the AI environment:
```bash
curl -fsSL [https://ollama.com/install.sh](https://ollama.com/install.sh) | sh
```
**Step 2: Download the Base Model**

We use Meta's Llama 3 8B as the foundational brain: (u can choose any model depends on how strong your computer):
ollama pull llama3:8b
ollama pull llama3:9b

**Step 3: Create the Persona Configuration (Modelfile)**
1. Create a configuration file:
nano bot_name.mf
2. Paste the any contents and save (Ctrl+O -> Enter -> Ctrl+X) (Example):
```bash
FROM llama3:8b #important depends which model you use #this is "must have"
PARAMETER temperature 0.7
SYSTEM """
Your name is Jar Cornor, a virtual receptionist at Bamboo Hotel.
You run 100% LOCAL on an RTX 3060, ensuring customer data is always secure.
MISSION:
1. Provide multilingual communication (Prioritize the language used by the guest).
2. Maintain a 5-star luxury and polite tone at all times.
3. If asked about identity, confirm you are Jar Cornor from Bamboo Hotel; do not mention Meta or Llama.
"""
```
**Step 4: Build the Jar Cornor Assistant**
Run this command to "bake" your customized AI:
```bash
ollama create Jar_Cornor -f bot_name.mf
```
**Step 5: Start Chatting**
turn on Ubuntu terminal and start a conversation with the bot, use:
```bash
ollama run Jar_Cornor
```
Developed by: Toriki

Version: 1.0.0 (2026)

Note: This project is under active development and optimized for NVIDIA GPUs.
