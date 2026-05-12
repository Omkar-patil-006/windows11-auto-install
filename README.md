# 🪟 Windows 11 Pro — Automatic Silent Installation Script

> **Fully automated Windows 11 Pro installation using `autounattend.xml` — No clicking, No forms, No Microsoft account required!**

![Windows 11](https://img.shields.io/badge/Windows-11%20Pro-0078D6?style=for-the-badge&logo=windows&logoColor=white)
![Ventoy](https://img.shields.io/badge/Boot-Ventoy-green?style=for-the-badge)
![Educational](https://img.shields.io/badge/Purpose-Educational-orange?style=for-the-badge)

---

## ✨ Benefits

- ✅ **Zero Manual Input** — No Next → Next → Next clicking required
- ✅ **No Microsoft Account** — Creates a local user account directly
- ✅ **Auto Partitioning** — C: (150GB) + D: (Remaining space) set automatically
- ✅ **Auto User Creation** — Username & Password pre-configured
- ✅ **Skips All OOBE Screens** — EULA, Privacy, Cortana all bypassed
- ✅ **Auto Timezone Setup** — India Standard Time set automatically
- ✅ **Boots Directly to Desktop** — No extra setup screens after install
- ✅ **Time Saving** — Manual install takes 30–40 min; this script finishes in 15–20 min

---

## 📁 Repository Structure

```
windows11-auto-install/
│
├── autounattend.xml        ← Main script (must be placed in root)
├── ventoy/
│   └── ventoy.json         ← Ventoy auto-install config
└── README.md               ← This file
```

---

## 🖥️ Disk Partition Layout

| Partition | Type  | Size       | Label   |
|-----------|-------|------------|---------|
| EFI       | FAT32 | 260 MB     | System  |
| MSR       | —     | 16 MB      | —       |
| **C:**    | NTFS  | **150 GB** | Windows |
| **D:**    | NTFS  | Remaining  | Data    |

---

## 🚀 Step-by-Step Usage Guide

### 📋 Requirements

- USB Drive or External HDD (minimum 8GB free space)
- Windows 11 ISO → [Download here](https://www.microsoft.com/software-download/windows11)
- Ventoy Software → [Download here](https://ventoy.net/en/download.html)

---

### Step 1 — Install Ventoy on External Drive

1. Connect your External HDD or USB Drive
2. Right Click `Ventoy2Disk.exe` → **Run as Administrator**
3. Select your drive from the Device dropdown
4. Go to `Option → Partition Style → GPT`
5. Click **Install** → OK

> ⚠️ All data on the drive will be erased — take a backup first!

---

### Step 2 — Copy Files to Ventoy Drive

```
Ventoy Drive (E:\)
├── Win11_xxxx_English_x64.iso     ← Windows 11 ISO
├── autounattend.xml                ← From this repo (root level)
└── ventoy\
    └── ventoy.json                 ← From this repo
```

> ⚠️ Make sure the ISO filename in `ventoy.json` matches your actual ISO file name!

---

### Step 3 — Update ventoy.json (if needed)

```json
{
    "auto_install":[
        {
            "image": "/YOUR_ISO_FILENAME.iso",
            "template": "/autounattend.xml"
        }
    ]
}
```

Replace `YOUR_ISO_FILENAME.iso` with your actual ISO file name.

---

### Step 4 — Boot from External Drive

1. Keep the External Drive connected
2. Restart your PC
3. Open Boot Menu using the key for your brand:

| Brand  | Key |
|--------|-----|
| Dell   | F12 |
| HP     | F9  |
| Asus   | F8  |
| Lenovo | F12 |
| Acer   | F12 |
| MSI    | F11 |

4. Select your External Drive
5. In Ventoy Menu → Select **Windows 11 ISO** → Choose **Normal Boot**

---

### Step 5 — Sit Back & Relax ☕

The installation is fully automatic — no input required!

| Phase              | Estimated Time |
|--------------------|----------------|
| Disk Partitioning  | ~1 min         |
| Windows Install    | ~10–15 min     |
| First Boot + Setup | ~3–5 min       |
| **Total**          | **~20 min**    |

---

## ⚙️ Default Configuration

| Setting       | Value               |
|---------------|---------------------|
| Username      | `Set by user`       |
| Password      | `Set by user`       |
| Computer Name | `MyPC`              |
| Timezone      | India Standard Time |
| C: Drive      | 150 GB              |
| D: Drive      | Remaining Space     |
| Account Type  | Local Administrator |

### 🔐 To Customize — Edit these fields in `autounattend.xml`:

```xml
<Name>YourUsername</Name>           <!-- Change username -->
<Value>YourPassword</Value>         <!-- Change password -->
<ComputerName>YourPCName</ComputerName>  <!-- Change PC name -->
```

---

## ⚠️ Important Notes

- 🔑 **Product Key** — A generic key is used for installation. After install, activate Windows with your original key via `Settings → System → Activation`
- 💾 **Disk 0 will be completely wiped** — Always backup your data before proceeding!
- 🌐 **No Internet Required** — Installation works completely offline
- 🔒 **Keep your credentials private** — Never share your edited `autounattend.xml` publicly with your real password inside

---

## 📄 Disclaimer

This script is for **educational purposes only.**
Windows is a product of Microsoft Corporation.
Make sure you have a valid Windows license before use.
This repository does not promote or support piracy in any form.

---

## 🤝 Contributing

Pull requests are welcome! If you have improvements or suggestions, feel free to contribute.

---

<div align="center">
  <b>⭐ If this helped you, don't forget to leave a Star! ⭐</b>
</div>
