# BASHRC

Para fazer com que estes arquivos sejam válidos para seu shell Bash, é necessário baixar este repositório e criar links simbólicos do diretório do seu usuário

```
$ git clone https://github.com/GustavoVS/bashrc.git
$ cd bashrc
$ ln -sf $(pwd)/bash_profile ~/.bash_profile
$ ln -sf $(pwd)/bashrc ~/.bashrc
$ . ~/.profile
```

Se preferir faça backup dos seus arquivos antes de removê-los.

