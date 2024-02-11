# Masquerade Emulator

**A multi-system emulator which emulates the following platforms:**
1) Chip8 (also supports S-CHIP and XO-CHIP)
2) Space Invaders
3) Pacman (supports both Midway and Namco roms)
4) Ms Pacman
5) Gameboy (GB)
6) Gameboy Color (GBC)
7) Game Of Life

**Below platforms are under developement:**
1) Game Boy Advance (GBA)
2) Nintendo Entertainment System (NES)
3) Super Nintendo Entertainment System (SNES)
4) Nintendo DS
5) Nintendo 3DS

**Few Notable Features:**
1) Supports Save States and Load States
2) Support OTA updates
3) Game Of Life supports Normal Mode and Torroidal Mode
4) Chip8 supports CHIP8, S-CHIP and XO-CHIP modes
5) Chip8 passes Timendus's chip8-test-suite v4.1 (except for scrolling tests)
6) Supports many 8080 test roms (Undocumented Opcode Tests are still not handled)
7) Supports many Z80 test roms (Undocumented Opcode Tests are still not handled)
8) Supports GB and GBC Bios
9) Has UI based debugger support (Only for GB and GBC)
10) Has Command-Line based debugger support for platforms other than GB and GBC (Note: This is currently disabled)
11) Options for different palettes for GB (Includes 'Gearboy', 'Sameboy' and 'BGB' palettes)
12) GB / GBC passes most of the Blargg tests (Except for the wave ram tests)
13) GB / GBC passes many of the Moon Eye tests (There are still many which doesn't pass as is, but would probably pass with little tweaks in the CONFIG.ini)
14) GB / GBC passes the RTC (rtc3test) tests
15) GB / GBC implements Pixel Fetcher/FIFO
16) GBC supports GB mode
17) Able to play a slightly glitchy version of mezase.gbc (with few tweaks in the CONFIG.ini) 
18) External Menu-bar based UI for Windows platform
19) Internal Menu-bar based UI for platforms other than Windows
20) Supports dynamic drag and drop of roms (this includes multiple rom files for Space Invaders and Pacman/MsPacman)

**Game Play:**

_Debugger (Supported by both Gameboy and Gameboy Color)_

![GBC-Debugger](https://github.com/Kotambail-Hegde/Masquerade-Emulator/assets/29670073/50e26ee3-abd8-432a-bbaa-0ca8891fc892)

_Gameboy_ _(Prehistorik Man in 'BGB' palette and Pokemon Green in 'Gearboy' palette)_

![PrehistorikMan](https://github.com/Kotambail-Hegde/Masquerade-Emulator/assets/29670073/8819c689-b3ad-444e-bece-d43a993e05b7) ![Green](https://github.com/Kotambail-Hegde/Masquerade-Emulator/assets/29670073/519c7f6e-ebb1-4e60-b677-d860ffb0f8a1)

_Gameboy Color_ _(Donkey Kong Country and Pokemon Crystal)_

![DonkeyKongCountry](https://github.com/Kotambail-Hegde/Masquerade-Emulator/assets/29670073/3d6bfb58-ae88-4b66-b299-ef20faf67112) ![Crystal](https://github.com/Kotambail-Hegde/Masquerade-Emulator/assets/29670073/3b318907-dc70-4488-8552-729b98504603)

_Pacman_

![Pacman](https://github.com/Kotambail-Hegde/Masquerade-Emulator/assets/29670073/81b421c4-bb53-4985-ae15-90d8dd572b5a) 

_Ms Pacman_

![MsPacman](https://github.com/Kotambail-Hegde/Masquerade-Emulator/assets/29670073/b55f29d8-fcfb-4d5b-b30c-fb9b8afe0e35)

_Space Invader_

![SpaceInvaders](https://github.com/Kotambail-Hegde/Masquerade-Emulator/assets/29670073/afac2f45-75e0-4a24-b087-1499360cf703)

_Chip8:_ _(Pong)_

![Chip8](https://github.com/Kotambail-Hegde/Masquerade-Emulator/assets/29670073/f162afa0-733e-4d4f-8fdf-7a907cb878e2)

_Game Of Life_

![GameOfLife](https://github.com/Kotambail-Hegde/Masquerade-Emulator/assets/29670073/44bd5adf-bbe5-4edc-a47a-eff03cc8faae)

**Host Platforms Supported:**
As of today, Masquerade is only tested for Windows Based System. There are plans to port this to Linux based system as well.

**User Interface:**

In Windows, external Menu-bar based UI can be used for using various options of the emulator (Whatever features not available in GUI could be accessed via CONFIG.ini)

![WIN32API](https://github.com/Kotambail-Hegde/Masquerade-Emulator/assets/29670073/33d62a3d-9daa-4bfc-b549-4e4bd42b09a3)

In Non-Windows system (when supported), for now, internal Menu-bar based UI which is independent of host platform needs to be used (Whatever features not available in GUI could be accessed via CONFIG.ini)

![RetroMode](https://github.com/Kotambail-Hegde/Masquerade-Emulator/assets/29670073/6b6ae213-20ff-44ef-a7af-bd7adcc56df6)

**Credits:**
1) Forked version of One Lone Coder's Pixel Game Engine is used for Graphics (https://github.com/Kotambail-Hegde/olcPixelGameEngine)
2) One Lone Coder's Sound Wave Engine is used for Audio
3) Gearboy used for testing (https://github.com/drhelius/Gearboy)
4) gbmulator used for testing (https://github.com/mpostaire/gbmulator)
5) The Ultimate Gameboy Talk (https://github.com/drhelius/Gearboy)
6) GB Dev Wiki (https://gbdev.gg8.se/wiki/articles/Memory_Bank_Controllers)
7) Codeslinger's blog (http://www.codeslinger.co.uk/pages/projects/gameboy.html)
8) Night Shade's blog for audio implementation (https://nightshade256.github.io/2021/03/27/gb-sound-emulation.html)
9) Blargg Roms used for testing
10) Antonio's blog (https://github.com/AntonioND/giibiiadvance/blob/master/docs/TCAGBD.pdf)
11) Boost for libraries to parse .ini files



