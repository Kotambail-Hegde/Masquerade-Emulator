# Masquerade Emulator


_This was just a hobby project that I started for fun, but was not able to put much effort because of my busy schedule._

_But still, the emulator tries to be as accurate as possible but since I don't have the actual hardware for any of the systems that I am trying to emulate, I was completely relying on other's research which is readily available on discord, blogposts and other emulator specific wiki pages for implementing the corner cases. I personally have done very minimal 'original research' for these platforms._

_I have avoided referencing other emulator's source code and tried to only rely on online information as much as possible, but still had to rely on few a cycle accurate emulators (mentioned in credit section below) and tweak them to either extract debug logs or to run my own custom roms and analyse the behaviour._

**_So, what is Masquerade ?_**

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

_**Below mentioned gaming consoles MAY PROBABLY be looked at in future**_
* Super Nintendo Entertainment System (SNES)
* Nintendo DS
* Nintendo 3DS

_**Supported features**_
* Supports GBA Bios
* GBA passes jsmolka/alysoha-tas's arm.gba, thumb.gba, memory.gba, flash and PPU tests
* GBA passes FuzzARM.gba
* GBA passes all the AGS test suite except for Prefetch and few Wait Cycles based memory tests
* GBA passes most of the tonc's test suite
* GBA mostly implements cycle accurate PPU access patterns documented by fleroviux
* GBA is able to play most of the GBA video roms
* GB / GBC supports NO MBC, MBC1, MBC2, MBC3, MBC5 and MBC30
* Supports GB and GBC Bios
* GB / GBC implements Pixel Fetcher/FIFO
* GB / GBC provides an upgraded version of PPU (v2), which tries to be 'PPU Dot Cycle Accurate'<br />
  * This particular version of PPU can be enabled via **Options->PPU Version->GB/GBC**<br />
  * Note that PPU v1 is set as default as PPU v2 is still under developement, so you might observe some graphical glitches.
  * PPU v2 will be made default once it is stable
* GBC supports GB mode
* GB / GBC passes Tom Harte's CPU test including cycles (both official and un-official opcodes)
* GB / GBC passes all of the Blargg tests except for oam bug
* GB / GBC passes most of the Moon Eye tests (some of the PPU tests fail with few T cycles differences)
* GB / GBC passes DMG Aging Catridge test
* GB / GBC passes the RTC (rtc3test) test
* GB / GBC passes all of the scribbltests tests except for few nops in statcount
* GB / GBC passes the TurtleTests
* GB / GBC passes mbc3-tester for both MBC3 and MBC30
* GBC is able to play a glitchy version of mezase.gbc (most of the glitch can be avoided if using PPU v2) :sweat_smile:
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
* Chip8 passes all Timendus's chip8-test-suite v4.0 (**_Most of v4.2 tests pass as well except for scrolling tests which is not implemented yet_**)
* Game Of Life supports Normal Mode and Torroidal Mode
* Supports Save States and Load States
* Has GUI based debugger support (**_For now, this is supported only in GB and GBC, currently in development for NES and GBA_**)
* Has CLI based debugger support (**_For now, this is supported only in NES and GBA, currently in developement for GB and GBC_**)
* Supports OTA updates
* Menu-bar based UI for Windows platform
* Internal GUI for platforms other than Windows
* Supports dynamic drag and drop of roms. This includes multiple rom files for Space Invaders and Pacman/MsPacman

_**Features under developement**_
* Support Link Cable for Gameboy and Gameboy Color
* Support for scrolling requirement by Timendus's chip8-test-suite v4.2
* Implement "_Sync to Audio Playback Rate_" to support audio for GB/GBC and NES

_**Known Major Issues**_
* GBA still doesn't support audio output (only GB/GBC based APU is implemented)
* GB/GBC audio is still has some undesired contents. "_Sync to Audio Playback Rate_" is expected to help in resolving these issue
* GB/GBC still doesn't support LIJI32's full motion videos other than the glitchy version of mezase.gbc
* NES still doesn't support audio output (APU is implemented except for DMC)

