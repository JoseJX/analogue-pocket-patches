# analogue-pocket-patches

## How they're generated

To convert a ROM, all accesses to the [LCDC](https://gbdev.io/pandocs/LCDC.html) and [STAT](https://gbdev.io/pandocs/STAT.html) registers need to be bit reversed. The pocket format also moves the LCDC hardware register to offset 0xFF4E from 0xFF40 in the actual Game Boy hardware. To make it work, you need to go through all of the code in the ROM and replace every instance where these registers are used (and memory locations that have values that get transferred to/from these registers) with the bit reversed operation (i.e. $83 -> $C1) and replace every LCDC usage with the new address ($4e or $ff4e).

For my workflow, to generate the `.pocket` file, the ROM is first decompiled with [mgbdis](https://github.com/mattcurrie/mgbdis) and then recompiled with [rgbds](https://github.com/gbdev/rgbds) after patching the above issues and whatever else pops up. Once it's recompiled, the [header](https://gbdev.io/pandocs/The_Cartridge_Header.html#0104-0133---nintendo-logo) needs to be modified to use Analogue's header rather than the Nintendo header.

I then generate the final IPS patch using [lipx](https://github.com/kylon/Lipx), which compares the original ROM with the patched version.

To debug issues with the patches, I have provided a copy of SameBoy that is patched to run `.pocket` files and to print some warnings if there are register accesses to 0xFF40. It is available here: [https://github.com/JoseJX/SameBoy](https://github.com/JoseJX/SameBoy).

Hopefully this helps!

## How to use the patches

You will need IPS patching software, the IPS patch for your chosen game and the specific ROM revision for the patch. Once the IPS patch is applied you need to change the file extension from `.gb` to `.pocket` and place them in a `GB Studio` folder on the root of your microSD card. Please make sure to keep the filename short, longer filenames appear to cause trouble.

Please note that link cable functionality and the real-time clock are not supported in GB Studio mode.

## Bionic Commando

This patch converts `Bionic Commando (U)` to the `.pocket format.

ROM MD5: `f89a33de3fa660a13ec29bb323efffa9`

You can [download the Analogue Pocket IPS patch here](https://github.com/JoseJX/analogue-pocket-patches/blob/main/BionicCommando.ips).

## Duck Tales

This patch converts `Duck Tales (U)` to the `.pocket` format.

ROM MD5: `785441d3d75913393807b10b3194dc48`

You can [download the Analogue Pocket IPS patch here](https://github.com/JoseJX/analogue-pocket-patches/blob/main/DuckTales.ips).

## Mario's Picross

This patch converts `Mario's Picross (U,E)` to the `.pocket` format.

ROM MD5: `ccaf9331318d4dfe3d1ee681928a74fd`

You can [download the Analogue Pocket IPS patch here](https://github.com/JoseJX/analogue-pocket-patches/blob/main/MarioPicross.ips).

## Mega Man - Dr. Wily's Revenge 

This patch converts `Mega Man - Dr. Wily's Revenge (U)` to the `.pocket` format.

ROM MD5: `4ba4398181d98958fa7434ba7716f11a`

You can [download the Analogue Pocket IPS patch here](https://github.com/JoseJX/analogue-pocket-patches/blob/main/MegaMan1.ips).

## Mega Man II

This patch converts `Mega Man II (U)` to the `.pocket` format.

ROM MD5: `7fe07271d04ed9e0bc0663dde55a2ae4`

You can [download the Analogue Pocket IPS patch here](https://github.com/JoseJX/analogue-pocket-patches/blob/main/MegaMan2.ips).

## Mega Man III

This patch converts `Mega Man III (U)` to the `.pocket` format.

ROM MD5: `4c614f884a07872f12056ad1a421e1f9`

You can [download the Analogue Pocket IPS patch here](https://github.com/JoseJX/analogue-pocket-patches/blob/main/MegaMan3.ips).

## Mega Man IV

This patch converts `Mega Man IV (U)` to the `.pocket` format.

ROM MD5: `8a00f627b8902c92327435901c249e19`

You can [download the Analogue Pocket IPS patch here](https://github.com/JoseJX/analogue-pocket-patches/blob/main/MegaMan4.ips).

## Mega Man V

This patch converts `Mega Man V (U)` to the `.pocket` format.

ROM MD5: `ceb17d831b410d91aa41bf2819cbed82`

You can [download the Analogue Pocket IPS patch here](https://github.com/JoseJX/analogue-pocket-patches/blob/main/MegaMan5.ips).

## Mole Mania

This patch converts `Mole Mania (U)` to the `.pocket` format.

It has been updated to fix [bug #2](https://github.com/JoseJX/analogue-pocket-patches/issues/2).

It has been updated again for another missed register access. (2021/12/30)

ROM MD5: `f28ade3926852a8ad2e449c274683956`

You can [download the Analogue Pocket IPS patch here](https://github.com/JoseJX/analogue-pocket-patches/blob/main/MoleMania.ips).

## Ms. Pac-Man

This patch converts `Ms. Pac-Man (U)` to the `.pocket` format.

ROM MD5: `ffa8642a18781fbe79df436a761a9775`

You can [download the Analogue Pocket IPS patch here](https://github.com/JoseJX/analogue-pocket-patches/blob/main/MsPacMan.ips).

## Pokemon Puzzle Challenge

This patch converts `Pokemon Puzzle Challenge (U)` to the `.pocket` format.

ROM MD5: `f9ec4cc3c9df3887dc731ccf53663ffb`

You can [download the Analogue Pocket IPS patch here](https://github.com/JoseJX/analogue-pocket-patches/blob/main/PokePuzzle.ips).

## Side Pocket

This patch converts `Side Pocket (U)` to the `.pocket` format.

ROM MD5: `3dbe9be772ca50da3a76d8860c7b08e2`

You can [download the Analogue Pocket IPS patch here](https://github.com/JoseJX/analogue-pocket-patches/blob/main/SidePocket.ips).

## Super Off Road

This patch converts `Super Off Road (U)` to the `.pocket` format.

ROM MD5: `85d05f95c07ed1b7d787062fe4d2e251`

You can [download the Analogue Pocket IPS patch here](https://github.com/JoseJX/analogue-pocket-patches/blob/main/SuperOffRoad.ips).

## Super R.C. Pro-Am

This patch converts `Super R.C. Pro-Am (U,E)` to the `.pocket` format.

ROM MD5: `9ba2999ef3ecf9e27ac6c88e995c9d7a`

You can [download the Analogue Pocket IPS patch here](https://github.com/JoseJX/analogue-pocket-patches/blob/main/SuperRC.ips).

## Tetris Attack

This patch converts `Tetris Attack (U) (1.0)` to the `.pocket` format.

ROM MD5: `7fbda0c87af7701bb5e75c2a77bb0143`

You can [download the Analogue Pocket IPS patch here](https://github.com/JoseJX/analogue-pocket-patches/blob/main/TetrisAttack.ips).

## Yoshi

This patch converts `Yoshi (U)` to the `.pocket` format.

ROM MD5: `a8804c8514619cc918960c2008ed65d1`

You can [download the Analogue Pocket IPS patch here](https://github.com/JoseJX/analogue-pocket-patches/blob/main/Yoshi.ips).

## Yoshi's Cookie

This patch converts `Yoshi's Cookie (U)` to the `.pocket` format.

ROM MD5: `bc1a3848092bdc900c157996c29a7783`

You can [download the Analogue Pocket IPS patch here](https://github.com/JoseJX/analogue-pocket-patches/blob/main/YoshisCookie.ips).

