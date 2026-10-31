### Rafael Romão

Director of Technology at Avenue Code. Twenty-four years of backend systems, and of the platforms and practices that keep them changeable. Lately: agentic engineering, and how autonomous coding agents fit inside a disciplined delivery process.

[rafaelromao.github.io](https://rafaelromao.github.io/) · [Blog](https://rafaelromao.github.io/blog/) · [LinkedIn](https://linkedin.com/in/rafaelromao) · [Email](mailto:rafaelromao@gmail.com)

**[Sandman](https://sandman.run/)**: an orchestrator for autonomous coding agents. It pulls issues from GitHub and runs each agent in an isolated worktree or container, with dependency-aware scheduling and a human review gate.

---

### Keyboards

A long-running interest, from the layout and the firmware down to the hardware. Two of these projects are written up on [my site](https://rafaelromao.github.io/#open-source): [LayerBench](https://rafaelromao.github.io/layerbench/) and [zmk-vim-mode](https://rafaelromao.github.io/zmk-vim-mode/).

**[keyboards](https://github.com/rafaelromao/keyboards)**: my split keyboard configuration in ZMK, tuned for Portuguese, English, numbers and programming with Vim. It builds from a containerized toolchain and git submodules rather than hosted CI, so a firmware build is reproducible on any machine and offline.

**[Romak](https://github.com/rafaelromao/romak)**: my own keyboard layout, for people who write both Portuguese and English. It optimizes for hand alternation and against same-finger bigrams, pinky load and centre-column reaches, and is published with the comparative analyses against a dozen existing layouts that justify each decision.

**[Diamond](https://github.com/rafaelromao/diamond)**: my own keyboard, a 24-key handwired split in a 1333+2 layout designed around hiding its own hardware. The controller, reset button and power switch mount upside down inside the base, under a cover that the column and row wiring passes through. Printable STLs in three builds, MX, wired and Choc.

**[zmk-layer-hud](https://rafaelromao.github.io/zmk-layer-hud/)**: an on-screen HUD that shows the layer you are on and lights the keys, combos and macros as you press them. A small ZMK module reports the keyboard's own active layers and key positions over Bluetooth or USB, so the HUD shows what the firmware did rather than what the host saw. Native overlay on macOS, layer-shell panel on Hyprland.

#### ZMK modules

| Module | What it does |
|---|---|
| [zmk-layer-morph](https://github.com/rafaelromao/zmk-layer-morph) | Morphs a keypress into a different binding when any of a named set of layers is active, so one keymap serves both macOS and Linux base layers. |
| [zmk-os-detection](https://github.com/rafaelromao/zmk-os-detection) | Tells macOS from Linux by how the host reads the keyboard's descriptors, over USB or BLE, and flips one layer to match. It never guesses. |
| [zmk-sentence-case](https://github.com/rafaelromao/zmk-sentence-case) | A sentence-aware space: after a full stop, question or exclamation mark, the next letter comes out capitalized. |
| [zmk-dongle-display](https://github.com/rafaelromao/zmk-dongle-display) (fork) | Peripheral status screens on the dongle display: host connection and every half's battery. |
