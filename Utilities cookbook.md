# Important commands for various utilities


## Macports
```bash
sudo port selfupdate
sudo port upgrade outdated
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




