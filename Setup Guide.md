# Obsidian IT Asset Management System: Setup Guide

## 1. Prerequisites

### Software Requirements
- [Obsidian](https://obsidian.md/) (Latest Version)
- [Dataview Plugin](https://github.com/blacksmithgu/obsidian-dataview)
- Git (optional, for version control)

### Recommended Environment
- macOS, Windows, or Linux
- Minimum 4GB RAM
- Text editor (VSCode recommended)

## 2. Installation Steps

### A. Install Obsidian
1. Download from [Obsidian Official Website](https://obsidian.md/)
2. Install and launch the application
3. Create a new vault or open existing folder

### B. Install Dataview Plugin
1. Open Obsidian
2. Go to Settings → Community Plugins
3. Enable Community Plugins
4. Click "Browse" and search for "Dataview"
5. Install and enable the plugin

## 3. Configuration Templates

### Template Types
- People
- Department
- Division
- Server
- Application
- Service

### Template Structure Example: Server
```markdown
---
ci-type: Server
name: [ServerName]
division: "[[DivisionName]]"
department: "[[DepartmentName]]"
description: [Server Purpose]
hardware-details:
  processor-name: 
  processor-count: 
  memory-gb: 
network-details:
  ip-address: 
  mac-address: 
---
Additional notes
```

## 4. Relationship Mapping

### Linking Strategies
- Use `[[Double Brackets]]` for wiki-links
- Maintain consistent naming
- Create cross-references between entities

### Relationship Types
- People → Department
- Servers → Applications
- Services → Infrastructure

## 5. Dataview Query Configuration

### Enable Advanced Queries
```dataviewjs
// Example: List servers by application
const servers = dv.pages("CI/Server")
    .where(p => p.hosts-application.includes("[[ApplicationName]]"))
```

## 6. Best Practices

### Data Management
- Use consistent naming conventions
- Provide comprehensive information
- Update regularly
- Validate cross-references

## 7. Initial Setup Workflow

1. Define organizational structure
2. Create people and department entries
3. Populate server inventory
4. Map applications and services
5. Generate initial reports
6. Validate relationships

## 8. Troubleshooting

### Common Issues
- Incorrect wiki-link spelling
- Dataview query errors
- Relationship mapping problems

### Debugging Tips
- Check link capitalization
- Verify plugin settings
- Manually audit wiki-links

## 9. Version Control (Optional)

### Git Integration
```bash
# Initialize repository
git init

# Add all files
git add .

# Commit initial setup
git commit -m "Initial Asset Management System Setup"
```

## 10. Scaling and Expansion

- Start small, add complexity gradually
- Document your specific organizational needs
- Customize templates as required

## Next Steps

- Review and customize templates
- Begin populating your asset database
- Create initial reports
- Validate system functionality

Happy Asset Tracking! 🚀