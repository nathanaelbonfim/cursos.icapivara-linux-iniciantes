---
title: O que é e como funciona o terminal? >> 002
date: 2021-10-31
author: Nathanael Bonfim
extensions:
    - image_ueberzug
    - terminal
---
# Terminal
## O que é?
CLI - Command Line Interface (Interface de Linha de comando)

## Prompt 
Mostra que o shell está pronto a receber comandos

    usuario@computador ~ $
- *usuario* nome do usuário logado na máquina
- *maquina* nome dado ao computador
- *~*       pasta em que o usuário está
- *$*       tipo de usuário
> $ -> Usuários comuns
> | # -> Usuários root (administradores)

---
# Terminal
## Estrutura de um comando
```sh
    $ ls /home -l
```

- comando
- argumento
- flags

## Prática

```terminal8
docker run -i -it ubuntu:focal /bin/bash
```

---
# Instalando um terminal

### Windows
Git Bash - [https://git-scm.com/](https://git-scm.com/)

### Linux/MacOS
Já possuem um terminal POSIX instalado

## Configurando Git
```sh
    $ git config --global user.name "Seu nome aqui"

    $ git config --global user.email "seuemail@noreply.com"
```
---
# Shell
## Variáveis de ambiente
São variáveis que o shell e outros programas reconhecem durante a execução.

## Manipulando variáveis
    $ NOME=Nathanael

Nesse caso, a variável está disponível apenas no shell atual. Para habilitar em
outros terminais subsequentes, use a palavra reservada `export`.

> Também é possível realizar operações aritméticas com as variáveis de ambiente.

---
# Shell
## Exemplos
| Variável | Conteúdo                                         |
|----------|--------------------------------------------------|
| `$USER`  | Variáveis de ambiente e outras funções           |
| `$PATH`  | Lista com os últimos 1000 comandos digitados     |
| `$PS1`   | Comandos executados no login/logout dos usuários |
| `$SHELL` | nome do usuário executando o shell               |

## Prática
```terminal8
docker run -i -it ubuntu:focal /bin/bash
```

---
# Shell
## Arquivos importantes (bash)

| Arquivo        | Função                                           |
|----------------|--------------------------------------------------|
| `.bashrc`      | Variáveis de ambiente e outras funções           |
| `.bash_history`| Lista com os últimos 1000 comandos digitados     |
| `.bash_logout` | Comandos executados no login/logout dos usuários |

### Prática

```terminal8
docker run -i -it ubuntu:focal /bin/bash
```

---
# Atividade
- [ ] Instalar o git bash
- [ ] Configurar o nome de usuário e e-mail do git
- [ ] Verificar a página de manual de três comandos

---
# Referências
[1] - [shell | Guia Linux](https://guialinux.uniriotec.br/shell/)

[2] - [Introdução ao Shell Linux](https://leg.ufpr.br/~fernandomayer/aulas/ce083/shell-linux.html)
