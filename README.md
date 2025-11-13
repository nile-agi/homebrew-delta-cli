# Delta CLI Homebrew Tap

Simple installation of Delta CLI via Homebrew.

## Quick Install

```bash
brew tap nile-agi/delta-cli && brew install --HEAD nile-agi/delta-cli/delta-cli
```

**Important:** 
- Use `--HEAD` flag because the formula uses the latest code from the main branch
- Use the full formula path `nile-agi/delta-cli/delta-cli` because Homebrew core has a package called `git-delta` that provides a `delta` command
- Everything is automatic - git cloning, building, and installation happen automatically
- Users don't need to know about git - it all happens behind the scenes

## What Happens During Installation

The installation is completely automatic:
- ✅ Automatically clones the repository (git happens in background)
- ✅ Automatically installs all dependencies (cmake, curl, pkg-config)
- ✅ Automatically builds from source (~40 seconds)
- ✅ Automatically configures PATH
- ✅ Creates alias to override conflicting commands

## Usage

After installation:

```bash
# Reload shell configuration (if needed)
source ~/.zshrc  # or restart terminal

# Check version
delta --version

# Download a model
delta pull qwen2.5:0.5b

# Start interactive mode
delta

# Start web server
delta server
```

## What Gets Installed

- `delta` - Main CLI application
- `delta-server` - Web server for browser interface
- Web UI (if available)

## Installation Location

- Binaries: `/opt/homebrew/bin/delta` (Apple Silicon) or `/usr/local/bin/delta` (Intel)
- Configuration: Automatically added to `~/.zshrc` or `~/.bash_profile`

## Troubleshooting

### Command Not Found

If `delta` command is not found after installation:

```bash
# Reload shell configuration
source ~/.zshrc

# Or use full path
/opt/homebrew/bin/delta --version
```

### PATH Conflicts

If you have another `delta` command (like llvm's delta), the installer automatically:
1. Configures PATH to prioritize Homebrew's bin directory
2. Creates an alias: `alias delta='/opt/homebrew/bin/delta'`

Just run `source ~/.zshrc` to activate.

## Uninstall

```bash
brew uninstall delta-cli
brew untap nile-agi/delta-cli
```

## More Information

- Project: https://github.com/nile-agi/delta
- Issues: https://github.com/nile-agi/delta/issues
- Documentation: https://github.com/nile-agi/delta/blob/main/README.md
