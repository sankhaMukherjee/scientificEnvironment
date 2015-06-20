

#Implementing a scientific computational environment on the Mac

### Laptop: 

| Date                 | 2015-06-12 |
|:---------------------|------------|
| OSX version          | 10.10.3 Yosemite


This is the basic installation for Git and iPython. This is absolutely a must. 

```bash
sudo port install git
sudo port install py27-numpy
sudo port install py27-scipy
sudo port install py27-ipython +notebook +parallel +pyqt4 +scientific

sudo port select --set python python27
sudo port select --set cython cython27
sudo port select --set sphinx py27-sphinx
sudo port select --set ipython ipython27
```

Let us now install some scientific libraries which we use all the time

```bash
sudo port install py27-matplotlib  +cairo +dvipng +ghostscript +latex +pdftops +qt4 +tkinter +webagg 

sudo port install py27-pyside
```
Now comes the statistic software which we shall be using for data analysis.

```bash
sudo port install py27-pandas
sudo port install py27-statsmodels
sudo port install py27-seaborn
sudo port install py27-scikit-learn
sudo port install py27-scikit-image
sudo port install py27-pymc
```


3D vizualization 



```bash
sudo port install vtk5 +python27 +qt4_mac +cocoa
sudo port -f activate vtk5 # Activate this port ...

# At this point I had to deactivate this port because
# the new version of mayavi uses vtk6. So there is no 
# need for installing vtk5 anymore ...

sudo port install py27-mayavi

```

