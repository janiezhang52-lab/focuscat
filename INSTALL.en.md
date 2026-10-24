# Install FocusCat English on a Mac

Updated 2026-10-24. This guide is for the separate **English preview**, not the Chinese app. You do not need an Apple Developer membership to use an app. The publisher has not signed this preview with Developer ID or notarized it; macOS may block its first launch. The per-app exception below is your own trust decision, not Apple certification or a guarantee it will run on every Mac.

## 1. Check your Mac and download the correct file

Use **Apple Silicon (M-series), macOS 13 or later**. Check Apple menu → About This Mac. Intel Macs and Windows are not supported by this ZIP.

Open the [English release](https://github.com/janiezhang52-lab/focuscat/releases/tag/v0.2.1-en-preview.1). Under Assets, download **`FocusCat-English-0.2.1-en-preview-macOS-arm64.zip`** and **`SHA256SUMS.txt`**. Do not choose GitHub's automatically generated Source code ZIP or tar.gz: those are not the English app installer.

## 2. Verify the download

With both files in Downloads, open Terminal and run:

```sh
cd "$HOME/Downloads"
shasum -a 256 "FocusCat-English-0.2.1-en-preview-macOS-arm64.zip"
```

Compare the entire 64-character result with the line for that exact ZIP in `SHA256SUMS.txt` from the **same release**. If your browser renamed the file, use its actual filename. Matching confirms the downloaded bytes match the release; it does not prove an app is harmless. If the result differs, do not launch it: download again from the release and report a repeated mismatch.

## 3. Install the app

Double-click the ZIP in Finder. Inside the extracted folder, drag **`FocusCat English.app`** to Applications. Move the whole .app bundle, not its Contents or executable. Keep the included README beside your download for reference. Open Applications and double-click **`FocusCat English.app`** once.

## 4. If macOS cannot verify the developer

Only continue if you trust this release and accept running an unnotarized preview. After the blocked launch, open **System Settings → Privacy & Security → Security**. Find this app's blocked-launch message, choose **Open Anyway**, authenticate if asked, and confirm **Open**. This creates an exception for this app. [Apple's opening instructions](https://support.apple.com/en-us/102445).

The exception button is available for about an hour after an attempt. If missing, retry opening this installed app, then revisit Settings. Button wording varies by macOS; follow the app-specific prompt. A managed work/school Mac may require IT approval. [Apple's Mac User Guide](https://support.apple.com/guide/mac-help/open-a-mac-app-from-an-unknown-developer-mh40616/mac).

This guide does not require disabling Gatekeeper, changing startup security, removing quarantine attributes, or running the app with sudo. If your Mac does not offer an exception, stop and report it; there is no promised fallback for this preview.

## 5. First use

Click the cat or menu-bar icon, start a focus session, pause it, and try Fill Bowl. Use Quit FocusCat to exit.

The English edition stores progress/settings separately in `~/Library/Application Support/FocusCat-English`. The Chinese edition and its data can remain installed. Do not rename or move the Chinese save into this directory. Quit the English app before replacing it with a future English build, and back up its data first. Removing only the .app leaves saved data intact.

## If it still does not open

- **Damage, malware, or “will damage your computer”:** do not treat this as the ordinary unidentified-developer warning. Stop. For a damaged-file message, recheck the ZIP hash and report the exact alert; matching hashes do not establish safety. [Apple explains these alerts](https://support.apple.com/en-us/102445).
- **Wrong system/chip or a crossed-out app icon:** check the requirements above; approving the app cannot add platform compatibility.
- **No Open Anyway / organization restriction:** ask your administrator, or wait for a notarized release. Do not change system-wide protections.
- **App opens but a feature fails:** report the step and visible error at [Issues](https://github.com/janiezhang52-lab/focuscat/issues), with macOS version, chip, release tag and whether the checksum matched. Omit API keys, passwords, chats and personal saves.

## What has actually been checked

Downloaded bytes, signature integrity and selected runtime/persistence checks passed on the development Mac. Default Gatekeeper assessment rejected this ad-hoc build. **The manual approval procedure above follows Apple documentation; it has not been verified end-to-end on a clean Mac for this exact release.** It does not change that limitation. See [the installation audit](INSTALLATION-CHECK.md).
