Directly installing `opencv`

```bash
Last login: Wed Apr  6 21:56:38 on ttys000
Sankha-desktop:SEM image segmentation user$ sudo port install opencv +python27
Password:
Warning: port definitions are more than two weeks old, consider updating them by running 'port selfupdate'.
Portfile changed since last build; discarding previous state.
--->  Computing dependencies for opencv
--->  Dependencies to be installed: ffmpeg XviD fribidi gmake gnutls libtasn1 nettle p11-kit desktop-file-utils lame libass libbluray libmodplug libogg libopus libsdl libtheora libvorbis schroedinger orc soxr speex x264
--->  Fetching archive for XviD
--->  Attempting to fetch XviD-1.3.4_0.darwin_15.x86_64.tbz2 from http://jog.id.packages.macports.org/macports/packages/XviD
--->  Attempting to fetch XviD-1.3.4_0.darwin_15.x86_64.tbz2.rmd160 from http://jog.id.packages.macports.org/macports/packages/XviD
--->  Installing XviD @1.3.4_0
--->  Activating XviD @1.3.4_0
--->  Cleaning XviD
--->  Fetching archive for fribidi
--->  Attempting to fetch fribidi-0.19.6_1.darwin_15.x86_64.tbz2 from http://jog.id.packages.macports.org/macports/packages/fribidi
--->  Attempting to fetch fribidi-0.19.6_1.darwin_15.x86_64.tbz2.rmd160 from http://jog.id.packages.macports.org/macports/packages/fribidi
--->  Installing fribidi @0.19.6_1
--->  Activating fribidi @0.19.6_1
--->  Cleaning fribidi
--->  Fetching archive for gmake
--->  Attempting to fetch gmake-4.1_0.darwin_15.x86_64.tbz2 from http://jog.id.packages.macports.org/macports/packages/gmake
--->  Attempting to fetch gmake-4.1_0.darwin_15.x86_64.tbz2.rmd160 from http://jog.id.packages.macports.org/macports/packages/gmake
--->  Installing gmake @4.1_0
--->  Activating gmake @4.1_0
--->  Cleaning gmake
--->  Fetching archive for libtasn1
--->  Attempting to fetch libtasn1-4.7_0.darwin_15.x86_64.tbz2 from http://jog.id.packages.macports.org/macports/packages/libtasn1
--->  Attempting to fetch libtasn1-4.7_0.darwin_15.x86_64.tbz2.rmd160 from http://jog.id.packages.macports.org/macports/packages/libtasn1
--->  Installing libtasn1 @4.7_0
--->  Activating libtasn1 @4.7_0
--->  Cleaning libtasn1
--->  Fetching archive for nettle
--->  Attempting to fetch nettle-3.1.1_0.darwin_15.x86_64.tbz2 from http://jog.id.packages.macports.org/macports/packages/nettle
--->  Attempting to fetch nettle-3.1.1_0.darwin_15.x86_64.tbz2.rmd160 from http://jog.id.packages.macports.org/macports/packages/nettle
--->  Installing nettle @3.1.1_0
--->  Activating nettle @3.1.1_0
--->  Cleaning nettle
--->  Fetching archive for desktop-file-utils
--->  Attempting to fetch desktop-file-utils-0.22_0.darwin_15.x86_64.tbz2 from http://jog.id.packages.macports.org/macports/packages/desktop-file-utils
--->  Attempting to fetch desktop-file-utils-0.22_0.darwin_15.x86_64.tbz2.rmd160 from http://jog.id.packages.macports.org/macports/packages/desktop-file-utils
--->  Installing desktop-file-utils @0.22_0
--->  Activating desktop-file-utils @0.22_0
--->  Cleaning desktop-file-utils
--->  Fetching archive for p11-kit
--->  Attempting to fetch p11-kit-0.22.1_0.darwin_15.x86_64.tbz2 from http://jog.id.packages.macports.org/macports/packages/p11-kit
--->  Attempting to fetch p11-kit-0.22.1_0.darwin_15.x86_64.tbz2.rmd160 from http://jog.id.packages.macports.org/macports/packages/p11-kit
--->  Installing p11-kit @0.22.1_0
--->  Activating p11-kit @0.22.1_0
--->  Cleaning p11-kit
--->  Fetching archive for gnutls
--->  Attempting to fetch gnutls-3.3.22_0.darwin_15.x86_64.tbz2 from http://jog.id.packages.macports.org/macports/packages/gnutls
--->  Attempting to fetch gnutls-3.3.22_0.darwin_15.x86_64.tbz2.rmd160 from http://jog.id.packages.macports.org/macports/packages/gnutls
--->  Installing gnutls @3.3.22_0
--->  Activating gnutls @3.3.22_0
--->  Cleaning gnutls
--->  Fetching archive for lame
--->  Attempting to fetch lame-3.99.5_1.darwin_15.x86_64.tbz2 from http://jog.id.packages.macports.org/macports/packages/lame
--->  Attempting to fetch lame-3.99.5_1.darwin_15.x86_64.tbz2.rmd160 from http://jog.id.packages.macports.org/macports/packages/lame
--->  Installing lame @3.99.5_1
--->  Activating lame @3.99.5_1
--->  Cleaning lame
--->  Fetching archive for libass
--->  Attempting to fetch libass-0.13.2_0.darwin_15.x86_64.tbz2 from http://jog.id.packages.macports.org/macports/packages/libass
--->  Attempting to fetch libass-0.13.2_0.darwin_15.x86_64.tbz2.rmd160 from http://jog.id.packages.macports.org/macports/packages/libass
--->  Installing libass @0.13.2_0
--->  Activating libass @0.13.2_0
--->  Cleaning libass
--->  Fetching archive for libbluray
--->  Attempting to fetch libbluray-0.9.2_0.darwin_15.x86_64.tbz2 from http://jog.id.packages.macports.org/macports/packages/libbluray
--->  Attempting to fetch libbluray-0.9.2_0.darwin_15.x86_64.tbz2.rmd160 from http://jog.id.packages.macports.org/macports/packages/libbluray
--->  Installing libbluray @0.9.2_0
--->  Activating libbluray @0.9.2_0
--->  Cleaning libbluray
--->  Fetching archive for libmodplug
--->  Attempting to fetch libmodplug-0.8.8.5_0.darwin_15.x86_64.tbz2 from http://jog.id.packages.macports.org/macports/packages/libmodplug
--->  Attempting to fetch libmodplug-0.8.8.5_0.darwin_15.x86_64.tbz2.rmd160 from http://jog.id.packages.macports.org/macports/packages/libmodplug
--->  Installing libmodplug @0.8.8.5_0
--->  Activating libmodplug @0.8.8.5_0
--->  Cleaning libmodplug
--->  Fetching archive for libogg
--->  Attempting to fetch libogg-1.3.2_1.darwin_15.x86_64.tbz2 from http://jog.id.packages.macports.org/macports/packages/libogg
--->  Attempting to fetch libogg-1.3.2_1.darwin_15.x86_64.tbz2.rmd160 from http://jog.id.packages.macports.org/macports/packages/libogg
--->  Installing libogg @1.3.2_1
--->  Activating libogg @1.3.2_1
--->  Cleaning libogg
--->  Fetching archive for libopus
--->  Attempting to fetch libopus-1.1.2_0.darwin_15.x86_64.tbz2 from http://jog.id.packages.macports.org/macports/packages/libopus
--->  Attempting to fetch libopus-1.1.2_0.darwin_15.x86_64.tbz2.rmd160 from http://jog.id.packages.macports.org/macports/packages/libopus
--->  Installing libopus @1.1.2_0
--->  Activating libopus @1.1.2_0
--->  Cleaning libopus
--->  Fetching archive for libsdl
--->  Attempting to fetch libsdl-1.2.15_3+x11.darwin_15.x86_64.tbz2 from http://jog.id.packages.macports.org/macports/packages/libsdl
--->  Attempting to fetch libsdl-1.2.15_3+x11.darwin_15.x86_64.tbz2.rmd160 from http://jog.id.packages.macports.org/macports/packages/libsdl
--->  Installing libsdl @1.2.15_3+x11
--->  Activating libsdl @1.2.15_3+x11
--->  Cleaning libsdl
--->  Fetching archive for libvorbis
--->  Attempting to fetch libvorbis-1.3.5_0.darwin_15.x86_64.tbz2 from http://jog.id.packages.macports.org/macports/packages/libvorbis
--->  Attempting to fetch libvorbis-1.3.5_0.darwin_15.x86_64.tbz2.rmd160 from http://jog.id.packages.macports.org/macports/packages/libvorbis
--->  Installing libvorbis @1.3.5_0
--->  Activating libvorbis @1.3.5_0
--->  Cleaning libvorbis
--->  Fetching archive for libtheora
--->  Attempting to fetch libtheora-1.1.1_2.darwin_15.x86_64.tbz2 from http://jog.id.packages.macports.org/macports/packages/libtheora
--->  Attempting to fetch libtheora-1.1.1_2.darwin_15.x86_64.tbz2.rmd160 from http://jog.id.packages.macports.org/macports/packages/libtheora
--->  Installing libtheora @1.1.1_2
--->  Activating libtheora @1.1.1_2
--->  Cleaning libtheora
--->  Fetching archive for orc
--->  Attempting to fetch orc-0.4.25_0.darwin_15.x86_64.tbz2 from http://jog.id.packages.macports.org/macports/packages/orc
--->  Attempting to fetch orc-0.4.25_0.darwin_15.x86_64.tbz2.rmd160 from http://jog.id.packages.macports.org/macports/packages/orc
--->  Installing orc @0.4.25_0
--->  Activating orc @0.4.25_0
--->  Cleaning orc
--->  Fetching archive for schroedinger
--->  Attempting to fetch schroedinger-1.0.11_0.darwin_15.x86_64.tbz2 from http://jog.id.packages.macports.org/macports/packages/schroedinger
--->  Attempting to fetch schroedinger-1.0.11_0.darwin_15.x86_64.tbz2.rmd160 from http://jog.id.packages.macports.org/macports/packages/schroedinger
--->  Installing schroedinger @1.0.11_0
--->  Activating schroedinger @1.0.11_0
--->  Cleaning schroedinger
--->  Fetching archive for soxr
--->  Attempting to fetch soxr-0.1.2_0.darwin_15.x86_64.tbz2 from http://jog.id.packages.macports.org/macports/packages/soxr
--->  Attempting to fetch soxr-0.1.2_0.darwin_15.x86_64.tbz2.rmd160 from http://jog.id.packages.macports.org/macports/packages/soxr
--->  Installing soxr @0.1.2_0
--->  Activating soxr @0.1.2_0
--->  Cleaning soxr
--->  Fetching archive for speex
--->  Attempting to fetch speex-1.2rc1_0.darwin_15.x86_64.tbz2 from http://jog.id.packages.macports.org/macports/packages/speex
--->  Attempting to fetch speex-1.2rc1_0.darwin_15.x86_64.tbz2.rmd160 from http://jog.id.packages.macports.org/macports/packages/speex
--->  Installing speex @1.2rc1_0
--->  Activating speex @1.2rc1_0
--->  Cleaning speex
--->  Fetching archive for x264
--->  Attempting to fetch x264-20160119_0.darwin_15.x86_64.tbz2 from http://jog.id.packages.macports.org/macports/packages/x264
--->  Attempting to fetch x264-20160119_0.darwin_15.x86_64.tbz2.rmd160 from http://jog.id.packages.macports.org/macports/packages/x264
--->  Installing x264 @20160119_0
--->  Activating x264 @20160119_0
--->  Cleaning x264
--->  Fetching archive for ffmpeg
--->  Attempting to fetch ffmpeg-2.8.6_1+gpl2+x11.darwin_15.x86_64.tbz2 from http://jog.id.packages.macports.org/macports/packages/ffmpeg
--->  Attempting to fetch ffmpeg-2.8.6_1+gpl2+x11.darwin_15.x86_64.tbz2 from http://nou.nc.packages.macports.org/pub/macports/packages.macports.org/ffmpeg
--->  Attempting to fetch ffmpeg-2.8.6_1+gpl2+x11.darwin_15.x86_64.tbz2 from http://packages.macports.org/ffmpeg
--->  Fetching distfiles for ffmpeg
--->  Attempting to fetch ffmpeg-2.8.6.tar.bz2 from http://jog.id.distfiles.macports.org/macports/distfiles/ffmpeg
--->  Verifying checksums for ffmpeg                                             
--->  Extracting ffmpeg
--->  Configuring ffmpeg
--->  Building ffmpeg
--->  Staging ffmpeg into destroot
--->  Installing ffmpeg @2.8.6_1+gpl2+x11
--->  Activating ffmpeg @2.8.6_1+gpl2+x11

*******
******* This build of ffmpeg includes GPLed code and
******* is therefore licensed under GPL v2 or later.
*******
******* The following modules are GPLed:
*******
*******      postproc
*******      libx264
*******      libx265
*******      libxvid
*******
******* To include all nonfree, GPLed and LGPL code use variant +nonfree.
******* To remove nonfree and GPLed code leaving only LGPL code remove the
******* +gpl2 variant.
*******

--->  Cleaning ffmpeg
--->  Fetching archive for opencv
--->  Attempting to fetch opencv-3.1.0_1+python27.darwin_15.x86_64.tbz2 from http://jog.id.packages.macports.org/macports/packages/opencv
--->  Attempting to fetch opencv-3.1.0_1+python27.darwin_15.x86_64.tbz2 from http://nou.nc.packages.macports.org/pub/macports/packages.macports.org/opencv
--->  Attempting to fetch opencv-3.1.0_1+python27.darwin_15.x86_64.tbz2 from http://packages.macports.org/opencv
--->  Fetching distfiles for opencv
--->  Attempting to fetch opencv-3.1.0.zip from http://nchc.dl.sourceforge.net/project/opencvlibrary/opencv-unix/3.1.0
--->  Verifying checksums for opencv                                             
--->  Extracting opencv
--->  Applying patches to opencv
--->  Configuring opencv
--->  Building opencv
--->  Staging opencv into destroot
--->  Installing opencv @3.1.0_1+python27
--->  Activating opencv @3.1.0_1+python27
--->  Cleaning opencv
--->  Updating database of binaries
--->  Scanning binaries for linking errors               
--->  No broken files found.   
```
