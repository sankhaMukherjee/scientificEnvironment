### Installing Sozi on my Mac : 2015-06020

I follow some of the instructions from [here](https://dl.dropboxusercontent.com/u/2324311/Sozi_Mountain_Lion.html) ...


1. Install [XQuartz](http://xquartz.macosforge.org/landing/) on my Mac because Inskape needs it
2. Install [Inskape](https://inkscape.org/en/doc/tutorials/elements/tutorial-elements.en.html)
3. Sozi - The table version is [13.11](http://sozi.baierouge.fr/pages/download.html).

Sozi is just a bunch of Python scripts which are to be put into the inkscape configuration pages. In the mac they should be here:  

```bash
Sankha-desktop:inkscape user$ ls -l
total 48
-rw-r--r--  1 user  staff   1142 Jun 21 20:59 extension-errors.log
drwxr-x--x  2 user  staff     68 Jun 21 20:58 extensions
drwxr-x--x  2 user  staff     68 Jun 21 20:58 icons
drwxr-x--x  2 user  staff     68 Jun 21 20:58 keys
drwxr-x--x  2 user  staff     68 Jun 21 20:58 palettes
-rw-r--r--  1 user  staff  17883 Jun 21 20:58 preferences.xml
drwxr-x--x  2 user  staff     68 Jun 21 20:58 templates
Sankha-desktop:inkscape user$ pwd
/Users/user/.config/inkscape
Sankha-desktop:inkscape user$ 
```

You just move the entire directory over there ...

As you can tell, `\usr\bin` is already exported in path:

```bash
Sankha-desktop:~ user$ $PATH
-bash: /opt/local/bin:/usr/local/bin:/usr/bin:/bin:/usr/sbin:/sbin:/opt/X11/bin:/usr/texbin: No such file or directory
```
