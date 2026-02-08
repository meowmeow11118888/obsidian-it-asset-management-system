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