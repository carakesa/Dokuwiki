# Command Line Tools

Brain dump of "must have" Command Line Tools (that I need to document for my package lists)

  # Use these in place of defaults:
    * exa - an alternative to 'ls'
    * bat - sometimes known as "batcat" is a better cat
    * less - less is 'more'
    * fd - alternative to find

  # Really Useful additions
    * LunarVIM (lvim)
    * tmux - Terminal Multiplexer
    * Fish - another shell, as opposed to bash or zsh.  Bash is always safe. zsh feels like there's too many options sometimes.
    * 





A side note on compression and multicore/multi-threading.

  # Package Compression (Multicore type)
      Shamelessly stolen from https://wiki.archlinux.org/title/makepkg

A chart from https://facebook.github.io/zstd/ regarding speeds vs/ ratios.

Compressor name 	Ratio 	Compression 	Decompress.

zstd 1.4.5 -1 	2.884 	500 MB/s 	1660 MB/s
zlib 1.2.11 -1 	2.743 	90 MB/s 	400 MB/s
brotli 1.0.7 -0 	2.703 	400 MB/s 	450 MB/s
zstd 1.4.5 --fast=1 	2.434 	570 MB/s 	2200 MB/s
zstd 1.4.5 --fast=3 	2.312 	640 MB/s 	2300 MB/s
quicklz 1.5.0 -1 	2.238 	560 MB/s 	710 MB/s
zstd 1.4.5 --fast=5 	2.178 	700 MB/s 	2420 MB/s
lzo1x 2.10 -1 	2.106 	690 MB/s 	820 MB/s
lz4 1.9.2 	2.101 	740 MB/s 	4530 MB/s
lzf 3.6 -1 	2.077 	410 MB/s 	860 MB/s
snappy 1.1.8 	2.073 	560 MB/s 	1790 MB/s



These packages were installed by default (I think) by Archcraft.  I simply adjusted the makepkg.conf settings and/or used the drop-in replacements as follows:

'#original command'
'multithreaded command'

    
#COMPRESSGZ=(gzip -c -f -n)
COMPRESSGZ=(pigz -c -f -n)

#COMPRESSBZ2=(bzip2 -c -f)
COMPRESSBZ2=(pbzip2 -c -f)

#COMPRESSXZ=(xz -c -z -)
COMPRESSXZ=(xz -c -z --threads=0 -)

#COMPRESSZST=(zstd -c -z -q -)
COMPRESSZST=(zstd -c -z -q --threads=0 -)

#COMPRESSLZ=(lzip -c -f)
COMPRESSLZ=(plzip -c -f)


    * zstd - 
    * 
      
      
