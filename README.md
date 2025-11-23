# Masquerade Emulator


_This was just a hobby project that I started for fun, but was not able to put much effort because of my busy schedule._

_But still, the emulator tries to be as accurate as possible but since I don't have the actual hardware for any of the systems that I am trying to emulate, I am completely relying on other's research that is available in discord, blogposts or other emulator specific wiki pages. I personally have done very minimal 'original research' for these platforms due to the lack of hardware._

_I have avoided referencing other emulator's source code and tried to only rely only on available documentation and QnA in discord as much as possible, but still had to tweak a few accurate emulators (mentioned in credit section below) to either extract debug logs or to run my own custom roms and analyse the behaviour._

_<ins>**Note : The source code for the masquerade emulator will be made open-source as soon as _P0152_ builds are ready**</ins>_

**_So, what is Masquerade ?_**

_**A multi-system emulator which emulates the following gaming consoles and simulators**_
- [x] Game Boy Advance (GBA)
- [x] Game Boy Color (GBC)
- [x] Game Boy (GB)
- [x] Nintendo Entertainment System (NES)
- [x] Ms Pacman
- [x] Pacman (supports both Midway and Namco versions)
- [x] Space Invaders
- [x] CHIP8
- [x] S-CHIP
- [x] XO-CHIP
- [x] Game Of Life

_**Below mentioned gaming consoles may probably be looked at in the future**_
- [ ] Super Game Boy
- [ ] Super Nintendo Entertainment System (SNES)
- [ ] Nintendo DS
- [ ] Nintendo 3DS

_**Supported features**_
* Masquerade is now available as a Web version!
* GBA
  * Supports GBA Bios
  * GBA passes jsmolka/alysoha-tas's arm.gba, thumb.gba, memory.gba, flash and PPU tests
  * GBA passes FuzzARM.gba
  * GBA passes all the tests within the AGS suite except for the following:
    - [ ] PREFETCH BUFFER
    - [ ] WAIT STATE WAIT CONTROL
    - [ ] CARTRIDGE RAM WAIT CONTROL
    - [ ] TIMER PRESCALER 0
  * GBA passes all the mgba-suite tests except for the following tests:
    - [ ] Timing Tests
    - [ ] Timer Count-Up Tests
    - [ ] Timer IRQ Tests
    - [ ] DMA Tests
    - [ ] SIO Tests
    - [ ] MISC Edge Case Tests
  * GBA passes all the tests in tonc's test suite
  * GBA passes all of the belogic's audio tests
* GB / GBC
  * Supports GB and GBC Bios
  * GB / GBC supports following MBCs
    - [x] NO MBC
    - [x] MBC1
    - [x] MBC2
    - [x] MBC3
    - [x] MBC5
    - [x] MBC30
  * GB / GBC implements Pixel-Fetcher/Pixel-FIFO
  * GBC supports GB mode
  * GB / GBC support GameGenie and GameShark cheats
  * GB / GBC completely passes Tom Harte's SingleStepTests (both official and un-official opcodes) for SM83
  * GB / GBC passes the all the Blargg test suite except for the following
    - [ ] oam_bug.gb
  * GB / GBC passes all of the Moon Eye tests except for the following:
    - [ ] boot_div-dmgABCmgb.gb
    - [ ] boot_hwio-dmgABCmgb.gb
    - [ ] intr_2_mode0_timing_sprites.gb
  * GB / GBC passes all of the Wilbert Pol's tests except for the following:
    * GB and GBC
      - [ ] intr_2_mode0_timing_sprites.gb
      - [ ] intr_2_mode0_timing_sprites_nops.gb
      - [ ] intr_2_mode0_timing_sprites_scx1_nops.gb
      - [ ] intr_2_mode0_timing_sprites_scx2_nops.gb
      - [ ] intr_2_mode0_timing_sprites_scx3_nops.gb
      - [ ] intr_2_mode0_timing_sprites_scx4_nops.gb
    * GB only
      - [ ] ly_lyc_153_write-GS.gb
      - [ ] stat_write_if-GS.gb
    * GBC only
      - [ ] ly_lyc_153_write-C.gb
      - [ ] ly_lyc_write-C.gb
      - [ ] stat_write_if-C.gb
  * GB / GBC passes all the Daid's GBEmulatorShootout tests except for the following
      - [ ] ppu_scanline_bgp.gb
  * GB passes all the PeachyHardwareAbuse tests including ctf.gb
  * GB / GBC passes DMG Aging Catridge test
  * GB / GBC passes the ax6's rtc3test suite
  * GB / GBC passes all the Hacktix's tests except for the following
    - [ ] strikethrough.gb
  * GB / GBC passes the TurtleTests
  * GBC passes MagenTests
  * GB / GBC passes mbc3-tester
  * GB / GBC still fails the following same-suite tests
    - [ ] apu
  * GB / GBC still fails the following age-test-roms tests
    - [ ] lcd-align-ly
    - [ ] m3-bg-bgp
    - [ ] m3-bg-lcdc
    - [ ] m3-bg-scx
    - [ ] oam
    - [ ] speed-switch
    - [ ] stat-interrupt
    - [ ] stat-mode
    - [ ] stat-mode-sprites
    - [ ] stat-mode-window
    - [ ] vram
  * GB/GBC supports BESS specification as option to be used for save/load states
  * GB / GBC is able to play several demo scenes including notable ones like oh.gb, 20y.gb, pocket.gb and demotronic.gbc
  * GB / GBC supports GBVideoPlayer2 video roms with audio support
  * GB / GBC APU is able to play ISSOtm's smooth-player.gb
  * GB supports multiple palettes
  * GBC support color correction to be more in line with the actual hardware
