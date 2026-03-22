# NMT Hunter - Silent Miner Hunter

NMT Hunter is a security tool designed to detect and remove cryptocurrency miners, backdoors, and other threats on Windows systems. The program combines multiple detection techniques including process analysis, registry monitoring, file scanning, service analysis, and YARA signature matching.

## System Requirements

- Windows 7 / 8 / 10 / 11 (64-bit or 32-bit)
- 100 MB free disk space
- Administrator privileges recommended for full functionality

## Installation

1. Download the latest release from the [Releases](https://github.com/AGaevskiy/NMT-Hunter---Silent-Miner-Hunter/releases) page.
2. Extract the archive to any folder.
3. Run `nmt-hunter.exe`.

The program does not require installation; all files are located in the folder with the executable.

## Project Structure
NMT-Hunter/
├── nmt-hunter.exe # Executable file
├── data/ # Configuration folder
│ └── whitelist.json # Whitelist of trusted files
├── logs/ # Scan logs (created automatically)
└── rules/ # YARA rules folder (optional)

text

## Usage

### Interactive Mode

Run the program without parameters to enter the interactive menu:
nmt-hunter.exe

text

The menu provides the following options:

1. **Scan Processes** – Analyze running processes  
2. **Scan Registry** – Check autorun and system policies  
3. **Scan Files** – Full disk file scanning  
4. **Scan Services** – Analyze Windows services  
5. **Full Scan** – Execute all scanning modules  
6. **Clean Threats** – Remove detected threats  
7. **Fix Registry** – Restore security settings  
8. **System Information** – Display system details  
9. **Last Scan Results** – View previous scan results  
0. **Update Databases** – Download latest whitelist  
H. **Help** – Display help information  
X. **Exit** – Exit the program  

### Command Line Options

| Parameter | Description |
|-----------|-------------|
| `--scan`, `-s` | Quick scan (processes only) |
| `--full`, `-f` | Full system scan |
| `--clean`, `-c` | Scan and clean threats |
| `--processes`, `-p` | Scan only processes |
| `--registry`, `-r` | Scan only registry |
| `--files`, `-fl` | Scan only files |
| `--services`, `-sv` | Scan only services |
| `--status`, `-i` | System information |
| `--version`, `-v` | Program version |
| `--help`, `-h` | Help information |

### Usage Examples

Interactive mode:
nmt-hunter.exe

text

Quick scan:
nmt-hunter.exe --scan

text

Full system scan:
nmt-hunter.exe --full

text

Scan and clean:
nmt-hunter.exe --clean

text

System information:
nmt-hunter.exe --status

text

## Threat Levels

| Level | Description | Score |
|-------|-------------|-------|
| APT | Targeted attack, advanced malware | 10 |
| CRITICAL | Critical threat, immediate action required | 9 |
| HIGH | High risk, intervention needed | 7–8 |
| MEDIUM | Suspicious behavior | 4–6 |
| LOW | Minor indicators | 2–3 |
| INFO | Informational message | 1 |

## Output Symbols

| Symbol | Meaning |
|--------|---------|
| `[!!!]` | Threat detected |
| `[+]` | Operation successful |
| `[x]` | Error occurred |
| `[!]` | Warning |
| `[#]` | Status information |

## Whitelist (whitelist.json)

The whitelist contains trusted paths, file names, and signatures. The program ignores files from this list, reducing false positives.

The whitelist automatically updates from GitHub when internet is available. You can also manually update it through the menu (option 0).

To add your own exceptions, edit `data/whitelist.json`:

```json
{
  "trusted_paths": ["C:\\MyFolder\\"],
  "trusted_names": ["myprogram.exe"],
  "trusted_signers": ["My Company"]
}
```

Restart the program.
Rules will be applied during file and process scanning.

Logging
All scans are recorded in the logs folder. Log files are formatted as:

text
NMT_Hunter_YYYYMMDD_HHMMSS.log
Logs contain:

Recommendations
Run as Administrator – Required for full functionality (process termination, file deletion)
Regular Scans – Perform full scans weekly
Update Databases – Periodically update the whitelist through the menu
Review Results – Check detected threats before cleaning

Disclaimer
This tool is intended for legitimate use. Use the program only on systems you own or have permission to scan. The authors are not responsible for any damage caused by the use or misuse of this software.
