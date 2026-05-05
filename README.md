# ⚡ Salesforce Essentials

A hands-on reference guide for Salesforce developers — covering CLI commands, org deployments, Apex execution, and real-world workflows. Built for speed, clarity, and daily use in VS Code.

---

### 1. Create a Project
**Shortcut:** `Ctrl + Shift + P`

```
Steps:
1. Ctrl + Shift + P
2. Type: SFDX: Create Project
3. Select: Standard
4. Enter project name
5. Select Desktop as location
6. Wait for project to load
```

---

### 2. Connect/Authorize Org
**Shortcut:** `Ctrl + Shift + P`

```
Steps:
1. Ctrl + Shift + P
2. Type: SFDX: Authorize an Org
3. Press Enter 
4. Enter alias name (e.g. VSCodePlayground)
5. Login in browser that opens
6. Click Allow
```

---

### 3. Verify Connection
```
Click Cloud Icon (🌥️) on left sidebar
        OR
Check for:
✅ Custom Objects
✅ Apex Classes
✅ Other metadata
```

---

### All Important Shortcuts:

| Action | Shortcut |
|--------|----------|
| Command Palette | `Ctrl + Shift + P` |
| Search Files | `Ctrl + P` |
| Open Terminal | `Ctrl + `` ` |
| Auto Suggestions | `Ctrl + Space` |

---

### Important Commands:

| Task | Command |
|------|---------|
| Create Project | `SFDX: Create Project` |
| Authorize Org | `SFDX: Authorize an Org` |
| Deploy to Org | `SFDX: Deploy This Source to Org` |
| Retrieve from Org | `SFDX: Retrieve This Source from Org` |
| Open Org | `SFDX: Open Default Org` |
| Create Apex Class | `SFDX: Create Apex Class` |
| Create Apex Trigger | `SFDX: Create Apex Trigger` |
| Create LWC | `SFDX: Create Lightning Web Component` |
| Execute Anonymous | `SFDX: Execute Anonymous Apex` |
| Restart Apex Server | `SFDX: Restart Apex Language Server` |

---

### Terminal Commands:

| Task | Command |
|------|---------|
| List orgs | `sf org list` |
| Open org | `sf org open --target-org aliasName` |
| Deploy | `sf project deploy start --target-org aliasName` |
| Set default org | `sf config set target-org aliasName` |
| Check current org | `sf config get target-org` |
| Rename alias | `sf alias set newName=username` |
| Remove org | `sf org logout --target-org aliasName` |

---

### Project Structure:
```
MyProject/
  ├── force-app/
  │     └── main/
  │           └── default/
  │                 ├── classes/      ← Apex Classes
  │                 ├── triggers/     ← Apex Triggers
  │                 ├── lwc/          ← LWC Components
  │                 └── objects/      ← Custom Objects
  ├── config/
  │     └── project-scratch-def.json ← Scratch org config
  └── sfdx-project.json              ← Project config
```
---

> 💡 **Quick Tips:**
> - Always check **bottom status bar** for connected org
> - Use **Cloud icon** on left to browse org metadata
> - Always **deploy** before testing in org
> - Use **run.apex** file for anonymous execution
> - **`.cls`** = Apex class, **`.trigger`** = trigger, **`.html/.js`** = LWC

---

# 🚀 Apex Class - Deploy & Execute

## Option 1 — VS Code + SF CLI

### Step 1 — Save the file
Press `Ctrl + S`
### Step 2 — Deploy to org
Press `Ctrl + Shift + D` or run:
```bash
sf project deploy start --target-org Accenture
```
### Step 3 — Create `run.apex` file and add:
```apex
DMLops.runDML();
```
### Step 4 — Execute Anonymous Apex
Right-click inside `run.apex` → select:
`SFDX: Execute Anonymous Apex with Currently Opened Editor`

### Expected Output (Output tab):
DEBUG|Inserted: 001xxxxxxxxxxxxxxx

---

## Option 2 — Developer Console (Browser)

### Step 1 — Open Command Palette
Press `Ctrl + Shift + P`
### Step 2 — Open Default Org
Type and select:
`SFDX: Open Default Org`
### Step 3 — Launch Developer Console
In browser → click **Setup gear ⚙️** → **Developer Console**
### Step 4 — Open Execute Anonymous Window
Press `Ctrl + E` → type:
```apex
DMLops.runDML();
```
### Step 5 — Run
Click **Execute**
### Step 6 — Check Logs
Go to **Logs tab** → double-click the latest log → check **"Debug Only" ✅**


# ⚡ Apex Triggers

### Step 1 — Create a Trigger file
Press `Ctrl + E` → type: `SFDX: Create Apex Trigger`
### Step 2 — Deploy to Org
Press `Ctrl + Shift + D`
```bash
sf project deploy start --target-org Accenture
```
### Step 4 — Create `run.apex`
```apex
// Insert a record to fire the trigger
insert new Account(Name = 'Test Account');
```
### Step 5 — Execute `run.apex`
Right-click inside `run.apex` → select:
`SFDX: Execute Anonymous Apex with Currently Opened Editor`