* NES
  * 6502 passes Klaus Dormann's 6502_65C02_functional_tests including BCD tests
  * NES supports following mappers
    - [x] NROM
    - [x] MMC1
    - [x] SEROM
    - [x] SHROM
    - [x] SH1ROM
    - [x] SuROM
    - [x] UxROM (002)
    - [x] CNROM
    - [x] MMC3
    - [x] AxROM
    - [x] GxROM
    - [x] Nanjian FC-001 (Mapper 163)
  * NES support GameGenie cheats
  * NES supports Zapper in Port 2 (using mouse clicks)
  * NES passes Nestest (both official and un-official opcodes)
  * NES completely passes Tom Harte's SingleStepTests (both official and un-official opcodes) for NES6502
  * NES passes the Blargg CPU tests (both official and un-official opcodes)
  * NES passes the Blargg's CPU timing tests (both official and un-official opcodes)
  * NES passes the Blargg's CPU dummy read/write tests (both official and un-official opcodes)
  * NES passes all CPU tests mentioned in Nes Dev Wiki (both official and un-official opcodes)
  * NES passes the blargg_ppu_tests_2005.09.15b tests
  * NES passes the blargg_apu_2005.07.30 tests
  * NES passes the Blargg's sprite_overflow_test suite
  * NES passes the Blargg's sprite_hit_tests_2005.10.05 test suite
  * NES passes all APU tests (including DMC tests)
  * NES passes Blargg's vbl_nmi_timing and ppu_vbl_nmi tests
  * NES passes Blargg's cpu_interrupt_v2 tests
  * NES passes the OAM stress tests
  * NES passes both Blargg's / Bisqwit's ppu_open_bus tests
  * NES passes Bisqwit's cpu_exec_space tests
  * NES passes the Blargg's mmc3_irq_tests suite
  * NES passes all of Blargg's mmc3_test/mmc3_test_2 expect for the following
    - [ ] 4-scanline_timing.nes
* Pacman and MsPacman
  * Pacman and MsPacman passes Tom Harte's SingleStepTests (both official and un-official opcodes) for Z80
  * Pacman and MsPacman passes the zexdoc and zexall tests
  * Supports both Midway and Namco variants
    * Pacman currently supports following boot-legs
      - [x] Hangly Man
      - [ ] Streaking
      - [ ] Titan
      - [ ] Caterpillar
      - [ ] Abscam
      - [ ] Joyman
      - [ ] Piranha
      - [ ] Galaxian Hardware Variant
      - [x] Uniprom Variant
      - [x] Baracuda
      - [x] NewPuc
      - [x] After Dark
      - [x] Snatcher Set 1 and 2
  * Supports MsPacman
    * MsPacman currently supports following boot-legs
      - [ ] MsPacPlus
      - [ ] After Dark
      - [ ] MsPacAttackNew
      - [ ] MsPacAtackOld
