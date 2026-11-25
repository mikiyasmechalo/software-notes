# Maintenance & Architecture Guide: Miki's Course Notes

This guide explains how your automated Obsidian-to-Web publishing system works, how to use it daily, and how to maintain, pause, or roll it back.

---

## 1. System Architecture

```
+-------------------------------------------------------------+
|                     Obsidian Vault                          |
|  C:\Users\JustMikiy\Documents\Obsidian Vault\Study          |
+-------------------------------------------------------------+
                              |
                     Windows Junction (Live)
                              v
+-------------------------------------------------------------+
|                     Quartz Repository                       |
|  C:\Users\JustMikiy\Documents\vscode\software-notes\content |
+-------------------------------------------------------------+
                              |
               Scheduled Task (every 4 hours)
                  silent-sync.vbs -> sync-notes.ps1
                              v
+-------------------------------------------------------------+
|                     GitHub Repository                       |
|  https://github.com/mikiyasmechalo/software-notes           |
+-------------------------------------------------------------+
                              |
               GitHub Actions (deploy.yml)
                     npx quartz build
                              v
+-------------------------------------------------------------+
|                     Live Web Site                           |
|  https://mikiyasmechalo.github.io/software-notes            |
+-------------------------------------------------------------+
```

### Key Principles
1. **Zero Duplicate Copies:** The `Study` folder in Obsidian is a NTFS directory junction pointing directly into `software-notes\content`. There is only one copy on disk.
2. **Untouched Vault Folders:** Only `Study/` is linked and published. All other folders (`Daily Notes`, `Ideas`, `Learn`, `.obsidian`, etc.) are completely isolated.
3. **Automated Publishing:** A lightweight background job pushes changes every 4 hours silently without any console popup. GitHub Actions builds and updates the live site automatically.

---

## 2. Daily Workflow

### Writing Notes
- Simply open Obsidian and edit notes inside `Study` as you always have.
- Changes save instantly to disk and are picked up on the next 10-minute sync cycle.

### Adding New Notes
1. Create a markdown note inside the appropriate semester folder (e.g. `Study/BSc/Year-5-Sem-1/MyNewSubject.md`).
2. Add the standard frontmatter at the top:
   ```yaml
   ---
   title: Full Subject Name
   tags:
     - MNS
     - bsc
   ---
   ```
3. Add a link in `Study/index.md` so visitors can navigate to it from the homepage.

### Images and Diagrams
- Paste images directly into Obsidian (`Ctrl + V`). They are saved to `Study/images/` and automatically published.
- For Excalidraw diagrams, export as PNG and link them via `![[diagram.png]]`.

---

## 3. Automation & Sync Controls

The background synchronization runs via Windows Task Scheduler task named **`PublishSoftwareNotes`**.

### Sync Script Location
`C:\Users\JustMikiy\Documents\vscode\notes-site-tools\sync-notes.ps1`

### Execution Log
`C:\Users\JustMikiy\Documents\vscode\notes-site-tools\sync.log`

### Useful PowerShell Commands

- **Run an immediate sync now:**
  ```powershell
  powershell -ExecutionPolicy Bypass -File "C:\Users\JustMikiy\Documents\vscode\notes-site-tools\sync-notes.ps1"
  ```

- **Check task status:**
  ```powershell
  Get-ScheduledTask -TaskName "PublishSoftwareNotes"
  ```

- **Temporarily pause auto-sync (e.g., during major rewrites):**
  ```powershell
  Disable-ScheduledTask -TaskName "PublishSoftwareNotes"
  ```

- **Resume auto-sync:**
  ```powershell
  Enable-ScheduledTask -TaskName "PublishSoftwareNotes"
  ```

---

## 4. Local Preview & Testing

To test site changes or preview notes locally in your browser before they go live:

1. Open PowerShell in the repo directory:
   ```powershell
   cd "C:\Users\JustMikiy\Documents\vscode\software-notes"
   ```
2. Start the local preview server:
   ```powershell
   npx quartz build --serve
   ```
3. Open your browser at: `http://localhost:8080/software-notes`
4. Press `Ctrl + C` in PowerShell to stop the server when done.

---

## 5. Starting a New Semester

When a new university semester begins:
1. In Obsidian, create the new semester folder under `Study/BSc/` or `Study/MSc/` (e.g. `Study/BSc/Year-5-Sem-2`).
2. Update `Study/index.md`:
   - Move the previous semester's links into an archived callout (`> [!note]- Previous Semester`).
   - Add the new semester under **Current Semesters**.
3. Save the note. The background job will push the updates to GitHub.

---

## 6. Re-enabling Mobile Sync (Nectarlink)

If you re-enable Nectarlink to sync Obsidian with your mobile phone:
> [!WARNING]
> Before re-enabling sync rules, delete or update the old `Study` folder on your **phone** so it matches the new semester folder structure (`BSc/`, `MSc/`, `images/`). If the phone still contains the old flat files, Nectarlink will push old loose copies back into your vault.

---

## 7. Emergency Rollback

If you ever wish to completely disconnect the website and revert Obsidian to its exact pre-migration state:

1. Close Obsidian.
2. Remove the junction and move back the untouched pre-migration folder:
   ```cmd
   rmdir "C:\Users\JustMikiy\Documents\Obsidian Vault\Study"
   move "C:\Users\JustMikiy\Documents\Study_pre-migration" "C:\Users\JustMikiy\Documents\Obsidian Vault\Study"
   ```
3. Disable the Task Scheduler job:
   ```powershell
   Unregister-ScheduledTask -TaskName "PublishSoftwareNotes" -Confirm:$false
   ```
4. An additional independent pre-migration backup is stored at:
   `C:\Users\JustMikiy\Documents\Obsidian Vault - Copy\Study`
