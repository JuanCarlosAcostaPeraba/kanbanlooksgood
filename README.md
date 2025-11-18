# Kanban Looks Good

[![GLPI](https://img.shields.io/badge/GLPI-10.x-blue.svg)](https://glpi-project.org)
[![License: GPLv2+](https://img.shields.io/badge/License-GPLv2+-blue.svg)](https://www.gnu.org/licenses/old-licenses/gpl-2.0.html)
[![Status](https://img.shields.io/badge/Status-Stable-brightgreen.svg)]()
[![Maintained](https://img.shields.io/badge/Maintained-yes-success.svg)]()

A lightweight and non-intrusive GLPI plugin that enhances the **Project Kanban** by displaying **Priority** and **Planned Duration** directly on each card — without modifying any GLPI core files.

## ✨ Features

- 🔹 Displays GLPI’s native **priority badge** on Project and ProjectTask cards  
- 🔹 Shows **planned duration** using GLPI’s own formatting  
- 🔹 Adds a clean metadata bar below each card header  
- 🔹 Applies softened background color according to priority  
- 🔹 Works for both Projects and ProjectTasks  
- 🔹 Fully hook-based — **no core overrides**

## 📦 Requirements

- GLPI **10.0.0+**
- PHP **7.4+**

## 🚀 Installation

1. Copy the folder `kanbanlooksgood` into: 
    ```
    glpi/plugins/
    ```
2. Go to **GLPI → Configuration → Plugins**
3. Find **Kanban Looks Good**
4. Click **Install**, then **Enable**

## 🧩 How it works

### Priority
- Uses GLPI’s priority configuration (badge + color)
- Applies priority color to the card header
- Softened version of the same color is used as card background

### Planned Duration
- **Projects**: sum of all related ProjectTask planned durations  
- **ProjectTasks**: uses their native `planned_duration` field  
- Always formatted the same way GLPI displays durations

## 🏗️ Plugin Structure

```
kanbanlooksgood/
    ├── setup.php # Plugin registration + hooks
    ├── inc/
    │    └── hook.class.php # Injects metadata into Kanban cards
    ├── js/
    │    └── kanban.js # Frontend enhancements (color + metadata bar)
    ├── css/
    │    └── kanban.css # Styling for metadata section
    └── README.md
```

## 🔌 Hooks Used

- **`Hooks::KANBAN_ITEM_METADATA`**  
  Injects priority, planned duration, and colors directly into card metadata so the frontend can render everything instantly.

## 📝 License

**GPLv2+**

Fully compatible with GLPI plugin licensing requirements.

## 👤 Author

Developed by **Juan Carlos Acosta Perabá**, for the IT Engineering Team at **HUC – Hospital Universitario de Canarias**.
