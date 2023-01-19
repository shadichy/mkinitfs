# mkinitfs

This is the initramfs generator for desktop Android (/w GearLock recovery)

## Dependencies

To compile manually, you need to have the following build tools available:

- make

## Installation

Build mkinitfs via `make` and install it via `make install`.
The installation honours the `DESTDIR` parameter to overwrite the sysroot path.

For testing, its not necessary to install `mkinitfs` into your root file system.

## Tweaking

The Makefile is kept slim and debuggable.
