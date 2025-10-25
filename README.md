# config-skhd

Helper scripts and keybindings for skhd window movement under macOS Sequoia with SIP fully enabled.

## Requirements

- `skhd` installed (e.g. via Homebrew) and configured to load configs from `~/.config/skhd`.
- `yabai` running (only for space/window queries; scripting addition not required).
- Python 3.9+.

## Setup

1. Create the virtual environment (one-time):

   ```sh
   cd ~/.config/skhd
   python3 -m venv .venv
   ~/.config/skhd/.venv/bin/pip install --upgrade pip
   ~/.config/skhd/.venv/bin/pip install 'pyobjc-core==10.1' 'pyobjc-framework-Quartz==10.1'
   ```

2. Restart `skhd` so it picks up the new bindings:

   ```sh
   brew services restart skhd
   ```

3. When macOS prompts for Accessibility/Input Monitoring access for `skhd` and the venv python, allow it.

## Usage

- `skhdrc` defines `shift + option + [1-0]` to move the focused window to spaces 1–10.
- `move_window.py` keeps the window “grabbed” with CoreGraphics while firing the normal `option + number` Mission Control shortcuts.

If you recreate the venv in a different location, update the interpreter path in `skhdrc`.
