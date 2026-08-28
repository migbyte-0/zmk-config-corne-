# Ported notes (read me)

This is the **eyelash_corne** config from [a741725193/zmk-corne](https://github.com/a741725193/zmk-corne)
(the seller's own repo — custom `cormoran/zmk` fork, its modules, the eyelash_corne
shield, nice!view + RGB + encoder) with **`config/eyelash_corne.keymap` replaced by a
Go60 layout ported to the 48-key eyelash board.**

## What changed vs. the seller's repo
- `config/eyelash_corne.keymap` → the Go60 port:
  - Base = **Colemak-DH**; **Numbers** layer done (RGB + BT controls).
  - All behaviors / macros / combos carried over. 30 more layers exist as
    `&trans` placeholders (so every `&mo`/`&to`/`&sl` compiles) — fill them in later.
  - 48 keys = standard 42-key Corne + the 6-key middle joystick cluster.
    Go60 rows R2/R3/R4 → the 3 physical rows.
  - **Joystick** = arrows / enter / space (base layer). **Knob** = volume (`rsr_vol`).
  - **RGB kept** (this board has underglow). Credential/PII macros redacted to `&none`.
- Everything else (west.yml, modules, shield, build.yaml, confs) is the seller's, unchanged.

## Build & flash
Push → GitHub Actions builds `eyelash_corne_left` / `eyelash_corne_right` (nice!view)
+ `settings_reset`. Download the artifact, then for each half: double-tap reset →
drag the matching `.uf2` onto the `NICENANO` drive. Flash `settings_reset` to both
first if the halves won't pair.

## Secrets
The password/phone/email macros type nothing (`&none`) and their names were
genericized. Keep a local un-pushed keymap with real values if you want them, and
rotate the previously-stored passwords.
