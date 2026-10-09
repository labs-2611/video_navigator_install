# Video Navigator downloads

Public Windows installers and release metadata for Video Navigator by 2611 Labs.

[Download a release](https://github.com/labs-2611/video_navigator_install/releases)

Choose the Windows x64 file ending in `setup.exe`, or extract the entire portable ZIP. Releases include the .NET runtime and LibVLC playback engine. Windows 10 version 2004 or later and Windows 11 are supported. Run a newer installer to upgrade an existing per-user installation.

The current alpha introduces **Share Review**, which saves a navigator project and creates a direct link to [Reviewinator](https://reviewinator.2611labs.com/). Put the saved project and its videos in the shared folder used to create the link. Web playback opens directly into presentation mode.

## Verify downloads

Each release includes a `.sha256` checksum file and `update.json`. Check the downloaded file's SHA-256 against its release before installation:

```powershell
Get-FileHash .\VideoNavigator-0.1.0-alpha.3-win-x64-setup.exe -Algorithm SHA256
```

These test releases are unsigned. Windows may display an unknown-publisher notice.

## Update metadata

`latest.json` points to the most recently published release in this repository. Its stable URL is:

`https://raw.githubusercontent.com/labs-2611/video_navigator_install/main/latest.json`

Schema version 1 includes `product`, `version`, `channel` (`alpha` or `stable`), `publishedAt`, `releaseUrl`, `sourceCommit`, `minimumWindowsVersion`, and `assets`. Each asset records `kind` (`installer` or `portable`), `platform`, `architecture`, `fileName`, immutable `url`, `bytes`, and `sha256`. Future update clients should compare semantic versions, respect the release channel, and verify the checksum before installing. The current desktop app does not automatically check or install updates.

Installer binaries are available as GitHub Release assets. This repository contains download documentation and update metadata.
