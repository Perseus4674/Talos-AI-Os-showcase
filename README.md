# 🤖 Talos: Cognitive Architecture 

> "Systems Online."

Talos is an advanced, locally-hosted AI operating system designed to replicate the capabilities of a virtual assistant like JARVIS. It features a dual-interface design (Terminal HUD & Web Dashboard), cinema-quality neural voice synthesis, and context-aware long-term memory.

![Terminal Interface](terminal_hud.png)
*Figure 1: The Terminal HUD (Iron Man Mode) running real-time CPU stats and voice loop.*

![Web Dashboard](web_dashboard.png)
*Figure 2: The Holographic Web Interface (v2.4) with neural voice toggle and glassmorphism UI.*

---

## ⚡ Core Features

### 🧠 The Brain
* **Engine:** Powered by **GPT-4o** for advanced reasoning and tool usage.
* **Memory:** Implements a Retrieval-Augmented Generation (RAG) system using **ChromaDB** to retain user context long-term.
* **Persona:** "Stark Mode" provides witty, concise, and professional responses.

### 🦾 Capabilities
* **Full Automation:** Autonomous agents can launch applications, manage system volume, and control PC peripherals.
* **Computer Vision:** capable of analyzing screen content in real-time to assist with coding or analysis tasks.
* **Neural Voice:** Utilizes **EdgeTTS** to generate low-latency, cinema-quality speech.

### 🖥️ Dual Interfaces
1.  **Terminal HUD:** Built with Python `Textual` for a keyboard-centric, hacker-style workflow.
2.  **Web Dashboard:** Built with `Streamlit` for touch-friendly, mobile access.

---

## 🏗️ System Architecture

```mermaid
graph TD
    User[User Voice/Text] -->|Input| Interface
    Interface{Interface Layer}
    Interface -->|TUI| Terminal[Textual HUD]
    Interface -->|GUI| Web[Streamlit Web App]
    
    Terminal -->|Request| Brain[GPT-4o Brain]
    Web -->|Request| Brain
    
    Brain -->|Query| Memory[(ChromaDB Vector Store)]
    Brain -->|Execute| Tools[Automation Skills]
    
    Tools -->|Action| PC[System Control / AppOpener]
    Tools -->|Action| Eyes[Vision / Screenshots]
    
    Brain -->|Response| TTS[Neural Voice Engine]
    TTS -->|Audio| User
