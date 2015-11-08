## Update for 2015-08-23

We want to install octave now so that we can implement some machine learning algorithms. 

 - we know that x code is already installed so we dont need to install it. 
 - We do have to upgrade MacPorts, which may take a while. 

- [Installation Instructions](https://codingnightly.wordpress.com/2015/03/31/install-octaves-extra-packages-on-osx-using-macports/)
- [More stuff here](http://verahill.blogspot.sg/2013/01/327-installing-octave-gnuplot-on-osx.html)
- [availabe ports](https://www.macports.org/ports.php?by=name&substr=octave&page=1&pagesize=50)

```bash
sudo port -v selfupdate
sudo port -v install gcc49 # fortran for Atlas
# Note that it t,akes a long time to install Fortran
sudo port -v install atlas # this takes all night ...
sudo port install -v octave
```

Port installation fails here for 

```bash
MAKEINFO='/bin/sh /opt/local/var/macports/build/_opt_local_var_macports_sources_rsync.macports.org_release_tarballs_ports_math_octave/octave/work/octave-3.8.2/build-aux/missing makeinfo   -I .' \
	/opt/local/bin/texi2dvi --build-dir=t2d_cache  --build-dir=octave.t2d -o octave.dvi  \
	octave.texi
You don't have a working TeX binary (tex) installed anywhere in
your PATH, and texi2dvi cannot proceed without one.  If you want to use
this script, you'll need to install TeX (if you don't have it) or change
your PATH or TEX environment variable (if you do).  See the --help
output for more details.
```

Lets install `texlive`

Discussion on MacTex vs. texlive [here](http://tex.stackexchange.com/questions/244470/how-to-migrate-from-texlive-macports-2014-to-texlive-mactex-2014)

MacTex is better, but I am afraid it may not install anythin within the Macports folder and we will fail to build again. Lets be safe and install texlive ...

```bash
sudo port -v install texlive # this takes a long time to build ...
```

Now lets try one more time ...

```bash
sudo port -v install octave
```
success !!!

## Adding a few things which were not added before

```bash
sudo port selfupdate
sudo port upgrade outdated
sudo port install py27-seaborn
sudo port install py27-scikit-learn
sudo port install py27-scikit-image
sudo port install py27-pymc
sudo port install py27-statsmodels
sudo port install pandoc
```

Current ports available:

```bash
Sankha-desktop:scientificEnvironment user$ port installed
The following ports are currently installed:
  blosc @1.5.2_0
  blosc @1.6.1_2 (active)
  bzip2 @1.0.6_0 (active)
  cairo @1.14.0_0+quartz+x11
  cairo @1.14.2_1+quartz+x11 (active)
  cctools @862_1+llvm35 (active)
  cloog @0.18.2_2
  cloog @0.18.3_0 (active)
  cmake @3.0.2_1
  cmake @3.2.3_0 (active)
  curl @7.40.0_0+ssl
  curl @7.43.0_0+ssl (active)
  curl-ca-bundle @7.40.0_0
  curl-ca-bundle @7.43.0_0 (active)
  cython_select @0.1_0 (active)
  db46 @4.6.21_9
  db46 @4.6.21_10 (active)
  db48 @4.8.30_4 (active)
  db_select @0.1_2 (active)
  dbus @1.8.12_0
  dbus @1.8.16_0 (active)
  dbus-glib @0.102_0
  dbus-glib @0.104_0 (active)
  dbus-python27 @1.2.0_1 (active)
  expat @2.1.0_0 (active)
  fftw-3 @3.3.4_1 (active)
  fontconfig @2.11.1_0 (active)
  freetype @2.5.5_0
  freetype @2.6_0 (active)
  gcc_select @0.1_8 (active)
  gdbm @1.11_1 (active)
  gettext @0.19.4_0 (active)
  ghc @7.8.3_2 (active)
  git @2.3.0_0+credential_osxkeychain+doc+pcre+perl5_16+python27
  git @2.4.3_0+credential_osxkeychain+doc+pcre+perl5_16+python27 (active)
  glib2 @2.42.1_0
  glib2 @2.44.1_0 (active)
  gmp @6.0.0_1 (active)
  gzip @1.6_0 (active)
  hdf5 @1.8.14_0+cxx
  hdf5 @1.8.15-patch1_0+cxx (active)
  hs-aeson @0.7.0.4_1 (active)
  hs-alex @3.1.3_1 (active)
  hs-async @2.0.1.5_1 (active)
  hs-attoparsec @0.10.4.0_4 (active)
  hs-base-unicode-symbols @0.2.2.4_2 (active)
  hs-base64-bytestring @1.0.0.1_5 (active)
  hs-blaze-builder @0.3.3.4_1 (active)
  hs-blaze-html @0.7.0.3_1 (active)
  hs-blaze-markup @0.6.2.0_1 (active)
  hs-conduit @1.2.3.1_1 (active)
  hs-data-default @0.5.3_4 (active)
  hs-data-default-class @0.0.1_3 (active)
  hs-data-default-instances-base @0.0.1_3 (active)
  hs-data-default-instances-containers @0.0.1_3 (active)
  hs-data-default-instances-dlist @0.0.1_4 (active)
  hs-data-default-instances-old-locale @0.0.1_3 (active)
  hs-deepseq-generics @0.1.1.2_1 (active)
  hs-digest @0.0.1.2_5 (active)
  hs-dlist @0.6.0.1_2 (active)
  hs-enclosed-exceptions @1.0.1_1 (active)
  hs-exceptions @0.6.1_1 (active)
  hs-extensible-exceptions @0.1.1.4_3 (active)
  hs-happy @1.19.4_1 (active)
  hs-hashable @1.2.2.0_1 (active)
  hs-highlighting-kate @0.5.11.1_1 (active)
  hs-hslua @0.3.9_2 (active)
  hs-http @4000.2.10_1 (active)
  hs-lifted-base @0.2.1.1_2 (active)
  hs-mmorph @1.0.0_2 (active)
  hs-monad-control @0.3.2.2_2 (active)
  hs-mtl @2.1.3.1_1 (active)
  hs-nats @0.1.2_2 (active)
  hs-network @2.4.2.3_1 (active)
  hs-pandoc-types @1.12.4.1_2 (active)
  hs-parsec @3.1.5_1 (active)
  hs-pcre-light @0.4.0.3_1 (active)
  hs-primitive @0.5.2.1_1 (active)
  hs-quickcheck @2.6_3 (active)
  hs-random @1.0.1.1_5 (active)
  hs-resourcet @1.1.3.3_1 (active)
  hs-scientific @0.2.0.2_1 (active)
  hs-semigroups @0.16.0.1_1 (active)
  hs-sha @1.6.4.1_1 (active)
  hs-stm @2.4.2_3 (active)
  hs-syb @0.4.1_1 (active)
  hs-tagsoup @0.13.3_1 (active)
  hs-temporary @1.2.0.3_1 (active)
  hs-texmath @0.6.6.3_1 (active)
  hs-text @1.1.0.0_1 (active)
  hs-transformers-base @0.4.1_2 (active)
  hs-unordered-containers @0.2.4.0_1 (active)
  hs-utf8-string @0.3.7_5 (active)
  hs-vector @0.10.9.1_1 (active)
  hs-void @0.7_1 (active)
  hs-xml @1.3.13_3 (active)
  hs-yaml @0.8.10.1_1 (active)
  hs-zip-archive @0.1.4_1 (active)
  hs-zlib @0.5.4.1_4 (active)
  ipython_select @0.3_1 (active)
  isl @0.14_2
  isl @0.14.1_0 (active)
  jbigkit @2.1_0 (active)
  jpeg @9a_1 (active)
  kerberos5 @1.13.2_0 (active)
  lcms @1.19_5 (active)
  lcms2 @2.6_0 (active)
  ld64 @2_0 (active)
  ld64-latest @236.3_1+llvm35
  ld64-latest @241.9_0+llvm35 (active)
  libarchive @3.1.2_0
  libarchive @3.1.2_1 (active)
  libcomerr @1.42.13_0 (active)
  libcxx @3.5.1_1
  libcxx @3.6.0_0 (active)
  libedit @20140620-3.1_0 (active)
  libffi @3.2.1_0 (active)
  libgcc @4.9.2_1
  libgcc @5.1.0_1 (active)
  libiconv @1.14_0 (active)
  libidn @1.29_0
  libidn @1.30_0 (active)
  libmng @1.0.10_3 (active)
  libmpc @1.0.2_1
  libmpc @1.0.3_0 (active)
  libpixman @0.32.6_0 (active)
  libpng @1.6.16_0
  libpng @1.6.17_0 (active)
  libxml2 @2.9.2_1
  libxml2 @2.9.2_2 (active)
  libxslt @1.1.28_0
  libxslt @1.1.28_1 (active)
  llvm-3.5 @3.5.1_3
  llvm-3.5 @3.5.2_3 (active)
  llvm_select @1.0_0 (active)
  lzo2 @2.08_0
  lzo2 @2.09_0 (active)
  mpfr @3.1.2-p10_3 (active)
  ncurses @5.9_2 (active)
  netcdf @4.3.2_4+dap+netcdf4
  netcdf @4.3.3.1_2+dap+netcdf4 (active)
  nosetests_select @0.1_0 (active)
  openjpeg @2.1.0_0 (active)
  openssl @1.0.2_0
  openssl @1.0.2c_0 (active)
  p5.16-authen-sasl @2.160.0_0 (active)
  p5.16-cpan-meta @2.143.240_0
  p5.16-cpan-meta @2.150.5_0 (active)
  p5.16-cpan-meta-requirements @2.132.0_0
  p5.16-cpan-meta-requirements @2.133.0_0 (active)
  p5.16-cpan-meta-yaml @0.12.0_0
  p5.16-cpan-meta-yaml @0.16.0_0 (active)
  p5.16-digest-hmac @1.30.0_0 (active)
  p5.16-digest-sha1 @2.130.0_4 (active)
  p5.16-error @0.170.230_0
  p5.16-error @0.170.240_0 (active)
  p5.16-file-slurp-tiny @0.3.0_0 (active)
  p5.16-gssapi @0.280.0_2
  p5.16-gssapi @0.280.0_3 (active)
  p5.16-inc-latest @0.500.0_0 (active)
  p5.16-io-socket-ssl @2.12.0_0
  p5.16-io-socket-ssl @2.16.0_0 (active)
  p5.16-module-build @0.421.100_0
  p5.16-module-build @0.421.400_0 (active)
  p5.16-module-metadata @1.0.26_0
  p5.16-module-metadata @1.0.27_0 (active)
  p5.16-net-libidn @0.120.0_4 (active)
  p5.16-net-smtp-ssl @1.10.0_0
  p5.16-net-smtp-ssl @1.20.0_0 (active)
  p5.16-net-ssleay @1.680.0_0
  p5.16-net-ssleay @1.690.0_0 (active)
  p5.16-parse-cpan-meta @1.441.400_0
  p5.16-parse-cpan-meta @1.441.700_0 (active)
  p5.16-pathtools @3.470.0_1 (active)
  p5.16-perl-ostype @1.8.0_0 (active)
  p5.16-pod-escapes @1.70.0_0 (active)
  p5.16-pod-simple @3.290.0_0
  p5.16-pod-simple @3.300.0_0 (active)
  p5.16-podlators @2.5.3_1 (active)
  p5.16-scalar-list-utils @1.410.0_0
  p5.16-scalar-list-utils @1.420.0_0 (active)
  p5.16-sub-uplevel @0.250.0_0 (active)
  p5.16-term-readkey @2.320.0_1
  p5.16-term-readkey @2.330.0_0 (active)
  p5.16-test-exception @0.360.0_0
  p5.16-test-exception @0.400.0_0 (active)
  p5.16-test-nowarnings @1.40.0_1 (active)
  p5.16-test-simple @1.1.14_0 (active)
  p5.16-test-warn @0.300.0_0 (active)
  p5.16-tree-dag_node @1.240.0_0
  p5.16-tree-dag_node @1.260.0_0 (active)
  p5.16-version @0.991.200_0 (active)
  pandoc @1.12.4.2_1 (active)
  pcre @8.36_0
  pcre @8.37_0 (active)
  perl5 @5.12.4_0+perl5_16
  perl5 @5.16.3_0+perl5_16 (active)
  perl5.16 @5.16.3_1 (active)
  phonon @4.8.3_1 (active)
  pkgconfig @0.28_0 (active)
  popt @1.16_0 (active)
  py26-cython @0.22_0
  py26-cython @0.22_1 (active)
  py26-nose @1.3.1_0
  py26-nose @1.3.1_1 (active)
  py26-numpy @1.9.1_2+gfortran
  py26-numpy @1.9.2_0+gfortran (active)
  py26-setuptools @12.1_0
  py26-setuptools @17.1.1_0 (active)
  py27-alabaster @0.7.2_0 (active)
  py27-altgraph @0.12_0 (active)
  py27-apptools @4.2.0_0
  py27-apptools @4.2.1_0 (active)
  py27-babel @1.3_0 (active)
  py27-backports @1.0_0 (active)
  py27-backports-ssl_match_hostname @3.4.0.2_0 (active)
  py27-bottleneck @1.0.0_0 (active)
  py27-cairo @1.10.0_3 (active)
  py27-certifi @14.05.14_0
  py27-certifi @2015.04.28_0 (active)
  py27-configobj @4.7.2_0 (active)
  py27-cython @0.22_0
  py27-cython @0.22_1 (active)
  py27-dateutil @2.4.0_0
  py27-dateutil @2.4.2_0 (active)
  py27-decorator @3.4.0_0 (active)
  py27-docutils @0.12_0 (active)
  py27-envisage @4.4.0_0 (active)
  py27-functools32 @3.2.3-1_0 (active)
  py27-ipython @2.4.1_0+notebook+parallel+pyqt4+scientific
  py27-ipython @3.1.0_1+notebook+parallel+pyqt4+scientific (active)
  py27-jinja2 @2.7.3_0 (active)
  py27-jsonschema @2.5.1_1 (active)
  py27-macholib @1.7_1 (active)
  py27-markupsafe @0.23_0 (active)
  py27-matplotlib @1.4.2_0+cairo+tkinter
  py27-matplotlib @1.4.3_0+cairo+tkinter (active)
  py27-mayavi @4.4.0_0 (active)
  py27-mistune @0.5_0 (active)
  py27-modulegraph @0.12_1
  py27-modulegraph @0.12.1_0 (active)
  py27-networkx @1.9.1_0 (active)
  py27-nose @1.3.1_0
  py27-nose @1.3.1_1 (active)
  py27-numexpr @2.4_0
  py27-numexpr @2.4.3_0 (active)
  py27-numpy @1.9.1_2+gfortran
  py27-numpy @1.9.2_0+gfortran (active)
  py27-pandas @0.15.2_0
  py27-pandas @0.16.2_0 (active)
  py27-parsing @2.0.3_0 (active)
  py27-patsy @0.3.0_0 (active)
  py27-Pillow @2.8.2_0 (active)
  py27-py2app @0.9_1 (active)
  py27-pyface @4.4.0_1+pyqt4 (active)
  py27-pygments @2.0.2_0 (active)
  py27-pymc @2.3.4_1+gcc48 (active)
  py27-pyobjc @3.0.1_0 (active)
  py27-pyobjc-cocoa @3.0.1_0 (active)
  py27-pyqt4 @4.11.3_0 (active)
  py27-pyside @1.2.2_1 (active)
  py27-readline @6.2.4.1_0 (active)
  py27-requests @2.5.1_0
  py27-requests @2.7.0_0 (active)
  py27-roman @2.0.0_0 (active)
  py27-scientific @2.9.4_0 (active)
  py27-scikit-image @0.11.3_0 (active)
  py27-scikit-learn @0.16.1_0 (active)
  py27-scipy @0.15.1_0+gfortran (active)
  py27-seaborn @0.5.1_0 (active)
  py27-setuptools @12.1_0
  py27-setuptools @17.1.1_0 (active)
  py27-shiboken @1.2.2_3 (active)
  py27-sip @4.16.5_0
  py27-sip @4.16.7_0 (active)
  py27-six @1.8.0_0
  py27-six @1.9.0_0 (active)
  py27-snowballstemmer @1.2.0_0 (active)
  py27-sphinx @1.2.3_0
  py27-sphinx @1.3.1_0 (active)
  py27-sphinx_rtd_theme @0.1.7_0 (active)
  py27-statsmodels @0.6.1_0 (active)
  py27-tables @3.1.1_4
  py27-tables @3.2.0_1 (active)
  py27-tkinter @2.7.9_0
  py27-tkinter @2.7.10_0 (active)
  py27-tornado @4.1_0
  py27-tornado @4.2_0 (active)
  py27-traits @4.4.0_0
  py27-traits @4.5.0_0 (active)
  py27-traitsui @4.4.0_0 (active)
  py27-tz @2014.10_0
  py27-tz @2015.4_0 (active)
  py27-vcversioner @2.14.0.0_0 (active)
  py27-zmq @14.5.0_0
  py27-zmq @14.6.0_0 (active)
  python2_select @0.0_1 (active)
  python26 @2.6.9_1
  python26 @2.6.9_2 (active)
  python27 @2.7.9_0
  python27 @2.7.10_2 (active)
  python_select @0.3_4
  python_select @0.3_5 (active)
  qt4-mac @4.8.6_0
  qt4-mac @4.8.7_0 (active)
  readline @6.3.003_0 (active)
  rsync @3.1.1_0 (active)
  sparsehash @2.0.2_1 (active)
  sphinx_select @0.1_0 (active)
  sqlite3 @3.8.8.2_0
  sqlite3 @3.8.10.2_0 (active)
  sudo @1.8.8_1
  sudo @1.8.13_0 (active)
  swig @3.0.5_0 (active)
  swig-python @3.0.5_0 (active)
  tcl @8.6.3_0+corefoundation+threads (active)
  tiff @4.0.3_4 (active)
  tk @8.6.3_0+quartz (active)
  vtk @6.1.0_0+python27
  vtk @6.2.0_0+python27 (active)
  vtk5 @5.10.1_2+python27+qt4_mac
  vtk5 @5.10.1_3+python27+qt4_mac
  webp @0.4.3_0 (active)
  xorg-kbproto @1.0.6_0 (active)
  xorg-libpthread-stubs @0.3_0 (active)
  xorg-libX11 @1.6.2_0
  xorg-libX11 @1.6.3_0 (active)
  xorg-libXau @1.0.8_0 (active)
  xorg-libxcb @1.11_1+python27 (active)
  xorg-libXdmcp @1.1.1_0
  xorg-libXdmcp @1.1.2_0 (active)
  xorg-libXext @1.3.3_0 (active)
  xorg-renderproto @0.11.1_0 (active)
  xorg-xcb-proto @1.11_1+python27 (active)
  xorg-xcb-util @0.4.0_0 (active)
  xorg-xextproto @7.3.0_0 (active)
  xorg-xproto @7.0.27_0
  xorg-xproto @7.0.27_1 (active)
  xrender @0.9.8_0 (active)
  xz @5.0.7_0
  xz @5.2.1_0 (active)
  zlib @1.2.8_0 (active)
  zmq @3.2.5_0 (active)
  ```
  
  