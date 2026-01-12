# System Optimization Prompt for Claude Code

A universal prompt template to optimize any computer using Claude Code. Works on **macOS**, **Linux**, and **Windows**.

---

## Quick Start

Copy and paste this prompt into Claude Code:

```
Analyze my computer and create a comprehensive optimization plan.

1. **Detect my system** - Identify my OS, hardware specs, and current state

2. **Audit everything**:
   - Memory usage and pressure
   - Disk space and what's consuming it
   - Swap/pagefile usage
   - Running services and background processes
   - Startup/login items
   - Network configuration

3. **Identify issues** - Find memory hogs, disk space wasters, unnecessary startup items, and performance bottlenecks

4. **Ask my preferences** before making changes:
   - How aggressive should optimization be? (conservative/balanced/aggressive)
   - Which startup items are essential to me?
   - Do I have services that should stay running vs start on-demand?
   - Should visual effects be reduced for performance?

5. **Optimize with my confirmation**:
   - Memory: Stop unnecessary services, reduce startup items
   - Disk: Clean package manager caches, temp files, logs, trash
   - Performance: Adjust animations and visual effects
   - Background: Disable unnecessary updaters and services
   - Network: Optimize DNS settings
   - Developer tools: Git, Node.js, Docker optimizations (if applicable)

6. **Generate a detailed report** with before/after metrics

7. **Provide rollback commands** for every change made

Ask me questions as you go. Don't make assumptions about what I need.
```

---

## Platform-Specific Prompts

### macOS

```
Optimize my Mac for best performance.

Analyze and optimize:
- Memory pressure and swap usage
- Disk space (check Docker, npm, Homebrew, Xcode, caches)
- Login items and launch agents
- Homebrew services (databases, etc.)
- System animations and transparency
- DNS settings

Ask before making changes. Provide rollback commands. Generate a report.
```

### Linux (Ubuntu/Debian)

```
Optimize my Linux system for best performance.

Analyze and optimize:
- Memory and swap usage
- Disk space (check apt cache, snap, flatpak, Docker, logs)
- Systemd services and startup applications
- Journal logs size
- Package manager cleanup
- DNS settings

Ask before making changes. Provide rollback commands. Generate a report.
```

### Windows

```
Optimize my Windows PC for best performance.

Analyze and optimize:
- Memory and pagefile usage
- Disk space (check temp files, Windows Update cache, package managers)
- Startup programs and scheduled tasks
- Background services
- Visual effects settings
- DNS settings

Ask before making changes. Provide rollback commands. Generate a report.
```

---

## Use-Case Specific Prompts

### For Developers

```
Optimize my system for development work.

Focus on:
- Development caches (npm, pip, cargo, maven, gradle, Docker)
- Database services (convert to on-demand if auto-starting)
- IDE caches and logs
- Git performance settings
- Container/VM resource usage
- Package manager cleanup

Keep my dev environment functional. Ask before removing anything.
```

### For Non-Technical Users

```
Help me speed up my computer. I'm not technical, so explain things simply.

Please:
1. Check why my computer might be slow
2. Find programs that start automatically that I might not need
3. Find files I can safely delete to free up space
4. Make the system feel faster

Ask me simple yes/no questions before deleting anything.
Explain what each thing does in plain language.
```

### For Maximum Performance

```
I want maximum performance. Be aggressive with optimizations.

1. Audit everything: memory, disk, processes, services
2. Disable ALL unnecessary startup items
3. Stop ALL background services I'm not actively using
4. Clear ALL safe-to-delete caches and temp files
5. Disable ALL unnecessary animations and visual effects
6. Optimize ALL developer tools (if present)

Ask for confirmation on destructive actions only. Generate a full report.
```

### For Disk Space Recovery Only

```
I'm running low on disk space. Find everything I can safely delete.

Check for:
- Package manager caches (npm, pip, apt, brew, chocolatey, etc.)
- Container/Docker data
- IDE and editor caches
- System logs and temp files
- Old downloads
- Trash/recycle bin
- Duplicate files

Show me sizes before deleting. Ask before each major deletion.
```

