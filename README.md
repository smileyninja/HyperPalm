# **HyperPalm**

**A tiny, portable, card‑based computing environment built first for the PiCalc (RP2040) — and designed to run everywhere.**

HyperPalm began on the **PiCalc**, a pocket‑sized RP2040 computer with a D‑pad, a crisp little LCD, and the spirit of a 90s PDA. The goal is to give devices like the PiCalc a *real*, scriptable, document‑centric OS — something instant‑on, humane, and easy to understand.

From that seed, HyperPalm grows outward to other tiny and not‑so‑tiny platforms:

- **PiCalc / RP2040** (the reference device)  
- Raspberry Pi Zero  
- Linux / BSD  
- Windows CE  
- Web (emscripten)

All powered by the same small, deterministic C engine and a friendly scripting language, HyperPalmScript.

HyperPalm is an alternate‑timeline computing platform: what card‑based systems *could* have become if they evolved on tiny hardware instead of disappearing.

---

## **Features (current & planned)**

- Portable C99 engine with a clean platform abstraction  
- Framebuffer‑based UI with 1‑bit or 8‑bit grayscale rendering  
- Card‑based document model (stacks, cards, fields, buttons, images)  
- Event system (click, key, timer, script events)  
- HyperPalmScript: a small, readable scripting language  
- Built‑in desktop, card editor, and script editor  
- Deterministic stack file format designed for longevity  
- Import pipelines for HyperCard stacks and PalmOS PDBs (structure only)  
- Runs on:
  - **PiCalc / RP2040**  
  - Raspberry Pi Zero  
  - Linux / BSD  
  - Windows CE  
  - Web (emscripten)

HyperPalm is designed so the PiCalc remains the “hero device,” but nothing in the engine depends on it.

---

## **Project Structure**

```
src/
  core/        # Engine logic (platform‑agnostic)
  platform/    # Per‑platform implementations (RP2040, Linux, WinCE, etc.)
  ui/          # Desktop, card editor, inspectors
  apps/        # Optional built‑in apps
  main.c       # Entry point

include/       # Public headers
scripts/       # HyperPalmScript standard library
stacks/        # Example stacks
tools/         # Stack tools, bytecode tools
cmake/         # Toolchain files
```

The engine stays stable and boring.  
All interesting behavior lives in scripts and stacks.

---

## **Building**

HyperPalm uses CMake and targets multiple platforms.

PiCalc / RP2040:

```
mkdir build && cd build
cmake .. -DPICO_SDK_PATH=/path/to/pico-sdk
make
```

Linux / BSD / macOS (SDL2):

```
mkdir build && cd build
cmake ..
make
```

Web (emscripten):

```
mkdir build && cd build
emcmake cmake ..
make
```

Platform toolchain files live in `cmake/`.

---

## **Why HyperPalm?**

Because the PiCalc deserves a real OS.  
Because tiny hardware is more fun when it’s expressive.  
Because card‑based computing is still one of the most humane UI models ever created.  
Because a small, deterministic engine is easier to preserve, port, and understand decades from now.

HyperPalm is built for:

- PiCalc owners  
- hobbyists  
- educators  
- retro‑computing fans  
- embedded developers  
- anyone who wants a simple, scriptable, document‑centric environment  

---

## **License**

MIT License — use it, fork it, port it, remix it.

---

## **Status**

Early development.  
The architecture is stable; the engine and scripting layer are being built out.  
Contributions, ports, and experiments are welcome.

---

If you want, I can now:

- tune the README tone (more technical, more playful, more manifesto‑like)  
- add badges, screenshots placeholders, or a PiCalc photo section  
- generate a CONTRIBUTING.md or ROADMAP.md  
- write a “Why PiCalc?” sidebar that really sells the origin story
