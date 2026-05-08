# Emergency MTU Tester
Version: 1.0.0  
Author: Valdis B.  
License: MIT License  
Platform: Windows 10 / Windows 11 (PowerShell 5+ / PowerShell 7+)

## Overview
Emergency MTU Tester is a lightweight, brute‑force MTU diagnostic tool designed for abnormal or emergency network situations.  
It tests MTU values using fragmentation‑aware ICMP probing and applies the discovered MTU only if a valid value is found.

This tool does **not** save configuration files and does **not** perform long‑term optimization.  
It is intended strictly for temporary troubleshooting when the network is severely degraded or non‑functional.

## Features
- Brute‑force MTU discovery using `ping -f -l`
- Detects the highest non‑fragmenting MTU value
- Applies MTU to both IPv4 and IPv6
- Requires administrator rights
- No files created, no telemetry, no internet downloads
- Fully portable and safe to run from clipboard or .ps1 file

## Important Notes
- **This is an emergency tool.**  
  It is not meant for daily use or long‑term MTU optimization.
- No `.ini` or configuration files are written.
- MTU is applied only if a valid value is found.
- If no valid MTU is detected, no changes are made.
- A reboot is not required, but some adapters may apply changes after restart.

## Requirements
- Windows 10 or Windows 11  
- PowerShell 5.0 or newer (including PowerShell 7)  
- Administrator privileges

## How It Works
1. Detects the first active IPv4 network adapter  
2. Tests MTU payload sizes from 1472 down to 1172 bytes  
3. Uses ICMP fragmentation responses to determine the maximum valid MTU  
4. If successful, applies MTU persistently to:
   - IPv4  
   - IPv6  
5. Displays results and waits for user confirmation before exit

## Usage
1. Save as `Emergency-MTU-Tester.ps1`  
   or run directly from clipboard  
2. Start PowerShell **as Administrator** 
3. Run the script  
4. Follow on‑screen output  
5. Press ENTER to exit

## Changelog

## Support
If you find this project useful, support it here:
https://paypal.me/ValdisBerzinsh

### 1.0.0
- Initial release
