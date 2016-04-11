# Installing Apache Spark

This is the first installation that I have not done using Macports. Thankfully, as of now, it does not need a package manager. Hopefully, in the future, we will be able to find the proper port that can be used for installing spark. We build spark by first downloading the source file from [here](http://spark.apache.org/docs/latest/building-spark.html), and

The initial install failed because `maven` wasn't installed. 

```bash
Sankha-desktop:~ user$ cd /Users/user/Documents/installers/spark/spark-1.6.1 
Sankha-desktop:spark-1.6.1 user$ build/mvn -Pyarn -Phadoop-2.4 -Dhadoop.version=2.4.0 -DskipTests clean package
exec: curl --progress-bar -L http://archive.apache.org/dist/maven/maven-3/3.3.3/binaries/apache-maven-3.3.3-bin.tar.gz
######################################################################## 100.0%
tar: Unrecognized archive format
tar: Error exit delayed from previous errors.
exec: curl --progress-bar -L http://downloads.typesafe.com/zinc/0.3.5.3/zinc-0.3.5.3.tgz
######################################################################## 100.0%
exec: curl --progress-bar -L http://downloads.typesafe.com/scala/2.10.5/scala-2.10.5.tgz
######################################################################## 100.0%
Using `mvn` from path: /Users/user/Documents/installers/spark/spark-1.6.1/build/apache-maven-3.3.3/bin/mvn
build/mvn: line 152: /Users/user/Documents/installers/spark/spark-1.6.1/build/apache-maven-3.3.3/bin/mvn: No such file or directory
```

## Installing `maven`

So let's install maven. But before than we need to update the ports tree.

```bash
Sankha-desktop:spark-1.6.1 user$ sudo port selfupdate
Password:
--->  Updating MacPorts base sources using rsync
MacPorts base version 2.3.4 installed,
MacPorts base version 2.3.4 downloaded.
--->  Updating the ports tree
--->  MacPorts base is already the latest version

The ports tree has been updated. To upgrade your installed ports, you should run
  port upgrade outdated
Sankha-desktop:spark-1.6.1 user$ sudo port upgrade outdated
--->  Fetching archive for autoconf-archive
--->  Attempting to fetch autoconf-archive-2016.03.20_0.darwin_15.noarch.tbz2 from http://jog.id.packages.macports.org/macports/packages/autoconf-archive
--->  Attempting to fetch autoconf-archive-2016.03.20_0.darwin_15.noarch.tbz2.rmd160 from http://jog.id.packages.macports.org/macports/packages/autoconf-archive
--->  Installing autoconf-archive @2016.03.20_0
--->  Cleaning autoconf-archive
--->  Deactivating autoconf-archive @2015.09.25_0
--->  Cleaning autoconf-archive
--->  Activating autoconf-archive @2016.03.20_0
--->  Cleaning autoconf-archive
--->  Computing dependencies for blosc
--->  Fetching archive for blosc
--->  Attempting to fetch blosc-1.8.1_0.darwin_15.x86_64.tbz2 from http://jog.id.packages.macports.org/macports/packages/blosc
--->  Attempting to fetch blosc-1.8.1_0.darwin_15.x86_64.tbz2.rmd160 from http://jog.id.packages.macports.org/macports/packages/blosc
--->  Installing blosc @1.8.1_0
--->  Cleaning blosc
--->  Computing dependencies for blosc
--->  Deactivating blosc @1.7.1_0
--->  Cleaning blosc
--->  Activating blosc @1.8.1_0
--->  Cleaning blosc
--->  Fetching archive for curl-ca-bundle
--->  Attempting to fetch curl-ca-bundle-7.48.0_0.darwin_15.noarch.tbz2 from http://jog.id.packages.macports.org/macports/packages/curl-ca-bundle
--->  Attempting to fetch curl-ca-bundle-7.48.0_0.darwin_15.noarch.tbz2.rmd160 from http://jog.id.packages.macports.org/macports/packages/curl-ca-bundle
--->  Installing curl-ca-bundle @7.48.0_0
--->  Cleaning curl-ca-bundle
--->  Deactivating curl-ca-bundle @7.47.1_0
--->  Cleaning curl-ca-bundle
--->  Activating curl-ca-bundle @7.48.0_0
--->  Cleaning curl-ca-bundle
--->  Computing dependencies for curl
--->  Fetching archive for curl
--->  Attempting to fetch curl-7.48.0_0+ssl.darwin_15.x86_64.tbz2 from http://jog.id.packages.macports.org/macports/packages/curl
--->  Attempting to fetch curl-7.48.0_0+ssl.darwin_15.x86_64.tbz2.rmd160 from http://jog.id.packages.macports.org/macports/packages/curl
--->  Installing curl @7.48.0_0+ssl
--->  Cleaning curl
--->  Computing dependencies for curl
--->  Deactivating curl @7.47.1_1+ssl
--->  Cleaning curl
--->  Activating curl @7.48.0_0+ssl
--->  Cleaning curl
--->  Computing dependencies for cmake
--->  Fetching archive for cmake
--->  Attempting to fetch cmake-3.5.1_0.darwin_15.x86_64.tbz2 from http://jog.id.packages.macports.org/macports/packages/cmake
--->  Attempting to fetch cmake-3.5.1_0.darwin_15.x86_64.tbz2.rmd160 from http://jog.id.packages.macports.org/macports/packages/cmake
--->  Installing cmake @3.5.1_0
--->  Cleaning cmake
--->  Computing dependencies for cmake
--->  Deactivating cmake @3.5.0_0
--->  Cleaning cmake
--->  Activating cmake @3.5.1_0
--->  Cleaning cmake
--->  Computing dependencies for sqlite3
--->  Fetching archive for sqlite3
--->  Attempting to fetch sqlite3-3.12.1_0.darwin_15.x86_64.tbz2 from http://jog.id.packages.macports.org/macports/packages/sqlite3
--->  Attempting to fetch sqlite3-3.12.1_0.darwin_15.x86_64.tbz2.rmd160 from http://jog.id.packages.macports.org/macports/packages/sqlite3
--->  Installing sqlite3 @3.12.1_0
--->  Cleaning sqlite3
--->  Computing dependencies for sqlite3
--->  Deactivating sqlite3 @3.11.1_1
--->  Cleaning sqlite3
--->  Activating sqlite3 @3.12.1_0
--->  Cleaning sqlite3
--->  Computing dependencies for glib2
--->  Fetching archive for glib2
--->  Attempting to fetch glib2-2.48.0_0.darwin_15.x86_64.tbz2 from http://jog.id.packages.macports.org/macports/packages/glib2
--->  Attempting to fetch glib2-2.48.0_0.darwin_15.x86_64.tbz2.rmd160 from http://jog.id.packages.macports.org/macports/packages/glib2
--->  Installing glib2 @2.48.0_0
--->  Cleaning glib2
--->  Computing dependencies for glib2
--->  Deactivating glib2 @2.46.2_0
--->  Cleaning glib2
--->  Activating glib2 @2.48.0_0
--->  Cleaning glib2
--->  Fetching archive for libpixman
--->  Attempting to fetch libpixman-0.34.0_0.darwin_15.x86_64.tbz2 from http://jog.id.packages.macports.org/macports/packages/libpixman
--->  Attempting to fetch libpixman-0.34.0_0.darwin_15.x86_64.tbz2.rmd160 from http://jog.id.packages.macports.org/macports/packages/libpixman
--->  Installing libpixman @0.34.0_0
--->  Cleaning libpixman
--->  Deactivating libpixman @0.32.8_0
--->  Cleaning libpixman
--->  Activating libpixman @0.34.0_0
--->  Cleaning libpixman
--->  Computing dependencies for gobject-introspection
--->  Fetching archive for gobject-introspection
--->  Attempting to fetch gobject-introspection-1.48.0_0.darwin_15.x86_64.tbz2 from http://jog.id.packages.macports.org/macports/packages/gobject-introspection
--->  Attempting to fetch gobject-introspection-1.48.0_0.darwin_15.x86_64.tbz2.rmd160 from http://jog.id.packages.macports.org/macports/packages/gobject-introspection
--->  Installing gobject-introspection @1.48.0_0
--->  Cleaning gobject-introspection
--->  Computing dependencies for gobject-introspection
--->  Deactivating gobject-introspection @1.46.0_2
--->  Cleaning gobject-introspection
--->  Activating gobject-introspection @1.48.0_0
--->  Cleaning gobject-introspection
--->  Computing dependencies for poppler
--->  Fetching archive for poppler
--->  Attempting to fetch poppler-0.42.0_2.darwin_15.x86_64.tbz2 from http://jog.id.packages.macports.org/macports/packages/poppler
--->  Attempting to fetch poppler-0.42.0_2.darwin_15.x86_64.tbz2 from http://nou.nc.packages.macports.org/pub/macports/packages.macports.org/poppler
--->  Attempting to fetch poppler-0.42.0_2.darwin_15.x86_64.tbz2 from https://packages.macports.org/poppler
--->  Fetching distfiles for poppler
--->  Verifying checksums for poppler
--->  Extracting poppler
--->  Applying patches to poppler
--->  Configuring poppler
--->  Building poppler
--->  Staging poppler into destroot
--->  Installing poppler @0.42.0_2
--->  Cleaning poppler
--->  Computing dependencies for poppler
--->  Deactivating poppler @0.42.0_0
--->  Cleaning poppler
--->  Activating poppler @0.42.0_2
--->  Cleaning poppler
--->  Fetching archive for graphite2
--->  Attempting to fetch graphite2-1.3.8_0.darwin_15.x86_64.tbz2 from http://jog.id.packages.macports.org/macports/packages/graphite2
--->  Attempting to fetch graphite2-1.3.8_0.darwin_15.x86_64.tbz2.rmd160 from http://jog.id.packages.macports.org/macports/packages/graphite2
--->  Installing graphite2 @1.3.8_0
--->  Cleaning graphite2
--->  Deactivating graphite2 @1.3.7_0
--->  Cleaning graphite2
--->  Activating graphite2 @1.3.8_0
--->  Cleaning graphite2
--->  Computing dependencies for harfbuzz
--->  Fetching archive for harfbuzz
--->  Attempting to fetch harfbuzz-1.2.5_0.darwin_15.x86_64.tbz2 from http://jog.id.packages.macports.org/macports/packages/harfbuzz
--->  Attempting to fetch harfbuzz-1.2.5_0.darwin_15.x86_64.tbz2.rmd160 from http://jog.id.packages.macports.org/macports/packages/harfbuzz
--->  Installing harfbuzz @1.2.5_0
--->  Cleaning harfbuzz
--->  Computing dependencies for harfbuzz
--->  Deactivating harfbuzz @1.1.3_0
--->  Cleaning harfbuzz
--->  Activating harfbuzz @1.2.5_0
--->  Cleaning harfbuzz
--->  Computing dependencies for harfbuzz-icu
--->  Fetching archive for harfbuzz-icu
--->  Attempting to fetch harfbuzz-icu-1.2.5_0.darwin_15.x86_64.tbz2 from http://jog.id.packages.macports.org/macports/packages/harfbuzz-icu
--->  Attempting to fetch harfbuzz-icu-1.2.5_0.darwin_15.x86_64.tbz2.rmd160 from http://jog.id.packages.macports.org/macports/packages/harfbuzz-icu
--->  Installing harfbuzz-icu @1.2.5_0
--->  Cleaning harfbuzz-icu
--->  Computing dependencies for harfbuzz-icu
--->  Deactivating harfbuzz-icu @1.1.3_0
--->  Cleaning harfbuzz-icu
--->  Activating harfbuzz-icu @1.2.5_0
--->  Cleaning harfbuzz-icu
--->  Computing dependencies for ghostscript
--->  Fetching archive for ghostscript
--->  Attempting to fetch ghostscript-9.19_0+x11.darwin_15.x86_64.tbz2 from http://jog.id.packages.macports.org/macports/packages/ghostscript
--->  Attempting to fetch ghostscript-9.19_0+x11.darwin_15.x86_64.tbz2 from http://nou.nc.packages.macports.org/pub/macports/packages.macports.org/ghostscript
--->  Attempting to fetch ghostscript-9.19_0+x11.darwin_15.x86_64.tbz2 from https://packages.macports.org/ghostscript
--->  Fetching distfiles for ghostscript
--->  Attempting to fetch ghostscript-9.19.tar.gz from http://jog.id.distfiles.macports.org/macports/distfiles/ghostscript
--->  Attempting to fetch ghostscript-fonts-std-8.11.tar.gz from http://nchc.dl.sourceforge.net/gs-fonts
--->  Attempting to fetch 0bdcfbe5e394d4519e5969918c34d4eebf76a386.zip from http://jog.id.distfiles.macports.org/macports/distfiles/ghostscript
--->  Verifying checksums for ghostscript                                            
--->  Extracting ghostscript
--->  Applying patches to ghostscript
--->  Configuring ghostscript
--->  Building ghostscript
--->  Staging ghostscript into destroot
--->  Installing ghostscript @9.19_0+x11
--->  Cleaning ghostscript
--->  Computing dependencies for ghostscript
--->  Deactivating ghostscript @9.16_1+x11
--->  Cleaning ghostscript
--->  Activating ghostscript @9.19_0+x11
--->  Cleaning ghostscript
--->  Computing dependencies for dvipng
--->  Fetching archive for dvipng
--->  Attempting to fetch dvipng-1.15_1.darwin_15.x86_64.tbz2 from http://jog.id.packages.macports.org/macports/packages/dvipng
--->  Attempting to fetch dvipng-1.15_1.darwin_15.x86_64.tbz2.rmd160 from http://jog.id.packages.macports.org/macports/packages/dvipng
--->  Installing dvipng @1.15_1
--->  Cleaning dvipng
--->  Computing dependencies for dvipng
--->  Deactivating dvipng @1.15_0
--->  Cleaning dvipng
--->  Activating dvipng @1.15_1
--->  Cleaning dvipng
--->  Computing dependencies for epstool
--->  Fetching archive for epstool
--->  Attempting to fetch epstool-3.08_9.darwin_15.x86_64.tbz2 from http://jog.id.packages.macports.org/macports/packages/epstool
--->  Attempting to fetch epstool-3.08_9.darwin_15.x86_64.tbz2 from http://nou.nc.packages.macports.org/pub/macports/packages.macports.org/epstool
--->  Attempting to fetch epstool-3.08_9.darwin_15.x86_64.tbz2 from https://packages.macports.org/epstool
--->  Fetching distfiles for epstool
--->  Verifying checksums for epstool
--->  Extracting epstool
--->  Applying patches to epstool
--->  Configuring epstool
--->  Building epstool
--->  Staging epstool into destroot
--->  Installing epstool @3.08_9
--->  Cleaning epstool
--->  Computing dependencies for epstool
--->  Deactivating epstool @3.08_8
--->  Cleaning epstool
--->  Activating epstool @3.08_9
--->  Cleaning epstool
--->  Computing dependencies for fltk-devel
--->  Fetching archive for fltk-devel
--->  Attempting to fetch fltk-devel-1.3.x-r11419_0.darwin_15.x86_64.tbz2 from http://jog.id.packages.macports.org/macports/packages/fltk-devel
--->  Attempting to fetch fltk-devel-1.3.x-r11419_0.darwin_15.x86_64.tbz2.rmd160 from http://jog.id.packages.macports.org/macports/packages/fltk-devel
--->  Installing fltk-devel @1.3.x-r11419_0
--->  Cleaning fltk-devel
--->  Computing dependencies for fltk-devel
--->  Deactivating fltk-devel @1.3.x-r11363_0
--->  Cleaning fltk-devel
--->  Activating fltk-devel @1.3.x-r11419_0
--->  Cleaning fltk-devel
--->  Computing dependencies for gdk-pixbuf2
--->  Fetching archive for gdk-pixbuf2
--->  Attempting to fetch gdk-pixbuf2-2.34.0_0+x11.darwin_15.x86_64.tbz2 from http://jog.id.packages.macports.org/macports/packages/gdk-pixbuf2
--->  Attempting to fetch gdk-pixbuf2-2.34.0_0+x11.darwin_15.x86_64.tbz2.rmd160 from http://jog.id.packages.macports.org/macports/packages/gdk-pixbuf2
--->  Installing gdk-pixbuf2 @2.34.0_0+x11
--->  Cleaning gdk-pixbuf2
--->  Computing dependencies for gdk-pixbuf2
--->  Deactivating gdk-pixbuf2 @2.32.3_0+x11
--->  Cleaning gdk-pixbuf2
--->  Activating gdk-pixbuf2 @2.34.0_0+x11
--->  Cleaning gdk-pixbuf2
--->  Computing dependencies for p5.22-net-ssleay
--->  Fetching archive for p5.22-net-ssleay
--->  Attempting to fetch p5.22-net-ssleay-1.720.0_1.darwin_15.x86_64.tbz2 from http://jog.id.packages.macports.org/macports/packages/p5.22-net-ssleay
--->  Attempting to fetch p5.22-net-ssleay-1.720.0_1.darwin_15.x86_64.tbz2 from http://nou.nc.packages.macports.org/pub/macports/packages.macports.org/p5.22-net-ssleay
--->  Attempting to fetch p5.22-net-ssleay-1.720.0_1.darwin_15.x86_64.tbz2 from https://packages.macports.org/p5.22-net-ssleay
--->  Fetching distfiles for p5.22-net-ssleay
--->  Verifying checksums for p5.22-net-ssleay
--->  Extracting p5.22-net-ssleay
--->  Applying patches to p5.22-net-ssleay
--->  Configuring p5.22-net-ssleay
--->  Building p5.22-net-ssleay
--->  Staging p5.22-net-ssleay into destroot
--->  Installing p5.22-net-ssleay @1.720.0_1
--->  Cleaning p5.22-net-ssleay
--->  Computing dependencies for p5.22-net-ssleay
--->  Deactivating p5.22-net-ssleay @1.720.0_0
--->  Cleaning p5.22-net-ssleay
--->  Activating p5.22-net-ssleay @1.720.0_1
--->  Cleaning p5.22-net-ssleay
--->  Computing dependencies for p5.22-io-socket-ssl
--->  Fetching archive for p5.22-io-socket-ssl
--->  Attempting to fetch p5.22-io-socket-ssl-2.25.0_0.darwin_15.noarch.tbz2 from http://jog.id.packages.macports.org/macports/packages/p5.22-io-socket-ssl
--->  Attempting to fetch p5.22-io-socket-ssl-2.25.0_0.darwin_15.noarch.tbz2.rmd160 from http://jog.id.packages.macports.org/macports/packages/p5.22-io-socket-ssl
--->  Installing p5.22-io-socket-ssl @2.25.0_0
--->  Cleaning p5.22-io-socket-ssl
--->  Computing dependencies for p5.22-io-socket-ssl
--->  Deactivating p5.22-io-socket-ssl @2.24.0_0
--->  Cleaning p5.22-io-socket-ssl
--->  Activating p5.22-io-socket-ssl @2.25.0_0
--->  Cleaning p5.22-io-socket-ssl
--->  Computing dependencies for git
--->  Fetching archive for git
--->  Attempting to fetch git-2.8.1_0+credential_osxkeychain+doc+pcre+perl5_22+python27.darwin_15.x86_64.tbz2 from http://jog.id.packages.macports.org/macports/packages/git
--->  Attempting to fetch git-2.8.1_0+credential_osxkeychain+doc+pcre+perl5_22+python27.darwin_15.x86_64.tbz2 from http://nou.nc.packages.macports.org/pub/macports/packages.macports.org/git
--->  Attempting to fetch git-2.8.1_0+credential_osxkeychain+doc+pcre+perl5_22+python27.darwin_15.x86_64.tbz2 from https://packages.macports.org/git
--->  Fetching distfiles for git
--->  Attempting to fetch git-2.8.1.tar.gz from http://jog.id.distfiles.macports.org/macports/distfiles/git
--->  Attempting to fetch git-manpages-2.8.1.tar.gz from http://jog.id.distfiles.macports.org/macports/distfiles/git
--->  Attempting to fetch git-htmldocs-2.8.1.tar.gz from http://jog.id.distfiles.macports.org/macports/distfiles/git
--->  Verifying checksums for git                                                    
--->  Extracting git
--->  Applying patches to git
--->  Configuring git
--->  Building git
--->  Staging git into destroot
--->  Installing git @2.8.1_0+credential_osxkeychain+doc+pcre+perl5_22+python27
--->  Cleaning git
--->  Computing dependencies for git
--->  Deactivating git @2.7.4_0+credential_osxkeychain+doc+pcre+perl5_22+python27
--->  Cleaning git
--->  Activating git @2.8.1_0+credential_osxkeychain+doc+pcre+perl5_22+python27
--->  Cleaning git
--->  Computing dependencies for glpk
--->  Fetching archive for glpk
--->  Attempting to fetch glpk-4.60_0.darwin_15.x86_64.tbz2 from http://jog.id.packages.macports.org/macports/packages/glpk
--->  Attempting to fetch glpk-4.60_0.darwin_15.x86_64.tbz2 from http://nou.nc.packages.macports.org/pub/macports/packages.macports.org/glpk
--->  Attempting to fetch glpk-4.60_0.darwin_15.x86_64.tbz2 from https://packages.macports.org/glpk
--->  Attempting to fetch glpk-4.60_0.darwin_15.x86_64.tbz2.rmd160 from https://packages.macports.org/glpk
--->  Installing glpk @4.60_0
--->  Cleaning glpk
--->  Computing dependencies for glpk
--->  Deactivating glpk @4.57_0
--->  Cleaning glpk
--->  Activating glpk @4.60_0
--->  Cleaning glpk
--->  Fetching archive for libnetpbm
--->  Attempting to fetch libnetpbm-10.74.01_0.darwin_15.x86_64.tbz2 from http://jog.id.packages.macports.org/macports/packages/libnetpbm
--->  Attempting to fetch libnetpbm-10.74.01_0.darwin_15.x86_64.tbz2.rmd160 from http://jog.id.packages.macports.org/macports/packages/libnetpbm
--->  Installing libnetpbm @10.74.01_0
--->  Cleaning libnetpbm
--->  Deactivating libnetpbm @10.73.00_0
--->  Cleaning libnetpbm
--->  Activating libnetpbm @10.74.01_0
--->  Cleaning libnetpbm
--->  Computing dependencies for netpbm
--->  Fetching archive for netpbm
--->  Attempting to fetch netpbm-10.74.01_0+x11.darwin_15.x86_64.tbz2 from http://jog.id.packages.macports.org/macports/packages/netpbm
--->  Attempting to fetch netpbm-10.74.01_0+x11.darwin_15.x86_64.tbz2.rmd160 from http://jog.id.packages.macports.org/macports/packages/netpbm
--->  Installing netpbm @10.74.01_0+x11
--->  Cleaning netpbm
--->  Computing dependencies for netpbm
--->  Deactivating netpbm @10.73.00_0+x11
--->  Cleaning netpbm
--->  Activating netpbm @10.74.01_0+x11
--->  Cleaning netpbm
--->  Computing dependencies for groff
--->  Fetching archive for groff
--->  Attempting to fetch groff-1.22.3_1.darwin_15.x86_64.tbz2 from http://jog.id.packages.macports.org/macports/packages/groff
--->  Attempting to fetch groff-1.22.3_1.darwin_15.x86_64.tbz2 from http://nou.nc.packages.macports.org/pub/macports/packages.macports.org/groff
--->  Attempting to fetch groff-1.22.3_1.darwin_15.x86_64.tbz2 from https://packages.macports.org/groff
--->  Fetching distfiles for groff
--->  Verifying checksums for groff
--->  Extracting groff
--->  Applying patches to groff
--->  Configuring groff
--->  Building groff
--->  Staging groff into destroot
--->  Installing groff @1.22.3_1
--->  Cleaning groff
--->  Computing dependencies for groff
--->  Deactivating groff @1.22.3_0
--->  Cleaning groff
--->  Activating groff @1.22.3_1
--->  Cleaning groff
--->  Computing dependencies for gtk-doc
--->  Fetching archive for gtk-doc
--->  Attempting to fetch gtk-doc-1.25_0.darwin_15.noarch.tbz2 from http://jog.id.packages.macports.org/macports/packages/gtk-doc
--->  Attempting to fetch gtk-doc-1.25_0.darwin_15.noarch.tbz2 from http://nou.nc.packages.macports.org/pub/macports/packages.macports.org/gtk-doc
--->  Attempting to fetch gtk-doc-1.25_0.darwin_15.noarch.tbz2 from https://packages.macports.org/gtk-doc
--->  Fetching distfiles for gtk-doc
--->  Attempting to fetch gtk-doc-1.25.tar.xz from http://jog.id.distfiles.macports.org/macports/distfiles/gtk-doc
--->  Verifying checksums for gtk-doc                                                
--->  Extracting gtk-doc
--->  Configuring gtk-doc
--->  Building gtk-doc
--->  Staging gtk-doc into destroot
--->  Installing gtk-doc @1.25_0
--->  Cleaning gtk-doc
--->  Computing dependencies for gtk-doc
--->  Deactivating gtk-doc @1.24_2
--->  Cleaning gtk-doc
--->  Activating gtk-doc @1.25_0
--->  Cleaning gtk-doc
--->  Computing dependencies for hdf5
--->  Fetching archive for hdf5
--->  Attempting to fetch hdf5-1.10.0_0+cxx+hl.darwin_15.x86_64.tbz2 from http://jog.id.packages.macports.org/macports/packages/hdf5
--->  Attempting to fetch hdf5-1.10.0_0+cxx+hl.darwin_15.x86_64.tbz2.rmd160 from http://jog.id.packages.macports.org/macports/packages/hdf5
--->  Installing hdf5 @1.10.0_0+cxx+hl
--->  Cleaning hdf5
--->  Computing dependencies for hdf5
--->  Deactivating hdf5 @1.8.16_2+cxx+hl
--->  Cleaning hdf5
--->  Activating hdf5 @1.10.0_0+cxx+hl
--->  Cleaning hdf5
--->  Computing dependencies for ImageMagick
--->  Fetching archive for ImageMagick
--->  Attempting to fetch ImageMagick-6.9.3-4_1+x11.darwin_15.x86_64.tbz2 from http://jog.id.packages.macports.org/macports/packages/ImageMagick
--->  Attempting to fetch ImageMagick-6.9.3-4_1+x11.darwin_15.x86_64.tbz2 from http://nou.nc.packages.macports.org/pub/macports/packages.macports.org/ImageMagick
--->  Attempting to fetch ImageMagick-6.9.3-4_1+x11.darwin_15.x86_64.tbz2 from https://packages.macports.org/ImageMagick
--->  Fetching distfiles for ImageMagick
--->  Verifying checksums for ImageMagick
--->  Extracting ImageMagick
--->  Configuring ImageMagick
--->  Building ImageMagick
--->  Staging ImageMagick into destroot
--->  Installing ImageMagick @6.9.3-4_1+x11
--->  Cleaning ImageMagick
--->  Computing dependencies for ImageMagick
--->  Deactivating ImageMagick @6.9.3-4_0+x11
--->  Cleaning ImageMagick
--->  Activating ImageMagick @6.9.3-4_1+x11
--->  Cleaning ImageMagick
--->  Computing dependencies for imlib2
--->  Fetching archive for imlib2
--->  Attempting to fetch imlib2-1.4.8_0.darwin_15.x86_64.tbz2 from http://jog.id.packages.macports.org/macports/packages/imlib2
--->  Attempting to fetch imlib2-1.4.8_0.darwin_15.x86_64.tbz2 from http://nou.nc.packages.macports.org/pub/macports/packages.macports.org/imlib2
--->  Attempting to fetch imlib2-1.4.8_0.darwin_15.x86_64.tbz2 from https://packages.macports.org/imlib2
--->  Attempting to fetch imlib2-1.4.8_0.darwin_15.x86_64.tbz2.rmd160 from https://packages.macports.org/imlib2
--->  Installing imlib2 @1.4.8_0
--->  Cleaning imlib2
--->  Computing dependencies for imlib2
--->  Deactivating imlib2 @1.4.7_0
--->  Cleaning imlib2
--->  Activating imlib2 @1.4.8_0
--->  Cleaning imlib2
--->  Computing dependencies for pango
--->  Fetching archive for pango
--->  Attempting to fetch pango-1.40.0_0+quartz+x11.darwin_15.x86_64.tbz2 from http://jog.id.packages.macports.org/macports/packages/pango
--->  Attempting to fetch pango-1.40.0_0+quartz+x11.darwin_15.x86_64.tbz2.rmd160 from http://jog.id.packages.macports.org/macports/packages/pango
--->  Installing pango @1.40.0_0+quartz+x11
--->  Cleaning pango
--->  Computing dependencies for pango
--->  Deactivating pango @1.38.1_0+quartz+x11
--->  Cleaning pango
--->  Activating pango @1.40.0_0+quartz+x11
--->  Cleaning pango
--->  Computing dependencies for vala
--->  Fetching archive for vala
--->  Attempting to fetch vala-0.32.0_0.darwin_15.x86_64.tbz2 from http://jog.id.packages.macports.org/macports/packages/vala
--->  Attempting to fetch vala-0.32.0_0.darwin_15.x86_64.tbz2.rmd160 from http://jog.id.packages.macports.org/macports/packages/vala
--->  Installing vala @0.32.0_0
--->  Cleaning vala
--->  Computing dependencies for vala
--->  Deactivating vala @0.30.1_0
--->  Cleaning vala
--->  Activating vala @0.32.0_0
--->  Cleaning vala
--->  Computing dependencies for librsvg
--->  Fetching archive for librsvg
--->  Attempting to fetch librsvg-2.40.15_0.darwin_15.x86_64.tbz2 from http://jog.id.packages.macports.org/macports/packages/librsvg
--->  Attempting to fetch librsvg-2.40.15_0.darwin_15.x86_64.tbz2.rmd160 from http://jog.id.packages.macports.org/macports/packages/librsvg
--->  Installing librsvg @2.40.15_0
--->  Cleaning librsvg
--->  Computing dependencies for librsvg
--->  Deactivating librsvg @2.40.13_0
--->  Cleaning librsvg
--->  Activating librsvg @2.40.15_0
--->  Cleaning librsvg
--->  Fetching archive for libsodium
--->  Attempting to fetch libsodium-1.0.10_0.darwin_15.x86_64.tbz2 from http://jog.id.packages.macports.org/macports/packages/libsodium
--->  Attempting to fetch libsodium-1.0.10_0.darwin_15.x86_64.tbz2.rmd160 from http://jog.id.packages.macports.org/macports/packages/libsodium
--->  Installing libsodium @1.0.10_0
--->  Cleaning libsodium
--->  Deactivating libsodium @1.0.8_0
--->  Cleaning libsodium
--->  Activating libsodium @1.0.10_0
--->  Cleaning libsodium
--->  Computing dependencies for netcdf
--->  Fetching archive for netcdf
--->  Attempting to fetch netcdf-4.4.0_1+dap+netcdf4.darwin_15.x86_64.tbz2 from http://jog.id.packages.macports.org/macports/packages/netcdf
--->  Attempting to fetch netcdf-4.4.0_1+dap+netcdf4.darwin_15.x86_64.tbz2.rmd160 from http://jog.id.packages.macports.org/macports/packages/netcdf
--->  Installing netcdf @4.4.0_1+dap+netcdf4
--->  Cleaning netcdf
--->  Computing dependencies for netcdf
--->  Deactivating netcdf @4.3.3.1_4+dap+netcdf4
--->  Cleaning netcdf
--->  Activating netcdf @4.4.0_1+dap+netcdf4

As of version 4.2 c++ and fortran interfaces are separate ports, netcdf-cxx and netcdf-fortran, respectively.

--->  Cleaning netcdf
--->  Computing dependencies for octave
--->  Fetching archive for octave
--->  Attempting to fetch octave-3.8.2_17+atlas+gcc5+glgui.darwin_15.x86_64.tbz2 from http://jog.id.packages.macports.org/macports/packages/octave
--->  Attempting to fetch octave-3.8.2_17+atlas+gcc5+glgui.darwin_15.x86_64.tbz2 from http://nou.nc.packages.macports.org/pub/macports/packages.macports.org/octave
--->  Attempting to fetch octave-3.8.2_17+atlas+gcc5+glgui.darwin_15.x86_64.tbz2 from https://packages.macports.org/octave
--->  Fetching distfiles for octave
--->  Verifying checksums for octave
--->  Extracting octave
--->  Applying patches to octave
--->  Configuring octave
--->  Building octave
--->  Staging octave into destroot
--->  Installing octave @3.8.2_17+atlas+gcc5+glgui
--->  Cleaning octave
--->  Computing dependencies for octave
--->  Deactivating octave @3.8.2_15+atlas+gcc5+glgui
--->  Cleaning octave
--->  Activating octave @3.8.2_17+atlas+gcc5+glgui

WARNING: Dependency 'arpack' is installed with the +accelerate variant, using Apple's Vector Libraries which have some known bugs that
can cause Octave to crash if using certain functions in arpack.  The +atlas variant does not have these issues with Octave, but does
take many hours to compile even on modern hardware.

--->  Cleaning octave
--->  Computing dependencies for p5.22-podlators
--->  Fetching archive for p5.22-podlators
--->  Attempting to fetch p5.22-podlators-4.70.0_0.darwin_15.noarch.tbz2 from http://jog.id.packages.macports.org/macports/packages/p5.22-podlators
--->  Attempting to fetch p5.22-podlators-4.70.0_0.darwin_15.noarch.tbz2.rmd160 from http://jog.id.packages.macports.org/macports/packages/p5.22-podlators
--->  Installing p5.22-podlators @4.70.0_0
--->  Cleaning p5.22-podlators
--->  Computing dependencies for p5.22-podlators
--->  Deactivating p5.22-podlators @4.60.0_0
--->  Cleaning p5.22-podlators
--->  Activating p5.22-podlators @4.70.0_0
--->  Cleaning p5.22-podlators
--->  Computing dependencies for p5.22-scalar-list-utils
--->  Fetching archive for p5.22-scalar-list-utils
--->  Attempting to fetch p5.22-scalar-list-utils-1.450.0_0.darwin_15.x86_64.tbz2 from http://jog.id.packages.macports.org/macports/packages/p5.22-scalar-list-utils
--->  Attempting to fetch p5.22-scalar-list-utils-1.450.0_0.darwin_15.x86_64.tbz2.rmd160 from http://jog.id.packages.macports.org/macports/packages/p5.22-scalar-list-utils
--->  Installing p5.22-scalar-list-utils @1.450.0_0
--->  Cleaning p5.22-scalar-list-utils
--->  Computing dependencies for p5.22-scalar-list-utils
--->  Deactivating p5.22-scalar-list-utils @1.440.0_0
--->  Cleaning p5.22-scalar-list-utils
--->  Activating p5.22-scalar-list-utils @1.450.0_0
--->  Cleaning p5.22-scalar-list-utils
--->  Computing dependencies for p5.22-socket6
--->  Fetching archive for p5.22-socket6
--->  Attempting to fetch p5.22-socket6-0.270.0_0.darwin_15.x86_64.tbz2 from http://jog.id.packages.macports.org/macports/packages/p5.22-socket6
--->  Attempting to fetch p5.22-socket6-0.270.0_0.darwin_15.x86_64.tbz2.rmd160 from http://jog.id.packages.macports.org/macports/packages/p5.22-socket6
--->  Installing p5.22-socket6 @0.270.0_0
--->  Cleaning p5.22-socket6
--->  Computing dependencies for p5.22-socket6
--->  Deactivating p5.22-socket6 @0.260.0_0
--->  Cleaning p5.22-socket6
--->  Activating p5.22-socket6 @0.270.0_0
--->  Cleaning p5.22-socket6
--->  Computing dependencies for p5.22-tree-dag_node
--->  Fetching archive for p5.22-tree-dag_node
--->  Attempting to fetch p5.22-tree-dag_node-1.290.0_0.darwin_15.noarch.tbz2 from http://jog.id.packages.macports.org/macports/packages/p5.22-tree-dag_node
--->  Attempting to fetch p5.22-tree-dag_node-1.290.0_0.darwin_15.noarch.tbz2.rmd160 from http://jog.id.packages.macports.org/macports/packages/p5.22-tree-dag_node
--->  Installing p5.22-tree-dag_node @1.290.0_0
--->  Cleaning p5.22-tree-dag_node
--->  Computing dependencies for p5.22-tree-dag_node
--->  Deactivating p5.22-tree-dag_node @1.270.0_0
--->  Cleaning p5.22-tree-dag_node
--->  Activating p5.22-tree-dag_node @1.290.0_0
--->  Cleaning p5.22-tree-dag_node
--->  Computing dependencies for py26-cython
--->  Fetching archive for py26-cython
--->  Attempting to fetch py26-cython-0.24_0.darwin_15.x86_64.tbz2 from http://jog.id.packages.macports.org/macports/packages/py26-cython
--->  Attempting to fetch py26-cython-0.24_0.darwin_15.x86_64.tbz2.rmd160 from http://jog.id.packages.macports.org/macports/packages/py26-cython
--->  Installing py26-cython @0.24_0
--->  Cleaning py26-cython
--->  Computing dependencies for py26-cython
--->  Deactivating py26-cython @0.23.4_0
--->  Cleaning py26-cython
--->  Activating py26-cython @0.24_0

To make the Python 2.6 version of Cython the one that is run when you execute the commands without a version suffix, e.g. 'cython',
run:

port select --set cython cython26

--->  Cleaning py26-cython
--->  Computing dependencies for py27-cython
--->  Fetching archive for py27-cython
--->  Attempting to fetch py27-cython-0.24_0.darwin_15.x86_64.tbz2 from http://jog.id.packages.macports.org/macports/packages/py27-cython
--->  Attempting to fetch py27-cython-0.24_0.darwin_15.x86_64.tbz2.rmd160 from http://jog.id.packages.macports.org/macports/packages/py27-cython
--->  Installing py27-cython @0.24_0
--->  Cleaning py27-cython
--->  Computing dependencies for py27-cython
--->  Deactivating py27-cython @0.23.4_0
--->  Cleaning py27-cython
--->  Activating py27-cython @0.24_0

To make the Python 2.7 version of Cython the one that is run when you execute the commands without a version suffix, e.g. 'cython',
run:

port select --set cython cython27

--->  Cleaning py27-cython
--->  Computing dependencies for py27-tz
--->  Fetching archive for py27-tz
--->  Attempting to fetch py27-tz-2016.3_0.darwin_15.noarch.tbz2 from http://jog.id.packages.macports.org/macports/packages/py27-tz
--->  Attempting to fetch py27-tz-2016.3_0.darwin_15.noarch.tbz2.rmd160 from http://jog.id.packages.macports.org/macports/packages/py27-tz
--->  Installing py27-tz @2016.3_0
--->  Cleaning py27-tz
--->  Computing dependencies for py27-tz
--->  Deactivating py27-tz @2016.1_0
--->  Cleaning py27-tz
--->  Activating py27-tz @2016.3_0
--->  Cleaning py27-tz
--->  Computing dependencies for py27-dateutil
--->  Fetching archive for py27-dateutil
--->  Attempting to fetch py27-dateutil-2.5.1_0.darwin_15.noarch.tbz2 from http://jog.id.packages.macports.org/macports/packages/py27-dateutil
--->  Attempting to fetch py27-dateutil-2.5.1_0.darwin_15.noarch.tbz2.rmd160 from http://jog.id.packages.macports.org/macports/packages/py27-dateutil
--->  Installing py27-dateutil @2.5.1_0
--->  Cleaning py27-dateutil
--->  Computing dependencies for py27-dateutil
--->  Deactivating py27-dateutil @2.4.2_0
--->  Cleaning py27-dateutil
--->  Activating py27-dateutil @2.5.1_0
--->  Cleaning py27-dateutil
--->  Computing dependencies for py27-py2app
--->  Fetching archive for py27-py2app
--->  Attempting to fetch py27-py2app-0.10_0.darwin_15.x86_64.tbz2 from http://jog.id.packages.macports.org/macports/packages/py27-py2app
--->  Attempting to fetch py27-py2app-0.10_0.darwin_15.x86_64.tbz2.rmd160 from http://jog.id.packages.macports.org/macports/packages/py27-py2app
--->  Installing py27-py2app @0.10_0
--->  Cleaning py27-py2app
--->  Computing dependencies for py27-py2app
--->  Deactivating py27-py2app @0.9_1
--->  Cleaning py27-py2app
--->  Activating py27-py2app @0.10_0
--->  Cleaning py27-py2app
--->  Computing dependencies for py27-matplotlib
--->  Fetching archive for py27-matplotlib
--->  Attempting to fetch py27-matplotlib-1.5.1_2+cairo+tkinter.darwin_15.x86_64.tbz2 from http://jog.id.packages.macports.org/macports/packages/py27-matplotlib
--->  Attempting to fetch py27-matplotlib-1.5.1_2+cairo+tkinter.darwin_15.x86_64.tbz2 from http://nou.nc.packages.macports.org/pub/macports/packages.macports.org/py27-matplotlib
--->  Attempting to fetch py27-matplotlib-1.5.1_2+cairo+tkinter.darwin_15.x86_64.tbz2 from https://packages.macports.org/py27-matplotlib
--->  Fetching distfiles for py27-matplotlib
--->  Verifying checksums for py27-matplotlib
--->  Extracting py27-matplotlib
--->  Applying patches to py27-matplotlib
--->  Configuring py27-matplotlib
--->  Building py27-matplotlib
--->  Staging py27-matplotlib into destroot
--->  Installing py27-matplotlib @1.5.1_2+cairo+tkinter
--->  Cleaning py27-matplotlib
--->  Computing dependencies for py27-matplotlib
--->  Deactivating py27-matplotlib @1.5.1_1+cairo+tkinter
--->  Cleaning py27-matplotlib
--->  Activating py27-matplotlib @1.5.1_2+cairo+tkinter

The default backend is the interactive Mac OS X backend. Different backends can be specified using the ~/.matplotlib/matplotlibrc
file. More details regarding backends can be found in the matplotlib FAQ:

http://matplotlib.sourceforge.net/faq/installing_faq.html#what-is-a-backend

--->  Cleaning py27-matplotlib
--->  Computing dependencies for py27-numexpr
--->  Fetching archive for py27-numexpr
--->  Attempting to fetch py27-numexpr-2.5.2_0.darwin_15.x86_64.tbz2 from http://jog.id.packages.macports.org/macports/packages/py27-numexpr
--->  Attempting to fetch py27-numexpr-2.5.2_0.darwin_15.x86_64.tbz2.rmd160 from http://jog.id.packages.macports.org/macports/packages/py27-numexpr
--->  Installing py27-numexpr @2.5.2_0
--->  Cleaning py27-numexpr
--->  Computing dependencies for py27-numexpr
--->  Deactivating py27-numexpr @2.5_0
--->  Cleaning py27-numexpr
--->  Activating py27-numexpr @2.5.2_0
--->  Cleaning py27-numexpr
--->  Computing dependencies for py27-Pillow
--->  Fetching archive for py27-Pillow
--->  Attempting to fetch py27-Pillow-3.2.0_0.darwin_15.x86_64.tbz2 from http://jog.id.packages.macports.org/macports/packages/py27-Pillow
--->  Attempting to fetch py27-Pillow-3.2.0_0.darwin_15.x86_64.tbz2.rmd160 from http://jog.id.packages.macports.org/macports/packages/py27-Pillow
--->  Installing py27-Pillow @3.2.0_0
--->  Cleaning py27-Pillow
--->  Computing dependencies for py27-Pillow
--->  Deactivating py27-Pillow @3.1.1_0
--->  Cleaning py27-Pillow
--->  Activating py27-Pillow @3.2.0_0
--->  Cleaning py27-Pillow
--->  Computing dependencies for py27-qtconsole
--->  Fetching archive for py27-qtconsole
--->  Attempting to fetch py27-qtconsole-4.2.1_0.darwin_15.noarch.tbz2 from http://jog.id.packages.macports.org/macports/packages/py27-qtconsole
--->  Attempting to fetch py27-qtconsole-4.2.1_0.darwin_15.noarch.tbz2.rmd160 from http://jog.id.packages.macports.org/macports/packages/py27-qtconsole
--->  Installing py27-qtconsole @4.2.1_0
--->  Cleaning py27-qtconsole
--->  Computing dependencies for py27-qtconsole
--->  Deactivating py27-qtconsole @4.2.0_0
--->  Cleaning py27-qtconsole
--->  Activating py27-qtconsole @4.2.1_0
--->  Cleaning py27-qtconsole
--->  Computing dependencies for py27-scientific
--->  Fetching archive for py27-scientific
--->  Attempting to fetch py27-scientific-2.9.4_1.darwin_15.x86_64.tbz2 from http://jog.id.packages.macports.org/macports/packages/py27-scientific
--->  Attempting to fetch py27-scientific-2.9.4_1.darwin_15.x86_64.tbz2.rmd160 from http://jog.id.packages.macports.org/macports/packages/py27-scientific
--->  Installing py27-scientific @2.9.4_1
--->  Cleaning py27-scientific
--->  Computing dependencies for py27-scientific
--->  Deactivating py27-scientific @2.9.4_0
--->  Cleaning py27-scientific
--->  Activating py27-scientific @2.9.4_1
--->  Cleaning py27-scientific
--->  Computing dependencies for py27-setuptools_scm
--->  Fetching archive for py27-setuptools_scm
--->  Attempting to fetch py27-setuptools_scm-1.11.0_0.darwin_15.noarch.tbz2 from http://jog.id.packages.macports.org/macports/packages/py27-setuptools_scm
--->  Attempting to fetch py27-setuptools_scm-1.11.0_0.darwin_15.noarch.tbz2.rmd160 from http://jog.id.packages.macports.org/macports/packages/py27-setuptools_scm
--->  Installing py27-setuptools_scm @1.11.0_0
--->  Cleaning py27-setuptools_scm
--->  Computing dependencies for py27-setuptools_scm
--->  Deactivating py27-setuptools_scm @1.10.1_0
--->  Cleaning py27-setuptools_scm
--->  Activating py27-setuptools_scm @1.11.0_0
--->  Cleaning py27-setuptools_scm
--->  Computing dependencies for py27-imagesize
--->  Fetching archive for py27-imagesize
--->  Attempting to fetch py27-imagesize-0.7.0_0.darwin_15.noarch.tbz2 from http://jog.id.packages.macports.org/macports/packages/py27-imagesize
--->  Attempting to fetch py27-imagesize-0.7.0_0.darwin_15.noarch.tbz2.rmd160 from http://jog.id.packages.macports.org/macports/packages/py27-imagesize
--->  Installing py27-imagesize @0.7.0_0
--->  Activating py27-imagesize @0.7.0_0
--->  Cleaning py27-imagesize
--->  Computing dependencies for py27-sphinx
--->  Fetching archive for py27-sphinx
--->  Attempting to fetch py27-sphinx-1.4_0.darwin_15.noarch.tbz2 from http://jog.id.packages.macports.org/macports/packages/py27-sphinx
--->  Attempting to fetch py27-sphinx-1.4_0.darwin_15.noarch.tbz2.rmd160 from http://jog.id.packages.macports.org/macports/packages/py27-sphinx
--->  Installing py27-sphinx @1.4_0
--->  Cleaning py27-sphinx
--->  Computing dependencies for py27-sphinx
--->  Deactivating py27-sphinx @1.3.6_0
--->  Cleaning py27-sphinx
--->  Activating py27-sphinx @1.4_0

To make the Python 2.7 version of Sphinx the one that is run when you execute the commands without a version suffix, e.g.
'sphinx-build', run:

port select --set sphinx py27-sphinx

--->  Cleaning py27-sphinx
--->  Computing dependencies for py27-tables
--->  Fetching archive for py27-tables
--->  Attempting to fetch py27-tables-3.2.2_2.darwin_15.x86_64.tbz2 from http://jog.id.packages.macports.org/macports/packages/py27-tables
--->  Attempting to fetch py27-tables-3.2.2_2.darwin_15.x86_64.tbz2.rmd160 from http://jog.id.packages.macports.org/macports/packages/py27-tables
--->  Installing py27-tables @3.2.2_2
--->  Cleaning py27-tables
--->  Computing dependencies for py27-tables
--->  Deactivating py27-tables @3.2.2_1
--->  Cleaning py27-tables
--->  Activating py27-tables @3.2.2_2
--->  Cleaning py27-tables
--->  Computing dependencies for vtk
--->  Fetching archive for vtk
--->  Attempting to fetch vtk-7.0.0_0+python27.darwin_15.x86_64.tbz2 from http://jog.id.packages.macports.org/macports/packages/vtk
--->  Attempting to fetch vtk-7.0.0_0+python27.darwin_15.x86_64.tbz2.rmd160 from http://jog.id.packages.macports.org/macports/packages/vtk
--->  Installing vtk @7.0.0_0+python27
--->  Cleaning vtk
--->  Computing dependencies for vtk
--->  Deactivating vtk @6.3.0_0+python27
--->  Cleaning vtk
--->  Activating vtk @7.0.0_0+python27
--->  Cleaning vtk
--->  Updating database of binaries
--->  Scanning binaries for linking errors               
--->  No broken files found.   
```

Now we install maven

```bash
Sankha-desktop:spark-1.6.1 user$ sudo port install maven
Password:
--->  Fetching distfiles for maven
--->  Verifying checksums for maven
--->  Extracting maven
--->  Configuring maven
Error: maven is a stub, use maven1 instead.
Error: org.macports.configure for port maven returned: obsolete port
Please see the log file for port maven for details:
    /opt/local/var/macports/logs/_opt_local_var_macports_sources_rsync.macports.org_release_tarballs_ports_java_maven/maven/main.log
To report a bug, follow the instructions in the guide:
    http://guide.macports.org/#project.tickets
Error: Processing of port maven failed
Sankha-desktop:spark-1.6.1 user$ sudo port install maven 32
--->  Configuring maven
Error: maven is a stub, use maven1 instead.
Error: org.macports.configure for port maven returned: obsolete port
Please see the log file for port maven for details:
    /opt/local/var/macports/logs/_opt_local_var_macports_sources_rsync.macports.org_release_tarballs_ports_java_maven/maven/main.log
To report a bug, follow the instructions in the guide:
    http://guide.macports.org/#project.tickets
Error: Processing of port maven failed
Sankha-desktop:spark-1.6.1 user$ sudo port install maven32
--->  Computing dependencies for maven32
--->  Dependencies to be installed: maven_select
--->  Fetching archive for maven_select
--->  Attempting to fetch maven_select-0.3_1.darwin_15.noarch.tbz2 from http://jog.id.packages.macports.org/macports/packages/maven_select
--->  Attempting to fetch maven_select-0.3_1.darwin_15.noarch.tbz2.rmd160 from http://jog.id.packages.macports.org/macports/packages/maven_select
--->  Installing maven_select @0.3_1
--->  Activating maven_select @0.3_1
--->  Cleaning maven_select
--->  Fetching archive for maven32
--->  Attempting to fetch maven32-3.2.5_1.darwin_15.noarch.tbz2 from http://jog.id.packages.macports.org/macports/packages/maven32
--->  Attempting to fetch maven32-3.2.5_1.darwin_15.noarch.tbz2.rmd160 from http://jog.id.packages.macports.org/macports/packages/maven32
--->  Installing maven32 @3.2.5_1
--->  Activating maven32 @3.2.5_1

To make maven 3.2.5 the default, please run
	sudo port select --set maven maven32

--->  Cleaning maven32
--->  Updating database of binaries
--->  Scanning binaries for linking errors
--->  No broken files found.
Sankha-desktop:spark-1.6.1 user$ sudo port select --set maven maven32
Selecting 'maven32' for 'maven' succeeded. 'maven32' is now active.
```

It looks like the maven is too old ...

```bash
Sankha-desktop:spark-1.6.1 user$ build/mvn -Pyarn -Phadoop-2.4 -Dhadoop.version=2.4.0 -DskipTests clean package
Using `mvn` from path: /opt/local/bin/mvn
[INFO] Scanning for projects...
Downloading: https://repo1.maven.org/maven2/org/apache/apache/14/apache-14.pom
Downloaded: https://repo1.maven.org/maven2/org/apache/apache/14/apache-14.pom (15 KB at 6.2 KB/sec)
[INFO] ------------------------------------------------------------------------
[INFO] Reactor Build Order:
[INFO] 
[INFO] Spark Project Parent POM
[INFO] Spark Project Test Tags
[INFO] Spark Project Launcher
[INFO] Spark Project Networking
[INFO] Spark Project Shuffle Streaming Service
[INFO] Spark Project Unsafe
[INFO] Spark Project Core
[INFO] Spark Project Bagel
[INFO] Spark Project GraphX
[INFO] Spark Project Streaming
[INFO] Spark Project Catalyst
[INFO] Spark Project SQL
[INFO] Spark Project ML Library
[INFO] Spark Project Tools
[INFO] Spark Project Hive
[INFO] Spark Project Docker Integration Tests
[INFO] Spark Project REPL
[INFO] Spark Project YARN Shuffle Service
[INFO] Spark Project YARN
[INFO] Spark Project Assembly
[INFO] Spark Project External Twitter
[INFO] Spark Project External Flume Sink
[INFO] Spark Project External Flume
[INFO] Spark Project External Flume Assembly
[INFO] Spark Project External MQTT
[INFO] Spark Project External MQTT Assembly
[INFO] Spark Project External ZeroMQ
[INFO] Spark Project External Kafka
[INFO] Spark Project Examples
[INFO] Spark Project External Kafka Assembly
[INFO]                                                                         
[INFO] ------------------------------------------------------------------------
[INFO] Building Spark Project Parent POM 1.6.1
[INFO] ------------------------------------------------------------------------
Downloading: https://repo1.maven.org/maven2/org/apache/maven/plugins/maven-remote-resources-plugin/1.5/maven-remote-resources-plugin-1.5.pom
Downloaded: https://repo1.maven.org/maven2/org/apache/maven/plugins/maven-remote-resources-plugin/1.5/maven-remote-resources-plugin-1.5.pom (14 KB at 21.0 KB/sec)
Downloading: https://repo1.maven.org/maven2/org/apache/maven/plugins/maven-plugins/24/maven-plugins-24.pom
Downloaded: https://repo1.maven.org/maven2/org/apache/maven/plugins/maven-plugins/24/maven-plugins-24.pom (11 KB at 15.8 KB/sec)
Downloading: https://repo1.maven.org/maven2/org/apache/maven/maven-parent/23/maven-parent-23.pom
Downloaded: https://repo1.maven.org/maven2/org/apache/maven/maven-parent/23/maven-parent-23.pom (32 KB at 13.0 KB/sec)
Downloading: https://repo1.maven.org/maven2/org/apache/apache/13/apache-13.pom
Downloaded: https://repo1.maven.org/maven2/org/apache/apache/13/apache-13.pom (14 KB at 24.4 KB/sec)
Downloading: https://repo1.maven.org/maven2/org/apache/maven/plugins/maven-remote-resources-plugin/1.5/maven-remote-resources-plugin-1.5.jar
Downloaded: https://repo1.maven.org/maven2/org/apache/maven/plugins/maven-remote-resources-plugin/1.5/maven-remote-resources-plugin-1.5.jar (68 KB at 40.2 KB/sec)
Downloading: https://repo1.maven.org/maven2/org/apache/maven/plugins/maven-site-plugin/3.3/maven-site-plugin-3.3.pom
Downloaded: https://repo1.maven.org/maven2/org/apache/maven/plugins/maven-site-plugin/3.3/maven-site-plugin-3.3.pom (21 KB at 22.3 KB/sec)
Downloading: https://repo1.maven.org/maven2/org/apache/maven/plugins/maven-site-plugin/3.3/maven-site-plugin-3.3.jar
Downloaded: https://repo1.maven.org/maven2/org/apache/maven/plugins/maven-site-plugin/3.3/maven-site-plugin-3.3.jar (122 KB at 62.9 KB/sec)
Downloading: https://repo1.maven.org/maven2/org/apache/maven/plugins/maven-dependency-plugin/2.10/maven-dependency-plugin-2.10.pom
Downloaded: https://repo1.maven.org/maven2/org/apache/maven/plugins/maven-dependency-plugin/2.10/maven-dependency-plugin-2.10.pom (12 KB at 19.3 KB/sec)
Downloading: https://repo1.maven.org/maven2/org/apache/maven/plugins/maven-plugins/27/maven-plugins-27.pom
Downloaded: https://repo1.maven.org/maven2/org/apache/maven/plugins/maven-plugins/27/maven-plugins-27.pom (12 KB at 18.1 KB/sec)
Downloading: https://repo1.maven.org/maven2/org/apache/maven/maven-parent/26/maven-parent-26.pom
Downloaded: https://repo1.maven.org/maven2/org/apache/maven/maven-parent/26/maven-parent-26.pom (39 KB at 47.4 KB/sec)
Downloading: https://repo1.maven.org/maven2/org/apache/apache/16/apache-16.pom
Downloaded: https://repo1.maven.org/maven2/org/apache/apache/16/apache-16.pom (16 KB at 35.8 KB/sec)
Downloading: https://repo1.maven.org/maven2/org/apache/maven/plugins/maven-dependency-plugin/2.10/maven-dependency-plugin-2.10.jar
Downloaded: https://repo1.maven.org/maven2/org/apache/maven/plugins/maven-dependency-plugin/2.10/maven-dependency-plugin-2.10.jar (157 KB at 81.6 KB/sec)
Downloading: https://repo1.maven.org/maven2/org/apache/maven/plugins/maven-enforcer-plugin/1.4.1/maven-enforcer-plugin-1.4.1.pom
Downloaded: https://repo1.maven.org/maven2/org/apache/maven/plugins/maven-enforcer-plugin/1.4.1/maven-enforcer-plugin-1.4.1.pom (8 KB at 3.7 KB/sec)
Downloading: https://repo1.maven.org/maven2/org/apache/maven/enforcer/enforcer/1.4.1/enforcer-1.4.1.pom
Downloaded: https://repo1.maven.org/maven2/org/apache/maven/enforcer/enforcer/1.4.1/enforcer-1.4.1.pom (8 KB at 13.6 KB/sec)
Downloading: https://repo1.maven.org/maven2/org/apache/maven/plugins/maven-enforcer-plugin/1.4.1/maven-enforcer-plugin-1.4.1.jar
Downloaded: https://repo1.maven.org/maven2/org/apache/maven/plugins/maven-enforcer-plugin/1.4.1/maven-enforcer-plugin-1.4.1.jar (27 KB at 29.3 KB/sec)
Downloading: https://repo1.maven.org/maven2/net/alchim31/maven/scala-maven-plugin/3.2.2/scala-maven-plugin-3.2.2.pom
Downloaded: https://repo1.maven.org/maven2/net/alchim31/maven/scala-maven-plugin/3.2.2/scala-maven-plugin-3.2.2.pom (17 KB at 33.0 KB/sec)
Downloading: https://repo1.maven.org/maven2/org/sonatype/oss/oss-parent/9/oss-parent-9.pom
Downloaded: https://repo1.maven.org/maven2/org/sonatype/oss/oss-parent/9/oss-parent-9.pom (7 KB at 12.6 KB/sec)
Downloading: https://repo1.maven.org/maven2/net/alchim31/maven/scala-maven-plugin/3.2.2/scala-maven-plugin-3.2.2.jar
Downloaded: https://repo1.maven.org/maven2/net/alchim31/maven/scala-maven-plugin/3.2.2/scala-maven-plugin-3.2.2.jar (117 KB at 94.7 KB/sec)
Downloading: https://repo1.maven.org/maven2/org/apache/maven/plugins/maven-source-plugin/2.4/maven-source-plugin-2.4.pom
Downloaded: https://repo1.maven.org/maven2/org/apache/maven/plugins/maven-source-plugin/2.4/maven-source-plugin-2.4.pom (7 KB at 10.7 KB/sec)
Downloading: https://repo1.maven.org/maven2/org/apache/maven/plugins/maven-plugins/25/maven-plugins-25.pom
Downloaded: https://repo1.maven.org/maven2/org/apache/maven/plugins/maven-plugins/25/maven-plugins-25.pom (10 KB at 18.1 KB/sec)
Downloading: https://repo1.maven.org/maven2/org/apache/maven/maven-parent/24/maven-parent-24.pom
Downloaded: https://repo1.maven.org/maven2/org/apache/maven/maven-parent/24/maven-parent-24.pom (37 KB at 39.5 KB/sec)
Downloading: https://repo1.maven.org/maven2/org/apache/maven/plugins/maven-source-plugin/2.4/maven-source-plugin-2.4.jar
Downloaded: https://repo1.maven.org/maven2/org/apache/maven/plugins/maven-source-plugin/2.4/maven-source-plugin-2.4.jar (31 KB at 50.4 KB/sec)
Downloading: https://repo1.maven.org/maven2/org/scalastyle/scalastyle-maven-plugin/0.7.0/scalastyle-maven-plugin-0.7.0.pom
Downloaded: https://repo1.maven.org/maven2/org/scalastyle/scalastyle-maven-plugin/0.7.0/scalastyle-maven-plugin-0.7.0.pom (9 KB at 11.5 KB/sec)
Downloading: https://repo1.maven.org/maven2/org/sonatype/oss/oss-parent/7/oss-parent-7.pom
Downloaded: https://repo1.maven.org/maven2/org/sonatype/oss/oss-parent/7/oss-parent-7.pom (5 KB at 9.3 KB/sec)
Downloading: https://repo1.maven.org/maven2/org/scalastyle/scalastyle-maven-plugin/0.7.0/scalastyle-maven-plugin-0.7.0.jar
Downloaded: https://repo1.maven.org/maven2/org/scalastyle/scalastyle-maven-plugin/0.7.0/scalastyle-maven-plugin-0.7.0.jar (19 KB at 34.0 KB/sec)
Downloading: https://repo1.maven.org/maven2/org/scalatest/scalatest-maven-plugin/1.0/scalatest-maven-plugin-1.0.pom
Downloaded: https://repo1.maven.org/maven2/org/scalatest/scalatest-maven-plugin/1.0/scalatest-maven-plugin-1.0.pom (8 KB at 12.8 KB/sec)
Downloading: https://repo1.maven.org/maven2/org/scalatest/scalatest-maven-plugin/1.0/scalatest-maven-plugin-1.0.jar
Downloaded: https://repo1.maven.org/maven2/org/scalatest/scalatest-maven-plugin/1.0/scalatest-maven-plugin-1.0.jar (24 KB at 49.8 KB/sec)
Downloading: https://repo1.maven.org/maven2/org/apache/maven/plugins/maven-clean-plugin/2.6.1/maven-clean-plugin-2.6.1.pom
Downloaded: https://repo1.maven.org/maven2/org/apache/maven/plugins/maven-clean-plugin/2.6.1/maven-clean-plugin-2.6.1.pom (5 KB at 7.5 KB/sec)
Downloading: https://repo1.maven.org/maven2/org/apache/maven/plugins/maven-plugins/26/maven-plugins-26.pom
Downloaded: https://repo1.maven.org/maven2/org/apache/maven/plugins/maven-plugins/26/maven-plugins-26.pom (12 KB at 12.1 KB/sec)
Downloading: https://repo1.maven.org/maven2/org/apache/maven/maven-parent/25/maven-parent-25.pom
Downloaded: https://repo1.maven.org/maven2/org/apache/maven/maven-parent/25/maven-parent-25.pom (37 KB at 38.3 KB/sec)
Downloading: https://repo1.maven.org/maven2/org/apache/apache/15/apache-15.pom
Downloaded: https://repo1.maven.org/maven2/org/apache/apache/15/apache-15.pom (15 KB at 19.4 KB/sec)
Downloading: https://repo1.maven.org/maven2/org/apache/maven/plugins/maven-clean-plugin/2.6.1/maven-clean-plugin-2.6.1.jar
Downloaded: https://repo1.maven.org/maven2/org/apache/maven/plugins/maven-clean-plugin/2.6.1/maven-clean-plugin-2.6.1.jar (29 KB at 38.1 KB/sec)
Downloading: https://repo1.maven.org/maven2/org/apache/maven/plugins/maven-antrun-plugin/1.8/maven-antrun-plugin-1.8.pom
Downloaded: https://repo1.maven.org/maven2/org/apache/maven/plugins/maven-antrun-plugin/1.8/maven-antrun-plugin-1.8.pom (4 KB at 6.6 KB/sec)
Downloading: https://repo1.maven.org/maven2/org/apache/maven/plugins/maven-antrun-plugin/1.8/maven-antrun-plugin-1.8.jar
Downloaded: https://repo1.maven.org/maven2/org/apache/maven/plugins/maven-antrun-plugin/1.8/maven-antrun-plugin-1.8.jar (36 KB at 44.3 KB/sec)
Downloading: https://repo1.maven.org/maven2/org/apache/maven/plugins/maven-jar-plugin/2.6/maven-jar-plugin-2.6.pom
Downloaded: https://repo1.maven.org/maven2/org/apache/maven/plugins/maven-jar-plugin/2.6/maven-jar-plugin-2.6.pom (6 KB at 11.3 KB/sec)
Downloading: https://repo1.maven.org/maven2/org/apache/maven/plugins/maven-jar-plugin/2.6/maven-jar-plugin-2.6.jar
Downloaded: https://repo1.maven.org/maven2/org/apache/maven/plugins/maven-jar-plugin/2.6/maven-jar-plugin-2.6.jar (26 KB at 46.3 KB/sec)
Downloading: https://repo1.maven.org/maven2/org/apache/maven/plugins/maven-shade-plugin/2.4.1/maven-shade-plugin-2.4.1.pom
Downloaded: https://repo1.maven.org/maven2/org/apache/maven/plugins/maven-shade-plugin/2.4.1/maven-shade-plugin-2.4.1.pom (9 KB at 14.5 KB/sec)
Downloading: https://repo1.maven.org/maven2/org/apache/maven/plugins/maven-shade-plugin/2.4.1/maven-shade-plugin-2.4.1.jar
Downloaded: https://repo1.maven.org/maven2/org/apache/maven/plugins/maven-shade-plugin/2.4.1/maven-shade-plugin-2.4.1.jar (101 KB at 82.0 KB/sec)
Downloading: https://repo1.maven.org/maven2/org/spark-project/spark/unused/1.0.0/unused-1.0.0.pom
Downloaded: https://repo1.maven.org/maven2/org/spark-project/spark/unused/1.0.0/unused-1.0.0.pom (3 KB at 4.6 KB/sec)
Downloading: https://repo1.maven.org/maven2/org/scalatest/scalatest_2.10/2.2.1/scalatest_2.10-2.2.1.pom
Downloaded: https://repo1.maven.org/maven2/org/scalatest/scalatest_2.10/2.2.1/scalatest_2.10-2.2.1.pom (6 KB at 8.6 KB/sec)
Downloading: https://repo1.maven.org/maven2/org/scala-lang/scala-library/2.10.5/scala-library-2.10.5.pom
Downloaded: https://repo1.maven.org/maven2/org/scala-lang/scala-library/2.10.5/scala-library-2.10.5.pom (2 KB at 1.5 KB/sec)
Downloading: https://repo1.maven.org/maven2/org/scala-lang/scala-reflect/2.10.5/scala-reflect-2.10.5.pom
Downloaded: https://repo1.maven.org/maven2/org/scala-lang/scala-reflect/2.10.5/scala-reflect-2.10.5.pom (2 KB at 3.6 KB/sec)
Downloading: https://repo1.maven.org/maven2/junit/junit/4.11/junit-4.11.pom
Downloaded: https://repo1.maven.org/maven2/junit/junit/4.11/junit-4.11.pom (3 KB at 4.9 KB/sec)
Downloading: https://repo1.maven.org/maven2/org/hamcrest/hamcrest-core/1.3/hamcrest-core-1.3.pom
Downloaded: https://repo1.maven.org/maven2/org/hamcrest/hamcrest-core/1.3/hamcrest-core-1.3.pom (766 B at 1.7 KB/sec)
Downloading: https://repo1.maven.org/maven2/org/hamcrest/hamcrest-parent/1.3/hamcrest-parent-1.3.pom
Downloaded: https://repo1.maven.org/maven2/org/hamcrest/hamcrest-parent/1.3/hamcrest-parent-1.3.pom (2 KB at 3.2 KB/sec)
Downloading: https://repo1.maven.org/maven2/com/novocode/junit-interface/0.11/junit-interface-0.11.pom
Downloaded: https://repo1.maven.org/maven2/com/novocode/junit-interface/0.11/junit-interface-0.11.pom (2 KB at 3.7 KB/sec)
Downloading: https://repo1.maven.org/maven2/org/scala-sbt/test-interface/1.0/test-interface-1.0.pom
Downloaded: https://repo1.maven.org/maven2/org/scala-sbt/test-interface/1.0/test-interface-1.0.pom (2 KB at 3.1 KB/sec)
Downloading: https://repo1.maven.org/maven2/org/spark-project/spark/unused/1.0.0/unused-1.0.0.jar
Downloading: https://repo1.maven.org/maven2/org/scalatest/scalatest_2.10/2.2.1/scalatest_2.10-2.2.1.jar
Downloading: https://repo1.maven.org/maven2/org/scala-lang/scala-library/2.10.5/scala-library-2.10.5.jar
Downloading: https://repo1.maven.org/maven2/org/scala-lang/scala-reflect/2.10.5/scala-reflect-2.10.5.jar
Downloading: https://repo1.maven.org/maven2/junit/junit/4.11/junit-4.11.jar
Downloaded: https://repo1.maven.org/maven2/org/spark-project/spark/unused/1.0.0/unused-1.0.0.jar (3 KB at 6.2 KB/sec)
Downloading: https://repo1.maven.org/maven2/org/hamcrest/hamcrest-core/1.3/hamcrest-core-1.3.jar
Downloaded: https://repo1.maven.org/maven2/org/hamcrest/hamcrest-core/1.3/hamcrest-core-1.3.jar (44 KB at 36.0 KB/sec)
Downloading: https://repo1.maven.org/maven2/com/novocode/junit-interface/0.11/junit-interface-0.11.jar
Downloaded: https://repo1.maven.org/maven2/com/novocode/junit-interface/0.11/junit-interface-0.11.jar (30 KB at 17.6 KB/sec)
Downloading: https://repo1.maven.org/maven2/org/scala-sbt/test-interface/1.0/test-interface-1.0.jar
Downloaded: https://repo1.maven.org/maven2/org/scala-sbt/test-interface/1.0/test-interface-1.0.jar (15 KB at 6.5 KB/sec)
Downloaded: https://repo1.maven.org/maven2/junit/junit/4.11/junit-4.11.jar (240 KB at 98.1 KB/sec)
Downloaded: https://repo1.maven.org/maven2/org/scala-lang/scala-reflect/2.10.5/scala-reflect-2.10.5.jar (3132 KB at 474.5 KB/sec)
Downloaded: https://repo1.maven.org/maven2/org/scalatest/scalatest_2.10/2.2.1/scalatest_2.10-2.2.1.jar (7316 KB at 863.9 KB/sec)
Downloaded: https://repo1.maven.org/maven2/org/scala-lang/scala-library/2.10.5/scala-library-2.10.5.jar (6964 KB at 425.6 KB/sec)
[INFO] 
[INFO] --- maven-clean-plugin:2.6.1:clean (default-clean) @ spark-parent_2.10 ---
Downloading: https://repo1.maven.org/maven2/org/apache/maven/maven-plugin-api/2.2.1/maven-plugin-api-2.2.1.pom
Downloaded: https://repo1.maven.org/maven2/org/apache/maven/maven-plugin-api/2.2.1/maven-plugin-api-2.2.1.pom (2 KB at 2.4 KB/sec)
Downloading: https://repo1.maven.org/maven2/org/apache/maven/maven/2.2.1/maven-2.2.1.pom
Downloaded: https://repo1.maven.org/maven2/org/apache/maven/maven/2.2.1/maven-2.2.1.pom (22 KB at 43.2 KB/sec)
Downloading: https://repo1.maven.org/maven2/org/apache/maven/maven-parent/11/maven-parent-11.pom
Downloaded: https://repo1.maven.org/maven2/org/apache/maven/maven-parent/11/maven-parent-11.pom (32 KB at 46.8 KB/sec)
Downloading: https://repo1.maven.org/maven2/org/apache/apache/5/apache-5.pom
Downloaded: https://repo1.maven.org/maven2/org/apache/apache/5/apache-5.pom (5 KB at 6.1 KB/sec)
Downloading: https://repo1.maven.org/maven2/org/apache/maven/shared/maven-shared-utils/0.7/maven-shared-utils-0.7.pom
Downloaded: https://repo1.maven.org/maven2/org/apache/maven/shared/maven-shared-utils/0.7/maven-shared-utils-0.7.pom (5 KB at 8.1 KB/sec)
Downloading: https://repo1.maven.org/maven2/org/apache/maven/shared/maven-shared-components/20/maven-shared-components-20.pom
Downloaded: https://repo1.maven.org/maven2/org/apache/maven/shared/maven-shared-components/20/maven-shared-components-20.pom (5 KB at 7.0 KB/sec)
Downloading: https://repo1.maven.org/maven2/com/google/code/findbugs/jsr305/2.0.1/jsr305-2.0.1.pom
Downloaded: https://repo1.maven.org/maven2/com/google/code/findbugs/jsr305/2.0.1/jsr305-2.0.1.pom (965 B at 1.9 KB/sec)
Downloading: https://repo1.maven.org/maven2/org/apache/maven/shared/maven-shared-utils/0.7/maven-shared-utils-0.7.jar
Downloading: https://repo1.maven.org/maven2/com/google/code/findbugs/jsr305/2.0.1/jsr305-2.0.1.jar
Downloading: https://repo1.maven.org/maven2/org/codehaus/plexus/plexus-utils/1.1/plexus-utils-1.1.jar
Downloaded: https://repo1.maven.org/maven2/org/codehaus/plexus/plexus-utils/1.1/plexus-utils-1.1.jar (165 KB at 239.3 KB/sec)
Downloaded: https://repo1.maven.org/maven2/org/apache/maven/shared/maven-shared-utils/0.7/maven-shared-utils-0.7.jar (167 KB at 220.6 KB/sec)
Downloaded: https://repo1.maven.org/maven2/com/google/code/findbugs/jsr305/2.0.1/jsr305-2.0.1.jar (32 KB at 27.6 KB/sec)
[INFO] 
[INFO] --- maven-enforcer-plugin:1.4.1:enforce (enforce-versions) @ spark-parent_2.10 ---
Downloading: https://repo1.maven.org/maven2/org/apache/maven/maven-artifact/2.2.1/maven-artifact-2.2.1.pom
Downloaded: https://repo1.maven.org/maven2/org/apache/maven/maven-artifact/2.2.1/maven-artifact-2.2.1.pom (2 KB at 2.6 KB/sec)
Downloading: https://repo1.maven.org/maven2/org/codehaus/plexus/plexus-utils/3.0.22/plexus-utils-3.0.22.pom
Downloaded: https://repo1.maven.org/maven2/org/codehaus/plexus/plexus-utils/3.0.22/plexus-utils-3.0.22.pom (4 KB at 6.1 KB/sec)
Downloading: https://repo1.maven.org/maven2/org/codehaus/plexus/plexus/3.3.1/plexus-3.3.1.pom
Downloaded: https://repo1.maven.org/maven2/org/codehaus/plexus/plexus/3.3.1/plexus-3.3.1.pom (20 KB at 37.5 KB/sec)
Downloading: https://repo1.maven.org/maven2/org/sonatype/spice/spice-parent/17/spice-parent-17.pom
Downloaded: https://repo1.maven.org/maven2/org/sonatype/spice/spice-parent/17/spice-parent-17.pom (7 KB at 13.6 KB/sec)
Downloading: https://repo1.maven.org/maven2/org/sonatype/forge/forge-parent/10/forge-parent-10.pom
Downloaded: https://repo1.maven.org/maven2/org/sonatype/forge/forge-parent/10/forge-parent-10.pom (14 KB at 20.9 KB/sec)
Downloading: https://repo1.maven.org/maven2/org/apache/maven/maven-project/2.2.1/maven-project-2.2.1.pom
Downloaded: https://repo1.maven.org/maven2/org/apache/maven/maven-project/2.2.1/maven-project-2.2.1.pom (3 KB at 6.2 KB/sec)
Downloading: https://repo1.maven.org/maven2/org/apache/maven/maven-settings/2.2.1/maven-settings-2.2.1.pom
Downloaded: https://repo1.maven.org/maven2/org/apache/maven/maven-settings/2.2.1/maven-settings-2.2.1.pom (3 KB at 3.2 KB/sec)
Downloading: https://repo1.maven.org/maven2/org/apache/maven/maven-model/2.2.1/maven-model-2.2.1.pom
Downloaded: https://repo1.maven.org/maven2/org/apache/maven/maven-model/2.2.1/maven-model-2.2.1.pom (4 KB at 5.2 KB/sec)
Downloading: https://repo1.maven.org/maven2/org/codehaus/plexus/plexus-interpolation/1.11/plexus-interpolation-1.11.pom
Downloaded: https://repo1.maven.org/maven2/org/codehaus/plexus/plexus-interpolation/1.11/plexus-interpolation-1.11.pom (889 B at 1.4 KB/sec)
Downloading: https://repo1.maven.org/maven2/org/codehaus/plexus/plexus-components/1.1.14/plexus-components-1.1.14.pom
Downloaded: https://repo1.maven.org/maven2/org/codehaus/plexus/plexus-components/1.1.14/plexus-components-1.1.14.pom (6 KB at 9.4 KB/sec)
Downloading: https://repo1.maven.org/maven2/org/codehaus/plexus/plexus/2.0.2/plexus-2.0.2.pom
Downloaded: https://repo1.maven.org/maven2/org/codehaus/plexus/plexus/2.0.2/plexus-2.0.2.pom (12 KB at 26.4 KB/sec)
Downloading: https://repo1.maven.org/maven2/org/codehaus/plexus/plexus-container-default/1.0-alpha-9-stable-1/plexus-container-default-1.0-alpha-9-stable-1.pom
Downloaded: https://repo1.maven.org/maven2/org/codehaus/plexus/plexus-container-default/1.0-alpha-9-stable-1/plexus-container-default-1.0-alpha-9-stable-1.pom (4 KB at 8.6 KB/sec)
Downloading: https://repo1.maven.org/maven2/org/codehaus/plexus/plexus-containers/1.0.3/plexus-containers-1.0.3.pom
Downloaded: https://repo1.maven.org/maven2/org/codehaus/plexus/plexus-containers/1.0.3/plexus-containers-1.0.3.pom (492 B at 1.1 KB/sec)
Downloading: https://repo1.maven.org/maven2/org/codehaus/plexus/plexus/1.0.4/plexus-1.0.4.pom
Downloaded: https://repo1.maven.org/maven2/org/codehaus/plexus/plexus/1.0.4/plexus-1.0.4.pom (6 KB at 12.7 KB/sec)
Downloading: https://repo1.maven.org/maven2/classworlds/classworlds/1.1-alpha-2/classworlds-1.1-alpha-2.pom
Downloaded: https://repo1.maven.org/maven2/classworlds/classworlds/1.1-alpha-2/classworlds-1.1-alpha-2.pom (4 KB at 6.9 KB/sec)
Downloading: https://repo1.maven.org/maven2/org/apache/maven/maven-profile/2.2.1/maven-profile-2.2.1.pom
Downloaded: https://repo1.maven.org/maven2/org/apache/maven/maven-profile/2.2.1/maven-profile-2.2.1.pom (3 KB at 5.0 KB/sec)
Downloading: https://repo1.maven.org/maven2/org/apache/maven/maven-artifact-manager/2.2.1/maven-artifact-manager-2.2.1.pom
Downloaded: https://repo1.maven.org/maven2/org/apache/maven/maven-artifact-manager/2.2.1/maven-artifact-manager-2.2.1.pom (4 KB at 4.2 KB/sec)
Downloading: https://repo1.maven.org/maven2/org/apache/maven/maven-repository-metadata/2.2.1/maven-repository-metadata-2.2.1.pom
Downloaded: https://repo1.maven.org/maven2/org/apache/maven/maven-repository-metadata/2.2.1/maven-repository-metadata-2.2.1.pom (2 KB at 3.6 KB/sec)
Downloading: https://repo1.maven.org/maven2/backport-util-concurrent/backport-util-concurrent/3.1/backport-util-concurrent-3.1.pom
Downloaded: https://repo1.maven.org/maven2/backport-util-concurrent/backport-util-concurrent/3.1/backport-util-concurrent-3.1.pom (880 B at 1.7 KB/sec)
Downloading: https://repo1.maven.org/maven2/org/apache/maven/maven-plugin-registry/2.2.1/maven-plugin-registry-2.2.1.pom
Downloaded: https://repo1.maven.org/maven2/org/apache/maven/maven-plugin-registry/2.2.1/maven-plugin-registry-2.2.1.pom (2 KB at 3.7 KB/sec)
Downloading: https://repo1.maven.org/maven2/org/apache/maven/maven-core/2.2.1/maven-core-2.2.1.pom
Downloaded: https://repo1.maven.org/maven2/org/apache/maven/maven-core/2.2.1/maven-core-2.2.1.pom (12 KB at 14.1 KB/sec)
Downloading: https://repo1.maven.org/maven2/org/apache/maven/maven-plugin-parameter-documenter/2.2.1/maven-plugin-parameter-documenter-2.2.1.pom
Downloaded: https://repo1.maven.org/maven2/org/apache/maven/maven-plugin-parameter-documenter/2.2.1/maven-plugin-parameter-documenter-2.2.1.pom (2 KB at 3.7 KB/sec)
Downloading: https://repo1.maven.org/maven2/org/slf4j/slf4j-jdk14/1.5.6/slf4j-jdk14-1.5.6.pom
Downloaded: https://repo1.maven.org/maven2/org/slf4j/slf4j-jdk14/1.5.6/slf4j-jdk14-1.5.6.pom (2 KB at 3.6 KB/sec)
Downloading: https://repo1.maven.org/maven2/org/slf4j/slf4j-parent/1.5.6/slf4j-parent-1.5.6.pom
Downloaded: https://repo1.maven.org/maven2/org/slf4j/slf4j-parent/1.5.6/slf4j-parent-1.5.6.pom (8 KB at 12.7 KB/sec)
Downloading: https://repo1.maven.org/maven2/org/slf4j/slf4j-api/1.5.6/slf4j-api-1.5.6.pom
Downloaded: https://repo1.maven.org/maven2/org/slf4j/slf4j-api/1.5.6/slf4j-api-1.5.6.pom (3 KB at 5.6 KB/sec)
Downloading: https://repo1.maven.org/maven2/org/slf4j/jcl-over-slf4j/1.5.6/jcl-over-slf4j-1.5.6.pom
Downloaded: https://repo1.maven.org/maven2/org/slf4j/jcl-over-slf4j/1.5.6/jcl-over-slf4j-1.5.6.pom (3 KB at 4.9 KB/sec)
Downloading: https://repo1.maven.org/maven2/org/apache/maven/reporting/maven-reporting-api/2.2.1/maven-reporting-api-2.2.1.pom
Downloaded: https://repo1.maven.org/maven2/org/apache/maven/reporting/maven-reporting-api/2.2.1/maven-reporting-api-2.2.1.pom (2 KB at 3.8 KB/sec)
Downloading: https://repo1.maven.org/maven2/org/apache/maven/reporting/maven-reporting/2.2.1/maven-reporting-2.2.1.pom
Downloaded: https://repo1.maven.org/maven2/org/apache/maven/reporting/maven-reporting/2.2.1/maven-reporting-2.2.1.pom (2 KB at 2.2 KB/sec)
Downloading: https://repo1.maven.org/maven2/org/apache/maven/doxia/doxia-sink-api/1.1/doxia-sink-api-1.1.pom
Downloaded: https://repo1.maven.org/maven2/org/apache/maven/doxia/doxia-sink-api/1.1/doxia-sink-api-1.1.pom (2 KB at 2.9 KB/sec)
Downloading: https://repo1.maven.org/maven2/org/apache/maven/doxia/doxia/1.1/doxia-1.1.pom
Downloaded: https://repo1.maven.org/maven2/org/apache/maven/doxia/doxia/1.1/doxia-1.1.pom (15 KB at 27.7 KB/sec)
Downloading: https://repo1.maven.org/maven2/org/apache/maven/doxia/doxia-logging-api/1.1/doxia-logging-api-1.1.pom
Downloaded: https://repo1.maven.org/maven2/org/apache/maven/doxia/doxia-logging-api/1.1/doxia-logging-api-1.1.pom (2 KB at 3.2 KB/sec)
Downloading: https://repo1.maven.org/maven2/org/codehaus/plexus/plexus-container-default/1.0-alpha-30/plexus-container-default-1.0-alpha-30.pom
Downloaded: https://repo1.maven.org/maven2/org/codehaus/plexus/plexus-container-default/1.0-alpha-30/plexus-container-default-1.0-alpha-30.pom (4 KB at 5.6 KB/sec)
Downloading: https://repo1.maven.org/maven2/org/codehaus/plexus/plexus-containers/1.0-alpha-30/plexus-containers-1.0-alpha-30.pom
Downloaded: https://repo1.maven.org/maven2/org/codehaus/plexus/plexus-containers/1.0-alpha-30/plexus-containers-1.0-alpha-30.pom (2 KB at 3.0 KB/sec)
Downloading: https://repo1.maven.org/maven2/org/codehaus/plexus/plexus/1.0.11/plexus-1.0.11.pom
Downloaded: https://repo1.maven.org/maven2/org/codehaus/plexus/plexus/1.0.11/plexus-1.0.11.pom (9 KB at 14.3 KB/sec)
Downloading: https://repo1.maven.org/maven2/org/codehaus/plexus/plexus-classworlds/1.2-alpha-9/plexus-classworlds-1.2-alpha-9.pom
Downloaded: https://repo1.maven.org/maven2/org/codehaus/plexus/plexus-classworlds/1.2-alpha-9/plexus-classworlds-1.2-alpha-9.pom (4 KB at 6.1 KB/sec)
Downloading: https://repo1.maven.org/maven2/org/codehaus/plexus/plexus/1.0.10/plexus-1.0.10.pom
Downloaded: https://repo1.maven.org/maven2/org/codehaus/plexus/plexus/1.0.10/plexus-1.0.10.pom (9 KB at 13.3 KB/sec)
Downloading: https://repo1.maven.org/maven2/org/apache/maven/maven-error-diagnostics/2.2.1/maven-error-diagnostics-2.2.1.pom
Downloaded: https://repo1.maven.org/maven2/org/apache/maven/maven-error-diagnostics/2.2.1/maven-error-diagnostics-2.2.1.pom (2 KB at 2.7 KB/sec)
Downloading: https://repo1.maven.org/maven2/commons-cli/commons-cli/1.2/commons-cli-1.2.pom
Downloaded: https://repo1.maven.org/maven2/commons-cli/commons-cli/1.2/commons-cli-1.2.pom (8 KB at 12.7 KB/sec)
Downloading: https://repo1.maven.org/maven2/org/apache/commons/commons-parent/11/commons-parent-11.pom
Downloaded: https://repo1.maven.org/maven2/org/apache/commons/commons-parent/11/commons-parent-11.pom (25 KB at 39.3 KB/sec)
Downloading: https://repo1.maven.org/maven2/org/apache/apache/4/apache-4.pom
Downloaded: https://repo1.maven.org/maven2/org/apache/apache/4/apache-4.pom (5 KB at 7.2 KB/sec)
Downloading: https://repo1.maven.org/maven2/org/apache/maven/maven-plugin-descriptor/2.2.1/maven-plugin-descriptor-2.2.1.pom
Downloaded: https://repo1.maven.org/maven2/org/apache/maven/maven-plugin-descriptor/2.2.1/maven-plugin-descriptor-2.2.1.pom (3 KB at 3.3 KB/sec)
Downloading: https://repo1.maven.org/maven2/org/codehaus/plexus/plexus-interactivity-api/1.0-alpha-4/plexus-interactivity-api-1.0-alpha-4.pom
Downloaded: https://repo1.maven.org/maven2/org/codehaus/plexus/plexus-interactivity-api/1.0-alpha-4/plexus-interactivity-api-1.0-alpha-4.pom (7 KB at 11.4 KB/sec)
Downloading: https://repo1.maven.org/maven2/org/apache/maven/maven-monitor/2.2.1/maven-monitor-2.2.1.pom
Downloaded: https://repo1.maven.org/maven2/org/apache/maven/maven-monitor/2.2.1/maven-monitor-2.2.1.pom (2 KB at 0.8 KB/sec)
Downloading: https://repo1.maven.org/maven2/classworlds/classworlds/1.1/classworlds-1.1.pom
Downloaded: https://repo1.maven.org/maven2/classworlds/classworlds/1.1/classworlds-1.1.pom (4 KB at 6.4 KB/sec)
Downloading: https://repo1.maven.org/maven2/org/sonatype/plexus/plexus-sec-dispatcher/1.3/plexus-sec-dispatcher-1.3.pom
Downloaded: https://repo1.maven.org/maven2/org/sonatype/plexus/plexus-sec-dispatcher/1.3/plexus-sec-dispatcher-1.3.pom (3 KB at 6.5 KB/sec)
Downloading: https://repo1.maven.org/maven2/org/sonatype/spice/spice-parent/12/spice-parent-12.pom
Downloaded: https://repo1.maven.org/maven2/org/sonatype/spice/spice-parent/12/spice-parent-12.pom (7 KB at 12.6 KB/sec)
Downloading: https://repo1.maven.org/maven2/org/sonatype/forge/forge-parent/4/forge-parent-4.pom
Downloaded: https://repo1.maven.org/maven2/org/sonatype/forge/forge-parent/4/forge-parent-4.pom (9 KB at 14.7 KB/sec)
Downloading: https://repo1.maven.org/maven2/org/sonatype/plexus/plexus-cipher/1.4/plexus-cipher-1.4.pom
Downloaded: https://repo1.maven.org/maven2/org/sonatype/plexus/plexus-cipher/1.4/plexus-cipher-1.4.pom (3 KB at 3.9 KB/sec)
Downloading: https://repo1.maven.org/maven2/commons-lang/commons-lang/2.3/commons-lang-2.3.pom
Downloaded: https://repo1.maven.org/maven2/commons-lang/commons-lang/2.3/commons-lang-2.3.pom (11 KB at 17.4 KB/sec)
Downloading: https://repo1.maven.org/maven2/org/apache/maven/enforcer/enforcer-api/1.4.1/enforcer-api-1.4.1.pom
Downloaded: https://repo1.maven.org/maven2/org/apache/maven/enforcer/enforcer-api/1.4.1/enforcer-api-1.4.1.pom (3 KB at 4.6 KB/sec)
Downloading: https://repo1.maven.org/maven2/org/codehaus/plexus/plexus-container-default/1.0-alpha-9/plexus-container-default-1.0-alpha-9.pom
Downloaded: https://repo1.maven.org/maven2/org/codehaus/plexus/plexus-container-default/1.0-alpha-9/plexus-container-default-1.0-alpha-9.pom (2 KB at 2.0 KB/sec)
Downloading: https://repo1.maven.org/maven2/org/apache/maven/enforcer/enforcer-rules/1.4.1/enforcer-rules-1.4.1.pom
Downloaded: https://repo1.maven.org/maven2/org/apache/maven/enforcer/enforcer-rules/1.4.1/enforcer-rules-1.4.1.pom (4 KB at 5.5 KB/sec)
Downloading: https://repo1.maven.org/maven2/org/apache/maven/shared/maven-common-artifact-filters/1.4/maven-common-artifact-filters-1.4.pom
Downloaded: https://repo1.maven.org/maven2/org/apache/maven/shared/maven-common-artifact-filters/1.4/maven-common-artifact-filters-1.4.pom (4 KB at 2.3 KB/sec)
Downloading: https://repo1.maven.org/maven2/org/apache/maven/shared/maven-shared-components/17/maven-shared-components-17.pom
Downloaded: https://repo1.maven.org/maven2/org/apache/maven/shared/maven-shared-components/17/maven-shared-components-17.pom (9 KB at 13.8 KB/sec)
Downloading: https://repo1.maven.org/maven2/org/apache/maven/maven-parent/21/maven-parent-21.pom
Downloaded: https://repo1.maven.org/maven2/org/apache/maven/maven-parent/21/maven-parent-21.pom (26 KB at 42.1 KB/sec)
Downloading: https://repo1.maven.org/maven2/org/apache/apache/10/apache-10.pom
Downloaded: https://repo1.maven.org/maven2/org/apache/apache/10/apache-10.pom (15 KB at 23.6 KB/sec)
Downloading: https://repo1.maven.org/maven2/org/apache/maven/maven-model/2.0.8/maven-model-2.0.8.pom
Downloaded: https://repo1.maven.org/maven2/org/apache/maven/maven-model/2.0.8/maven-model-2.0.8.pom (4 KB at 4.3 KB/sec)
Downloading: https://repo1.maven.org/maven2/org/apache/maven/maven/2.0.8/maven-2.0.8.pom
Downloaded: https://repo1.maven.org/maven2/org/apache/maven/maven/2.0.8/maven-2.0.8.pom (12 KB at 8.7 KB/sec)
Downloading: https://repo1.maven.org/maven2/org/apache/maven/maven-parent/6/maven-parent-6.pom
Downloaded: https://repo1.maven.org/maven2/org/apache/maven/maven-parent/6/maven-parent-6.pom (20 KB at 28.5 KB/sec)
Downloading: https://repo1.maven.org/maven2/org/codehaus/plexus/plexus-container-default/1.5.5/plexus-container-default-1.5.5.pom
Downloaded: https://repo1.maven.org/maven2/org/codehaus/plexus/plexus-container-default/1.5.5/plexus-container-default-1.5.5.pom (3 KB at 4.4 KB/sec)
Downloading: https://repo1.maven.org/maven2/org/codehaus/plexus/plexus-containers/1.5.5/plexus-containers-1.5.5.pom
Downloaded: https://repo1.maven.org/maven2/org/codehaus/plexus/plexus-containers/1.5.5/plexus-containers-1.5.5.pom (5 KB at 8.1 KB/sec)
Downloading: https://repo1.maven.org/maven2/org/codehaus/plexus/plexus/2.0.7/plexus-2.0.7.pom
Downloaded: https://repo1.maven.org/maven2/org/codehaus/plexus/plexus/2.0.7/plexus-2.0.7.pom (17 KB at 20.6 KB/sec)
Downloading: https://repo1.maven.org/maven2/org/codehaus/plexus/plexus-classworlds/2.2.2/plexus-classworlds-2.2.2.pom
Downloaded: https://repo1.maven.org/maven2/org/codehaus/plexus/plexus-classworlds/2.2.2/plexus-classworlds-2.2.2.pom (4 KB at 6.5 KB/sec)
Downloading: https://repo1.maven.org/maven2/org/codehaus/plexus/plexus/2.0.3/plexus-2.0.3.pom
Downloaded: https://repo1.maven.org/maven2/org/codehaus/plexus/plexus/2.0.3/plexus-2.0.3.pom (16 KB at 30.7 KB/sec)
Downloading: https://repo1.maven.org/maven2/org/apache/xbean/xbean-reflect/3.4/xbean-reflect-3.4.pom
Downloaded: https://repo1.maven.org/maven2/org/apache/xbean/xbean-reflect/3.4/xbean-reflect-3.4.pom (3 KB at 5.2 KB/sec)
Downloading: https://repo1.maven.org/maven2/org/apache/xbean/xbean/3.4/xbean-3.4.pom
Downloaded: https://repo1.maven.org/maven2/org/apache/xbean/xbean/3.4/xbean-3.4.pom (19 KB at 29.5 KB/sec)
Downloading: https://repo1.maven.org/maven2/log4j/log4j/1.2.12/log4j-1.2.12.pom
Downloaded: https://repo1.maven.org/maven2/log4j/log4j/1.2.12/log4j-1.2.12.pom (145 B at 0.2 KB/sec)
Downloading: https://repo1.maven.org/maven2/commons-logging/commons-logging-api/1.1/commons-logging-api-1.1.pom
Downloaded: https://repo1.maven.org/maven2/commons-logging/commons-logging-api/1.1/commons-logging-api-1.1.pom (6 KB at 7.3 KB/sec)
Downloading: https://repo1.maven.org/maven2/com/google/collections/google-collections/1.0/google-collections-1.0.pom
Downloaded: https://repo1.maven.org/maven2/com/google/collections/google-collections/1.0/google-collections-1.0.pom (3 KB at 4.3 KB/sec)
Downloading: https://repo1.maven.org/maven2/com/google/google/1/google-1.pom
Downloaded: https://repo1.maven.org/maven2/com/google/google/1/google-1.pom (2 KB at 3.4 KB/sec)
Downloading: https://repo1.maven.org/maven2/org/beanshell/bsh/2.0b4/bsh-2.0b4.pom
Downloaded: https://repo1.maven.org/maven2/org/beanshell/bsh/2.0b4/bsh-2.0b4.pom (2 KB at 1.9 KB/sec)
Downloading: https://repo1.maven.org/maven2/org/beanshell/beanshell/2.0b4/beanshell-2.0b4.pom
Downloaded: https://repo1.maven.org/maven2/org/beanshell/beanshell/2.0b4/beanshell-2.0b4.pom (2 KB at 2.3 KB/sec)
Downloading: https://repo1.maven.org/maven2/org/apache/maven/shared/maven-dependency-tree/2.2/maven-dependency-tree-2.2.pom
Downloaded: https://repo1.maven.org/maven2/org/apache/maven/shared/maven-dependency-tree/2.2/maven-dependency-tree-2.2.pom (8 KB at 11.0 KB/sec)
Downloading: https://repo1.maven.org/maven2/org/codehaus/plexus/plexus-component-annotations/1.5.5/plexus-component-annotations-1.5.5.pom
Downloaded: https://repo1.maven.org/maven2/org/codehaus/plexus/plexus-component-annotations/1.5.5/plexus-component-annotations-1.5.5.pom (815 B at 1.3 KB/sec)
Downloading: https://repo1.maven.org/maven2/org/eclipse/aether/aether-util/0.9.0.M2/aether-util-0.9.0.M2.pom
Downloaded: https://repo1.maven.org/maven2/org/eclipse/aether/aether-util/0.9.0.M2/aether-util-0.9.0.M2.pom (2 KB at 3.9 KB/sec)
Downloading: https://repo1.maven.org/maven2/org/eclipse/aether/aether/0.9.0.M2/aether-0.9.0.M2.pom
Downloaded: https://repo1.maven.org/maven2/org/eclipse/aether/aether/0.9.0.M2/aether-0.9.0.M2.pom (28 KB at 38.8 KB/sec)
Downloading: https://repo1.maven.org/maven2/org/codehaus/plexus/plexus-i18n/1.0-beta-6/plexus-i18n-1.0-beta-6.pom
Downloaded: https://repo1.maven.org/maven2/org/codehaus/plexus/plexus-i18n/1.0-beta-6/plexus-i18n-1.0-beta-6.pom (771 B at 1.1 KB/sec)
Downloading: https://repo1.maven.org/maven2/org/codehaus/plexus/plexus-components/1.1.4/plexus-components-1.1.4.pom
Downloaded: https://repo1.maven.org/maven2/org/codehaus/plexus/plexus-components/1.1.4/plexus-components-1.1.4.pom (3 KB at 3.3 KB/sec)
Downloading: https://repo1.maven.org/maven2/org/codehaus/plexus/plexus-container-default/1.0-alpha-8/plexus-container-default-1.0-alpha-8.pom
Downloaded: https://repo1.maven.org/maven2/org/codehaus/plexus/plexus-container-default/1.0-alpha-8/plexus-container-default-1.0-alpha-8.pom (8 KB at 4.6 KB/sec)
Downloading: https://repo1.maven.org/maven2/org/apache/maven/plugin-testing/maven-plugin-testing-harness/1.3/maven-plugin-testing-harness-1.3.pom
Downloaded: https://repo1.maven.org/maven2/org/apache/maven/plugin-testing/maven-plugin-testing-harness/1.3/maven-plugin-testing-harness-1.3.pom (4 KB at 6.5 KB/sec)
Downloading: https://repo1.maven.org/maven2/org/apache/maven/plugin-testing/maven-plugin-testing/1.3/maven-plugin-testing-1.3.pom
Downloaded: https://repo1.maven.org/maven2/org/apache/maven/plugin-testing/maven-plugin-testing/1.3/maven-plugin-testing-1.3.pom (10 KB at 10.1 KB/sec)
Downloading: https://repo1.maven.org/maven2/org/codehaus/plexus/plexus-archiver/2.2/plexus-archiver-2.2.pom
Downloaded: https://repo1.maven.org/maven2/org/codehaus/plexus/plexus-archiver/2.2/plexus-archiver-2.2.pom (4 KB at 6.1 KB/sec)
Downloading: https://repo1.maven.org/maven2/org/codehaus/plexus/plexus-components/1.1.20/plexus-components-1.1.20.pom
Downloaded: https://repo1.maven.org/maven2/org/codehaus/plexus/plexus-components/1.1.20/plexus-components-1.1.20.pom (3 KB at 4.9 KB/sec)
Downloading: https://repo1.maven.org/maven2/org/codehaus/plexus/plexus/3.1/plexus-3.1.pom
Downloaded: https://repo1.maven.org/maven2/org/codehaus/plexus/plexus/3.1/plexus-3.1.pom (19 KB at 29.7 KB/sec)
Downloading: https://repo1.maven.org/maven2/org/codehaus/plexus/plexus-io/2.0.4/plexus-io-2.0.4.pom
Downloaded: https://repo1.maven.org/maven2/org/codehaus/plexus/plexus-io/2.0.4/plexus-io-2.0.4.pom (2 KB at 3.3 KB/sec)
Downloading: https://repo1.maven.org/maven2/org/codehaus/plexus/plexus-components/1.1.19/plexus-components-1.1.19.pom
Downloaded: https://repo1.maven.org/maven2/org/codehaus/plexus/plexus-components/1.1.19/plexus-components-1.1.19.pom (3 KB at 5.2 KB/sec)
Downloading: https://repo1.maven.org/maven2/org/codehaus/plexus/plexus/3.0.1/plexus-3.0.1.pom
Downloaded: https://repo1.maven.org/maven2/org/codehaus/plexus/plexus/3.0.1/plexus-3.0.1.pom (19 KB at 35.2 KB/sec)
Downloading: https://repo1.maven.org/maven2/backport-util-concurrent/backport-util-concurrent/3.1/backport-util-concurrent-3.1.jar
Downloading: https://repo1.maven.org/maven2/org/codehaus/plexus/plexus-interpolation/1.11/plexus-interpolation-1.11.jar
Downloading: https://repo1.maven.org/maven2/org/slf4j/slf4j-jdk14/1.5.6/slf4j-jdk14-1.5.6.jar
Downloading: https://repo1.maven.org/maven2/org/slf4j/slf4j-api/1.5.6/slf4j-api-1.5.6.jar
Downloading: https://repo1.maven.org/maven2/org/slf4j/jcl-over-slf4j/1.5.6/jcl-over-slf4j-1.5.6.jar
Downloaded: https://repo1.maven.org/maven2/org/codehaus/plexus/plexus-interpolation/1.11/plexus-interpolation-1.11.jar (50 KB at 109.6 KB/sec)
Downloaded: https://repo1.maven.org/maven2/org/slf4j/slf4j-jdk14/1.5.6/slf4j-jdk14-1.5.6.jar (9 KB at 19.0 KB/sec)
Downloading: https://repo1.maven.org/maven2/org/apache/maven/reporting/maven-reporting-api/2.2.1/maven-reporting-api-2.2.1.jar
Downloading: https://repo1.maven.org/maven2/org/apache/maven/doxia/doxia-sink-api/1.1/doxia-sink-api-1.1.jar
Downloaded: https://repo1.maven.org/maven2/org/apache/maven/doxia/doxia-sink-api/1.1/doxia-sink-api-1.1.jar (13 KB at 11.7 KB/sec)
Downloading: https://repo1.maven.org/maven2/org/apache/maven/doxia/doxia-logging-api/1.1/doxia-logging-api-1.1.jar
Downloaded: https://repo1.maven.org/maven2/org/apache/maven/reporting/maven-reporting-api/2.2.1/maven-reporting-api-2.2.1.jar (10 KB at 8.9 KB/sec)
Downloading: https://repo1.maven.org/maven2/commons-cli/commons-cli/1.2/commons-cli-1.2.jar
Downloaded: https://repo1.maven.org/maven2/backport-util-concurrent/backport-util-concurrent/3.1/backport-util-concurrent-3.1.jar (324 KB at 246.3 KB/sec)
Downloading: https://repo1.maven.org/maven2/org/codehaus/plexus/plexus-interactivity-api/1.0-alpha-4/plexus-interactivity-api-1.0-alpha-4.jar
Downloaded: https://repo1.maven.org/maven2/org/apache/maven/doxia/doxia-logging-api/1.1/doxia-logging-api-1.1.jar (12 KB at 7.4 KB/sec)
Downloading: https://repo1.maven.org/maven2/org/sonatype/plexus/plexus-sec-dispatcher/1.3/plexus-sec-dispatcher-1.3.jar
Downloaded: https://repo1.maven.org/maven2/commons-cli/commons-cli/1.2/commons-cli-1.2.jar (41 KB at 26.6 KB/sec)
Downloading: https://repo1.maven.org/maven2/org/sonatype/plexus/plexus-cipher/1.4/plexus-cipher-1.4.jar
Downloaded: https://repo1.maven.org/maven2/org/codehaus/plexus/plexus-interactivity-api/1.0-alpha-4/plexus-interactivity-api-1.0-alpha-4.jar (14 KB at 7.5 KB/sec)
Downloading: https://repo1.maven.org/maven2/org/codehaus/plexus/plexus-utils/3.0.22/plexus-utils-3.0.22.jar
Downloaded: https://repo1.maven.org/maven2/org/sonatype/plexus/plexus-sec-dispatcher/1.3/plexus-sec-dispatcher-1.3.jar (28 KB at 14.4 KB/sec)
Downloading: https://repo1.maven.org/maven2/commons-lang/commons-lang/2.3/commons-lang-2.3.jar
Downloaded: https://repo1.maven.org/maven2/org/slf4j/jcl-over-slf4j/1.5.6/jcl-over-slf4j-1.5.6.jar (17 KB at 8.4 KB/sec)
Downloading: https://repo1.maven.org/maven2/org/apache/maven/enforcer/enforcer-api/1.4.1/enforcer-api-1.4.1.jar
Downloaded: https://repo1.maven.org/maven2/org/sonatype/plexus/plexus-cipher/1.4/plexus-cipher-1.4.jar (14 KB at 6.8 KB/sec)
Downloading: https://repo1.maven.org/maven2/org/apache/maven/enforcer/enforcer-rules/1.4.1/enforcer-rules-1.4.1.jar
Downloaded: https://repo1.maven.org/maven2/org/slf4j/slf4j-api/1.5.6/slf4j-api-1.5.6.jar (22 KB at 11.2 KB/sec)
Downloading: https://repo1.maven.org/maven2/org/apache/maven/shared/maven-common-artifact-filters/1.4/maven-common-artifact-filters-1.4.jar
Downloaded: https://repo1.maven.org/maven2/org/apache/maven/enforcer/enforcer-api/1.4.1/enforcer-api-1.4.1.jar (12 KB at 4.3 KB/sec)
Downloading: https://repo1.maven.org/maven2/org/beanshell/bsh/2.0b4/bsh-2.0b4.jar
Downloaded: https://repo1.maven.org/maven2/org/apache/maven/shared/maven-common-artifact-filters/1.4/maven-common-artifact-filters-1.4.jar (31 KB at 11.2 KB/sec)
Downloading: https://repo1.maven.org/maven2/org/apache/maven/shared/maven-dependency-tree/2.2/maven-dependency-tree-2.2.jar
Downloaded: https://repo1.maven.org/maven2/org/apache/maven/enforcer/enforcer-rules/1.4.1/enforcer-rules-1.4.1.jar (97 KB at 32.6 KB/sec)
Downloading: https://repo1.maven.org/maven2/org/codehaus/plexus/plexus-component-annotations/1.5.5/plexus-component-annotations-1.5.5.jar
Downloaded: https://repo1.maven.org/maven2/commons-lang/commons-lang/2.3/commons-lang-2.3.jar (240 KB at 77.3 KB/sec)
Downloading: https://repo1.maven.org/maven2/org/eclipse/aether/aether-util/0.9.0.M2/aether-util-0.9.0.M2.jar
Downloaded: https://repo1.maven.org/maven2/org/codehaus/plexus/plexus-utils/3.0.22/plexus-utils-3.0.22.jar (240 KB at 76.7 KB/sec)
Downloading: https://repo1.maven.org/maven2/org/codehaus/plexus/plexus-i18n/1.0-beta-6/plexus-i18n-1.0-beta-6.jar
Downloaded: https://repo1.maven.org/maven2/org/apache/maven/shared/maven-dependency-tree/2.2/maven-dependency-tree-2.2.jar (63 KB at 18.4 KB/sec)
Downloading: https://repo1.maven.org/maven2/org/apache/maven/plugin-testing/maven-plugin-testing-harness/1.3/maven-plugin-testing-harness-1.3.jar
Downloaded: https://repo1.maven.org/maven2/org/beanshell/bsh/2.0b4/bsh-2.0b4.jar (276 KB at 81.2 KB/sec)
Downloading: https://repo1.maven.org/maven2/org/codehaus/plexus/plexus-archiver/2.2/plexus-archiver-2.2.jar
Downloaded: https://repo1.maven.org/maven2/org/codehaus/plexus/plexus-component-annotations/1.5.5/plexus-component-annotations-1.5.5.jar (5 KB at 1.2 KB/sec)
Downloading: https://repo1.maven.org/maven2/org/codehaus/plexus/plexus-io/2.0.4/plexus-io-2.0.4.jar
Downloaded: https://repo1.maven.org/maven2/org/codehaus/plexus/plexus-i18n/1.0-beta-6/plexus-i18n-1.0-beta-6.jar (12 KB at 3.2 KB/sec)
Downloaded: https://repo1.maven.org/maven2/org/eclipse/aether/aether-util/0.9.0.M2/aether-util-0.9.0.M2.jar (131 KB at 34.2 KB/sec)
Downloaded: https://repo1.maven.org/maven2/org/apache/maven/plugin-testing/maven-plugin-testing-harness/1.3/maven-plugin-testing-harness-1.3.jar (35 KB at 8.9 KB/sec)
Downloaded: https://repo1.maven.org/maven2/org/codehaus/plexus/plexus-io/2.0.4/plexus-io-2.0.4.jar (57 KB at 14.6 KB/sec)
Downloaded: https://repo1.maven.org/maven2/org/codehaus/plexus/plexus-archiver/2.2/plexus-archiver-2.2.jar (181 KB at 39.7 KB/sec)
[WARNING] Rule 0: org.apache.maven.plugins.enforcer.RequireMavenVersion failed with message:
Detected Maven Version: 3.2.5 is not in the allowed range 3.3.3.
[WARNING] Rule 1: org.apache.maven.plugins.enforcer.RequireJavaVersion failed with message:
Detected JDK Version: 1.6.0-65 is not in the allowed range 1.7.
[INFO] ------------------------------------------------------------------------
[INFO] Reactor Summary:
[INFO] 
[INFO] Spark Project Parent POM ........................... FAILURE [01:59 min]
[INFO] Spark Project Test Tags ............................ SKIPPED
[INFO] Spark Project Launcher ............................. SKIPPED
[INFO] Spark Project Networking ........................... SKIPPED
[INFO] Spark Project Shuffle Streaming Service ............ SKIPPED
[INFO] Spark Project Unsafe ............................... SKIPPED
[INFO] Spark Project Core ................................. SKIPPED
[INFO] Spark Project Bagel ................................ SKIPPED
[INFO] Spark Project GraphX ............................... SKIPPED
[INFO] Spark Project Streaming ............................ SKIPPED
[INFO] Spark Project Catalyst ............................. SKIPPED
[INFO] Spark Project SQL .................................. SKIPPED
[INFO] Spark Project ML Library ........................... SKIPPED
[INFO] Spark Project Tools ................................ SKIPPED
[INFO] Spark Project Hive ................................. SKIPPED
[INFO] Spark Project Docker Integration Tests ............. SKIPPED
[INFO] Spark Project REPL ................................. SKIPPED
[INFO] Spark Project YARN Shuffle Service ................. SKIPPED
[INFO] Spark Project YARN ................................. SKIPPED
[INFO] Spark Project Assembly ............................. SKIPPED
[INFO] Spark Project External Twitter ..................... SKIPPED
[INFO] Spark Project External Flume Sink .................. SKIPPED
[INFO] Spark Project External Flume ....................... SKIPPED
[INFO] Spark Project External Flume Assembly .............. SKIPPED
[INFO] Spark Project External MQTT ........................ SKIPPED
[INFO] Spark Project External MQTT Assembly ............... SKIPPED
[INFO] Spark Project External ZeroMQ ...................... SKIPPED
[INFO] Spark Project External Kafka ....................... SKIPPED
[INFO] Spark Project Examples ............................. SKIPPED
[INFO] Spark Project External Kafka Assembly .............. SKIPPED
[INFO] ------------------------------------------------------------------------
[INFO] BUILD FAILURE
[INFO] ------------------------------------------------------------------------
[INFO] Total time: 02:04 min
[INFO] Finished at: 2016-04-10T20:23:00+08:00
[INFO] Final Memory: 29M/82M
[INFO] ------------------------------------------------------------------------
[ERROR] Failed to execute goal org.apache.maven.plugins:maven-enforcer-plugin:1.4.1:enforce (enforce-versions) on project spark-parent_2.10: Some Enforcer rules have failed. Look above for specific messages explaining why the rule failed. -> [Help 1]
[ERROR] 
[ERROR] To see the full stack trace of the errors, re-run Maven with the -e switch.
[ERROR] Re-run Maven using the -X switch to enable full debug logging.
[ERROR] 
[ERROR] For more information about the errors and possible solutions, please read the following articles:
[ERROR] [Help 1] http://cwiki.apache.org/confluence/display/MAVEN/MojoExecutionException
```

We need to install maven correctly and install the paths properly. The following is in my `~\.bash_profile`.

Note that you need to find the java path using the following command: `/usr/libexec/java_home`
Download the recent version of java and maven from their respective websites ...

 - [maven](http://maven.apache.org/download.cgi)
 - [jdk](http://www.oracle.com/technetwork/java/javase/downloads/jdk8-downloads-2133151.html)


```bash
export LC_ALL=en_US.UTF-8
export LANG=en_US.UTF-8
export QT_API='pyside'
export ETS_TOOLKIT='qt4'
export PATH=/opt/local/bin:$PATH
export CLICOLOR=1
export LSCOLORS=GxFxCxDxBxegedabagaced
export JAVA_HOME=/Library/Java/JavaVirtualMachines/jdk1.8.0_77.jdk/Contents/Home
export M2_HOME=/opt/local/share/java/maven33
export M2=/opt/local/share/java/maven33/bin

##
# Your previous /Users/user/.bash_profile file was backed up as /Users/user/.bash_profile.macports-saved_2015-11-06_at_22:56:47
##

# MacPorts Installer addition on 2015-11-06_at_22:56:47: adding an appropriate PATH variable for use with MacPorts.
export PATH="/opt/local/bin:/opt/local/sbin:/usr/local/mysql/bin:$PATH"
# Finished adapting your PATH environment variable for use with MacPorts.

export PATH=$M2:$M2_HOME:$JAVA_HOME:$PATH
```


Also install jdk 1.7 because that is needed by the installer ...

```bash
export LC_ALL=en_US.UTF-8
export LANG=en_US.UTF-8
export QT_API='pyside'
export ETS_TOOLKIT='qt4'
export PATH=/opt/local/bin:$PATH
export CLICOLOR=1
export LSCOLORS=GxFxCxDxBxegedabagaced
export JAVA_HOME=/Library/Java/JavaVirtualMachines/jdk1.7.0_79.jdk/Contents/Home
export M2_HOME=/opt/local/share/java/maven33
export M2=/opt/local/share/java/maven33/bin

##
# Your previous /Users/user/.bash_profile file was backed up as /Users/user/.bash_profile.macports-saved_2015-11-06_at_22:56:47
##

# MacPorts Installer addition on 2015-11-06_at_22:56:47: adding an appropriate PATH variable for use with MacPorts.
export PATH="/opt/local/bin:/opt/local/sbin:/usr/local/mysql/bin:$PATH"
# Finished adapting your PATH environment variable for use with MacPorts.

export PATH=$M2:$M2_HOME:$JAVA_HOME:$PATH
```

Which points to the right path for the jdk, *even if you have the latest version* for jdk.

```bash
Sankha-desktop:spark-1.6.1 user$ cd /Library/Java/JavaVirtualMachines/
Sankha-desktop:JavaVirtualMachines user$ ls
1.6.0.jdk       jdk1.8.0_77.jdk
Sankha-desktop:JavaVirtualMachines user$ ls
1.6.0.jdk       jdk1.7.0_79.jdk jdk1.8.0_77.jdk
```

Then try again ...

It didnt work either. Se we disabled the zinc build in the `pom.xml` file. And tried again. It finally worked ...
