# android-debloat-lists

A curated collection of package names that can be safely removed from Android devices to reduce bloat, improve performance, and enhance privacy.

> ⚠️ Use at your own risk. Always verify each package’s purpose before removal. Misuse may cause system instability, break core functionality, or even lead to a soft-brick.

---

## 📁 Directory Structure

All lists are organized by manufacturer and model:

```

/
├── Xiaomi/
│   └── 2201116SG.list
├── README.md
└── LICENSE

```

Each `.list` file contains one package name per line:

```

com.facebook.katana
com.samsung.android.bixby.agent
com.google.android.youtube

````

---

## 🛠 How to Use

Use `adb` to uninstall packages listed in the `.list` files:

```bash
while read -r package; do
  adb shell pm uninstall --user 0 "$package"
done < samsung/galaxy_s10.list
````

Or use a debloat tool that supports importing package lists.

---

## 📌 Notes

* These lists are tailored for specific models and may not be universally applicable.
* Check the file name to match your exact device before use.
* Some packages may auto-reinstall after factory reset or system update.

---

## 🤝 Contributing

Want to add support for another device?
1. Get your device's manufacturer and model using ADB (you can find them directly in the system information on some ROMs).
2. Create a `.list` file under the appropriate manufacturer directory (e.g., `Xiaomi/2201116SG.list`).
3. Submit a pull request with a clear title and description.

## 📱 Getting model and manufacturer using ADB
```bash
adb shell "getprop ro.product.manufacturer && getprop ro.product.model"
```

---

## 📜 License

This project is licensed under the GNU General Public License v3.0 (GPL v3).
