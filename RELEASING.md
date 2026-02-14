# Release Instructions

This project uses GitHub Actions to automatically build and publish releases for multiple platforms.

## Creating a Release

1. **Update version in Cargo.toml**
   ```toml
   version = "0.3.3"  # Bump version
   ```

2. **Commit the version bump**
   ```bash
   git add Cargo.toml
   git commit -m "Bump version to 0.3.3"
   ```

3. **Create and push a tag**
   ```bash
   git tag v0.3.3
   git push origin v0.3.3
   ```

4. **GitHub Actions will automatically:**
   - Build binaries for:
     - Linux x86_64
     - Linux ARM64 (aarch64)
     - macOS x86_64 (Intel)
     - macOS ARM64 (Apple Silicon)
   - Create a GitHub Release
   - Upload all binaries with checksums
   - Generate release notes from commits

5. **Release will be available at:**
   ```
   https://github.com/Twsts/roon-tui/releases
   ```

## Installing from Release

Users can download and install like this:

```bash
# Download for your platform
curl -LO https://github.com/Twsts/roon-tui/releases/latest/download/roon-tui-linux-x86_64

# Make executable
chmod +x roon-tui-linux-x86_64

# Move to PATH
sudo mv roon-tui-linux-x86_64 /usr/local/bin/roon-tui

# Or for local install
mkdir -p ~/.local/bin
mv roon-tui-linux-x86_64 ~/.local/bin/roon-tui
```

## Platforms

- **roon-tui-linux-x86_64** - Linux 64-bit (Intel/AMD)
- **roon-tui-linux-aarch64** - Linux ARM64 (Raspberry Pi, etc.)
- **roon-tui-macos-x86_64** - macOS Intel
- **roon-tui-macos-aarch64** - macOS Apple Silicon (M1/M2/M3)

## Vim Keybindings Feature

This fork includes custom vim-style keybindings:
- `Ctrl+J/K` - Volume down/up
- `Ctrl+H/L` - Previous/next track
- `Ctrl+T` - Help (moved from Ctrl+H)

All original keybindings still work.
