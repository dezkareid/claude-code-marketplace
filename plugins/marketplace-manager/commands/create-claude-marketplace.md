---
allowed-tools: Bash(mkdir:*), Bash(cat:*), Bash(git config --list)
argument-hint: [marketplace-name] [marketplace-description]
description: Create skeleton for marketplace
---

## Rules
- The #$1 (marketplace name) is mandatary, if is not provided you should ask for it

## Your task

You will create a claude code marketplace following the next subtasks:

### 1. Create setup folders and files

Create file marketplace.json in folder .claude-plugin

Write marketplace.json add the marketplace name (should be kebab notation), if #$2 marketplace description is not provided, don't include the field.

This is the template

```json
{
  "name": "",
  "metadata": {
    "description": "",
    "version": "0.0.1"
  },
}
```

### 2. Add owner information
Get git config information to add owner information, the only required information is the name.

If name is missing ask for it.

If url is found, show the example of how will be added to owner field (this should be an HTTPS URL) and ask to procced (user can give you the value of field too)

```json
{
  "owner": {
    "name": "",
    "email": "",
    "url": ""
  }
}
```

Ask to user if he wants to add additional information to file.

### 3. Add documentation

Create a README.md with market place information

Add "Installation" information section, about how to install it and use the repository information to modify template information about owner and repo of the next template

```
/plugin marketplace add owner/repo
```

Before to finish ask to user verify result and make modifications if he wants.