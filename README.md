# Masquerade Emulator

_**A multi-system emulator which emulates the following gaming consoles and simulators**_
* Game Boy Advance (GBA)
* Game Boy Color (GBC)
* Game Boy (GB)
* Nintendo Entertainment System (NES)
* Ms Pacman
* Pacman (supports both Midway and Namco versions)
* Space Invaders
* CHIP8
* S-CHIP
* XO-CHIP
* Game Of Life

_**Below mentioned gaming consoles are in roadmap**_
* Super Nintendo Entertainment System (SNES)
* Nintendo DS
* Nintendo 3DS

_**Supported features**_
* Supports GBA Bios
* GBA passes jsmolka/alysoha-tas's arm.gba, thumb.gba, memory.gba, flash and PPU tests
* GBA passes FuzzARM.gba
* GBA passes all the AGS test suite except for Prefetch and Wait Control Memory tests
* GBA passes most of the tonc's test suite
* GBA mostly implements cycle accurate PPU access patterns documented by fleroviux
* GBA is able to play most of the GBA video roms
* GB / GBC supports NO MBC, MBC1, MBC2, MBC3 and MBC5
* Supports GB and GBC Bios
* GB / GBC implements Pixel Fetcher/FIFO
* GBC supports GB mode
* GB / GBC passes Tom Harte's CPU test including cycles (both official and un-official opcodes)
* GB / GBC passes all of the Blargg tests except for Wave RAM tests (**_Wave Ram tests are under debug_**)
* GB / GBC passes many of the Moon Eye tests (**_Failing tests probably would pass with tweaks in the CONFIG.ini file_**)
* GB / GBC passes the RTC (rtc3test) tests
* GBC is able to play a slightly glitchy version of mezase.gbc (**_With few tweaks in the CONFIG.ini_**) 
* GB has options for different palettes (Includes 'Gearboy', 'Sameboy' and 'BGB' palettes)
* NES supports NROM, MMC1, UxROM (002), CNROM, MMC3, AxROM and GxROM
* NES supports Zapper in Port 2 (using mouse clicks)
* NES supports battery backed PRG RAM
* NES passes Nestest (both official and un-official opcodes)
* NES passes Tom Harte's CPU test including cycles (both official and un-official opcodes)
* NES passes all of Blargg's CPU tests (both official and un-official opcodes)
* NES passes all of Blargg's CPU timing tests (both official and un-official opcodes)
* NES passes all of Blargg's CPU dummy read/write tests (both official and un-official opcodes)
* NES passes all CPU tests mentioned in Nes Dev Wiki (both official and un-official opcodes)
* NES passes all the Blargg's blargg_ppu_tests_2005.09.15b tests
* NES passes all the Blargg's blargg_apu_2005.07.30
* NES passes all the Blargg's sprite_overflow_tests
* NES passes all the Blargg's sprite_hit_tests_2005.10.05 tests
* NES passes all other APU tests except for DMC (**_DMC is not implemented yet_**)
* NES passes Blargg's vbl_nmi_timing and ppu_vbl_nmi tests
* NES passes Blargg's cpu_interrupt_v2 tests
* NES passes the OAM stress tests
* NES passes both Blargg's and Bisqwit's ppu_open_bus tests
* NES passes Bisqwit's cpu_exec_space tests
* NES passes all of Blargg's mmc3_irq_tests
* NES passes all of Blargg's mmc3_test/mmc3_test_2 expect for 4-scanline_timing.nes (**_This is under debug_**)
* Supports many Z80 test roms (**_Undocumented Opcode Tests are still not handled_**)
* Supports many c6502 test roms (both official and un-official opcodes)
* Supports many 8080 test roms (**_Undocumented Opcode Tests are still not handled_**)
* Chip8 supports CHIP8, S-CHIP and XO-CHIP modes
* Chip8 passes all Timendus's chip8-test-suite v4.2 expect for scrolling tests (**_Support is not implemented yet_**)
* Game Of Life supports Normal Mode and Torroidal Mode
* Supports Save States and Load States
* Has GUI based debugger support (**_For now, this is supported only in GB and GBC, currently in development for NES and GBA_**)
* Has CLI based debugger support (**_For now, this is supported only in NES and GBA, currently in developement for GB and GBC_**)
* Supports OTA updates
* Menu-bar based UI for Windows platform
* Internal GUI for platforms other than Windows
* Supports dynamic drag and drop of roms. This includes multiple rom files for Space Invaders and Pacman/MsPacman

_**Features under developement**_
* Support for scrolling requirement by Timendus's chip8-test-suite v4.2
* Support Link Cable for Gameboy and Gameboy Color
* Implement "_Sync to Audio Playback Rate_" to support audio for GBA and NES
* Implement ROM prefetch and review the currently implemented sequential and non sequential wait cycles

_**Known Major Issues**_
* GBA not so often exibits few minor graphical glitches. Suspected to be related to some startup or initialization not happening as expected.
* GB/GBC audio is still has lot of undesired interference. "_Sync to Audio Playback Rate_" is expected to help in resolving these issue.

# Game Play

**Masquerade also provides some debugging facilites for homebrew developement.**

## Game Play with Debugger

* **QT5 based Debugger**

  - _Not supported yet_

* **ImGui based Debugger**

  - _Not supported yet_

* **Windows API based Debugger**

  - _Not supported yet_

* **Bare Metal (OLC) based Debugger**

  - _Currently supported only when emulator runs in Gameboy and Gameboy Color modes_

