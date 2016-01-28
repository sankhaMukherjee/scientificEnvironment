Let us first update our repositories ...

```bash
Sankha-desktop:~ user$ sudo port selfupdate

...
dyld-headers is obsolete; please uninstall it.

```

And lots of errors after this ...

```bash
sudo port uninstall dyld-headers
```
Resume stuff ...

```bash
Please note that since version 4.0 IPython was refactored and splitted across several packages under new project named Jupyter.

To make this the default IPython or IPython2 (i.e., the version run by the 'ipython' or 'ipython2' commands), run one or both of:

    sudo port select --set ipython py27-ipython
    sudo port select --set ipython2 py27-ipython
    
To enable support for parallel computing please install py27-ipyparallel port:

    sudo port install py27-ipyparallel
    
To enable support for the Qt console please install py27-pyqt4 and py27-qtconsole ports:

    sudo port install py27-pyqt4
    sudo port install py27-qtconsole
    
To enable support for the notebook please install py27-notebook port:

    sudo port install py27-notebook
```

Some other error:

```bash
--->  Cleaning py27-pyface
--->  Computing dependencies for py27-pymc
--->  Fetching archive for py27-pymc
--->  Attempting to fetch py27-pymc-2.3.6_0+gcc48.darwin_15.x86_64.tbz2 from http://jog.id.packages.macports.org/macports/packages/py27-pymc
--->  Attempting to fetch py27-pymc-2.3.6_0+gcc48.darwin_15.x86_64.tbz2 from http://nou.nc.packages.macports.org/pub/macports/packages.macports.org/py27-pymc
--->  Attempting to fetch py27-pymc-2.3.6_0+gcc48.darwin_15.x86_64.tbz2 from http://sea.us.packages.macports.org/macports/packages/py27-pymc
--->  Fetching distfiles for py27-pymc
Error: Install port:py27-numpy +gcc48
Error: org.macports.fetch for port py27-pymc returned: port:py27-numpy +gcc48 not installed
Please see the log file for port py27-pymc for details:
    /opt/local/var/macports/logs/_opt_local_var_macports_sources_rsync.macports.org_release_tarballs_ports_python_py-pymc/py27-pymc/main.log
Error: Unable to upgrade port: 1
To report a bug, follow the instructions in the guide:
    http://guide.macports.org/#project.tickets
```
    
Lets try to install it ...

```bash
sudo port clean py27-numpy
sudo port install py27-numpy +gfortran
sudo port upgrade outdated 
```

Doesnt work ...

So now,

```bash
sudo port uninstall py27-pymc
```
I dont have `pymc` right now!!!


I have submitted a ticket for this [here](https://trac.macports.org/ticket/50453)