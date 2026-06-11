# ⏰ Scheduling GitHub Actions Workflows

## 📌 Project Overview

Is project ka objective GitHub Actions ke **Scheduled Workflows** ko samajhna hai. GitHub Actions ki help se hum workflows ko specific time par automatically run karwa sakte hain bina manually trigger kiye.

Ye feature background tasks, automated reports, backups aur regular maintenance ke liye bahut useful hota hai.

---

## 🤔 Scheduled Workflow Kya Hota Hai?

Scheduled Workflow ek aisa workflow hota hai jo predefined time par automatically execute hota hai.

Iske liye GitHub Actions me **cron expression** ka use kiya jata hai.

Simple words me:

> "Hum GitHub ko bata dete hain ki workflow kis din aur kis time run karna hai."

---

## 🎯 Scheduled Workflows Kyu Use Karte Hain?

Scheduled workflows ka use:

* Daily backups ke liye
* Automated testing ke liye
* Database cleanup ke liye
* Security scans ke liye
* Report generation ke liye
* Dependency updates check karne ke liye

---

## ⚙️ Cron Expression Kya Hai?

Cron expression ek format hai jo schedule define karta hai.

Format:

```text id="s1"
* * * * *
│ │ │ │ │
│ │ │ │ └── Day of Week (0-7)
│ │ │ └──── Month (1-12)
│ │ └────── Day of Month (1-31)
│ └──────── Hour (0-23)
└────────── Minute (0-59)
```

---

## 💻 Example: Daily Workflow

Agar workflow har din 12:00 AM UTC par run karna ho:

```yaml id="s2"
name: Daily Workflow

on:
  schedule:
    - cron: '0 0 * * *'

jobs:
  test:
    runs-on: ubuntu-latest

    steps:
      - name: Print Message
        run: echo "Workflow Executed Successfully"
```

---

## 📅 Common Cron Examples

### Every Day at Midnight

```yaml id="s3"
cron: '0 0 * * *'
```

### Every Day at 6 AM

```yaml id="s4"
cron: '0 6 * * *'
```

### Every Sunday

```yaml id="s5"
cron: '0 0 * * 0'
```

### Every Monday

```yaml id="s6"
cron: '0 0 * * 1'
```

### Every Hour

```yaml id="s7"
cron: '0 * * * *'
```

### Every 30 Minutes

```yaml id="s8"
cron: '*/30 * * * *'
```

---

## 📂 Workflow File Structure

```text id="s9"
.github/
└── workflows/
    └── schedule.yml
```

YAML file ko `.github/workflows` folder ke andar store kiya jata hai.

---

## 🔄 Workflow Execution Process

```text id="s10"
Scheduled Time Arrives
           ↓
GitHub Actions Trigger
           ↓
Workflow Starts
           ↓
Execute Steps
           ↓
Task Completed
```

---

## 🚀 Scheduled Workflow + CI/CD

GitHub Actions scheduling ko CI/CD process ke saath bhi use kiya ja sakta hai.

Example:

```text id="s11"
Every Night
      ↓
Run Tests
      ↓
Build Project
      ↓
Generate Reports
      ↓
Deploy Updates
```

Isse application ki health regularly monitor ki ja sakti hai.

---


