# jd

#### Install

copy and paste this code in your .bashrc

```bash
function jd {
    cd -P "${HOME}/.jump/$1"
}
```

source it. then,

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

#### Completion

create ```/etc/bash_completion.d/jd``` and paste this.

```bash
_jd() 
{
    COMPREPLY=()
    if [ -d ~/.jump ]; then
        local dirs=`ls ~/.jump`
        local cur="${COMP_WORDS[COMP_CWORD]}"
        COMPREPLY=($(compgen -W "${dirs}" -- ${cur}))
        return 0
    fi
}
complete -F _jd jd
```
