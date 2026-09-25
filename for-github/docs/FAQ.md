# FAQ

**Does it work on servers / multiplayer?**
No — by design. Modules only tick inside a singleplayer world. There is no
anticheat bypass and there never will be.

**Can I get banned?**
Not from singleplayer (there's nothing to ban you). On servers: yes, like with
any cheat — up to HWID bans. Don't do it.

**Why does my antivirus flag it?**
Because it injects a DLL into `javaw.exe`, like every game tool does. Add the
folder as an exclusion, or compile it yourself from `codigo-fuente/` and compare.

**Windows SmartScreen warns about unknown publisher?**
Binaries are self-signed as Lowk Inc (Properties → Digital Signatures). Only a
paid certificate removes the warning. The signature still proves the file is
exactly what we released.

**Which versions are supported?**
Only Fabric 1.21.11. Anything else and the DLL stays inert on purpose.

**How do I open the menu / unload?**
In-game: **INSERT** menu, **END** unload.

**How do I contact support?**
Discord: **whoislowk** — or the Support tab (tickets) inside the launcher.

**Where is the source?**
`codigo-fuente/`. Build with `build.bat` (needs CMake + JDK + VS2022).
