# 3DGEN

3DGEN turns photos into 3D models on your own Windows PC, with Pixal3D (best quality, from several sides) or TripoSR
(fast, one photo). Your photos and models stay on your computer.
**Free** for any lawful use, including commercial work. No account, no payment.

This repository holds the **release files only**. The source code is not published here.

Needs Windows 10 or 11 (64-bit). An NVIDIA graphics card is recommended. The Pixal3D engine needs an NVIDIA card with
8 GB or more, 16 GB of RAM and 100 GB free on the drive you choose for it.

## 1. Install

1. Click **Start**, type `PowerShell`, and open **Windows PowerShell**.
2. Copy this line, paste it into the PowerShell window (**Ctrl + V**, or right-click), and press **Enter**:
   ```powershell
   irm https://github.com/mixocreative/mixo3dgen-releases/releases/latest/download/install.ps1 | iex
   ```
3. It asks where to install: press **Enter** for `C:\3DGEN`. It checks your PC and downloads about 180 MB.
4. It asks whether to add shortcuts: type `y` and press **Enter**.
5. Wait until it says **Done** in green. No administrator rights are needed. Yellow `NOTE` lines are information only:
   do not act on them (3DGEN's Setup handles everything the AI engines need). A red `ERROR` line means nothing was
   changed: read it, and if it does not help, see *Report a problem* below.

The installer downloads `3DGEN-<version>.zip` from the
[latest release](https://github.com/mixocreative/mixo3dgen-releases/releases/latest), checks its SHA-256 (a fingerprint
that proves the file is the real one) against `SHA256SUMS.txt`, and installs nothing if they differ.

## 2. Open

Double-click **3DGEN** on your desktop. Without shortcuts, double-click the file on the installer's `Run :` line in
File Explorer (for example `C:\3DGEN\3DGEN\3DGEN.exe`). The first time, read the licence to the end, tick, and accept.

Press **Make a 3D model**: it asks for photos, then what the model is for, then shows your model. It works straight
away, offline, with the **Built-in relief** engine. To add an AI engine, open **Status** and press **Set up →** next to
it. TripoSR downloads a few GB. Pixal3D downloads about 54 GB, asks once for administrator permission, and may restart
the PC.

## 3. Update

Close 3DGEN (see step 4). Run the same line from step 1 again. When it asks where to install, give the same folder as
the first time (press **Enter** if you used `C:\3DGEN`). It keeps your settings, results and engines.

## 4. Remove

1. If you turned on "Start 3DGEN when Windows starts", turn it off in 3DGEN's Settings.
2. Close 3DGEN: close its window, then find its icon by the clock (click the `^` arrow if you do not see it),
   right-click it and choose **Quit**.
3. If you installed Pixal3D, run `wsl --unregister 3DGEN-Pixal3D` in PowerShell (this deletes its Linux part).
4. Delete the folder you installed into (`C:\3DGEN` by default) and, if you chose another drive for Pixal3D, the
   `3DGEN\wsl` folder on that drive.
5. Delete the two **3DGEN** shortcuts (desktop and Start menu).

## How it works

Nothing is built on your PC. The AI engines are downloaded from their own publishers and each file is checked before
use.

## Check a download yourself

Each release has `SHA256SUMS.txt` with the SHA-256 of every file in it. In PowerShell, in the folder you downloaded to:

```powershell
Get-FileHash .\3DGEN-<version>.zip -Algorithm SHA256
```

Put the version you downloaded in place of `<version>`. The hash must equal the line for that file in `SHA256SUMS.txt` (case does not matter).

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

## Report a problem

Open an [issue](https://github.com/mixocreative/mixo3dgen-releases/issues/new) or e-mail mixocreative@gmail.com. Please
include the error code shown on the card (for example `3DG-GPU-001`) and, if you can, the support file from
**Save support file** on the PC (it holds technical facts about your PC and the install, never your photos or models).
Do not post your 3DGEN passcode or phone link in a public issue.
