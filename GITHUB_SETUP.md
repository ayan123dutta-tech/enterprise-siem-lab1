# 🚀 GitHub Repository Setup Guide

**Project:** Enterprise SIEM Lab — Ayan Dutta  
**This guide walks you through creating a GitHub repository and pushing all project files in under 10 minutes.**

---

## 📋 What You Will Push

| File | Description |
|------|-------------|
| `Ayan Dutta_Enterprise SIEM Lab.ipynb` | Main project notebook (42 cells) |
| `Ayan Dutta_Project Report.docx` | Full project report — MS Word |
| `Ayan Dutta_Project Report.pdf` | Full project report — PDF |
| `requirements.txt` | Python dependency list |
| `README.md` | Project overview (this becomes your repo homepage) |
| `generate_siem_report.py` | Script that generates the Word report |
| `generate_siem_pdf.py` | Script that generates the PDF report |
| `gitignore_template.txt` | Rename to `.gitignore` before pushing |

---

## ✅ Prerequisites

Install these before starting:

| Tool | Download Link | Purpose |
|------|--------------|---------|
| **Git** | https://git-scm.com/download/win | Version control CLI |
| **GitHub Account** | https://github.com/signup | Free account |
| **GitHub CLI** *(optional)* | https://cli.github.com/ | Create repo from terminal |

Verify Git after installing:
```bash
git --version
# Expected: git version 2.x.x
```

---

## 🛠️ Step-by-Step Instructions

---

### STEP 1 — Create a New Repository on GitHub

1. Go to **https://github.com/new**
2. Fill in the form:

| Field | Value |
|-------|-------|
| **Repository name** | `enterprise-siem-lab` |
| **Description** | `Deployed a Wazuh SIEM cluster to aggregate logs and create custom alert dashboards` |
| **Visibility** | Public *(or Private — your choice)* |
| **Initialize with README** | ❌ **Do NOT check** — you already have one |
| **Add .gitignore** | ❌ **Do NOT check** — you already have one |
| **Choose a license** | MIT *(optional)* |

3. Click **"Create repository"**

4. GitHub will show you a page with a URL like:
   ```
   https://github.com/YOUR-USERNAME/enterprise-siem-lab.git
   ```
   **Copy this URL** — you'll need it in Step 4.

---

### STEP 2 — Prepare Your Local Files

Open **PowerShell** (or Command Prompt) and navigate to your project folder:

```powershell
cd "d:\COLLEGE DOCUMENTS\COLLEGE PROJECT"
```

Rename the gitignore template to `.gitignore`:

```powershell
Rename-Item "gitignore_template.txt" ".gitignore"
```

> **Why?** Files starting with `.` can't be created directly in Windows Explorer, but PowerShell can rename them fine.

---

### STEP 3 — Initialise a Local Git Repository

```bash
# Initialise git in the project folder
git init

# Set your identity (only needed once per machine)
git config --global user.name  "Ayan Dutta"
git config --global user.email "your-email@example.com"
```

---

### STEP 4 — Stage All Project Files

```bash
# Add all project files to the staging area
git add "Ayan Dutta_Enterprise SIEM Lab.ipynb"
git add "Ayan Dutta_Project Report.docx"
git add "Ayan Dutta_Project Report.pdf"
git add requirements.txt
git add README.md
git add generate_siem_report.py
git add generate_siem_pdf.py
git add .gitignore
```

Or add everything at once (the `.gitignore` will automatically exclude temp files):

```bash
git add .
```

Verify what will be committed:

```bash
git status
```

Expected output:
```
On branch main

Changes to be committed:
  new file:   .gitignore
  new file:   Ayan Dutta_Enterprise SIEM Lab.ipynb
  new file:   Ayan Dutta_Project Report.docx
  new file:   Ayan Dutta_Project Report.pdf
  new file:   README.md
  new file:   generate_siem_pdf.py
  new file:   generate_siem_report.py
  new file:   requirements.txt
```

---

### STEP 5 — Create the First Commit

