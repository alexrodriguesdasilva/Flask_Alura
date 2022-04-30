# Chegou a hora de implementar o que vimos na aula!

1) Abra o PyCharm e crie seu projeto. No curso demos o nome de "jogoteca", então não se esqueça de selecionar o Python 3 como interpretador.

2) Crie um arquivo Python com nome de jogoteca.

3) Abra o terminal e escreva a linha abaixo para instalar o flask:

```shell
pip install flask==2.0.2
```

4) No arquivo Python que criamos, importe o flask no topo do arquivo, conforme abaixo:
```python
from flask import Flask
```

5) Crie uma variável que receberá um novo objeto sendo instanciado, conforme o código abaixo:
```python
from flask import Flask

app = Flask(__name__)
```

6) Adicione a linha de código abaixo para rodar sua aplicação, veja a parte final do nosso código.
```python
from flask import Flask

app = Flask(__name__)

app.run()
```

7) Complemente seu código Python definindo um caminho(/inicio) e logo abaixo função (utilizamos o nome Ola para a função teste), veja abaixo:
```python
from flask import Flask

app = Flask(__name__)

@app.route('/inicio')
def ola():
    return '<h1>Olá Mundo!</h1>'

app.run()
```

8) Execute seu arquivo Python e cheque o link fornecido no seu navegador!

OBS: Não se esqueça de adicionar inicio no seu browser, conforme definimos no código.

Certo, aqui temos uma amostra de como subir o servidor Flask. Agora vamos ver como mostrar um HTML.

9) Agora modifique o seu código para usar o helper do flask chamado render_template, primeiro importe o render_template, veja a primeira linha do código:
```python
from flask import Flask, render_template

app = Flask(__name__)

@app.route('/inicio')
def ola():
    return '<h1>Olá Mundo!</h1>'

app.run()
```

10) Crie uma pasta chamada templates e em seguida crie um arquivo HTML dentro dela com o conteúdo abaixo (no curso utilizamos o nome lista.html):

Conteúdo HTML

```html
<!DOCTYPE html>
<html>
  <head>
    <meta charset="utf-8">
    <meta name="viewport" content="width=device-width, initial-scale=1">
    <title>Jogoteca</title>
  </head>
  <body>
    <div class="container">
        <div class="page-header">
            <h1>{{ titulo }}</h1>
        </div>
        <table class="table table-striped table-responsive table-bordered">
            <thead class="thead-default">
                <tr>
                    <th>Nome</th>
                </tr>
            </thead>
            <tbody>
                <tr>
                    <td>God of War</td>
                </tr>
                <tr>
                    <td>Skyrim</td>
                </tr>
                <tr>
                    <td>Valorant</td>
                </tr>
            </tbody>
        </table>
    </div>
  </body>
</html>
```

Agora utilize o render_template para mostrar a página criada.

Modificações em jogoteca para usarmos esse HTML
```python
from flask import Flask, render_template

app = Flask(__name__)

@app.route('/inicio')
def ola():
    return render_template('lista.html');

app.run()
```

Execute e veja que agora temos uma lista sendo mostrada pelo navegador!