# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Purpose

This is a **public distribution mirror** for Konvilo desktop installer artifacts. It contains no application source code — the actual source lives in the private Macroza/DrStone repository. Installer binaries (.msi, .exe, .dmg, .deb, .rpm) are auto-published here by a CI/CD pipeline triggered on `qa-v*` tags in the private repo.

## Repository Structure

There are no build scripts, test suites, or source files here. The repository exists solely to host GitHub Releases that end users can download from.

## Release Workflow

Releases are created automatically when a `qa-v*` tag is pushed in the private Macroza/DrStone repository. Manual intervention should be rare; if you need to add or correct a release, use the GitHub CLI:

```sh
# List existing releases
gh release list

# Create a release manually (only if the pipeline cannot)
gh release create <tag> <artifacts...> --title "<title>" --notes "<notes>"

# Upload additional assets to an existing release
gh release upload <tag> <file>

# Delete a bad release
gh release delete <tag>
```