### For Memory Issues Only

```
My computer is running slow due to memory issues. Help me fix it.

1. Check current memory usage and swap/pagefile
2. Identify memory-hungry processes
3. Find services running that don't need to be
4. Review startup items consuming RAM
5. Suggest apps to close or replace with lighter alternatives

Focus only on memory - don't touch disk or other settings.
```

---

## What Gets Optimized

| Area | macOS | Linux | Windows |
|------|-------|-------|---------|
| **Package Caches** | Homebrew, npm | apt, snap, npm | Chocolatey, npm |
| **Container Data** | Docker Desktop | Docker | Docker Desktop, WSL |
| **IDE Caches** | VS Code, Xcode | VS Code, JetBrains | VS Code, Visual Studio |
| **System Logs** | ~/Library/Logs | /var/log, journald | Event logs |
| **Temp Files** | /tmp, caches | /tmp, ~/.cache | %TEMP%, prefetch |
| **Startup Items** | Login Items | systemd, autostart | Startup folder, registry |
| **Services** | launchd, brew services | systemd | Windows services |
| **Animations** | Dock, Mission Control | Compositor | Windows effects |

---

## Safety Features

The prompts are designed to:

- **Ask before deleting** - No destructive actions without your confirmation
- **Explain changes** - You understand what each optimization does
- **Provide rollback** - Commands to undo every change
- **Preserve essentials** - Won't break your workflow or system

---

## Prerequisites

- [Claude Code](https://claude.ai/code) installed
- Terminal/command line access
- Admin/sudo password (some optimizations require elevated privileges)

---

## Example Session

```
You: [paste the Quick Start prompt]

Claude: I'll analyze your system. Let me detect your OS and gather information...

[Claude runs diagnostic commands]

Claude: You're running macOS on a MacBook Pro with 16GB RAM. I found:
- Memory: 85% used, 8GB swap (high)
- Disk: 450GB total, only 20GB free
- Startup: 8 apps launching at login
- Services: 3 databases auto-starting

Questions:

1. How aggressive should I be?
   □ Conservative - minimal changes
   □ Balanced - reasonable optimization
   □ Aggressive - maximum performance

2. Which startup apps do you need?
   [lists apps found]

3. Should databases start on-demand instead of at boot?

[You answer]

Claude: Optimizing now...
[performs actions with your approval]

Claude: Done! Results:
- Disk recovered: 25GB
- Memory freed: 3GB
- Startup items: 8 → 2
- Boot time will be faster

Reboot recommended to apply all changes.
```

---

## Common Rollback Commands

### macOS
```bash
# Restore Dock animations
defaults delete com.apple.dock autohide-delay
killall Dock

# Restore DNS
networksetup -setdnsservers Wi-Fi "Empty"

# Re-enable a service
brew services start <service-name>
```

### Linux
```bash
# Re-enable a service
sudo systemctl enable --now <service-name>

# Restore DNS
sudo systemctl restart systemd-resolved
```

### Windows (PowerShell)
```powershell
# Re-enable a service
Set-Service -Name "<service>" -StartupType Automatic
Start-Service -Name "<service>"

# Restore visual effects
SystemPropertiesPerformance.exe
```

---

## Tips

1. **Reboot after optimization** - Memory/swap clears on restart
2. **Run periodically** - Caches rebuild over time (monthly is good)
3. **Start services on-demand** - Don't auto-start what you don't always need
4. **Monitor resource usage** - Activity Monitor (mac), htop (linux), Task Manager (win)
5. **Keep browser tabs low** - Each tab consumes significant memory

---

## Troubleshooting

**"Permission denied" errors**
- Some commands need admin/sudo - Claude will guide you

**"Service/command not found"**
- You may not have that software installed - safe to ignore

**Disk space didn't increase immediately**
- Running apps hold files open - reboot to reclaim fully

**Something broke**
- Use rollback commands provided in your optimization report
- Ask Claude to undo specific changes

---

## Contributing

Found improvements? Contributions welcome.

---

*Works with Claude Code on macOS, Linux, and Windows. Optimizations are detected and applied based on your specific system.*
