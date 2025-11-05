# Release Process

This document describes the process for creating and managing releases of Morrigan client applications.

## Overview

This repository serves as the central location for distributing Morrigan client application releases. All official releases are published here with proper versioning, release notes, and downloadable assets.

## Versioning

We follow [Semantic Versioning](https://semver.org/) (SemVer):

- **MAJOR** version when you make incompatible API changes
- **MINOR** version when you add functionality in a backward compatible manner
- **PATCH** version when you make backward compatible bug fixes

Format: `vMAJOR.MINOR.PATCH` (e.g., `v1.2.3`)

## Creating a Release

### Manual Release Process

1. **Prepare the Release**
   - Update CHANGELOG.md with all changes for this version
   - Ensure all code is merged and tested
   - Verify version numbers in application code match the intended release version

2. **Create a Git Tag**
   ```bash
   git tag -a v1.0.0 -m "Release version 1.0.0"
   git push origin v1.0.0
   ```

3. **Create GitHub Release**
   - Go to the [Releases page](../../releases)
   - Click "Draft a new release"
   - Select the tag you just created
   - Fill in the release title (e.g., "Morrigan Client v1.0.0")
   - Add release notes from CHANGELOG.md
   - Upload compiled binaries and assets
   - Mark as pre-release if applicable
   - Publish the release

### Automated Release Process (Future)

A GitHub Actions workflow can be set up to automate parts of this process:
- Automatic changelog generation from commit messages
- Building and packaging release assets
- Creating draft releases automatically from tags

## Release Assets

Each release should include:

- **Windows**: `.exe` installer or `.zip` archive
- **macOS**: `.dmg` or `.pkg` installer
- **Linux**: `.deb`, `.rpm`, or `.AppImage` packages
- **Source Code**: Automatically included by GitHub
- **Checksums**: SHA256 checksums for all binary assets

## Release Notes Template

Use this template for release notes:

```markdown
## What's New

[Brief description of the release]

### Features
- [New feature 1]
- [New feature 2]

### Bug Fixes
- [Bug fix 1]
- [Bug fix 2]

### Improvements
- [Improvement 1]
- [Improvement 2]

## Installation

[Platform-specific installation instructions]

## Upgrade Notes

[Any important notes for users upgrading from previous versions]

## Known Issues

[List any known issues in this release]

## Full Changelog

[Link to full changelog]
```

## Pre-release Versions

For alpha, beta, or release candidate versions, use the following format:
- Alpha: `v1.0.0-alpha.1`
- Beta: `v1.0.0-beta.1`
- Release Candidate: `v1.0.0-rc.1`

Always mark these as "pre-release" in GitHub.

## Hotfix Releases

For critical bug fixes:
1. Create a hotfix branch from the release tag
2. Apply the fix
3. Increment the PATCH version
4. Follow the standard release process

## Support Policy

- Latest major version: Full support
- Previous major version: Security updates only
- Older versions: No support

## Questions

For questions about the release process, please open an issue in this repository.
