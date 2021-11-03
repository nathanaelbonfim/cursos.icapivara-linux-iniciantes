---
title: O que é e como usar o SSH? >> 003
date: 2021-10-31
author: Nathanael Bonfim
extensions:
    - image_ueberzug
    - terminal
---

# O que é SSH?
É o nome dada ao protocolo e ao conjunto de ferramentas usados para conexão
através de terminais remotos

## Características
- Todo conteúdo é encriptado
- Baseia-se na troca de chaves públicas
- Pode ser usado em conjunto com senhas
- Usa a porta 22 por padrão
- Tunelamento SSH (port forwarding)
- Conexão e gerenciamento remoto
- Transferência de arquivos
- Automação

---
# Autenticação
## Senha
- Tradicional
- Vulterável a ataques de força bruta
- Pode ser usado de qualquer local

## Chave
- Utiliza o método chave pública-privada
- Mais seguro
- Requer que a chave esteja instalada

---
# Como conectar?
    $ ssh nomeUsuario@enderecoMaquina
É necessário ter um cliente SSH instalado.

`Windows`: PuTTY, GitBash (linha de comando).

`Linux/MacOS`: cliente já instalado.

    $ ssh usuario@servidor

## Prática

```terminal8
bash
```
---
# Como gerar uma chave SSH?
Utilize o utilitário `ssh-keygen`.

    $ ssh-keygen -C seuUsuario@email.com

## Considerações
- Gera uma chave pública (id_rsa.pub) e privada (id_rsa)
- É possível associar _uma senha à chave_
- Por padrão, ela é armazenada na pasta ~/.ssh/

## Permissões
`Privada`: 600 (-rw-------); 
    $ chmod 700 id_rsa

`Pública`: 644 (-rw-------); 
    $ chmod 700 id_rsa.pub

---

# Gerando uma chave SSH na prática
```terminal8
docker run -i -it ubuntu:focal /bin/bash
```
---
# Authorized Keys
Arquivo com todas as *chaves públicas* autorizadas a conectar no servidor.

## Localização e permissões
600 (-rw-------) `~/.ssh/authorized_keys`

## Adicionando uma chave
**Método 1**: Utilize o utilitário `ssh-copy-id`, caso já possua uma conta no servidor.
    $ ssh-copy-id seuUsuario@servidor.com

**Método 2**: Cole a sua chave pública no arquivo authorized_keys do servidor.

    @local  $ cat ~/.ssh/id_rsa.pub # Copie o resultado desse comando
    @remoto $ echo "SUACHAVEAQUI" >> ~/.ssh/authorized_keys

---
# Bônus: arquivo config
Usado para preterminar chaves, hosts e usuários.

*Localização*: ~/.ssh/config

```sshconfig
Host icapivara
    HostName ssh.icapivara.com.br
    User nathanael
    Port 22
    IdentityFile ~/.ssh/icapivara
    IdentitiesOnly yes
```

## Conectando
    $ ssh icapivara

---
# Referências 
[1] - [What is SSH (Secure Shell)](https://searchsecurity.techtarget.com/definition/Secure-Shell)

[2] - [What is SSH and How Does It Work?](https://geekflare.com/understanding-ssh/)

[3] - [Como configurar as chaves SSH no Ubuntu 16.04](https://www.digitalocean.com/community/tutorials/how-to-set-up-ssh-keys-on-ubuntu-1604-pt)