_**Other Known Issues**_
* GBA still fails a lot of 'Wait Cycles' and 'Catridge Prefetch (this is not even implemented yet)' based tests present in AGS and mgba test-suite
* GBA not so often / rarely exibits few minor graphical glitches. Suspected to be related to some startup/initialization not happening as expected.
* GB/GBC still fails many of the Wilbertpol's 'non Moon Eye tests'
* GB/GBC still fails many roms in the AGE test suite


# Game Play

Masquerade also provides some debugging facilites for homebrew developement.

## Game Play with Debugger

* **QT5 based Debugger**

  - _Not supported yet_

* **ImGui based Debugger**

  - _Not supported yet_

* **Windows API based Debugger**

  - _Not supported yet_

* **OLC based Debugger**

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


_Gameboy_ _(Prehistorik Man in 'BGB' palette, Pokemon Green in 'Gearboy' palette and Altered Space in 'Sameboy' palette)_

![PrehistorikMan](https://github.com/Kotambail-Hegde/Masquerade-Emulator/assets/29670073/8819c689-b3ad-444e-bece-d43a993e05b7) ![Green](https://github.com/Kotambail-Hegde/Masquerade-Emulator/assets/29670073/519c7f6e-ebb1-4e60-b677-d860ffb0f8a1) ![alteredSpace](https://github.com/user-attachments/assets/b6c38587-8d40-4f41-ab1a-e921194ebf53)




_Nintendo Entertainment System_ _(Super Mario Bros 3 and Zelda II: The Adventure of Link)_

![smb3-ezgif com-video-to-gif-converter](https://github.com/user-attachments/assets/ddd2fc8c-bd61-4ed2-b8f3-0bacdcd08987) ![zelda2](https://github.com/user-attachments/assets/fd9da1bc-8ecb-4922-95fb-512b984cfabd)


_Nintendo Entertainment System_ _(Super Mario Bros and Kong Classic)_

 ![SMB](https://github.com/user-attachments/assets/0d7448a5-e353-46e1-8635-6d37cce576d8) ![kongClassic](https://github.com/user-attachments/assets/42b79a0a-b867-4734-88de-dd9efe273193)




_Pacman_

![Pacman](https://github.com/Kotambail-Hegde/Masquerade-Emulator/assets/29670073/81b421c4-bb53-4985-ae15-90d8dd572b5a) 

_Ms Pacman_

![MsPacman](https://github.com/Kotambail-Hegde/Masquerade-Emulator/assets/29670073/b55f29d8-fcfb-4d5b-b30c-fb9b8afe0e35) 


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
_Not supported yet_

## ImGui
_Not supported yet_

## Windows API
In windows platform, Windows API based user interface can be used for accessing various options of the emulator (whatever features not available via the menu-bar should be accessible via the CONFIG.ini)

## OLC
In non-windows and windows platforms, OLC based user interface is supported (whatever features not available via the internal menu-window should be accessible via the CONFIG.ini)

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
* Gearboy used for testing as I don't have the actual GBC (https://github.com/drhelius/Gearboy)
* gbmulator used for testing as I don't have the actual GBC (https://github.com/mpostaire/gbmulator)
* Emulator Development Discord Channel (https://discord.com/invite/emudev)
* gbatek (http://problemkaputt.de/gbatek-gba-reference.htm)
* TONC (https://gbadev.net/tonc/)
* NBA HW Docs (https://nba-emu.github.io/hw-docs/)
* GBA Docs (https://gbadev.net/gbadoc/)
* Dillonb blog for catridges (https://dillonbeliveau.com/2020/06/05/GBA-FLASH.html)
* Dillonb used for testing and also for providing the inspiration for the CLI based logger/debugger (https://github.com/Dillonb/gba/tree/master)
* NBA used for testing as I don't have the actual GBA (https://github.com/nba-emu/NanoBoyAdvance)
* SkyEmu used for testing (https://github.com/skylersaleh/SkyEmu)
* jsmolka and alyosha-tas test roms
* AGS test roms and their source files from DenSinH (https://github.com/DenSinH/AGSTests/tree/main)
* NES Dev Wiki (https://www.nesdev.org/wiki/Nesdev_Wiki)
* GBA PPU access pattern (https://nba-emu.github.io/hw-docs/ppu/ppu.html)
* Tom Harte tests for 6502 and SM82 cpu testing




