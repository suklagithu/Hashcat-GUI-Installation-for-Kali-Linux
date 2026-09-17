# Hashcat GUI Installation for Kali Linux

Installation guide for running **Hashcat GUI** on Kali Linux.

<p align="center">
  <img src="Hashcat GUI Windows Icon.png" width="180">
</p>

## Requirements

* Kali Linux
* Hashcat
* PyQt5
* hcxtools
* PoCL (CPU OpenCL runtime)

## Installation

### 1. Install Hashcat

```bash
sudo apt install hashcat
```

Verify:

```bash
hashcat --version
```

### 2. Install PoCL

PoCL provides OpenCL support for running Hashcat on the CPU.

```bash
sudo apt install pocl-opencl-icd
```

Verify Hashcat can detect the CPU:

```bash
hashcat -I
```

### 3. Install hcxtools

`hcxtools` is required for converting supported Wi-Fi capture files to Hashcat's `.hc22000` format.

```bash
sudo apt install hcxtools
```

Verify:

```bash
hcxpcapngtool --version
```

### 4. Install PyQt5

```bash
sudo apt install python3-pyqt5
```

### 5. Download the Hashcat GUI

Clone the GUI repository:

```bash
git clone https://github.com/suklagithu/Hashcat-GUI-for-Windows.git
```

Enter the directory:

```bash
cd Hashcat-GUI-for-Windows
```

### 6. Run the GUI

```bash
python3 hashcat_gui.py
```

The Hashcat GUI should now open.

## GPU Verification

To check available Hashcat devices:

```bash
hashcat -I
```

To run a benchmark:

```bash
hashcat -b
```

## Supported Hash Modes

| Hash Type | Hashcat Mode |
| --------- | -----------: |
| WPA/WPA2  |        22000 |
| MD5       |            0 |
| SHA1      |          100 |
| SHA256    |         1400 |
| NTLM      |         1000 |
| bcrypt    |         3200 |

## Disclaimer

This project is intended for educational purposes, authorized security testing, password recovery, digital forensics, and security research.

Only use Hashcat against systems and data that you own or have explicit permission to test.
