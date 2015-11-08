# Important commands for various utilities

## Rootless feature in *El Capitan*
> Sun Nov  8 2015,  08:11:27

The following is from this [link](http://www.macworld.com/article/2986118/security/how-to-modify-system-integrity-protection-in-el-capitan.html)

Follow these steps to disable SIP:

1. Restart your Mac.
2. Before OS X starts up, hold down Command-R and keep it held down until you see an Apple icon and a progress bar. Release. This boots you into Recovery.
3. From the Utilities menu, select Terminal.
4. At the prompt type exactly the following and then press Return: `csrutil disable`
5. Terminal should display a message that SIP was disabled.
6. From the  menu, select Restart.

You can re-enable SIP by following the above steps, but using `csrutil enable` instead.

<hr>

The information is from this [discussion](http://apple.stackexchange.com/questions/193368/what-is-the-rootless-feature-in-el-capitan-really) ...

First: the name "rootless" is misleading, since there's still a root account, and you can still access it (the official name, "System Integrity Protection", is more accurate). What it really does is limit the power of the root account, so that even if you become root, you don't have full control over the system. Essentially, the idea is that it's too easy for malware to get root access (e.g. by presenting an auth dialog to the user, which will cause the user to reflexively enter the admin password). SIP adds another layer of protection, which malware can't penetrate even if it gets root. The bad part of this, of course, it that it must also apply to things you're doing intentionally. But the restrictions it places on root aren't that bad; they don't prevent most "normal" system customization.

Here's what it restricts, even from root:

You can't modify anything in `/System`, `/bin`, `/sbin`, or `/usr` (except `/usr/local`); or any of the built-in apps and utilities. Only Installer and software update can modify these areas, and even they only do it when installing Apple-signed packages. But since normal OS X-style customizations go in `/Library` (or `~/Library`, or `/Applications`), and unix-style customizations (e.g. Homebrew) go in `/usr/local` (or sometimes `/etc` or `/opt`), this shouldn't be a big deal. It also prevents block-level writes to the startup disk, so you can't bypass it that way.

The full list of restricted directories (and exceptions like /usr/local and a few others) is in /System/Library/Sandbox/rootless.conf. Of course, this file is itself in a restricted area.

When you upgrade to El Capitan, it moves any "unauthorized" files from restricted areas to `/Library/SystemMigration/History/Migration-(some UUID)/QuarantineRoot/`.

You can't attach to system processes (e.g. those running from those system locations) for things like debugging (or changing what dynamic libraries they load, or some other things). Again, not too much of a big deal; developers can still debug their own programs.

This does block some significant things like injecting code into the built-in Apple apps (notably the Finder). It also means that dtrace-based tools for system monitoring (e.g. [opensnoop](https://developer.apple.com/library/mac/documentation/Darwin/Reference/ManPages/man1/opensnoop.1m.html)) will not be able to monitor & report on many system processes.

You can't load kernel extensions (kexts) unless they're properly signed (i.e. by Apple or an Apple-approved developer). Note that this replaces the old system for enforcing kext signing (and the old ways of bypassing it). But since v10.10.4 Apple has [had a way to enable trim support for third-party SSDs](http://arstechnica.com/apple/2015/06/latest-os-x-update-allows-you-to-enable-trim-for-third-party-ssds/), the #1 reason to use unsigned kexts has gone away.

If you don't want these restrictions -- either because you want to modify your system beyond what this allows, or because you're developing & debugging something like kexts that aren't practical under these restrictions, you can turn SIP off. Currently this requires rebooting into recovery mode and running the command csrutil disable (and you can similarly reenable it with csrutil enable).

But please stop and think before disabling SIP, even temporarily: do you really need to disable it, or is there a better (SIP-compliant) way to do what you want? Do you really need to modify something in /System/Library or /bin or whatever, or could it go in a better place like /Library or /usr/local/bin etc? SIP may "feel" constraining if you aren't used to it, and there are some legitimate reasons to disable it, but a lot of what it enforces it really just best practice anyway.

References and further info: [WWDC presentation on "Security and Your Apps"](https://developer.apple.com/videos/wwdc/2015/?id=706), a [good explanation by Eldad Eilam](http://www.quora.com/Can-someone-elaborate-on-the-OS-X-10-11-feature-called-Rootless) on quora.com, the [Ars Technica review of El Capitan](https://support.apple.com/en-us/HT204899), and an Apple support article on SIP, and [a deep dive by Rich Trouton](https://derflounder.wordpress.com/2015/10/01/system-integrity-protection-adding-another-layer-to-apples-security-model/).


## Macports

#### 1. Nromal updates

```bash
sudo port selfupdate
sudo port upgrade outdated
```

#### 2. Installing some port

```bash
sudo port install py27-notebook
```

#### 3. Selecting a name for a port for a particular function

```bash
sudo port select --set cython cython27
```

## git

[Tutorial with no deep shit](http://rogerdudler.github.io/git-guide/)


### Initializing and stuff

For a new directory:

```bash
git init
```

For cloning an existing directory

```bash
# git clone <path to directory>
# Example:
git clone https://github.com/sankhaMukherjee/scientificEnvironment
```

### Adding an existing file to the Git website

`working directory` $\rightarrow$ `Stage` (Index) $\rightarrow$ `commit`

```bash
git add fileName
git add *
git commit -m "This is some description"
git push origin master
```




