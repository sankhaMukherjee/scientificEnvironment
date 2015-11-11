
## Installing pip for Macports

The problem of `pip` is that the standard installer doesn't play well with the Mac, because the normal `pip` is installed at ...

```bash
Sankha-desktop:ex8 user$ which pip
/usr/local/bin/pip
``` 

So lets install Macports `pip`

```bash
sudo port install py27-pip
sudo port select --set pip pip27
```
Now we have the right version for `pip`

```bash
Sankha-desktop:ex8 user$ which pip
/opt/local/bin/pip
```


### Appendix

Full implementation ...

```bash
Sankha-desktop:ex8 user$ which pip
/usr/local/bin/pip
Sankha-desktop:ex8 user$ sudo port install py27-pip
Password:
--->  Computing dependencies for py27-pip
--->  Dependencies to be installed: pip_select
--->  Fetching archive for pip_select
--->  Attempting to fetch pip_select-0.1_0.darwin_15.noarch.tbz2 from http://jog.id.packages.macports.org/macports/packages/pip_select
--->  Attempting to fetch pip_select-0.1_0.darwin_15.noarch.tbz2 from http://packages.macports.org/pip_select
--->  Attempting to fetch pip_select-0.1_0.darwin_15.noarch.tbz2 from http://mse.uk.packages.macports.org/sites/packages.macports.org/pip_select
--->  Fetching distfiles for pip_select
--->  Verifying checksums for pip_select
--->  Extracting pip_select
--->  Configuring pip_select
--->  Building pip_select
--->  Staging pip_select into destroot
--->  Installing pip_select @0.1_0
--->  Activating pip_select @0.1_0
--->  Cleaning pip_select
--->  Fetching archive for py27-pip
--->  Attempting to fetch py27-pip-7.1.2_0.darwin_15.noarch.tbz2 from http://jog.id.packages.macports.org/macports/packages/py27-pip
--->  Attempting to fetch py27-pip-7.1.2_0.darwin_15.noarch.tbz2 from http://packages.macports.org/py27-pip
--->  Attempting to fetch py27-pip-7.1.2_0.darwin_15.noarch.tbz2 from http://mse.uk.packages.macports.org/sites/packages.macports.org/py27-pip
--->  Fetching distfiles for py27-pip
--->  Attempting to fetch pip-7.1.2.tar.gz from https://pypi.python.org/packages/source/p/pip/
--->  Verifying checksums for py27-pip                                               
--->  Extracting py27-pip
--->  Configuring py27-pip
--->  Building py27-pip
--->  Staging py27-pip into destroot
--->  Installing py27-pip @7.1.2_0
--->  Activating py27-pip @7.1.2_0

To make the Python 2.7 version of pip the one that is run when you execute the commands without a version suffix, e.g. 'pip',
run:

port select --set pip pip27


--->  Cleaning py27-pip
--->  Updating database of binaries
--->  Scanning binaries for linking errors
--->  No broken files found.                             
Sankha-desktop:ex8 user$ port select --set pip pip27
Selecting 'pip27' for 'pip' failed: could not create new link "/opt/local/bin/pip" pointing to "/opt/local/Library/Frameworks/Python.framework/Versions/2.7/bin/pip": permission denied
Sankha-desktop:ex8 user$ sudo port select --set pip pip27
Selecting 'pip27' for 'pip' succeeded. 'pip27' is now active.
Sankha-desktop:ex8 user$ which pip
/opt/local/bin/pip
Sankha-desktop:ex8 user$ 
```