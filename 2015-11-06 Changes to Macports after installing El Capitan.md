
## Macports Update

After installing the Capitan the `macports` needs to be reinstalled. So this is what I have done for that.

### Initial Attempt

1. Install the `Xcode`. <- this is already installed. 
   `xcode-select --install` 
2. Download the Macport for `El Capitan` and `MacPorts-2.3.4-10.11-ElCapitan.pkg` 
3. Update `MacPorts`
   `sudo port selfupdate`
4. Upgrade all existing ports. 
   `sudo port upgrade outdated`
   
I had to do an `xcode-select --install` one more time. This is bacause the the command line tools didnt appear to have been installed. 

> This is going to take a long time, so I shall go to sleep. Get up in the morning and figure out what to do ...

### Issues encountered ...

1. `fltk` had an installation issue and to fix this issue, octave had to be uninstalled. It will be reinstalled once the other ports are updated. (See Appendix, Section 1).

  ```bash
  sudo port deactivate fltk # didnt work
  sudo port uninstall octave # worked
  sudo deactivate fltk # worked
  sudo port upgrade outdated # continue with the installation
  # need to install octave back when I have a chance ...
  ```
2. It asked me do select the right version of python for `cython` and a few other useful installers using the commands

   ```bash
    port select      --set cython cython27
    sudo port select --set ipython py27-ipython
    sudo port install py27-ipyparallel
    sudo port install py27-pyqt4
    sudo port install py27-qtconsole
    sudo port install py27-notebook
    port select --set sphinx py27-sphinx
   ```
   
   will do that later ...  
   
