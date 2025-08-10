# BlockAssist Deployment Guide

This guide explains how to deploy and run **BlockAssist** on OctaSpace.

---

## Requirements
- OctaSpace account https://octa.space?ref=riZBsYWzjYx
- Node with:
  - **CPU:** 6+ cores
  - **RAM:** 16 GB or more
  - **Storage:** 100 GB (recommended)
  - **GPU:** RTX 3060 / Ada4000 / RTX 4070 / RTX 5070 or similar
- Hugging Face token - https://huggingface.co/settings/tokens/new?tokenType=write

---

## Steps

### 1. Deploy Node
1. Go to https://octa.space?ref=riZBsYWzjYx
2. In **Desktop & Gaming**, select **Octa EGL Desktop**.
3. Choose a node with the recommended specs.
4. Click **Configure** (keep default settings, select 100 GB storage).
5. Click **Deploy**.
6. Wait until status changes to **Service Configured**.

---

### 2. Open Desktop Session
1. Click **Session**.
2. Click the **HTTP Services** link to open the desktop.
3. In the desktop, click **Start** → **Konsole**.

---

### 3. Install and Run BlockAssist

```bash
git clone https://github.com/gensyn-ai/blockassist
cd blockassist
./setup.sh
```

Install **pyenv**:
```bash
curl -fsSL https://pyenv.run | bash
export PATH="$HOME/.pyenv/bin:$PATH"
eval "$(pyenv init -)"
eval "$(pyenv virtualenv-init -)"
source ~/.bashrc
```

Install required packages:
```bash
sudo apt update
sudo apt install make build-essential libssl-dev zlib1g-dev libbz2-dev libreadline-dev libsqlite3-dev curl git libncursesw5-dev xz-utils tk-dev libxml2-dev libxmlsec1-dev libffi-dev liblzma-dev -y
```

Install Python:
```bash
pyenv install 3.10.7
pip install psutil readchar
```

---

### 4. Install cuDNN

```bash
wget https://developer.download.nvidia.com/compute/cudnn/...
sudo dpkg -i cudnn-local-repo-ubuntu2204-8.x.x.x_1.0-1_amd64.deb
sudo cp /var/cudnn-local-repo-ubuntu2204-8.x.x.x/cudnn-local-<key>.pub /usr/share/keyrings/
echo 'deb [signed-by=/usr/share/keyrings/cudnn-local-<key>.pub] file:///var/cudnn-local-repo-ubuntu2204-8.x.x.x /' | sudo tee /etc/apt/sources.list.d/cudnn-local.list
sudo apt update
sudo apt install libcudnn9 libcudnn9-dev -y
echo 'export LD_LIBRARY_PATH=/usr/local/cuda/lib64:$LD_LIBRARY_PATH' >> ~/.bashrc
source ~/.bashrc
```

---

### 5. Run BlockAssist

```bash
python run.py
```

When prompted:
- Enter your **Hugging Face token**.
- Wait for Minecraft to load.
- Press **Enter** in terminal when 2 minecraft windows ready.
- Switch to full screen for better experience.
- play the game on minecraft window 1 dont play on window 2 because window 2 reserved for blockassist
- play untill 100% goal compeletion 
---

## Troubleshooting
- If screen turns black: close tab and restart from Marketplace.
- If GPU errors occur: choose another node or check drivers.
- Ensure storage is at least 100 GB for smooth operation.

---

**follow our channel for more unique airdrops https://t.me/andhiiTGkamaii **