* Space Invader
  * Supports color overlays
* Chip8
  * Chip8 supports following variants
    - [x] Chip8
    - [x] S-Chip Legacy
    - [x] S-Chip Modern
    - [x] XO-Chip (Supports audio and upto 4 planes)
  * Chip8 completely passes Timendus's chip8-test-suite v4.2
  * Chip8 completely passes the CubeChip test suite
  * Chip8 supports ROM database which is used for auto-detection of the following
    * Variants
    * Quirks
    * Recommended Palettes
    * Recommended Keybindings
    * Recommended Rate
* Game Of Life supports following modes
  - [x] Normal Mode
  - [ ] Normal Mode with Pan/Zoom support
  - [x] Torroidal Mode
* Supports and passes a huge number of 8080 test roms (both official and un-official opcodes)
* Supports and passes a huge number of Z80 test roms (both official and un-official opcodes)
* Supports and passes a huge number of SM83 test roms (both official and un-official opcodes)
* Supports and passes a huge number of c6502 test roms (both official and un-official opcodes)
* Supports Save States and Load States
* Supports OTA updates
* Supports dynamic drag and drop of roms. This includes multiple rom files for Space Invaders and Pacman/MsPacman

_**Known Major Issues / Features under Debug / Implementations, other than the ones mentioned above**_
  * GBA
    - [ ] GBA is still not able to play few video roms like Dragon Ball GT
    - [ ] GBA still has very minor visual artifacts at top left corner in mode 3 while playing few video roms like Pokemon
    - [ ] GBA still has some undesired audio artifacts (expected to be fixed in **_P0152_** variant)
    - [ ] GBA is still not able to run at full speed consistenly without PGOs (expected to be fixed in **_P0152_** variant)
  * GB/GBC
    - [ ] GBC fails MMIO_exec_1.gb
    - [ ] GB/GBC still fails cgb-acid-hell
    - [ ] GB/GBC still fails many of the age-test-roms tests
    - [ ] GB/GBC still fails many of the docboy-test-suite roms
    - [ ] GB/GBC still fails many of the Mealybug Tearoom tests
    - [ ] GB/GBC still doesn't support Link Cable
    - [ ] GB/GBC still has many quirks unique to CGB which needs to be implemented
  * NES
    - [ ] NES is still not able to boot Dragon Warrior III
    - [ ] NES's DMC DMA's obscure timing quirks needs to be properly emulated

# Variants

As of today, there are 2 variants of masquerade available, P0052 and P0010.
The major differences between the two variants is the libraries used
* _P0052 : Is based on ImGui + SDL3 + OpenGL3_
* _P0010 : Is based on OLC_

# Game Play

## :white_check_mark: P0052 : ImGui + SDL3 + OpenGL3 (_Recommended_)

_UI_

<img width="440" height="319" alt="image" src="https://github.com/user-attachments/assets/f7af5623-f801-4d18-bcda-f18f7470454f" /> <img width="442" height="318" alt="image" src="https://github.com/user-attachments/assets/115f97b2-5858-4e2c-80b9-f6ba3049aa4a" />
  
_Gameboy Color_ _(Pokemon Crystal)_, _Gameboy Advance_ _(Pokemon Emerald)_ _and_ _Gameboy_ _(Pokemon Blue)_

