# ctvn - Chrono Trigger SNES Vietnamese Translation

Using chronotools https://bisqwit.iki.fi/source/chronotools.html

Quick guide: https://bisqwit.iki.fi/ctfin/dev/quickstart.html

## Compile chronotools
### Linux
To build *utils/viewer*, install libslang2-dev
```
sudo apt-get install libslang2-dev
```

Download latest version and extract:

```
$ tar xfj chronotools-1.15.8.tar.bz2
$ mv chronotools-1.15.8 ct
$ make -C ct
```

May need to remove file ```ct/.depend``` if got this error:
```
.depend:3: *** missing separator.  Stop.
```

## Usage

US rom checksum:
```
❯ md5sum chrono_trigger_us.smc 
a2bc447961e52fd2227baed164f729dc  chrono_trigger_us.smc
```

Create a working directory
```
mkdir ~/ctvn
```
and copy the original ROM file and the configuration file to this directory
```
cp ct/etc/ct.cfg ~/ctvn
cp <rom_file> ~/ctvn
```

In the working directory, run the ctdump to extract ROM contents
```
❯ ../ct/ctdump chrono_trigger_us.smc 
Chrono Trigger script dumper version 1.15.8
Copyright (C) 1992,2005 Bisqwit (http://iki.fi/bisqwit/)
Reading ct.cfg... done
Loading ROM... $400000 bytes... memmap succesful (0x7f6934c15000), done
Dictionary end byte for this ROM is $A0... Dictionary is at $1EFA00
Creating ctdump.out (all text content)...
Creating ct8fn.tga (8pix font)... done
Creating ct16fn.tga (12pix font)... done
Creating titlegfx.tga (title screen gfx)... done
Creating pontpo.tga (worldmap gfx 1)... done
Creating eraes.tga (epoch control gfx)... done
Creating active2.tga (batlmode prompt gfx 2)... done
Creating active1.tga (batlmode prompt gfx 1)... done
Creating misc1.tga (symbol gfx 1)... done
Creating misc2.tga (symbol gfx 2)... done
Creating misc3.tga (symbol gfx 3)... done
Creating elem1.tga (elemental symbol 1)... done
Creating elem2.tga (elemental symbol 2)... done
Creating elem3.tga (elemental symbol 3)... done
Creating elem4.tga (elemental symbol 4)... done
All done
```
These are the dumped files:
```
❯ lt
total 4,7M
-rw-rw-r-- 1 hungdt hungdt 4,0M Jun 24 22:32 chrono_trigger_us.smc
-rw-rw-r-- 1 hungdt hungdt  13K Jun 24 22:35 ct.cfg
-rw-rw-r-- 1 hungdt hungdt  12K Jun 24 22:35 titlegfx.tga
-rw-rw-r-- 1 hungdt hungdt 8,1K Jun 24 22:35 pontpo.tga
-rw-rw-r-- 1 hungdt hungdt 2,1K Jun 24 22:35 misc3.tga
-rw-rw-r-- 1 hungdt hungdt 1,7K Jun 24 22:35 misc2.tga
-rw-rw-r-- 1 hungdt hungdt  798 Jun 24 22:35 misc1.tga
-rw-rw-r-- 1 hungdt hungdt 7,2K Jun 24 22:35 eraes.tga
-rw-rw-r-- 1 hungdt hungdt  834 Jun 24 22:35 elem4.tga
-rw-rw-r-- 1 hungdt hungdt  834 Jun 24 22:35 elem3.tga
-rw-rw-r-- 1 hungdt hungdt  834 Jun 24 22:35 elem2.tga
-rw-rw-r-- 1 hungdt hungdt  834 Jun 24 22:35 elem1.tga
-rw-rw-r-- 1 hungdt hungdt  21K Jun 24 22:35 ct8fn.tga
-rw-rw-r-- 1 hungdt hungdt 128K Jun 24 22:35 ct16fn.tga
-rw-rw-r-- 1 hungdt hungdt  798 Jun 24 22:35 active2.tga
-rw-rw-r-- 1 hungdt hungdt 2,4K Jun 24 22:35 active1.tga
-rw-rw-r-- 1 hungdt hungdt  83K Jun 24 22:35 ct_addr.log
-rw-rw-r-- 1 hungdt hungdt 353K Jun 24 22:35 ctdump.out
-rw-rw-r-- 1 hungdt hungdt  12K Jun 24 22:35 ct_map.log
```

File ctdump.out is the script
