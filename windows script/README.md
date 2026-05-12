# 🪟 Windows 11 Pro — Automatic Silent Installation Script

> **Fully automated Windows 11 Pro installation using `autounattend.xml` — No clicking, No forms, No Microsoft account required!**

![Windows 11](https://img.shields.io/badge/Windows-11%20Pro-0078D6?style=for-the-badge&logo=windows&logoColor=white)
![Ventoy](https://img.shields.io/badge/Boot-Ventoy-green?style=for-the-badge)
![License](https://img.shields.io/badge/License-MIT-yellow?style=for-the-badge)

---

## ✨ Benefits / Fayde

- ✅ **Zero Manual Input** — No Next→Next→Next clicking
- ✅ **No Microsoft Account** — Seedha Local Account banta hai
- ✅ **Auto Partitioning** — C: (150GB) + D: (Remaining) automatic
- ✅ **Auto User Creation** — Username & Password pre-set
- ✅ **Skips All OOBE Screens** — EULA, Privacy, Cortana sab skip
- ✅ **India Timezone Auto Set** — Manually nahi karna padta
- ✅ **Seedha Desktop** — Install hote hi directly desktop milta hai
- ✅ **Time Saving** — Manual install mein 30-40 min, yeh script sirf 15-20 min mein khatam

---

## 📁 Repository Structure

```
windows11-auto-install/
│
├── autounattend.xml        ← Main script (root mein hona zaroori)
├── ventoy/
│   └── ventoy.json         ← Ventoy auto-install config
└── README.md               ← Yeh file
```

---

## 🖥️ Disk Partition Layout

| Partition | Type   | Size       | Label   |
|-----------|--------|------------|---------|
| EFI       | FAT32  | 260 MB     | System  |
| MSR       | —      | 16 MB      | —       |
| **C:**    | NTFS   | **150 GB** | Windows |
| **D:**    | NTFS   | Remaining  | Data    |

---

## 🚀 Step-by-Step Usage Guide

### 📋 Requirements
- USB Drive / External HDD (minimum 8GB)
- Windows 11 ISO → [Download here](https://www.microsoft.com/software-download/windows11)
- Ventoy Software → [Download here](https://ventoy.net/en/download.html)

---

### Step 1 — Install Ventoy on External Drive

1. External HDD / USB connect karo
2. `Ventoy2Disk.exe` **Right Click → Run as Administrator**
3. Device mein apna drive select karo
4. `Option → Partition Style → GPT` select karo
5. **Install** click karo → OK

> ⚠️ Drive ka sara data delete hoga — pehle backup lo!

---

### Step 2 — Copy Files to Ventoy Drive

```
Ventoy Drive (E:\)
├── Win11_xxxx_English_x64.iso     ← Windows 11 ISO
├── autounattend.xml                ← Is repo se
└── ventoy\
    └── ventoy.json                 ← Is repo se
```

> ⚠️ `ventoy.json` mein ISO ka naam apne ISO file ke naam se match karo!

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

Replace `YOUR_ISO_FILENAME.iso` with your actual ISO filename.

---

### Step 4 — Boot from External Drive

1. External Drive connected rakho
2. PC Restart karo
3. Boot Menu kholo:

| Brand  | Key  |
|--------|------|
| Dell   | F12  |
| HP     | F9   |
| Asus   | F8   |
| Lenovo | F12  |
| Acer   | F12  |
| MSI    | F11  |

4. External Drive select karo
5. Ventoy Menu → **Windows 11 ISO** select karo → **Normal Boot**

---

### Step 5 — Sit Back & Relax ☕

Installation fully automatic hai — kuch bhi click nahi karna!

| Phase               | Time        |
|---------------------|-------------|
| Disk Partitioning   | ~1 min      |
| Windows Install     | ~10-15 min  |
| First Boot + Setup  | ~3-5 min    |
| **Total**           | **~20 min** |

---

## ⚙️ Default Configuration

| Setting       | Value                  |
|---------------|------------------------|
| Username      | `Admin`                |
| Password      | *(set by user)*        |
| Computer Name | `MyPC`                 |
| Timezone      | India Standard Time    |
| C: Drive      | 150 GB                 |
| D: Drive      | Remaining Space        |
| Account Type  | Local Administrator    |

> 🔐 **Customize karne ke liye** `autounattend.xml` mein yeh fields badlo:
> - `<Name>` — Username
> - `<Value>` — Password  
> - `<ComputerName>` — PC Name

---

## ⚠️ Important Notes

- 🔑 **Product Key** — Generic key se install hoga. Baad mein `Settings → System → Activation` mein apna original key daalo.
- 💾 **Disk 0 completely wipe hoga** — pehle data backup karo!
- 🌐 **Internet optional** — Installation ke liye internet ki zarurat nahi

---

## 🤝 Contributing

Pull requests welcome hai! Agar aapke paas improvements hain toh feel free to contribute.

---

## 📄 License

MIT License — Free to use, modify and share!

---

<div align="center">
  <b>⭐ Agar helpful laga toh Star dena mat bhoolo! ⭐</b>
</div>
