# Download & verify

Releases live on the **[Releases page](../../releases)**.

Each release contains:
- `Vibe Launcher.exe` — the app (DLL embedded, single file)
- `VibeTickets.exe` — owner ticket responder
- SHA256 hashes in the release notes

## Verify (30 seconds, do it)

1. Right-click the `.exe` → Properties → **Digital Signatures**.
2. Confirm signer **Lowk Inc** and digest SHA256.
3. Optional: compare the SHA256 with the release notes:
   `certutil -hashfile "Vibe Launcher.exe" SHA256`

## Antivirus / SmartScreen

Expect a flag: injectors always trigger heuristics. Either exclude the folder
or build from source (`codigo-fuente/build.bat`) — same code, your machine.
Self-signed ≠ trusted: SmartScreen may still warn. That's normal and honest.
