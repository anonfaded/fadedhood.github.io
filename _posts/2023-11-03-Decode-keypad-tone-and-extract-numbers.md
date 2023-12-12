---
layout: post
title: "Digital Forensics: Decoding Dialpad Tones into Plain Numbers"
category: [Forensics]
tags: [forensics,steganography,cybersecurity,dtmf,decoding]
pin: true
image:
  path: /assets/img/post7-forensics/37269234598.jpg
  lqip: data:image/webp;base64,UklGRpoAAABXRUJQVlA4WAoAAAAQAAAADwAABwAAQUxQSDIAAAARL0AmbZurmr57yyIiqE8oiG0bejIYEQTgqiDA9vqnsUSI6H+oAERp2HZ65qP/VIAWAFZQOCBCAAAA8AEAnQEqEAAIAAVAfCWkAALp8sF8rgRgAP7o9FDvMCkMde9PK7euH5M1m6VWoDXf2FkP3BqV0ZYbO6NA/VFIAAAA
comments: true
---

Ever wondered if keypad dialing sounds * _beeps_ * are more than random noise? In fact, they're assigned specific tones to numbers and can be extracted by recording these tones. This tool will extract the numbers for you.

## Technology:
### DTMF - Dual-tone multi-frequency signaling
- Dual-tone multi-frequency signaling is a telecommunication signaling system using the voice-frequency band over telephone lines between telephone equipment and other communications devices and switching centers.

## Syntax & Usage:
This is the command which is used to decode the frequency into plain-text numbers. first we type `dtmf` and then the audio file-name which we want to decode.

`dtmf [-h] [-v] [-l] [-r] [-d] [-t F] [-i T] file.wav`

```bash
optional arguments:
  -h, --help     show this help message and exit
  -v, --verbose  show a complete timeline
  -l, --left     left channel only (if the sound is stereo)
  -r, --right    right channel only (if the sound is stereo)
  -d, --debug    show graphs to debug
  -t F           acceptable frequency error (in hertz, 20 by default)
  -i T           process by T seconds intervals (0.05 by default)
```
Now lets install the tool on our linux:
## Installation:
Open the terminal on your linux and use the following commands to install the tool:
```bash
git clone https://github.com/ribt/dtmf-decoder.git
cd dtmf-decoder/
sudo python3 -m pip install -r requirements.txt --upgrade
chmod +x dtmf.py
sudo cp dtmf.py /usr/local/bin/dtmf
```

You may face some issue related to `pip` and will need to setup a private environment for the tool, so for that you would do the following steps:

## Create a Virtual Environment:

Navigate to the directory where you have your project for example `cd /path/to/your/project`, and create a virtual environment using:
```python
python3 -m venv venv
```

### Activate the Virtual Environment:

Activate the virtual environment using the `source` command:
```bash
source venv/bin/activate
```

### Install the Required Packages:

Now, you can install the Python packages from your `requirements.txt` file without using `sudo`:
```bash
pip install -r requirements.txt --upgrade
```

### Deactivate the Virtual Environment:

When you're done working with your project and want to leave the virtual environment, you can deactivate it using the following command:
```bash
deactivate
```

### Install Dependencies:

Some Python packages require specific system dependencies to build successfully. You might need to install these dependencies manually. For example, on Ubuntu, you can install `numpy` dependencies using:   
```bash
sudo apt-get install python3-dev libblas-dev liblapack-dev libatlas-base-dev
```

### Install `matplotlib`:

You can install `matplotlib` using `pip`:
```bash
pip install matplotlib
```

### Install `scipy`:

You can install `scipy` using `pip`:
```bash
pip install scipy
```
We're done! Now we can use the tools :)

