# Masquerade Emulator

_**A multi-system emulator which emulates the following consoles:**_
* Chip8 (also supports S-CHIP and XO-CHIP)
* Space Invaders
* Pacman (supports both Midway and Namco)
* Ms Pacman
* Gameboy (GB)
* Gameboy Color (GBC)
* Game Of Life

_**Below consoles are under developement:**_
* Game Boy Advance (GBA)
* Nintendo Entertainment System (NES)
* Super Nintendo Entertainment System (SNES)
* Nintendo DS
* Nintendo 3DS

_**Supported features:**_
* Supports Save States and Load States
* Support OTA updates
* Game Of Life supports Normal Mode and Torroidal Mode
* Chip8 supports CHIP8, S-CHIP and XO-CHIP modes
* Chip8 passes Timendus's chip8-test-suite v4.1 (except for scrolling tests)
* Supports many 8080 test roms (Undocumented Opcode Tests are still not handled)
* Supports many Z80 test roms (Undocumented Opcode Tests are still not handled)
* Supports GB and GBC Bios
* Has UI based debugger support (Only for GB and GBC)
* Has Command-Line based debugger support for platforms other than GB and GBC (Note: This is currently disabled)
* Options for different palettes for GB (Includes 'Gearboy', 'Sameboy' and 'BGB' palettes)
* GB / GBC passes most of the Blargg tests (Except for the wave ram tests)
* GB / GBC passes many of the Moon Eye tests (There are still many which doesn't pass as is, but would probably pass with little tweaks in the CONFIG.ini)
* GB / GBC passes the RTC (rtc3test) tests
* GB / GBC implements Pixel Fetcher/FIFO
* GBC supports GB mode
* Able to play a slightly glitchy version of mezase.gbc (with few tweaks in the CONFIG.ini) 
* External Menu-bar based UI for Windows platform
* Internal Menu-bar based UI for platforms other than Windows
* Supports dynamic drag and drop of roms (this includes multiple rom files for Space Invaders and Pacman/MsPacman)

_**Features under developement:**_
* Support Link Cable for Gameboy and Gameboy Color
* Support Super-Gameboy
* Pass Timendus's chip8-test-suite v4.1's scrolling tests for Chip8
* Pass blargg's waveram and oam-bug tests for Gameboy
* Pass all Moon Eye Tests for Gameboy and Gameboy Color
* Emulate undocumented opcodes for I8080 and Z80 based platforms

# Game Play

_Debugger (Supported only when emulator runs in Gameboy and Gameboy Color modes)_

![GBC-Debugger](https://github.com/Kotambail-Hegde/Masquerade-Emulator/assets/29670073/50e26ee3-abd8-432a-bbaa-0ca8891fc892)

_Gameboy_ _(Prehistorik Man in 'BGB' palette and Pokemon Green in 'Gearboy' palette)_

![PrehistorikMan](https://github.com/Kotambail-Hegde/Masquerade-Emulator/assets/29670073/8819c689-b3ad-444e-bece-d43a993e05b7) ![Green](https://github.com/Kotambail-Hegde/Masquerade-Emulator/assets/29670073/519c7f6e-ebb1-4e60-b677-d860ffb0f8a1)

_Gameboy Color_ _(Donkey Kong Country and Pokemon Crystal)_

![DonkeyKongCountry](https://github.com/Kotambail-Hegde/Masquerade-Emulator/assets/29670073/3d6bfb58-ae88-4b66-b299-ef20faf67112) ![Crystal](https://github.com/Kotambail-Hegde/Masquerade-Emulator/assets/29670073/3b318907-dc70-4488-8552-729b98504603)

_Ms Pacman_

![MsPacman](https://github.com/Kotambail-Hegde/Masquerade-Emulator/assets/29670073/b55f29d8-fcfb-4d5b-b30c-fb9b8afe0e35) 

_Pacman_

![Pacman](https://github.com/Kotambail-Hegde/Masquerade-Emulator/assets/29670073/81b421c4-bb53-4985-ae15-90d8dd572b5a) 

_Space Invader_

![SpaceInvaders](https://github.com/Kotambail-Hegde/Masquerade-Emulator/assets/29670073/afac2f45-75e0-4a24-b087-1499360cf703)

_Chip8:_ _(Pong)_

![Chip8](https://github.com/Kotambail-Hegde/Masquerade-Emulator/assets/29670073/f162afa0-733e-4d4f-8fdf-7a907cb878e2)

_Game Of Life_ _(Toroidal Mode)_

![GameOfLife](https://github.com/Kotambail-Hegde/Masquerade-Emulator/assets/29670073/44bd5adf-bbe5-4edc-a47a-eff03cc8faae)

# Supported Platforms

As of today, Masquerade is only tested for Windows. There are plans to port this to Linux as well.

# User Interface

In Windows, external Menu-bar based UI can be used for using various options of the emulator (Whatever features not available in GUI could be accessed via CONFIG.ini)

![WIN32API](https://github.com/Kotambail-Hegde/Masquerade-Emulator/assets/29670073/33d62a3d-9daa-4bfc-b549-4e4bd42b09a3)

In Non-Windows system (when supported), for now, internal Menu-bar based UI which is independent of host platform needs to be used (Whatever features not available in GUI could be accessed via CONFIG.ini)

![RetroMode](https://github.com/Kotambail-Hegde/Masquerade-Emulator/assets/29670073/6b6ae213-20ff-44ef-a7af-bd7adcc56df6)

# Credits
* Forked version of One Lone Coder's Pixel Game Engine is used for Graphics (https://github.com/Kotambail-Hegde/olcPixelGameEngine)
* One Lone Coder's Sound Wave Engine is used for Audio (https://github.com/OneLoneCoder/olcSoundWaveEngine)
* Boost libraries to parse .ini files
* GB Pacdocs (https://gbdev.io/pandocs/)
* GB Dev Wiki (https://gbdev.gg8.se/wiki/articles/Memory_Bank_Controllers)
* Codeslinger's blog (http://www.codeslinger.co.uk/pages/projects/gameboy.html)
* Night Shade's blog for audio implementation (https://nightshade256.github.io/2021/03/27/gb-sound-emulation.html)
* Blargg Roms used for testing
* The Ultimate Gameboy Talk (https://github.com/drhelius/Gearboy)
* Antonio's blog (https://github.com/AntonioND/giibiiadvance/blob/master/docs/TCAGBD.pdf)
* Gearboy used for testing (https://github.com/drhelius/Gearboy)
* gbmulator used for testing (https://github.com/mpostaire/gbmulator)





