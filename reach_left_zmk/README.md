# Reach left-half ZMK starter

This is a **source-only, uncompiled** starter from the discovered left-half matrix. It has not been validated on a physical controller or by a ZMK build. It uses the nRF52840 SuperMini as `nice_nano//zmk`, which assumes the clone matches that board's bootloader and configuration.

## Build

1. Make a new GitHub repository and upload **the contents** of this folder to the repository root. Ensure the `.github/workflows/build.yml` directory is included.
2. In GitHub Actions, start the build workflow (or push a commit).
3. Download the artifact containing the `reach_left-nice_nano_zmk.uf2` (actual filename may vary).
4. Disconnect the battery, enter the controller's UF2 bootloader, and copy the resulting UF2 to the bootloader drive.
5. Test keys over USB first, then pair over Bluetooth.

## Known limitations

- Only the left-half's GPIO mapping is known. This shield declares the left controller as split central, but the right peripheral is NOT yet defined.
- The supplied 28-key keymap is deliberately provisional, because only matrix traversal order (not every physical legend) was supplied. Edit `config/reach_left.keymap` to match your keys.
- ZMK Studio is not yet enabled: a full 56-key layout with accurate physical geometry is needed for a useful visual layout.
- If your controller's firmware build or USB behavior is incompatible with nice_nano, check its precise variant/bootloader before further flashing.

Electrical rows: P0.10, P0.20, P0.22, P0.24, P1.00
Electrical columns: P1.11, P1.13, P0.31, P0.29, P0.02, P1.15
Direction: col2row. Populated last row: columns 2–5.
