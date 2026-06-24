# BG-Files
Drop a ZIP or RAR onto BG Files, hit Run — it extracts the archive, finds the main executable automatically, skips junk folders like CommonRedist, launches the app and creates a Desktop shortcut. No installation needed, just download and open.
Extract archives and launch the app inside with one click.

## Download & Run

1. Download **[BGFiles.exe](../../releases/latest/download/BGFiles.exe)**
2. Double-click it — BG Files opens immediately, no installation needed

## Requirements

- Windows 10 / 11
- WinRAR or 7-Zip (for `.rar` / `.7z` — `.zip` works out of the box)
## ⚠️ Windows Defender may flag this file — here's why it's safe

Some antivirus programs, including Windows Defender, may show a warning when you open `BGFiles.exe`. **This is a false positive** — the file contains no malware of any kind.

**Why does it happen?**

`BGFiles.exe` is a self-extracting archive (SFX) built with WinRAR that runs a PowerShell script. Antivirus software uses heuristic detection — it looks at *how* a file behaves, not just *what* it does. Because:

- SFX executables that silently extract files are a technique sometimes used by malware
- PowerShell scripts launched with `-ExecutionPolicy Bypass` are flagged as suspicious by default
- The file has no digital signature (code signing certificates cost hundreds of euros per year)

...the antivirus engine raises an alert even though the script does nothing harmful.

**What does BGFiles.exe actually do?**

It extracts three plain text files (`BGFiles.ps1`, `BGFiles.vbs`, `BGFiles.ico`) into a temporary folder and opens the app. You can inspect the full source code of every file directly in this repository — nothing is hidden.

**What can you do?**

- Add an exclusion for the file in Windows Defender (Settings → Virus & threat protection → Exclusions)
- Or download the source files directly from this repo and run `BGFiles.vbs` manually — no warnings at all
