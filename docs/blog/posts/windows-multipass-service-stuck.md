---
date:
  created: 2025-06-21
categories:
  - Technology
tags:
  - Multipass
  - Windows
---

# (Windows) Multipass Service Stuck

In some cases, the Multipass service on Windows can get stuck, preventing you from starting or stopping it properly. If you encounter this issue, follow these steps to resolve it:
<!-- more -->

## Step 1: Check for stuck processes

Open Task Manager `(Ctrl+Shift+Esc)`, look for any `multipassd.exe` or related Multipass processes, and end them manually.

## Step 2: Force kill the service

Find the PID of the Multipass service by running as an administrator in PowerShell:

```powershell
Get-WmiObject win32_service | Where-Object { $_.Name -eq "Multipass" } | Select-Object ProcessId
Stop-Process -Id <PID> -Force
```

## Step 3: Restart the Multipass service

```powershell
Restart-Service Multipass
```

## Step 4: (Optional) Reboot your computer if the service is still stuck after the above steps.
