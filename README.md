# Padrões e tecnicas avançadas com Git e Github

## Introdução

## Iniciando com gitflow
O gitflow é um plugin e também uma metodologia.
O esquema abaixo explica como é a metodologia:
```
main
hotfix/
release/
develop
feature/

```

Para usar o `git flow` é necessário fazer a [instalação](https://github.com/petervanderdoes/gitflow-avh/wiki/Installation).

Teste a instalação, digitando no console:
`git flow`

Repare que ele dá suporte as seguintes funcionalidades:
- init: para iniciar a configuração e uso do git flow;

- feature: usada para demandas novas, que geralmente, partem da branch de develop;

- release: usada para demandas já validadas em develop, que já poderiam ir para prod (master/main) a qualquer momento;

- hotfix:

- bugfix: 
## Assinatura de commits

GPG: É usado, entre outras coisas, para garantir que os commits feitos, foram, de fato, assinados pelo usuário.

Geralmente, a primeira configuração que fazer ao iniciar com o git, é realizar a configuração do usuário e do email que será usado, como por exemplo:

```
# Configurar o nome de usuário
git config --global user.name Markus Vinicius Candido

# Configurar o e-mail do usuário
git config --global user.email markus.candido@gmail.com
```

Com o GPG instalado, vamos configurar para criar nossa GPG key e utilizar para assinar nossos commmits e nossas gerações de tag do git.

```
# Listar se já temos GPG configurado
gpg --list-secret-key --keyid-format LONG



# Criar GPG
gpg --full-generate-key
- kind of key: (1) RSA and RSA
- key size: 4096
- key valid: 1y (1 year) (n = days | Xw = x weeks | Xm = x months | Xy = x years)
- Real name: Markus Vinicius Candido (same of git config user.name)
- Email address: markus.candido@gmail.com (same of git config user.email)
- Comment: Algo que faça você lembrar da chave
- press 'o' (ok)
- Cadastrar uma senha de acesso ao GPG key
# Exportar chave publica criada
gpg --armor --export B4E841012460B662

# Acessar o https://github.com/settings/keys, clicar em "New GPG key" e colar a chave pública exportada anteriormente

# Definir chave gpg padrão para assinatura dos commits
git config --global user.sigingkey=B4E841012460B662
git config --global commit.gpgsign=true
git config --global tag.gpgsign=true

# Configurar a variável de ambiente GPG_TTY
nano ~/.bashrc
export GPG_TTY=$(tty)

source ~/.bashrc


```
## PRs e Code Review

### protegendo branches

## SemVer e Conventional Commits
