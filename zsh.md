Remove file extension within directory
```zsh
for f in *.java; do mv $f `basename $f .java`; done;
```

Add extension
```zsh
for f in *; do mv $f ${f}.ts; done;
```

symlink files
```zsh
ln -sf src dist
```