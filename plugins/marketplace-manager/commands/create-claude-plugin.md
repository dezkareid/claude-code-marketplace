---
allowed-tools: Bash(mkdir:*), Bash(cat:*), Bash(git config --list)
argument-hint: [plugin-name] [plugin-description]
description: Create skeleton for plugin
---

## Context
- Main folder is where is execute this session
- Plugin folder is inside of #$1 (kebab-notation) folder.

## Rules
- The #$1 (plugin name) is mandatary, if is not provided you should ask for it

## Your task

You will create a claude code plugin following the next subtasks:

### 1. Create setup folders and files

Create folder plugins and create folder with the name of plugin-name (should be kebab notation). This should be the plugin folder.

In plugin folder create the plugin.json inside .claude-plugin.

Get information about author using `git config --list`

Use the next template to write information

```json
{
  "name": "",
  "description": "",
  "version": "0.0.1",
  "author": {
    "name": ""
  }
}
```

Show to the user the information before to write. Ask to user if he wants to add additional information to file.

### 2.  Add plugin to marketplace
Modify plugins property in .claude-plugin/marketplace.json of main folder using the plugin.json information and the change the source property with using the relative path to plugin folder:

```json
{
  "plugins":[
    {
      // Plugin information
      "source": "./plugins/:plugin-name",
    }
  ]
}
```

### 3. Create agents, commands and or skills

Ask to user if he wants to create agents, commands and/or skills, he only needs to say the names and descriptions.

You should create files with extension.md using the names in kebab notation in folders: agents, commands or skills inside plugin folder.

```
---
name: 
description:
---
```

### 3. Add README.md in plugin folder

Create a README.md with plugin information like name and description

Add section installation using marketplace.json and plugin.json information, marketplace name and plugin name:

```
/plugin install plugin-name@market-place-name
```

