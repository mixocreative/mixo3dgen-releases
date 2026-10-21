# 3DGEN

3DGEN turns photos into 3D models on your own Windows PC, with Pixal3D (best quality, from several sides) or TripoSR
(fast, one photo). Your photos and models stay on your computer.
**Free** for any lawful use, including commercial work. No account, no payment.

This repository holds the **release files only**. The source code is not published here.

## Install (one line)

Open **Windows PowerShell** (Start menu, type `PowerShell`) and paste:

```powershell
irm https://github.com/mixocreative/mixo3dgen-releases/releases/latest/download/install.ps1 | iex
```

The installer asks where to install (default `C:\3DGEN`), downloads `3DGEN-<version>.zip` from the
[latest release](https://github.com/mixocreative/mixo3dgen-releases/releases/latest), checks its SHA-256 against
`SHA256SUMS.txt`, and installs nothing if they differ. Running the line again updates 3DGEN and keeps your settings,
models and results. No administrator rights are needed for 3DGEN itself.

Needs Windows 10 or 11 (64-bit). An NVIDIA graphics card is recommended; the Pixal3D engine needs one with 8 GB or more.

## How it works

Nothing is built on your PC. The installer downloads the ready-made app (about 180 MB) and checks it. The app works
straight away with its built-in engine, offline. The AI engines are optional: you start them from **Setup** inside the
app, and your PC downloads each file from its own publisher and checks it before use (TripoSR a few GB; Pixal3D about
54 GB plus a small Linux part, which asks for administrator rights once).

## Check a download yourself

Each release has `SHA256SUMS.txt` with the SHA-256 of every file in it. In PowerShell, in the folder you downloaded to:

```powershell
Get-FileHash .\3DGEN-0.1.0.zip -Algorithm SHA256
```

The hash must equal the line for that file in `SHA256SUMS.txt` (case does not matter).

## Licence and privacy

- Licence (shown again on first start): `EULA.md` inside the zip, English and Traditional Chinese. 3DGEN is provided
  free by Mixo Creative Ltd. (明上堂有限公司), Taiwan.
- The AI engines and their model files are downloaded by your PC from their own publishers (PyPI, python.org, PyTorch,
  conda-forge, Hugging Face, GitHub, and for Pixal3D Microsoft and Canonical), each under its own licence: see
  `THIRD_PARTY_NOTICES.md` and the `licenses` folder in the zip.
- A few parts with a non-commercial licence are optional, off by default, and need your one-click agreement.
- Privacy: `PRIVACY.md` in the zip. 3DGEN sends nothing to us and has no tracking. Photos, chats and phone scans stay on
  your PC (a phone scan stays in the phone's browser until you send it); the phone link goes through Cloudflare, with
  the free address or your own, only if you turn it on.

## The other files in a release

`<component>-lock.json` are the download lists 3DGEN reads to find more download addresses for a file it already
knows by its SHA-256. They cannot change which files are installed or their hashes.

## Report a problem

Open an [issue](https://github.com/mixocreative/mixo3dgen-releases/issues/new) or e-mail mixocreative@gmail.com. Please
include the error code shown on the card (for example `3DG-GPU-001`) and, if you can, the support file from
**Save support file** (it holds technical facts about your PC and the install, never your photos or models). Do not
post your passcode or phone link in a public issue.
