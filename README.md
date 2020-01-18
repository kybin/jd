# jd

#### Install

copy and paste this code in your .bashrc

```bash
function jd {
    cd -P "$HOME/.jd/$1"
}

function _jd {
    COMPREPLY=()
    if [ -d ~/.jd ]; then
        local dirs=`ls ~/.jd`
        local cur="${COMP_WORDS[COMP_CWORD]}"
        COMPREPLY=($(compgen -W "$dirs" -- $cur))
        return 0
    fi
}

complete -F _jd jd
```

source it.

then,

```bash
mkdir $HOME/.jd
cd $HOME/.jd
ln -s {destdir} {key}
```

finally, you can jump.

```bash
jd {key}
```

