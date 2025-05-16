# pkgtracker

**Track installed system and Python packages over time with ease.**

`pkgtracker` helps developers, sysadmins, and researchers capture and compare snapshots of software environments. It supports tracking system-level packages (APT, DNF, or Homebrew), Python packages (via `pip` or `pkg_resources`), and optionally Conda packages. Snapshots are stored as timestamped JSON files, allowing users to monitor changes, audit setups, and share reproducible environments.

---

## ✨ Features

- 🖥 **Track System Packages**: Supports `apt` (Debian/Ubuntu), `dnf` (Fedora), and `brew` (macOS).
- 🐍 **Track Python Packages**: Lists installed packages in the current Python environment.
- 🧬 **Optional Conda Support**: Detects and lists packages in active Conda environments.
- 🧾 **Snapshot Creation**: Saves environment snapshots to JSON files with timestamps.
- 🔍 **Snapshot Comparison**: Highlights added, removed, or updated packages between snapshots.
- 🧰 **Simple CLI Tool**: Use the `pkgtracker` command-line interface for all operations.
- ⚙️ **Zero External Dependencies**: Built using Python standard libraries only.

---

## 🚀 Installation

### Clone and install locally:
```bash
git clone https://github.com/jaicdev/pkgtracker.git
cd pkgtracker
pip install . --break-system-packages
````

---

## 🛠 Usage

The CLI provides three main commands:

### 1. Create a Snapshot

Save a snapshot of all packages to a JSON file:

```bash
pkgtracker snapshot snapshot.json
```

**Sample Output:**

```
Snapshot saved to snapshot.json
Snapshot taken at: 2025-05-16T17:02:00.123456
System Packages:
  Manager: apt
  Packages: 123
    - package1
    - package2
Python Packages:
    - numpy==1.21.0
    - requests==2.26.0
Conda Packages:
    (No Conda environment detected)
```

---

### 2. List Current Packages

List installed packages in the current environment:

```bash
pkgtracker list
```

Filter by type:

```bash
pkgtracker list --type python      # or system / conda
```

---

### 3. Compare Two Snapshots

Identify changes between two saved snapshots:

```bash
pkgtracker compare snapshot1.json snapshot2.json
```

**Sample Output:**

```
System Package Differences:
  Manager: apt
  Added:
    - new-package
  Removed:
    - old-package

Python Package Differences:
  Added:
    - pandas==1.3.0
  Removed:
    - old-lib==0.1.0
  Changed:
    - numpy: 1.21.0 -> 1.22.0
```

---

## 📂 Project Structure

```
pkgtracker/
├── pkgtracker/
│   ├── __init__.py
│   ├── cli.py              # CLI logic
│   ├── system_tracker.py   # System package tracking
│   ├── python_tracker.py   # Python package tracking
│   ├── conda_tracker.py    # Conda environment tracking
│   ├── snapshot.py         # Snapshot creation & comparison
│   └── utils.py            # Utility functions
├── setup.py
├── README.md
└── requirements.txt
```

---

## 🤝 Contributing

Contributions are welcome! To contribute:

1. Fork the repository.
2. Create a new branch:
   `git checkout -b feature/your-feature`
3. Make your changes and commit:
   `git commit -m "Add your feature"`
4. Push to your fork:
   `git push origin feature/your-feature`
5. Open a Pull Request.

Please ensure your code follows **PEP 8** and includes tests if applicable.

---

## 📜 License

This project is licensed under the **GPL-3.0 License**. See the [LICENSE](LICENSE) file for details.

---

## 📬 Contact

For issues or suggestions, please [open an issue](https://github.com/jaicdev/pkgtracker/issues) .

---

## ⭐ Star the Repo

If you find `pkgtracker` useful, please consider giving it a ⭐ on GitHub!
