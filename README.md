# Obsidian IT Asset Management System

## Overview

A lightweight, flexible, and powerful IT asset management solution built using Obsidian and the Dataview plugin. Designed for organizations seeking a cost-effective, customizable approach to tracking IT infrastructure, personnel, and organizational relationships.

## Motivation

Traditional IT asset management systems are:
- Expensive
- Complex to implement
- Rigid in their structure
- Require significant training

Our solution offers:
- **Zero Cost**: Uses free, open-source tools
- **Flexibility**: Easily customizable markdown-based system
- **Transparency**: Version control friendly
- **Simplicity**: Intuitive wiki-style linking

## Features

### Comprehensive Asset Tracking
- Server inventory management
- Application and service mapping
- Personnel and organizational structure tracking

### Dynamic Reporting
- Automatic relationship visualization
- Hierarchical organizational reports
- Flexible querying with DataviewJS

### Key Capabilities
- Detailed hardware specifications tracking
- IP and network interface management
- Lifecycle and status monitoring
- Interconnected entity relationships

## Prerequisites

- [Obsidian](https://obsidian.md/) (Latest Version)
- [Dataview Plugin](https://github.com/blacksmithgu/obsidian-dataview)

## Installation

1. Install Obsidian Desktop
   ```
   # macOS
   brew install --cask obsidian

   # Windows
   winget install Obsidian.Obsidian

   # Linux
   # Download from official website
   ```

2. Install Dataview Plugin
   - Open Obsidian
   - Go to Settings > Community Plugins
   - Enable Community Plugins
   - Search for "Dataview" and install

3. Clone the Repository
   ```bash
   git clone https://github.com/meowmeow11118888/obsidian-it-asset-management.git
   ```

4. Open as Obsidian Vault
   - In Obsidian, click "Open folder as vault"
   - Select the cloned repository folder

### Recommended Plugin Settings
- Enable Wikilinks
- Enable Dataview Query Execution

## Project Structure

```
Asset Management/
│
├── CI/
│   ├── Application/    # IT Applications
│   ├── Server/         # Server Inventory
│   └── Service/        # IT Services
│
├── Org/
│   ├── People/         # Personnel Records
│   ├── Department/     # Organizational Departments
│   └── Division/       # Organizational Divisions
│
├── Reports/            # Auto-generated Reports
│   ├── People List.md
│   └── Server List.md
│
└── Templates/          # Entry Templates
    ├── Template-People.md
    ├── Template-Server.md
    └── ...
```

## License

MIT License

## Acknowledgments

- [Obsidian](https://obsidian.md/)
- [Dataview Plugin](https://github.com/blacksmithgu/obsidian-dataview)