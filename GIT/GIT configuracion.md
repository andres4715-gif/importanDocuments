# Para hacer la configuración al momento de iniciar con Git:

1. Comando para validar la configuración que tiene git:

```shell
$ git config --list
```

2. Comando para hacer la configuración global al inicio de git, como darle el nombre:

```shell
$ git config --global user.name "Andres Rios"
```

2. Comando para hacer la configuración global al inicio de git, como darle el correo:

```shell
$ git config --global user.email "andres.com"
```

NOTA: Ya con este setup se acaban de agregar los datos y despues de agregar el comando de git

```shell
$ git config --list
```

es posible que la nueva configuración es correcta:

```shell
credential.helper=osxkeychain
user.email=andres.rios@zemmoga.com
user.name=Andres Rios
alias.logline=log --graph --pretty=format:'%Cred%h%Creset -%C(yellow)%d%Creset %s %Cgreen(%cr) %C(bold blue)<%an>%Creset' --abbrev-commit
core.excludesfile=/Users/andresrios/.gitignore_global
difftool.sourcetree.cmd=opendiff "$LOCAL" "$REMOTE"
difftool.sourcetree.path=
```

fin