![imgui_Crystal](https://github.com/user-attachments/assets/3011b49f-45c6-4f18-bbc5-6ede797e81ad) ![imgui_Emerald](https://github.com/user-attachments/assets/d668bc27-9589-4897-bc92-8e1ca14c5d7b) ![imgui_Blue](https://github.com/user-attachments/assets/3fa02907-9902-4b73-a75a-af8e74df8ef6)

## :warning: P0010 : OLC (_Not supported anymore, please switch to P0052_)

_UI_

<img width="443" height="315" alt="image" src="https://github.com/user-attachments/assets/331178df-2d66-4fba-8d10-dc5c186acb86" />

_Gameboy Advance_ _(Pokemon Ruby, Emerald and Sapphire)_

![Ruby](https://github.com/user-attachments/assets/4d50ea26-2368-46ea-8753-53c470a056d4)  ![Emerald](https://github.com/user-attachments/assets/511e90e0-aa1b-491c-9937-40c9d1e57ee6) ![Sapphire](https://github.com/user-attachments/assets/8b5a58cb-d602-4b47-9fc9-833e36f6737a)

_Gameboy Advance_ _(Pokemon Fire Red and Leaf Green)_

![FireRed](https://github.com/user-attachments/assets/c1d64f3a-ff2e-4b36-9adf-612df56e178e) ![leafGreen](https://github.com/user-attachments/assets/471c901a-b278-406b-8b99-41bdb4787188)

_Gameboy Color_ _(Donkey Kong Country and Pokemon Crystal)_

![DonkeyKongCountry](https://github.com/Kotambail-Hegde/Masquerade-Emulator/assets/29670073/3d6bfb58-ae88-4b66-b299-ef20faf67112) ![Crystal](https://github.com/Kotambail-Hegde/Masquerade-Emulator/assets/29670073/3b318907-dc70-4488-8552-729b98504603)

_Gameboy_ _(Prehistorik Man in 'BGB' palette, Pinball Deluxe in 'Gearboy' palette and Altered Space in 'Sameboy' palette)_

![PrehistorikMan](https://github.com/Kotambail-Hegde/Masquerade-Emulator/assets/29670073/8819c689-b3ad-444e-bece-d43a993e05b7) ![pinball](https://github.com/user-attachments/assets/85f488ce-09e3-4624-b98f-73de539d051c) ![alteredSpace](https://github.com/user-attachments/assets/b6c38587-8d40-4f41-ab1a-e921194ebf53)

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
## Currently Supported
- 🪟 **Windows**
- 🌐 **Web** – Now available as a browser-based version!
## Future Support
- 🍎 **macOS**
- 🐧 **Linux**

# Additional Libaries Used
## :white_check_mark: P0052 : ImGui + SDL3 + OpenGL3
* ImGui
* SDL3
* OpenGL3
* nativefiledialog-extended
* Boost libraries to parse .ini files

## :warning: P0010 : OLC
* Forked version of One Lone Coder's Pixel Game Engine
* One Lone Coder's Sound Wave Engine
* Boost libraries to parse .ini files

# Credits
* GB Pandocs (https://gbdev.io/pandocs/)
* GB Dev Wiki (https://gbdev.gg8.se/wiki/articles/Memory_Bank_Controllers)
* Codeslinger's blog (http://www.codeslinger.co.uk/pages/projects/gameboy.html)
* Night Shade's blog for audio implementation (https://nightshade256.github.io/2021/03/27/gb-sound-emulation.html)
* Blargg Roms used for testing
* The Ultimate Gameboy Talk (https://github.com/drhelius/Gearboy)
* Antonio's blog (https://github.com/AntonioND/giibiiadvance/blob/master/docs/TCAGBD.pdf)
* Gearboy used for testing as I don't have the actual Gameboy or Gameboy Color (https://github.com/drhelius/Gearboy)
* gbmulator used for testing as I don't have the actual Gameboy or Gameboy Color (https://github.com/mpostaire/gbmulator)
* Emulator Development Discord Channel (https://discord.com/invite/emudev)
* gbatek (http://problemkaputt.de/gbatek-gba-reference.htm)
* TONC (https://gbadev.net/tonc/)
* NBA HW Docs (https://nba-emu.github.io/hw-docs/)
* GBA Docs (https://gbadev.net/gbadoc/)
* Dillonb blog for catridges (https://dillonbeliveau.com/2020/06/05/GBA-FLASH.html)
* Dillonb used for testing and also for providing the inspiration for the CLI based logger/debugger (https://github.com/Dillonb/gba/tree/master)
* NBA used for testing as I don't have the actual Gameboy Advance (https://github.com/nba-emu/NanoBoyAdvance)
* SkyEmu used for testing as I don't have the actual Gameboy Advance (https://github.com/skylersaleh/SkyEmu)
* SkyEmu for inspiring the themes for the frontend (https://github.com/skylersaleh/SkyEmu)
* jsmolka and alyosha-tas test roms
* AGS test roms and their source files from DenSinH (https://github.com/DenSinH/AGSTests/tree/main)
* NES Dev Wiki (https://www.nesdev.org/wiki/Nesdev_Wiki)
* GBA PPU access pattern (https://nba-emu.github.io/hw-docs/ppu/ppu.html)
* Tom Harte tests for 6502 and SM84 cpu testing




