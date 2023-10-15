# Utilizar poetry e pyenv para versionamento do Python e criação de ambiente virtual
### Instalação

#### Poetry (Linux)

Para instalar o [poetry](https://python-poetry.org/docs/), execute o seguinte comando:

```bash
curl -sSL https://install.python-poetry.org | python3 -
```
#### Poetry (Mac OS)

Para instalar o [poetry](https://python-poetry.org/docs/) no Mac OS, execute o seguinte comando:

```bash
brew install pipx
pipx ensurepath
pipx install poetry
```

#### Pyenv (Linux)
Para instalar o pyenv, siga o conteúdo deste [link](https://gist.github.com/trongnghia203/9cc8157acb1a9faad2de95c3175aa875). Não precisa instalar a parte do **pyenv-virtualenv**. Pois usaremos o poetry para criar um ambiente virtual. Enquanto, o pyenv será para a versão do Python que quisermos utilizar.

*obs.: não esqueça de adicionar os códigos no arquivo `.bashrc`.*

Após instalado ambos, embora o Python já venha instalado em algumas máquinas, iremos instalar outra versão por meio do `pyenv`. Para que evitemos sujar a nossa máquina com instalações indevidas. Por isto, a ideia de ambiente virtual.

#### Poetry (Mac OS)

Para instalar o pyenv no Mac OS, execute:

```bash
brew update
brew install pyenv
```

### Python
O comando abaixo apresenta diversas versões do `python` que o `pyenv` nos dá:
```bash
pyenv install -l
```

Para ficar melhor a pesquisa, você pode executar:
```bash
pyenv install -l | grep 3.12
```
Após escolher qual versão, execute:
```bash
pyenv install 3.12
```

Com o `pyenv` você consegue gerenciar qual versão do `python` quer utilizar globalmente e localmente.

**globalmente**:

o `global` irá representar o python geral da sua máquina

```bash
pyenv global 3.12
```

**localmente**:

o `local` será usado para um projeto em específico

```bash
pyenv local 3.12
```

Agora, inicie um projeto com poetry:
```bash
poetry init
```

esse comando irá te pedir algumas informações, mas você também pode utilizar, o comando:
```bash
poetry new nome-do-projeto
 ```
*obs.: o poetry criará pastas com sua estrutura*


#### Informações extras
Caso o projeto que vc está mexendo já tenha a estrutura do `poetry`, você pode apenas definir a versão local do `python` com `pyenv`, sendo a mesma do projeto. Em seguida, executar:

```bash
pyenv local 3.12
poetry env use 3.12
poetry install
```

**Para adicionar pacotes**

Execute:

```bash
poetry add fastapi
```

**Para atualizar pacotes**

Execute:

```bash
poetry update fastapi
```

**Para remover pacotes**

Execute:

```bash
poetry remove fastapi
```

*obs.: Esses comandos conseguem manter os teus `requirements` atualizados automaticamente. Ao adicionar um pacote é criado um outro arquivo chamado `poetry.lock`*

Caso, tenha a necessidade de atualizar o próprio `poetry`, execute:

```bash
poetry self update
```