![GBC-Debugger](https://github.com/Kotambail-Hegde/Masquerade-Emulator/assets/29670073/50e26ee3-abd8-432a-bbaa-0ca8891fc892)

* **CLI based Debugger**

  - _Currently supported only when emulator runs in Gameboy Advance and Nintendo Entertainment System modes_

## Normal Game Play

_Gameboy Advance_ _(Pokemon Ruby, Emerald and Sapphire)_

![Ruby](https://github.com/user-attachments/assets/4d50ea26-2368-46ea-8753-53c470a056d4) ![Emerald](https://github.com/user-attachments/assets/d7dea1b2-f6eb-4ebc-a041-4f25b5a191b5) ![Sapphire](https://github.com/user-attachments/assets/8b5a58cb-d602-4b47-9fc9-833e36f6737a)

_Gameboy Advance_ _(Pokemon Fire Red and Leaf Green)_

![FireRed](https://github.com/user-attachments/assets/c1d64f3a-ff2e-4b36-9adf-612df56e178e) ![leafGreen](https://github.com/user-attachments/assets/471c901a-b278-406b-8b99-41bdb4787188)

_Gameboy Color_ _(Donkey Kong Country and Pokemon Crystal)_

![DonkeyKongCountry](https://github.com/Kotambail-Hegde/Masquerade-Emulator/assets/29670073/3d6bfb58-ae88-4b66-b299-ef20faf67112) ![Crystal](https://github.com/Kotambail-Hegde/Masquerade-Emulator/assets/29670073/3b318907-dc70-4488-8552-729b98504603)


_Gameboy_ _(Prehistorik Man in 'BGB' palette and Pokemon Green in 'Gearboy' palette)_

![PrehistorikMan](https://github.com/Kotambail-Hegde/Masquerade-Emulator/assets/29670073/8819c689-b3ad-444e-bece-d43a993e05b7) ![Green](https://github.com/Kotambail-Hegde/Masquerade-Emulator/assets/29670073/519c7f6e-ebb1-4e60-b677-d860ffb0f8a1)


_Nintendo Entertainment System_ _(Super Mario Bros 3)_

![smb3-ezgif com-video-to-gif-converter](https://github.com/user-attachments/assets/e57d0412-043f-4fe5-89b6-2b6b157289cf)

_Nintendo Entertainment System_ _(Super Mario Bros)_

![SMB](https://github.com/user-attachments/assets/40cb5e26-0033-4243-863b-5adc9bbe72bb)

_Nintendo Entertainment System_ _(Zelda II: The Adventure of Link)_

![zelda2](https://github.com/user-attachments/assets/0429cac5-3d0d-4205-8ed2-878854601d89)

_Nintendo Entertainment System_ _(Kong Classic)_

![kongClassic](https://github.com/user-attachments/assets/c8784239-7515-45b3-aa55-3a6863669e74)


_Ms Pacman_

![MsPacman](https://github.com/Kotambail-Hegde/Masquerade-Emulator/assets/29670073/b55f29d8-fcfb-4d5b-b30c-fb9b8afe0e35) 


_Pacman_

![Pacman](https://github.com/Kotambail-Hegde/Masquerade-Emulator/assets/29670073/81b421c4-bb53-4985-ae15-90d8dd572b5a) 


_Space Invader_

![SpaceInvaders](https://github.com/Kotambail-Hegde/Masquerade-Emulator/assets/29670073/afac2f45-75e0-4a24-b087-1499360cf703)


_Chip8_ _(Pong)_

![Chip8](https://github.com/Kotambail-Hegde/Masquerade-Emulator/assets/29670073/f162afa0-733e-4d4f-8fdf-7a907cb878e2)


_Game Of Life_ _(Toroidal Mode)_

![GameOfLife](https://github.com/Kotambail-Hegde/Masquerade-Emulator/assets/29670073/44bd5adf-bbe5-4edc-a47a-eff03cc8faae)

# Supported Platforms

As of now, masquerade is only tested for windows platform. There are plans to port this to other platforms in near future.

# User Interface

## QT5
Not supported yet

## ImGui
Not supported yet

## Windows API
In windows platform, Windows API based user interface can be used for accessing various options of the emulator (whatever features not available via the menu-bar should be accessible via the CONFIG.ini)

![Win32api](https://github.com/user-attachments/assets/e5d14f79-484f-4479-bd25-0efe7b1f0bd4)

## Bare Metal (OLC)
In non-windows (and also supported in windows) based platforms, for now, only the bare metal user interface is supported (whatever features not available via the internal menu-window should be accessible via the CONFIG.ini)

![RetroMode](https://github.com/user-attachments/assets/35f4caee-2601-4211-97b6-44afc6f57b3f)

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
* BGB and Sameboy for the palettes
* BGB for providing the inspiration for the GUI based debugger
* Emulator Development Discord Channel (https://discord.com/invite/emudev)
* gbatek (http://problemkaputt.de/gbatek-gba-reference.htm)
* TONC (https://gbadev.net/tonc/)
* NBA HW Docs (https://nba-emu.github.io/hw-docs/)
* GBA Docs (https://gbadev.net/gbadoc/)
* Dillonb blog for catridges (https://dillonbeliveau.com/2020/06/05/GBA-FLASH.html)
* Dillonb used for testing and also for providing the inspiration for the CLI based logger/debugger (https://github.com/Dillonb/gba/tree/master)
* NBA used for testing (https://github.com/nba-emu/NanoBoyAdvance)
* SkyEmu used for testing (https://github.com/skylersaleh/SkyEmu)
* jsmolka and alyosha-tas test roms
* AGS test roms and their source files from DenSinH (https://github.com/DenSinH/AGSTests/tree/main)
* NES Dev Wiki (https://www.nesdev.org/wiki/Nesdev_Wiki)
* GBA PPU access pattern (https://nba-emu.github.io/hw-docs/ppu/ppu.html)
* Tom Harte tests for 6502 and SM82 cpu testing




