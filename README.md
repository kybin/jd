# jd

copy and paste this code in your .bashrc

```bash
function jd {
    cd -P "${HOME}/.jump/$1"
}
```

source it.

```bash
source ~/.bashrc
```

then

```bash
cd
mkdir .jump
cd .jump
ln -s {destdir} {key}
```

finally, you can jump.

```bash
jd {key}
```
