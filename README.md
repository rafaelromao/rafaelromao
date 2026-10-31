<h1 align="center">Rafael Romão</h1>

<p align="center">
  Backend engineer since 2002, from Belo Horizonte, Brazil.<br>
  Off the clock I build tools for coding agents, and keyboards: the layout, the firmware and the hardware.
</p>

---

<p align="center">
  <a href="https://sandman.run/">
    <img src="https://github.com/rafaelromao/sandman/raw/HEAD/assets/sandman-banner.png" alt="Sandman: sleep while your agents code" width="100%">
  </a>
</p>

### [Sandman](https://github.com/rafaelromao/sandman)

**Sleep while your agents code.** An orchestrator for autonomous coding agents. It pulls issues from GitHub, renders them through prompt templates, and runs each agent inside an isolated sandbox, a git worktree or a container, with dependency-aware parallel scheduling and a local portal for watching the runs.

It exists because agentic engineering needs the same things any delivery process needs: a clear specification, an isolated execution boundary, an event log, verification, and a human review gate.

```console
$ sandman run 42 43 44 45
```

[sandman.run](https://sandman.run/) · [Repository](https://github.com/rafaelromao/sandman) · Go

---

## ⌨️ Keyboards

<table>
  <tr>
    <td width="50%" valign="top">
      <a href="https://github.com/rafaelromao/diamond"><img src="https://github.com/rafaelromao/keyboards/raw/HEAD/docs/img/builds/Diamond.jpeg" alt="Diamond, a 24-key handwired split keyboard" width="100%"></a>
    </td>
    <td width="50%" valign="top">
      <h3><a href="https://github.com/rafaelromao/keyboards">keyboards</a> <img src="https://img.shields.io/github/stars/rafaelromao/keyboards?style=flat&label=%E2%98%85&color=555" alt="stars" align="absmiddle"></h3>
      <p>My split keyboard configuration in ZMK, tuned for Portuguese, English, numbers and programming with Vim. It builds from a containerized toolchain and git submodules rather than hosted CI, so a firmware build is reproducible on any machine and offline.</p>
      <h3><a href="https://github.com/rafaelromao/diamond">Diamond</a></h3>
      <p>My own keyboard: a 24-key handwired split in a 1333+2 layout, designed around hiding its own hardware. The controller, reset button and power switch mount upside down inside the base, under a cover the wiring passes through. Printable STLs in three builds: MX, wired and Choc.</p>
      <h3><a href="https://github.com/rafaelromao/romak">Romak</a></h3>
      <p>A layout for people who write both Portuguese and English. It optimizes for hand alternation and against same-finger bigrams, pinky load and centre-column reaches, with the comparative analyses against a dozen existing layouts that justify each decision.</p>
    </td>
  </tr>
</table>

### [zmk-vim-mode](https://rafaelromao.github.io/zmk-vim-mode/)

**The keyboard should be in NORMAL when the editor is.** zmk-vim-mode keeps a ZMK keyboard's layers in sync with the editor's real Vim state: NORMAL in normal mode, INSERT while typing, and out of Vim layers entirely when keys must pass through untouched.

That needs the host to tell the keyboard something, and HID runs keyboard to host. Except for one byte: the output report the host sends to light Caps Lock and Num Lock. Three of its bits, Scroll Lock, Compose and Kana, are never set by any operating system, so together they make a silent 3-bit channel, eight states, more than Vim has modes. It works the same over USB and Bluetooth, with no pairing and no custom transport. A 60 ms hold-off and a 150 ms guard keep a stale host message from undoing a correct local one: the keyboard wins in motion, the host wins at rest.

<p align="center">
  <a href="https://rafaelromao.github.io/zmk-vim-mode/">
    <img src="https://github.com/rafaelromao/zmk-vim-mode/raw/HEAD/docs/img/showcase-hero.png" alt="Neovim in normal mode with the keyboard on its VIM NORMAL layer" width="100%">
  </a>
</p>

### [zmk-layer-hud](https://rafaelromao.github.io/zmk-layer-hud/)

**Ask the keyboard, not the operating system.** An on-screen HUD that shows the layer you are on and lights the keys, combos and macros as you press them, drawn from the same keymap the firmware is built from. It is for learning a layout, and for recording or sharing a screen while you type on one.

Overlays like this usually infer the key from an OS event tap. This one infers nothing: a small ZMK module reports the keyboard's own active layers and the position of every press, over Bluetooth or a serial interface of its own on USB, so the HUD shows what the firmware did rather than what the host saw. It runs as a native overlay panel on macOS and a layer-shell panel on Hyprland, and redraws live when the keymap changes.

<p align="center">
  <a href="https://rafaelromao.github.io/zmk-layer-hud/">
    <img src="https://github.com/rafaelromao/zmk-layer-hud/raw/HEAD/docs/hud.gif" alt="The HUD lighting keys on the Alpha 1 layer as they are pressed" width="80%">
  </a>
</p>

### [LayerBench](https://rafaelromao.github.io/layerbench/)

**A layout analyzer that types the way the keyboard does.** Layout analyzers score a grid of letters. A ZMK keymap is not a grid of letters: it has one-shot and momentary layers, combos, adaptive and repeat keys, sticky shift and caps word, and each of them changes which physical keys a word actually costs. LayerBench simulates how a corpus is typed on the real keymap, then computes same-finger bigrams, scissors, rolls, redirects and effort on the resulting physical key stream. It runs entirely in the browser.

<p align="center">
  <a href="https://rafaelromao.github.io/layerbench/">
    <picture>
      <source media="(prefers-color-scheme: dark)" srcset="https://github.com/rafaelromao/layerbench/raw/HEAD/docs/site/assets/img/analyze-board-dark.png">
      <img src="https://github.com/rafaelromao/layerbench/raw/HEAD/docs/site/assets/img/analyze-board-light.png" alt="LayerBench heatmap of a keymap layer" width="80%">
    </picture>
  </a>
</p>

### ZMK modules

| Module | What it does |
|---|---|
| [zmk-layer-morph](https://github.com/rafaelromao/zmk-layer-morph) | Morphs a keypress into a different binding when any of a named set of layers is active, so one keymap serves both macOS and Linux base layers. |
| [zmk-os-detection](https://github.com/rafaelromao/zmk-os-detection) | Tells macOS from Linux by how the host reads the keyboard's descriptors, over USB or BLE, and flips one layer to match. It never guesses. |
| [zmk-sentence-case](https://github.com/rafaelromao/zmk-sentence-case) | A sentence-aware space: after a full stop, question or exclamation mark, the next letter comes out capitalized. |
| [zmk-dongle-display](https://github.com/rafaelromao/zmk-dongle-display) <sub>fork</sub> | Peripheral status screens on the dongle display: host connection and every half's battery. |
