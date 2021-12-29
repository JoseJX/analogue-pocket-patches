# analogue-pocket-patches

## How they're generated

To convert a ROM, all accesses to the `LCDC` and `STAT` register need to be bit reversed. The pocket format also moves the `LCDC` register to offset `0xFF4E`.

To generate the `.pocket` file, the ROM is decompiled with [mgbdis](https://github.com/mattcurrie/mgbdis) and recompiled with [rgbds](https://github.com/gbdev/rgbds) after patching.

Finally, the header needs to be modified to use Analogue's header rather than the Nintendo header. After compilation, modify the header.

The final IPS patch is generated using [lipx](https://github.com/kylon/Lipx), comparing the original ROM with the patched version.

A version of SameBoy that is patched to run `.pocket` files is available here: [https://github.com/JoseJX/SameBoy](https://github.com/JoseJX/SameBoy), this has been useful for finding bugs in the patches!

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

## Mole Mania

This patch converts `Mole Mania (U)` to the `.pocket` format.

It has been updated to fix [bug #2](https://github.com/JoseJX/analogue-pocket-patches/issues/2).

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

