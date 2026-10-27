# 3DGEN

3DGEN turns photos into 3D models on your own Windows PC, with Pixal3D (best quality, from several sides) or TripoSR
(fast, one photo). Your photos and models stay on your computer.
**Free** for any lawful use, including commercial work. No account, no payment.

This repository holds the **release files only**. The source code is not published here.

Needs Windows 10 or 11 (64-bit). An NVIDIA graphics card is recommended; the Pixal3D engine needs one with 8 GB or more.

## 1. Install

1. Click **Start**, type `PowerShell`, and open **Windows PowerShell**.
2. Copy this line, paste it into the blue window (right-click pastes), and press **Enter**:
   ```powershell
   irm https://github.com/mixocreative/mixo3dgen-releases/releases/latest/download/install.ps1 | iex
   ```
3. Answer its two questions: where to install (press **Enter** for `C:\3DGEN`) and whether to add shortcuts (type `y`).
4. Wait until it says **Done**. No administrator rights are needed.

The installer downloads `3DGEN-<version>.zip` from the
[latest release](https://github.com/mixocreative/mixo3dgen-releases/releases/latest), checks its SHA-256 against
`SHA256SUMS.txt`, and installs nothing if they differ.

## 2. Open

Double-click **3DGEN** on your desktop. Without shortcuts, open the file the installer named at the end (for example
`C:\3DGEN\3DGEN\3DGEN.exe`). The first time, read and accept the licence. Then
press **Make a 3D model**. It works straight away with the built-in engine; the better AI engines are one click each in
**Setup**.

## 3. Update

Run the same line from step 1 again. It keeps your settings, models and results.

## 4. Remove

Close 3DGEN (also from its icon by the clock), then delete the `C:\3DGEN` folder and the two **3DGEN** shortcuts. If you
turned on "Start 3DGEN when Windows starts", turn it off in 3DGEN before deleting. If you installed Pixal3D, also
run `wsl --unregister 3DGEN-Pixal3D` in PowerShell to delete its Linux part.

## How it works

Nothing is built on your PC. The installer downloads the ready-made app (about 180 MB) and checks it. The app works
straight away with its built-in engine, offline. The AI engines are optional: you start them from **Setup** inside the
app, and your PC downloads each file from its own publisher and checks it before use (TripoSR a few GB; Pixal3D about
54 GB plus a small Linux part, which asks for administrator rights once).

## Check a download yourself

Each release has `SHA256SUMS.txt` with the SHA-256 of every file in it. In PowerShell, in the folder you downloaded to:

```powershell
Get-FileHash .\3DGEN-1.0.0.zip -Algorithm SHA256
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
