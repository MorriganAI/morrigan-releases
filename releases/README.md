# Release Assets Directory

This directory can be used to store release-related files and documentation.

## Structure

```
releases/
├── templates/          # Release note templates
├── checksums/          # SHA256 checksum files
└── archives/           # Historical release information
```

## Usage

When preparing a release:

1. Build all platform-specific binaries
2. Generate SHA256 checksums for all binaries
3. Prepare release notes using the templates
4. Upload assets to GitHub Releases

## Checksum Generation

Generate checksums for release assets:

```bash
# Linux/macOS
sha256sum morrigan-client-* > checksums-SHA256.txt

# Windows (PowerShell)
Get-FileHash morrigan-client-* -Algorithm SHA256 | Format-List
```

## Asset Naming Convention

Use the following naming convention for release assets:

- **Windows**: `morrigan-client-{version}-windows-{arch}.{ext}`
  - Example: `morrigan-client-1.0.0-windows-x64.exe`
- **macOS**: `morrigan-client-{version}-macos-{arch}.{ext}`
  - Example: `morrigan-client-1.0.0-macos-universal.dmg`
- **Linux**: `morrigan-client-{version}-linux-{arch}.{ext}`
  - Example: `morrigan-client-1.0.0-linux-x64.deb`

Where:
- `{version}` is the semantic version (e.g., 1.0.0)
- `{arch}` is the architecture (x64, arm64, universal, etc.)
- `{ext}` is the file extension (exe, dmg, deb, rpm, AppImage, etc.)