3. There was a problem with `gcc48`. Now we need to figure out how to fix this. A temporary solution is to use `gcc49` which may not work because of the dependencies of `OpenBLAS`. The known dependency is provided here ... [link](https://trac.macports.org/ticket/48471). (See Appendix, Section 2.7).
  
  <hr>
  
  Now in *El Capitan*, it is [not possible](http://superuser.com/questions/279235/why-does-chown-report-operation-not-permitted-on-os-x) to change permissions for certain root folders and files, since they are so important. even with the `sudo` command. So we need to go [rootless ourselves](http://apple.stackexchange.com/questions/193368/what-is-the-rootless-feature-in-el-capitan-really) to make modifications on these files.

  Apparently, there is also this neat trick which can be applied, but doesn't work for me. I tried moving the 
  
  ```bash
   Sankha-desktop:include user$ mv Availability.h Availability.h.old 
   mv: rename Availability.h to Availability.h.old: Operation not permitted
   Sankha-desktop:include user$ 
   ```
   
   So, rootless it is ...
   
   The following is from this [link](http://www.macworld.com/article/2986118/security/how-to-modify-system-integrity-protection-in-el-capitan.html)

   Follow these steps to disable SIP:

   1. Restart your Mac.
   2. Before OS X starts up, hold down Command-R and keep it held down until you see an Apple icon and a progress bar. Release. This boots you into Recovery.
   3. From the Utilities menu, select Terminal.
   4. At the prompt type exactly the following and then press Return: `csrutil disable`
   5. Terminal should display a message that SIP was disabled.
   6. From the  menu, select Restart.

   You can re-enable SIP by following the above steps, but using `csrutil enable` instead.
   
   ```c++
   /* for use marking APIs available info for Mac OSX */
   #if defined(__has_feature)
       #if __has_attribute(availability)
          #define __OSX_UNAVAILABLE                    __OS_AVAILABILITY(macosx,unavailable)
          #define __OSX_AVAILABLE(_vers)               __OS_AVAILABILITY(macosx,introduced=_vers)
          #define __OSX_DEPRECATED(_start, _dep, _msg) __OSX_AVAILABLE(_start) __OS_AVAILABILITY_MSG(macosx,deprecated=_dep,_msg)
       #endif
   #endif
   ```

   <hr>
   
   Changed it. Lets disable the rootless permissions and get back to installation ...
   
   <hr>
   
   No success. I now see 2 places where this needs to be changed. Do the whole routikne again ...
   
   ```c++
		   /* for use marking APIs available info for Mac OSX */
		#if defined(__has_feature)  // << - we need to change the problem here as well ...
		  #if __has_attribute(availability)
		    #define __OSX_UNAVAILABLE                    __OS_AVAILABILITY(macosx,unavailable)
		    #define __OSX_AVAILABLE(_vers)               __OS_AVAILABILITY(macosx,introduced=_vers)
		    #define __OSX_DEPRECATED(_start, _dep, _msg) __OSX_AVAILABLE(_start) __OS_AVAILABILITY_MSG(macosx,deprecated=_dep,_msg)
		  #endif
		#endif

		#ifndef __OSX_UNAVAILABLE
		  #define __OSX_UNAVAILABLE
		#endif

		#ifndef __OSX_AVAILABLE
		  #define __OSX_AVAILABLE(_vers)
		#endif

		#ifndef __OSX_DEPRECATED
		  #define __OSX_DEPRECATED(_start, _dep, _msg)
		#endif


		/* for use marking APIs available info for iOS */
		#if defined(__has_attribute)
		  #if __has_attribute(availability)
		    #define __IOS_UNAVAILABLE                    __OS_AVAILABILITY(ios,unavailable)
		    #define __IOS_PROHIBITED                     __OS_AVAILABILITY(ios,unavailable)
		    #define __IOS_AVAILABLE(_vers)               __OS_AVAILABILITY(ios,introduced=_vers)
		    #define __IOS_DEPRECATED(_start, _dep, _msg) __IOS_AVAILABLE(_start) __OS_AVAILABILITY_MSG(ios,deprecated=_dep,_msg)
		  #endif
		#endif
   ```
   
   ```bash
		--->  Deactivating sudo @1.8.13_0
		--->  Cleaning sudo
		--->  Activating sudo @1.8.14p3_0

		To complete the installation, run:

			/opt/local/bin/sudo /opt/local/sbin/visudo

		Edit as necessary. (See the sudoers manpage for additional information.)

		--->  Cleaning sudo
		--->  Fetching archive for t1utils
		--->  Attempting to fetch t1utils-1.39_0.darwin_15.x86_64.tbz2 from http://jog.id.packages.macports.org/macports/packages/t1utils
		--->  Attempting to fetch t1utils-1.39_0.darwin_15.x86_64.tbz2 from http://packages.macports.org/t1utils
		--->  Attempting to fetch t1utils-1.39_0.darwin_15.x86_64.tbz2 from http://mse.uk.packages.macports.org/sites/packages.macports.org/t1utils
		--->  Fetching 
	```

	This is the rest of the stuff that we need to install
	
	```bash
	Nothing to upgrade.
	Sankha-desktop:~ user$ sudo port install py27-ipyparallel py27-pyqt4 py27-qtconsole py27-notebook
	Sankha-desktop:~ user$ sudo port install octave
	```
	
	Looks like now everything is installed ...



## Appendix

### 1. Problem with `fltk`

There appears to be a problem with fltk. 

```bash
--->  Computing dependencies for fltk-devel
Error: Unable to exec port: Can't install fltk-devel because conflicting ports are active: fltk
To report a bug, follow the instructions in the guide:
    http://guide.macports.org/#project.tickets
Sankha-desktop:scientificEnvironment user$ sudo port deactivate wxwidgets
Password:
Error: port deactivate failed: Image error: port wxwidgets is not active.
Sankha-desktop:scientificEnvironment user$ sudo port install wxwidgets-devel
Error: Port wxwidgets-devel not found
Sankha-desktop:scientificEnvironment user$ sudo port upgrade outdated
--->  Computing dependencies for fltk-devel
Error: Unable to exec port: Can't install fltk-devel because conflicting ports are active: fltk
To report a bug, follow the instructions in the guide:
    http://guide.macports.org/#project.tickets
Sankha-desktop:scientificEnvironment user$ sudo deactivate fltk
```

Didnt know that to do exactly. So tried to deactivate `fltk` ...

```bash
sudo: deactivate: command not found
Sankha-desktop:scientificEnvironment user$ sudo port deactivate fltk
--->  Deactivating fltk @1.3.3_0
--->  Unable to deactivate fltk @1.3.3_0, the following ports depend on it:
--->  	octave @3.8.2_11+atlas+gcc49+glgui
Error: org.macports.deactivate for port fltk returned: Please uninstall the ports that depend on fltk first.
Please see the log file for port fltk for details:
    /opt/local/var/macports/logs/_opt_local_var_macports_registry_portfiles_fltk-1.3.3_0_db0f2c73ff7d87bce8f8a40ef5cb4253a6036cd5e41d883705775cbc899b3ffd-4174/fltk/main.log
Warning: Failed to execute portfile from registry for fltk @1.3.3_0
--->  Deactivating fltk @1.3.3_0
--->  Unable to deactivate fltk @1.3.3_0, the following ports depend on it:
--->  	octave @3.8.2_11+atlas+gcc49+glgui
Error: port deactivate failed: Please uninstall the ports that depend on fltk first.
```

So I uninstalled octave ...

```bash
Sankha-desktop:scientificEnvironment user$ sudo port uninstall octave
--->  Deactivating octave @3.8.2_11+atlas+gcc49+glgui
--->  Cleaning octave
--->  Uninstalling octave @3.8.2_11+atlas+gcc49+glgui
--->  Cleaning octave
```

Then deactivated fltk

```bash
Sankha-desktop:scientificEnvironment user$ sudo deactivate fltk
sudo: deactivate: command not found
Sankha-desktop:scientificEnvironment user$ sudo port deactivate fltk
--->  Deactivating fltk @1.3.3_0
--->  Cleaning fltk
```
And continued with the rest of the installation ...

```bash
Sankha-desktop:scientificEnvironment user$ sudo port upgrade outdated
--->  Fetching archive for p5.16-algorithm-diff
--->  Attempting to fetch p5.16-algorithm-diff-1.190.300_0.darwin_15.noarch.tbz2 from http://jog.id.packages.macports.org/macports/packages/p5.16-algorithm-diff
--->  Attempting to fetch p5.16-algorithm-diff-1.190.300_0.darwin_15.noarch.tbz2 from http://packages.macports.org/p5.16-algorithm-diff
--->  Attempting to fetch p5.16-algorithm-diff-1.190.300_0.darwin_15.noarch.tbz2 from http://mse.uk.packages.macports.org/sites/packages.macports.org/p5.16-algorithm-diff
--->  Computing dependencies for p5.16-algorithm-diff
--->  Fetching distfiles for p5.16-algorithm-diff
--->  Verifying checksums for p5.16-algorithm-diff
--->  Extracting p5.16-algorithm-diff
--->  Configuring p5.16-algorithm-diff
--->  Building p5.16-algorithm-di
```

### 2. Some messages that may be useful 

#### 2.1. I dont know what this is ...

```bash
Don't forget that dbus needs to be started as the local user (not with sudo) before any KDE programs will launch.
To start it run the following command:
 launchctl load -w /Library/LaunchAgents/org.freedesktop.dbus-session.plist
```

#### 2.2. Some information about the Licencing of `py27-sip`

```bash
py27-sip is available under a PSF license with one addition: 

    4. Licensee may not use SIP to generate Python bindings for any C or
       C++ library for which bindings are already provided by Riverbank. 

GPL-2 or GPL-3 licenses are also available. For details see
/opt/local/share/doc/py27-sip/LICENSE [-GPL2 -GPL3]
```

#### 2.3. Backends items which need to be taken care of ...

```bash
If multiple backends are installed, the toolkit backend may be set with environment variables ETS_TOOLKIT and QT_API, e.g., ETS_TOOLKIT=qt4, QT_API=pyqt.
```
#### 2.4. Selecting ports and installing other software 

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

#### 2.5. Dealing with backends in matplotlib in OS X

```bash
-matplotlib
--->  Activating py27-matplotlib @1.5.0_0+cairo+tkinter

The default backend is the interactive Mac OS X backend. Different backends can be specified using the ~/.matplotlib/matplotlibrc file. More details regarding backends can be found in the matplotlib
FAQ:

http://matplotlib.sourceforge.net/faq/installing_faq.html#what-is-a-backend

```

#### 2.6. More selection 

```bash
port select --set sphinx py27-sphinx

```
#### 2.7. Problems with `gcc48`

This is the Fortran 48 compiler... The best thing is to install a later version of R on which it appears to be dependent upon ...


```bash
Error: org.macports.build for port gcc48 returned: command execution failed
Please see the log file for port gcc48 for details:
    /opt/local/var/macports/logs/_opt_local_var_macports_sources_rsync.macports.org_release_tarballs_ports_lang_gcc48/gcc48/main.log
Error: Problem while installing gcc48
To report a bug, follow the instructions in the guide:
    http://guide.macports.org/#project.tickets
Sankha-desktop:scientificEnvironment user$ 
```

Trying to solve using

```bash
Sankha-desktop:scientificEnvironment user$ sudo port install gcc49
```