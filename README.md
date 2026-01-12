# CC System Optimizer

A universal system optimization prompt for [Claude Code](https://claude.ai/code). Automatically analyzes and optimizes your computer for better performance.

## Supported Platforms

- macOS
- Linux (Ubuntu, Debian, Fedora, Arch, etc.)
- Windows

## What It Does

- Audits memory, disk, swap, and running processes
- Identifies performance bottlenecks
- Cleans package manager caches (npm, pip, brew, apt, etc.)
- Removes unnecessary startup items
- Converts services to on-demand startup
- Optimizes system animations and visual effects
- Configures faster DNS
- Tunes developer tools (Git, Node.js, Docker)

## Quick Start

1. Install [Claude Code](https://claude.ai/code)
2. Open your terminal
3. Run `claude`
4. Paste this prompt:

```
Analyze my computer and create a comprehensive optimization plan.

1. Detect my system - Identify my OS, hardware specs, and current state
2. Audit everything: memory, disk, swap, services, startup items
3. Identify issues - Find memory hogs, disk wasters, unnecessary processes
4. Ask my preferences before making changes
5. Optimize with my confirmation
6. Generate a detailed report with before/after metrics
7. Provide rollback commands for every change made

Ask me questions as you go. Don't make assumptions about what I need.
```

## More Prompts

See [prompt.md](prompt.md) for:

- Platform-specific prompts (macOS, Linux, Windows)
- Developer-focused optimization
- Non-technical user prompts
- Aggressive mode for maximum performance
- Disk-only or memory-only optimization
- Rollback commands for all platforms

## Safety

- Always asks before making changes
- Explains what each optimization does
- Provides rollback commands for everything
- Never deletes personal files

## Typical Results

| Metric | Improvement |
|--------|-------------|
| Disk Space | 10-30 GB recovered |
| Startup Time | 30-50% faster |
| Memory Usage | 1-4 GB freed |
| Swap/Pagefile | 50-80% reduction |

## License

MIT

---

*Created with Claude Code*
