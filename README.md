# Vibe-Launcher
 VIBE Client

> Modern singleplayer utility mod-menu for **Minecraft Fabric 1.21.11** — C++, ImGui, MinHook, JNI.

![version](https://img.shields.io/badge/version-1.0.0-amber)
![minecraft](https://img.shields.io/badge/minecraft-1.21.11-green)
![loader](https://img.shields.io/badge/loader-Fabric-blue)
![mode](https://img.shields.io/badge/mode-singleplayer_only-red)

##  Features

| Area | What you get |
|------|--------------|
|  Launcher UI | Dark brown modern UI: **Injection**, **Console**, **Support** tabs |
|  Combat | Triggerbot, legit Aim Assist, Hit Select (cooldown-gated) |
|  Visuals | Target ESP (box + distance + HP) |
|  World | Legit Scaffold helper |
|  Support | In-app tickets for `whoislowk` + owner responder app |
|  Signed | Binaries signed as **Lowk Inc** (self-signed, see below) |

## ⬇ Download

Grab the latest signed `.exe` from the
**[Releases page](../../releases)** *(first public release coming soon)*.

Verify before running: right-click → Properties → Digital Signatures → **Lowk Inc**.
SmartScreen may still warn (self-signed cert) — that's expected, see FAQ.

##  Quick start

1. Open your **singleplayer** world on Fabric 1.21.11.
2. Run `Vibe Launcher.exe`, accept the terms, press **INJECT**.
3. In-game: **INSERT** = menu, **END** = unload.

##  Safety & honesty

- **Singleplayer only.** Modules are hard-gated: outside a SP world they do nothing.
- **No anticheat bypass**, no kernel driver, no hidden processes — and there never will be.
- **Antivirus will likely flag it.** Injectors always do (ours injects a DLL into `javaw.exe`).
  Add the folder as an exclusion, or build it yourself and compare hashes.
- **Multiplayer = bans (incl. HWID).** Using this or any cheat on servers is on you.

##  Support

- Discord owner: **whoislowk**
- Or open the **Support** tab in the launcher and create a ticket.

##  Build from source

Everything is auditable in [`codigo-fuente/`](codigo-fuente/):

```bat
cd codigo-fuente
build.bat     ← double-click, outputs the single Vibe.exe
```

Needs only: CMake + JDK 17+ (official pages) + VS2022 with C++. Deps (ImGui, MinHook)
download as ZIPs from their official GitHub repos — no login, no mirrors.

## ⚠️ Disclaimer (short)

Singleplayer tool, no warranties. Server cheating gets you banned. Details in
[Aviso legal y de uso](#aviso-legal-y-de-uso-leer-antes-de-ejecutar) below.

---

## Aviso legal y de uso (leer antes de ejecutar)

1. **SOLO SINGLEPLAYER.** Diseñado y bloqueado para tu mundo local de
   Minecraft Fabric 1.21.11. Fuera de singleplayer los módulos no hacen nada.
2. **SIN BYPASS DE ANTICHEAT NI LO HABRÁ.** Sin driver kernel, sin ocultación
   de procesos, sin evasión. Que funcione en tu PC no lo hace indetectable
   en un servidor.
3. **MULTIPLAYER = SANCIONES.** Servidores y anticheats penalizan trampas,
   incluyendo baneos de cuenta y de HWID. Usarlo fuera de SP es 100% tu
   responsabilidad y riesgo.
4. **SIN GARANTÍAS.** Se entrega "tal cual": sin responsabilidad por cuentas
   sancionadas o alertas de antivirus (falso positivo común en inyectores
   caseros sin firma).
5. **CÓDIGO INCLUIDO.** Todo está en `codigo-fuente/` para auditarlo. Si no
   confiás en un .exe, compilalo vos (ver arriba).
Al ejecutar Vibe.exe aceptás estos puntos.

---

##  Repo layout

```
README.md / LICENSE / CHANGELOG.md
Vibe Launcher.exe / VibeTickets.exe   (signed releases, also on Releases page)
docs/          FAQ, download & verify guide
web/           landing page draft (download site)
codigo-fuente/ full source (DLL + launcher + tickets app + scripts)
```

## Technical notes (for developers)

- Version-locked JNI mappings for Fabric 1.21.11 (Yarn `1.21.11` branch).
- JNI ids cached once at init; every module tick is singleplayer-gated.
- MinHook hooks `wglSwapBuffers` for the ImGui overlay only.