```bash
git commit -m "Initial commit: Enterprise SIEM Lab — Ayan Dutta

- Wazuh SIEM cluster deployment (Docker Compose)
- Custom detection rules mapped to MITRE ATT&CK
- Python log simulation and Wazuh REST API client
- Elasticsearch DSL queries and Kibana dashboard panels
- MS Word and PDF project report
- requirements.txt and README.md"
```

---

### STEP 6 — Connect to GitHub and Push

Replace `YOUR-USERNAME` with your actual GitHub username:

```bash
# Set the remote origin to your GitHub repository
git remote add origin https://github.com/YOUR-USERNAME/enterprise-siem-lab.git

# Rename the default branch to 'main'
git branch -M main

# Push to GitHub
git push -u origin main
```

You will be prompted to sign in to GitHub.  
**Choose:** "Sign in with your browser" — this opens GitHub authentication automatically.

---

### STEP 7 — Verify on GitHub

1. Visit: `https://github.com/YOUR-USERNAME/enterprise-siem-lab`
2. You should see:
   - ✅ `README.md` rendered as the homepage
   - ✅ All files listed in the file tree
   - ✅ Commit message visible

---

### STEP 8 — Update README.md Badge URL

Once your repo is live, open [`README.md`](README.md) and replace the placeholder in the **Setup** section:

Find:
```markdown
git clone https://github.com/<your-username>/enterprise-siem-lab.git
```

Replace with your actual URL:
```markdown
git clone https://github.com/YOUR-USERNAME/enterprise-siem-lab.git
```

Then push the update:
```bash
git add README.md
git commit -m "docs: update clone URL in README"
git push
```

---

## 🔁 How to Push Future Changes

Whenever you update a file:

```bash
# Stage the changed file(s)
git add <filename>

# Or stage everything changed
git add .

# Commit with a descriptive message
git commit -m "feat: add alert enrichment module"

# Push to GitHub
git push
```

---

## 📌 Recommended Repository Settings

After creating the repo, configure these in **Settings → General**:

| Setting | Recommended Value |
|---------|------------------|
| **Topics / Tags** | `siem`, `wazuh`, `elasticsearch`, `cybersecurity`, `python`, `docker`, `mitre-attack` |
| **Website** | Leave blank or add your LinkedIn |
| **Releases** | Create a release tagged `v1.0.0` after your initial push |

To add topics — click the ⚙️ gear icon next to "About" on your repo homepage.

---

## 🏷️ Create a Release Tag (Optional but Recommended)

```bash
# Tag the initial release
git tag -a v1.0.0 -m "Enterprise SIEM Lab v1.0.0 — Initial release"

# Push the tag to GitHub
git push origin v1.0.0
```

Then on GitHub: **Releases → Draft a new release → Choose tag v1.0.0 → Publish release**

---

## 🔒 If Your Repository is Private

To share with a supervisor or evaluator:

1. Go to **Settings → Collaborators**
2. Click **"Add people"**
3. Enter their GitHub username or email
4. Set role: **Read** (view-only) or **Write** (can edit)

---

## 🆘 Troubleshooting

| Problem | Solution |
|---------|----------|
| `git` not recognised | Install Git from https://git-scm.com/download/win and restart PowerShell |
| Authentication failed | Use `git config --global credential.helper manager` then retry push |
| `remote origin already exists` | Run `git remote set-url origin https://github.com/YOUR-USERNAME/enterprise-siem-lab.git` |
| Large file rejected (>100 MB) | Check with `git ls-files --others` — ensure large files are in `.gitignore` |
| `.gitignore` not working | Run `git rm -r --cached .` then `git add .` to reset tracking |
| Push rejected (non-fast-forward) | Run `git pull --rebase origin main` then `git push` |

---

## 📎 Final Repository URL Format

```
https://github.com/YOUR-USERNAME/enterprise-siem-lab
```

Share this link as your **GitHub repository submission answer**.

---

<div align="center">
  <sub>Enterprise SIEM Lab &nbsp;|&nbsp; Author: Ayan Dutta &nbsp;|&nbsp; GitHub Setup Guide</sub>
</div>
