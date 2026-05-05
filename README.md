# ⚡ Salesforce Essentials

A hands-on reference guide for Salesforce developers — covering CLI commands, org deployments, Apex execution, and real-world workflows. Built for speed, clarity, and daily use in VS Code.

---

# 🚀 Deploying & Executing Apex

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
`SFDX: Execute Anonymous Apex with Editor Contents`

### ✅ Expected Output (Output tab):
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
