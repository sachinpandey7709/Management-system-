# 💎 Marg Gold Edition

> **Complete User Management System — Unlimited Users · Unlimited Rights · Single File**

A modern desktop application built with Python and Tkinter for managing users and their granular permissions. No database, no server — just run and go.

[![Python](https://img.shields.io/badge/Python-3.8%2B-blue?logo=python&logoColor=white)](https://python.org)
[![Platform](https://img.shields.io/badge/Platform-Windows%20%7C%20macOS%20%7C%20Linux-lightgrey)](https://github.com)
[![License](https://img.shields.io/badge/License-MIT-green)](LICENSE)
[![Status](https://img.shields.io/badge/Status-Production%20Ready-brightgreen)](https://github.com)

---

## 📖 About

**Marg Gold Edition** is a fully-functional, single-file desktop application for managing users and permissions. Perfect for small businesses, retail shops, and accounting firms — **without needing a database or server setup**.

Built with **unlimited users**, **unlimited rights**, **bulk import/export**, **audit logging**, and a **beautiful dark-themed GUI** — all in **one Python file**.

---

## ✨ Features

| Category | Features |
|----------|----------|
| **Users** | Unlimited users · Create · Edit · Delete · Reset password · Toggle active · Live search |
| **Rights** | Unlimited granular rights · 6 actions (VIEW/ADD/EDIT/DELETE/PRINT/EXPORT) · Interactive grid |
| **Security** | SHA-256 + salt hashing · Self-protection guards · Audit trail |
| **Import/Export** | CSV · Excel (3 sheets) · Bulk import · Template · Preview · Conflict handling |
| **UI** | Dark theme · Sidebar navigation · Modal dialogs · Emoji icons |

---

## 🚀 Quick Start

### 1. Install Python

Download from [python.org](https://www.python.org/downloads/) (3.8+)

### 2. Clone this repo

```bash
git clone https://github.com/YOUR-USERNAME/marg-gold-edition.git
cd marg-gold-edition
```

### 3. Install dependency

```bash
pip install -r requirements.txt
```

### 4. Run

```bash
python marg_gold_edition.py
```

### 5. First run

Create your admin account when prompted → log in → start managing users 🎉

---

## 📦 Installation

### Option A — Direct Download

1. Download `marg_gold_edition.py`
2. `pip install openpyxl`
3. `python marg_gold_edition.py`

### Option B — Clone & Install

```bash
git clone https://github.com/YOUR-USERNAME/marg-gold-edition.git
cd marg-gold-edition
pip install -r requirements.txt
python marg_gold_edition.py
```

### Option C — Build Windows `.exe`

```bash
pip install pyinstaller
pyinstaller --onefile --windowed --name "MargGold" marg_gold_edition.py
```

The `.exe` will be in `dist/`.

### Platform Notes

| Platform | Extra Step |
|----------|-----------|
| Windows | ✅ Nothing — Tkinter included |
| macOS | ✅ Nothing — Tkinter included |
| Ubuntu/Debian | `sudo apt install python3-tk` |
| Fedora | `sudo dnf install python3-tkinter` |
| Arch | `sudo pacman -S tk` |

---

## 🎯 Usage

### First Login

1. **Create admin** when prompted (first run only)
2. **Log in** with your credentials
3. Start exploring the 5 panels

### Create a User

1. Go to **👥 Users** panel
2. Click **➕ New User**
3. Fill fields → click **💾 Save**

### Set Permissions

1. Go to **🔑 Rights** panel
2. Select a user from dropdown
3. **Double-click any cell** to toggle that right
4. Saves instantly ✅

### Bulk Import Users

1. Click **📄 Template** → save CSV
2. Edit CSV in Excel/Sheets
3. Click **📥 Import** → select file
4. Review preview → **✅ Import Now**

### Backup Data

Copy these 3 files to a safe place:

```
marg_users.json
marg_rights.json
marg_audit.json
```

---

## 📥 Import Format

```csv
username,password,full_name,role,is_admin,active
john_doe,Pass@123,John Doe,USER,NO,YES
jane_admin,Admin@456,Jane Smith,ADMIN,YES,YES
cashier1,cash123,Rajesh Kumar,CASHIER,NO,YES
```

| Column | Required | Accepted Values |
|--------|----------|-----------------|
| `username` | ✅ | Any unique string |
| `password` | ✅ | Min 3 chars |
| `full_name` | ❌ | Any string |
| `role` | ❌ | USER, ADMIN, etc. |
| `is_admin` | ❌ | YES/NO, Y/N, TRUE/FALSE, 1/0 |
| `active` | ❌ | Same as `is_admin` |

---

## 🛠️ Customization

### Add a New Module

Edit `DEFAULT_MODULES` in `marg_gold_edition.py`:

```python
DEFAULT_MODULES = {
    # ... existing ...
    "PAYROLL": ["Salary", "Attendance", "Leave", "Bonus"],
}
```

### Add a New Right Type

Edit `RIGHT_TYPES`:

```python
RIGHT_TYPES = ["VIEW", "ADD", "EDIT", "DELETE", "PRINT", "EXPORT", "APPROVE"]
```

### Change Theme

Edit the `COLORS` dict — change hex codes to your brand colors.

---

## 🔧 Troubleshooting

### `openpyxl` missing
```bash
pip install openpyxl
```

### `No module named 'tkinter'`

| OS | Command |
|----|---------|
| Ubuntu/Debian | `sudo apt install python3-tk` |
| Fedora | `sudo dnf install python3-tkinter` |
| Arch | `sudo pacman -S tk` |

### Import shows all rows as "Invalid"
- Check headers: `username` and `password` **must** be in row 1
- Ensure CSV is UTF-8 encoded
- Remove empty rows before row 2

### Forgot admin password
No built-in recovery. Options:
1. Edit `marg_users.json` — remove your admin entry, restart, create new
2. Delete all 3 JSON files — start fresh ⚠️ (loses all users)

**Back up `marg_users.json` regularly!**

---

## ❓ FAQ

<details>
<summary><b>Do I need internet?</b></summary>
No. Works 100% offline.
</details>

<details>
<summary><b>Can multiple users access it simultaneously?</b></summary>
No — it's a single-user desktop app.
</details>

<details>
<summary><b>Is data encrypted?</b></summary>
Passwords are hashed (SHA-256 + salt). Other data is plain JSON.
</details>

<details>
<summary><b>How many users can it handle?</b></summary>
Unlimited in code. Performance fine up to ~10,000 users.
</details>

<details>
<summary><b>Where is data stored?</b></summary>
Three JSON files next to <code>marg_gold_edition.py</code>.
</details>

<details>
<summary><b>Can I use this commercially?</b></summary>
Yes — MIT License. Modify, redistribute, sell freely.
</details>

<details>
<summary><b>Does it work on Mac M1/M2?</b></summary>
Yes — Python 3.8+ works natively.
</details>

<details>
<summary><b>Can I export to PDF?</b></summary>
Not built-in. Export to Excel → print to PDF.
</details>

---

## 🏆 Best Practices

### For Admins
- 🔐 Use a **strong admin password** (12+ chars, mixed case, symbols)
- 👥 Create a **second admin** as backup
- 📜 **Review audit log weekly**
- 💾 **Back up JSON files daily**

### For Daily Use
- 📝 Use clear usernames (`john_doe`, not `user123`)
- 🏷 Use consistent roles (`ADMIN`, `MANAGER`, `CASHIER`)
- 📊 Export audit log monthly for records
- 🔐 Reset passwords when staff leave

### For Bulk Imports
- 📄 **Always start from the template**
- ✅ **Test with 2-3 rows first**
- 💾 **Keep the original CSV** for re-import

---

## 🗺️ Roadmap

- [x] Unlimited users + rights
- [x] Full CRUD + audit logging
- [x] CSV + Excel import/export
- [x] Dark modern theme
- [ ] Backup / Restore (one-click ZIP)
- [ ] Role templates (Cashier/Manager presets)
- [ ] Multi-company support
- [ ] Web version (FastAPI + React)
- [ ] Two-factor authentication

---

## 🤝 Contributing

1. Fork the repo
2. Create feature branch: `git checkout -b feature/AmazingFeature`
3. Commit: `git commit -m "Add some AmazingFeature"`
4. Push: `git push origin feature/AmazingFeature`
5. Open a Pull Request

---

## 📄 License

[MIT](LICENSE) — Free to use, modify, and distribute.

---

## ⭐ Show Your Support

If this helped you:
- ⭐ **Star this repo**
- 🐛 **Report bugs** via [Issues](https://github.com/YOUR-USERNAME/marg-gold-edition/issues)
- 🔀 **Fork and improve**
- 📢 **Share with others**

---

<p align="center">
  <b>💎 MARG GOLD EDITION</b><br>
  <i>Complete User Management. Unlimited. Beautiful. Free.</i><br><br>
  Made with ❤️ using Python + Tkinter<br>
  <sub>© 2026 · MIT License</sub>
</p>
