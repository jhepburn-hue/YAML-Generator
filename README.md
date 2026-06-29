# YAML Generator

This is a web application designed to simplify the process of configuring and programming Secure Access Module (SAM) chips in the lab. 
Previously, creating these configuration files required tedious, manual formatting. This application provides an intuitive form that 
collects necessary hardware parameters and automatically generates a perfectly structured, ready-to-download `.yml` configuration file.

---

## Features
- **Dynamic SKU Mapping:** Tracks and automatically updates OEM IDs on-the-fly, auto-incrementing IDs for new entries.
- **TCI Byte Splitting:** Accepts standard 6-character hex values (e.g., `0x020A0C`) and seamlessly splits them into individual byte components (`tci_1`, `tci_2`, `tci_3`).
- **Custom Hex Output Formatting:** Features a custom YAML representer (`HexInt`) to ensure that specific hardware addresses and identifiers preserve their clean, uppercase hexadecimal notation (e.g., `0xC3`, `0x10`) rather than being cast back to plain decimals.
- [cite_start]**Specialty Key Configuration:** Optional conditional expansion to support specialized key injections (slots, types, versions, and usage constraints)[cite: 89, 96, 98, 104, 109].
- **Clean Block Spacing:** Post-processes the generated document string to introduce empty line breaks between logical yaml paragraphs for enhanced readability.

---

## Local Setup

### 1. Prerequisites
- **Python 3.10+**
- **Bash/Shell**

### 2. Installation
Clone the repository and navigate into the folder:
```bash
git clone https://github.com/jhepburn-hue/YAML-Generator.git
cd yaml-generator
```

Create and activate a virtual environment:
```bash
python3 -m venv venv
source venv/bin/activate  # On Windows use: venv\Scripts\activate
```

Install requirements:
```bash
pip install Flask PyYAML
```

---

### Running Locally

Start the Flask server:
```bash
python3 app.py
```

Open your browser and navigate to:
```bash
http://127.0.0.1:5000
```
