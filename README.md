# 🚀 AI Code Setup on Ubuntu

## 1️⃣ Install Python 3.8

```bash
sudo apt update && sudo apt upgrade -y
sudo wget https://www.python.org/ftp/python/3.8.10/Python-3.8.10.tgz
sudo tar xzf Python-3.8.10.tgz
cd Python-3.8.10
sudo ./configure --enable-optimizations
sudo make altinstall
sudo apt install -y build-essential
sudo add-apt-repository ppa:deadsnakes/ppa -y
sudo apt install python3.8
python3.8 --version
```

---

## 2️⃣ Install VS Code

```bash
cd ~/Downloads
sudo apt install ./code_1.99.2-1744250061_amd64.deb 
```

---

## 3️⃣ Manage Python Versions

```bash
ls /usr/bin/python*
sudo update-alternatives --config python3
sudo update-alternatives --install /usr/bin/python3 python3 /usr/bin/python3.8 1
sudo update-alternatives --config python3
```

---

## 4️⃣ Fix distutils (if needed)

```bash
sudo apt install python3-distutils
sudo cp -r Lib/distutils /usr/lib/python3.8/
python3.8 -c 'from distutils.cmd import Command; print("distutils is installed and working!")'
```

---

## 5️⃣ Install Libraries

```bash
python3.8 -m pip install facenet-pytorch mediapipe pymongo
```

---

## 6️⃣ Fix Pillow (PIL) Errors

```bash
sudo apt remove python3-pil
python3.8 -m pip uninstall pillow
python3.8 -m pip install --user pillow
python3.8 -c "from PIL import Image; print('Pillow version:', Image.__version__)"
```

---

## 📝 Quick Reference Table

| Step | Description            | Command Example/Notes                                  |
|------|------------------------|--------------------------------------------------------|
| 1    | Install Python 3.8     | See step 1 above                                       |
| 2    | Install VS Code        | See step 2 above                                       |
| 3    | Manage Python versions | See step 3 above                                       |
| 4    | Fix distutils          | See step 4 above                                       |
| 5    | Install libraries      | See step 5 above                                       |
| 6    | Fix PIL errors         | See step 6 above                                       |

---

> **Tip:**  
> If you face module errors, check your Python version and reinstall the libraries using `python3.8 -m pip install <library>`.

---

## 📜 History

View all your commands with:
```bash
history
```
