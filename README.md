# BASHRC

Para fazer com que estes arquivos sejam válidos para seu shell Bash, é necessário baixar este repositório e criar links simbólicos do diretório do seu usuário.

## Alterando o bash de UM USUÁRIO

1 - Faça uma cópia do repositório. Essa cópia pode ser feita em qualquer lugar do sistema, mas recomendamos que você o faça em um espaço que não seja perdido dentro de seu sistema. Isso pode ser feito na pasta /home do usuario por exemplo:
```
$ git clone https://github.com/GustavoVS/bashrc.git
```

2 - Entre dentro da pasta:
```
$ cd bashrc
```
3 - Crie um link simbólico dos arquivos locais que foram baixados para pasta de bash profiles do usuário em questão. A opção -f é para forçar a criação do link caso já existam links anteriores e a opção -s é para links simbólicos ao invés de links reais. 
```
$ ln -sf $(pwd)/bash_profile ~/.bash_profile
$ ln -sf $(pwd)/bashrc ~/.bashrc
```

4 - De um reload no bash:
```
$ . ~/.profile
```

Se preferir faça backup dos seus arquivos antes de removê-los.

## Alterando o Bash de TODOS OS USUÁRIOS de um sistema

Siga os passos 1 e 2. 

3 - Crie um link simbólico dos arquivos locais que foram baixados para pasta de bash profiles GLOBAL DO SISTEMA. A opção -f é para forçar a criação do link caso já existam links anteriores e a opção -s é para links simbólicos ao invés de links reais. 

```
$ ln -sf $(pwd)/bash_profile /etc/profile
$ ln -sf $(pwd)/bashrc /etc/bash.bashrc
```

## Fazendo funcionar no server

1 - Adicione portas ativas para conexão do ssh com sublime: abra o arquivo `/etc/ssh/ssh_config` e adicione a linha abaixo: 

```
RemoteForward 52698 127.0.0.1:52698
```

2 - Abra o sublime

3 - Conecte no server que quer atuar usando o comando `s` + `ip`:
```
$ s user@0.0.0.0
```

4 - Caso mude de usuário, use a seguinte linha para retornar ao bash customizado:
```
$ bash --rcfile /tmp/.bashrc_temp
```


