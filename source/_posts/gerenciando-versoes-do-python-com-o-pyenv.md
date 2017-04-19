title: Gerenciando versões do python com o pyenv
date: 2017-04-18 23:56:47
tags:
    - python
---

Hoje trago uma dica bem valiosa pra quem tem dor de cabeça pra usar várias versões do python no linux. A solução que vos
apresento é o [Pyenv](https://github.com/pyenv/pyenv).

O mais interessente do Pyenv é que ele não é apenas um gerenciador de versões do python, o
[pacote completo](https://github.com/pyenv/pyenv-installer) ainda permite gerenciar inclusive virtualenvs.

Para quem não é do python, um virtualenv é um ambiente isolado python, onde você pode controlar todas as dependências
do mesmo.

Vamos ao que interessa:

#### Instalando o Pyenv

Execute a seguinte linha no seu terminal com o seu usuário normal:

```bash
curl -L https://raw.githubusercontent.com/pyenv/pyenv-installer/master/bin/pyenv-installer | bash
```

<!-- more -->

Adicione as seguintes linhas ao seu `~/.bashrc`:

```bash
export PATH="$HOME/.pyenv/bin:$PATH"
eval "$(pyenv init -)"
eval "$(pyenv virtualenv-init -)"
```

#### Gerenciando versões do python

##### Instalar

```bash
pyenv install 2.7.5
```

No exemplo, basta trocar `2.7.5` pela versão desejada.

##### Ativar

```
pyenv local 2.7.5
```

No exemplo, ativa-se a utilização do python `2.7.5` no diretório atual. Dessa forma,
sempre que você acessar esse diretórió, essa versão do python já vai estar ativada.

##### Desativar

```
pyenv local --unset
```

No exemplo, desativa-se o python que estiver associado ao diretório atual (se existir).

##### Remover

```
pyenv uninstall 2.7.5
```

#### Gerenciando virtualenvs:

##### Criar

```bash
pyenv virtualenv 2.7.5 venv
```

No exemplo, cria-se um virtualenv com o nome `venv` com a versão `2.7.5` do python.

##### Ativar

```bash
pyenv activate venv
```

No exemplo, ativa-se o virtualenv do nome `venv`.

##### Desativar

```bash
pyenv deactivate
```

##### Remover

```bash
pyenv uninstall venv
```

Bem simples, né?

Para mais comandos, basta digitar `pyenv help` no seu terminal que será exibido uma lista com todos os comandos
disponíveis do pyenv.

Links úteis:

- Pyenv: [https://github.com/pyenv/pyenv](https://github.com/pyenv/pyenv)

- Pyenv installer: [https://github.com/pyenv/pyenv-installer](https://github.com/pyenv/pyenv-installer)

- Caso tenha algum problema na instalação do pyenv ou de alguma versão do python: [https://github.com/pyenv/pyenv/wiki/Common-build-problems](https://github.com/pyenv/pyenv/wiki/Common-build-problems)

Qualquer dúvida, podem dizer nos comentários que terei o prazer de ajudar!