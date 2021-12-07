# Monero Ilaro
This document serves to describe the goals of the Ilaro project and its potential use for the crypto currency Monero (XMR).

**monero**: *currency or coin*

**ilaro**: *kit or toolkit. a collection of tools*

## Highest Level Project Goals
- To increase the adoption and use of Monero by the average everyday citizen of the world.
- To accelerate the pace of new Monero software development by increasing the number of dev contributors.

### What most engages the interest of a potential new user?
- **Privacy** (obviously).
- **Mining** which can be done on almost any computer.
- **Various philosophical beliefs** that arrive at an identical conclusion that the existence of Monero is a necessity.

### How can a greater percent of initial interest be converted into adoption?
- "On-boarding" experience for the non-technical folks needs to be drop-dead simple. Users should be able to create a wallet and begin mining ***within the first 5 minutes***.
- Coders and tech-ninjas need a common computer system platform on which to build their towers of code. Coders should not have to take into consideration multiple different operating systems and UI software layers to be able to contribute to the Monero project.

## So What Is Ilaro?

***Basic summary:***
The ability to plug a USB stick into any computer and temporarily turn it into an XMR miner, p2pool node, and/or monero blockchain node. A simple reboot and the computer is returned back to normal.

***Technical summary:***
The source code of the Ilaro project creates a bootable ISO image of a Linux operating system customized for using Monero. An additional core component of the Ilaro project is a robust terminal user interface (TUI) system. Familiar UI concepts like button clicks, application windows, scrolling and other mouse events are emulated within the context of a CLI terminal.

### Platform Details
- Customized Alpine Linux distro with APK package system.
- Does not require a hard drive. Allows for *motherboard-only* mining rigs.
- Essentional Monero CLI programs and dev libraries pre-installed. Can be recompiled from source.
- !!Rock steady max hashrates!!

#### Boot System
- BIOS and EFI motherboard bootloader compatible. BIOS uses Syslinux/isolinux. EFI uses Grub2.
- Ilaro ISO file can be burned to CD or flashed to a USB stick. Currently ISO file size < 200MB.
- "Live USB/CD" will boot on any x86_64 CPU hardware. Including Apple Mac desktops and laptops.
- Installs to RAM (like Tails OS). Currently uses ~100MB of RAM total at startup.
- Makes no modifications to the computer it is used on.
#### Operating System
- Core operating system cannot be permanently hacked or modified by malware due to ISO filesystem. Reboot resets OS to base.
- Can be user configured to run as a miner, p2pool, blockchain-node, or other in "plug-n-play" mode.
- Linux customizations and additional packages can be installed and made to persist on reboot with OS "overlay" system.
- When an ISO is flashed to a USB stick the remaining disk space becomes unusable. This issue has been solved. USB will appear as a "normal" drive if inserted into computer running Windows/Mac OS, while the boot partition will not be visible. This allows drag-n-drop config file transfer from an existing rig setup.

### TUI System Details
- Emulates the look and feel of traditional GUI application "windows" and mouse events, but runs entirely from the command line terminal.
- "X", "Wayland", and other window-managers bloat-code is not required to build user interfaces that are easy to operate and understand.
- Keeps ISO filesize and RAM system usage to a minimum. 

#### "Configure/Run/Monitor" TUI Application (no name yet, still experimenting with app scope)
- Monitors XMRig worker stats through XMRig HTTP API.
- Can monitor multiple workers simultaneously.
- (WiP) Connect and display stats from P2Pool Observer API.
- (WiP) P2Pool service node interface
- (WiP) Monerod service node interface
- (TBD) Graphs & charts

### Future stuff
- Tor (for sure)
- PXE network bootloader (maybe)
- DEX platform??? Haveno integration? (not even sure exactly what this means, or could mean, but I would relish the opportunity to attempt something)
