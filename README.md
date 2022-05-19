# curso_flask
Curso Flask: crie uma webapp com Python - Alura
01 - Criando uma aplicação web super rápido

1 - Apresentação

[00:00] Seja bem-vindo(a) ao curso de Flask: crie uma webapp com Python, meu nome é Bruno Divino, faço parte do time de instrutores aqui da Alura e eu vou acompanhar você nessa sua jornada de aprendizagem a respeito do microframework de desenvolvimento web Flask.

[00:13] Então, você vai aprender tudo que precisa saber a respeito do Flask e como colocar uma aplicação web no ar de forma rápida e eficiente através de um projeto que vamos desenvolver juntos.

[00:24] Então vai ser um website chamado o Jogoteca, em que vamos colocar uma lista de jogos que podemos adicionar, logar, mas tudo isso vamos ver com calma, então não vou dar mais spoilers, vamos ver daqui a pouco.

[00:37] Deixa eu falar um pouco então dos pré-requisitos para fazer esse curso, é interessante que você tenha conhecimentos a respeito do protocolo HTTP, então principalmente os métodos, post e get, que vamos utilizar bastante.

[00:49] É interessante também que você tenha conhecimento a respeito de orientação a objetos em Python, então aquele paradigma que usamos bastante na linguagem e que é legal de sabermos para fazer esse curso.

[01:00] E precisamos também saber um pouco de HTML e CSS, ter uma base, porque vamos trabalhar com aplicações web, vamos trabalhar com estruturação do site e um pouco com a estilização dele também, então é interessante ter uma base.

[01:16] A boa notícia é que todos esses conteúdos têm na nossa plataforma da Alura, então, tem cursos a respeito dessas temáticas. Basta você ir lá na página principal aqui desse curso, subir lá, scrollar lá para cima, no canto direito superior que vai ter uma lista de links para os cursos a respeito dessas temáticas e você pode ir lá dar uma checada, ver como que é a coisa e se você já tem conhecimento a respeito dessas temáticas, então você já está pronto e já podemos seguir. Então vamos começar finalmente, se acomoda, pega uma água e vamos lá!


2 - Saudação e Ambiente

Quero lhe dar as boas vindas a esse curso e espero que você tenha uma ótima jornada de aprendizagem ao decorrer do curso! Passo a passo, vamos desbravar juntos os mistérios desse Microframework de desenvolvimento web com Python chamado Flask.


Divisão das Aulas

Aula
O que vamos aprender?
Criando uma aplicação web super rápido
Inicializar a nossa aplicação e organizar os primeiros templates
Listando jogos usando o Flask
Mostrar uma lista de jogos e utilizar valores dinâmicos
Criação de um novo jogo
Receber dados de formulário e resolver métodos
Melhorando o código e a usabilidade
Estilizar a aplicação e utilizar URLs dinâmicas
Autenticando usuários com sessão do Flask
Criar tela de login e utilizar Sessions
Implementando autorização para criar Jogos
Restringir acessos e criar novos usuários

Preparando o ambiente


Para conseguir acompanhar este curso, é recomendado que você tenha o Python 3 instalado.

Caso necessite ajuda para instalação do Python, recomendamos os seguintes links:

- Passo a passo para instalar o Python3 no Windows.
- Passo a passo para instalar em outros sistemas operacionais.

Também recomendamos utilização do PyCharm Community como IDE para esse curso, entretanto é válido lembrar que existe uma variedade de opções como o VScode e Sublime Text.

- PyCharm Community para Windows
- PyCharm Community para Linux
- PyCharm Community para MacOS

Versões utilizadas:

- Python: 3.9.9
- Flask: 2.0.2
- PyCharm: 2021.3.2
- Bootstrap: 5.1.x

3 - O que é Flask?


[00:00] Antes de colocarmos a mão na massa, antes de adentrarmos realmente no projeto, vamos dar uma contextualizada, vamos ver o que que é o Flask de fato, da onde que ele surgiu, o que é essa coisa de ser um microframework.

[00:12] Então vamos lá, o Flask é um framework que foi lançado em 2010, ele é de código aberto, e foi feito pelo desenvolvedor Armin Ronacher com um objetivo muito modesto na verdade, muito simples, bem direto ao ponto, que é ser um framework capaz de colocar uma aplicação web de forma rápida e eficiente.

[00:31] E quais são as suas principais características? Tanto naquela época quanto ainda hoje, é a sua simplicidade, a sua rapidez e a sua eficiência. Eu já meio que dei a dica. E eu tenho que chamar atenção para a simplicidade, a simplicidade é muito importante porque ela eleva as outras, ela eleva a sua rapidez de execução de código e a sua eficiência principalmente em aplicações menores.

[00:52] Aplicações menores, simplicidade, será então que o Flask é um framework que só funciona para aplicações menores? Será que ele deixa a desejar se comparado a outros frameworks porque ele é muito simples? Não, não exatamente, não mesmo na verdade.

[01:11] A simplicidade dele é dado o fato de que quando ele estava sendo desenvolvido, a intenção era criar um núcleo do Flask que só tivesse as bibliotecas essenciais para se colocar uma aplicação no ar.

[01:24] Então, vamos imaginar que o Flask seja uma peça de lego, o núcleo do Flask seja uma peça de lego. Então se colocaram as bibliotecas essenciais para se colocar uma aplicação web no ar, para se configurar, desenvolver uma aplicação web, que é a Jinja e Werkzeug, e fizeram ele de uma forma que ele fosse extensível, que fosse capaz de outros blocos se conectarem a ele, conforme o desenvolvedor ficasse interessado, conforme o projeto demandasse.

[01:52] Então se o desenvolvedor precisa conectar uma biblioteca que seja capaz de fazer uma conexão com banco de dados, ou que seja capaz de fazer o envio de e-mails, então o desenvolvedor teria a capacidade de conectar isso, estender isso ao núcleo do Flask.

[02:09] Mas isso é uma vantagem? Isso é uma vantagem, ele dá duas grandes vantagens ao desenvolvedor.

[02:18] A primeira é que o desenvolvedor tem mais controle a respeito do framework dele, sabe exatamente o que tem no framework, ele sabe que tem o essencial, que é aquilo que já vem no núcleo do Flask, e sabe que tem as bibliotecas que ele precisa para fazer a aplicação dele acontecer, essa coisa do banco de dados, a biblioteca do banco de dados, a biblioteca do e-mail, várias outras, então ele vai colocando na medida que ele tem a necessidade, isso dá um controle maior para ele do que é o framework, do que está sendo.

[02:44] E sem falar que também como não tem código extra, código que não está sendo usado ali dentro, isso faz com que o framework acaba ficando mais leve e a execução acaba sendo mais rápida, então essas são duas grandes vantagens do Flask.

[03:01] E por que que ele é um microframework, ele é considerado um microframework? Justamente por causa dessa característica dele, do núcleo ter apenas o essencial para se colocar as coisas no ar, enquanto a maioria dos frameworks já tem coisas embutidas, o Flask ele só tem o essencial e pode daí sim acoplar coisas estendidas nele, as bibliotecas estendidas, então isso que faz dele microframework, então tem que colocar até a entre aspas isso.

[03:26] E isso dá uma grande vantagem, e isso faz dele um dos melhores frameworks do Python, e eu acho que existe no mercado também, e um grande competidor também.

[03:39] Para finalizar aqui então, vou mostrar então um pouco do site do Flask, documentação do Flask, eu estou aqui no site do Flask aqui contém a documentação dele, o que é uma coisa muito importante para qualquer desenvolvedor que está iniciando, você ficar em constante contato com a documentação da tecnologia que você está utilizando, porque ela pode ter muitas respostas para muitas das suas dúvidas.

[04:01] Vamos desenvolver um projeto ao decorrer do curso, e é interessante que conforme você vai fazendo o projeto, e vai querendo entender um pouco mais sobre determinado conceitos ali do código, eu vou explicando mais ao longo do curso, mas é interessante que você saiba que exista essa página, que exista essa documentação e que ela pode tirar muitas das suas dúvidas e não apenas tirar suas dúvidas mas te inspirar a fazer várias outras questões, tem modelos, exemplos e estruturas aqui do Flask que ele te ensina como usar.

[04:32] Então no próximo vídeo já vamos começar colocando a mão na massa, começar a fazer o projeto de fato, te vejo lá!


Documentação: https://flask.palletsprojects.com/en/2.1.x/

4 - Para saber mais: Flask vs Django

No vídeo anterior vimos alguns dos principais aspectos do Flask que o tornam uma das melhores opções de framework de desenvolvimento web para Python. Contudo, é importante ressaltar que existe outro pacote bem utilizado no mercado chamado Django. No artigo a seguir, fazemos a comparação de vantagens e desvantagens de ambas tecnologias, fazendo uma análise das principais características das duas.

- Artigo Django ou Flask: Características, semelhanças e diferenças

5 - A primeira aplicação

[00:00] Então vamos começar aqui finalmente com nosso projeto. Nosso projeto vai ser um sitechamado Jogoteca, uma aplicação chamada Jogoteca, e vai se tratar de um siteque exibe lista de jogos, então vai exibir lá nome do jogo, a plataforma o qual o jogo pertence, o consoleo qual o jogo pertence, vai possibilitar também que cadastremos novos jogos e que façamos login, e só quem tiver login vai conseguir acessar as páginas de lista de jogos de criar um novo jogo.

[00:32] Então vamos ter um sistema de restringir acesso, que vai ser bem interessante, vamos conseguir cadastrar os jogos a partir do próprio site, ele instala os jogos, vai ser bem interessante.

[00:43] Mas antes de começar vamos lembrar como que funciona a web, vamos lembrar todas as questões a cerca do protocolo HTTP, então como que funciona? Temos um navegador, e na barra de endereço do navegador colocamos o endereço do sitee acessamos o site, mas como que isso funciona?

[01:02] Basicamente temos o servidor que é aonde fica as informações do sitepropriamente dito, e o que acontece é que o nosso navegador faz uma requisição uma request, para o servidor para ele liberar as informações a respeito daquele sitepara o nosso no navegador e liberar o acesso para nós.

[01:20] E o servidor responde isso com uma responsee a partir daí temos acesso ao site, mas que que isso tem a ver? Você vai ver que no nosso caso aqui quem vai fazer o papel do servidor, vai ser o Flask, então momentaneamente vamos ter o Flask, frameworkFlask, como o servidor.

[01:39] Vamos começar o projeto de fato, deixa eu acessar aqui o Pycharm, que vai ser a IDE que vamos utilizar e eu vou vir aqui na barra superior em novo projeto na parte superior da tela, “New Project”, em "Location" vou digitar Jogoteca, vou esperar ele criar, ele está criando um ambiente virtual para fazermos isso, isso é a vantagem do Pycharm, já cria um ambiente virtual para fazermos tudo certo, e ele já dá esse arquivo “main.py” para nós, só que não vamos usar, vamos criar o nosso próprio, então eu vou clicar em cima dele com o botão direito do mouse e escolher e opção "Delete" para deletar e em seguida "Ok".

[02:22] E daí eu vou criar um novo arquivo.pyque é aonde vamos deixar o projeto mesmo. Vou clicar aqui na lateral esquerda em cima da pasta do projeto e criar um novo arquivo Python selecionando "New" e depois "Python gile" e digitar “jogoteca” e foi, criamos um arquivo da Jogoteca.

[02:43] Vou aumentar aqui um pouco a letra e vamos digitar em jogoteca.py, from flask import Flask, então temos aqui, por que essa repetição de nomes? Porque um estamos nos referenciando a biblioteca que é o Flask, e a outra estamos importando a função Flask que vai nos permitir criar a aplicação.

[03:07] Só que tem um problema, porque o Flask ele não é uma biblioteca embutida do Python, é uma biblioteca que temos que baixar, temos que fazer o download disso, então vamos fazer o download.

[03:18] Vamos vir aqui embaixo da tela na quarta opção "terminal", o Pycharm já dá essa opção para nós acessarmos o terminal, também podemos selecionar as teclas “Alt + F12” para abrir o terminal.

[03:29] Então clicamos aqui na barra inferior para aparecer o terminal, deixa eu aumentar a letra aqui, e vamos usar o instalador pippara fazer a instalação do Flask, então podemos fazer assim, podemos digitar, pip install flask.

[03:46] Só que se eu fizer isso ele sempre vai pegar a versão mais atualizada do Flask, isso é bom por um motivo de que sempre temos a versão mais atualizada do Flask e tudo certo. Só que imagina o seguinte, você está desenvolvendo um projeto agora com a versão mais atualizada do Flask, ai por algum motivo daqui a três meses você quer voltar a ver essa aplicação, mas está em outro computador, está em um computador do seu amigo, sei lá, e você conseguiu os arquivos do projeto.

[04:10] A versão do Flask já é outra, já se atualizou e você vai utilizar aquele mesmo projeto, vai instalar a versão mais atualizada de meses depois que você já devolveu aquele projeto e vai dar uma incompatibilidade, acaba dando uma incompatibilidade.

[04:25] Então não é uma boa prática sempre instalarmos a última versão do Flask, porque às vezes pode dar um problema de compatibilidade quando vamos testar a nossa aplicação em tempos diferentes, fazemos a aplicação hoje, vamos testar daqui a três meses, pode ser que o a biblioteca do Flask mudou, ou alguma atualização aconteceu e já não vai mais funcionar.

[04:47] Então sempre temos que acostumar a ver uma versão específica do Flask e selecionar ela dando um pip install flask==e no caso aqui vamos usar 2.0.2, essa é a versão que vou utilizar do Flask para fazer o projeto, então vamos dar um “Enter”, ele vai procurar e fazer a instalação, já fez a instalação, vou minimizar essa tela do terminal, e agora ele já vai importar em from flask import Flaska função que precisamos para iniciarmos a aplicação.

```
pip install flask==2.0.2COPIAR CÓDIGO
```

[05:22] Agora vamos começar criando uma variável onde vamos colocar a aplicação em jogoteca.py, então vamos criar essa variável app=, onde vamos chamar a função Flask(), e dentro dessa função Flask vamos passar underline underline name, app = Flask(__name__), esse namefaz uma referência ao próprio arquivo, garantindo que isso vai fazer rodar a aplicação.

[05:54] Então já criamos uma boa parte, e para fazer rodar essa aplicação temos que terminar isso daqui com app.run(), e isso vai fazer rodar a nossa aplicação, só que ainda não está pronto, porque não colocamos nenhuma informação no nosso sitepara colocar uma informação no site, vamos precisar criar uma rota.

[06:17] E vamos fazer isso a partir do `@app.routee vamos criar uma nova rota, e daí precisamos nomear essa rota, então eu vou colocar’/inicio’` que vai ser o nosso início, então assim criamos uma nova rota, só que toda vez que criamos uma nova rota vamos precisar de uma função que vai definir o que existe dentro dessa rota.

[06:42] Vamos colocar aqui o nome da função de "olá", def ola():, vamos fazer inicialmente uma saudação, para aparecer alguma coisa lá na tela do site, vou colocar um "olá mundo", então vou colocar returne digitar o "olá mundo", ’Olá mundo’, pronto.

[07:11] Contudo, temos que lembrar que não estamos lidando com só o terminal do Python, estamos fazendo um site, e na web não se é entendido esse tipo de linguagem, não podemos só colocar uma stringlá e ela vai aparecer, precisamos trabalhar com HTML.

[07:28] Então vamos colocar uma tagaqui, crua aqui mesmo de h1, só para aparecer no sitede forma correta, essa aqui é uma tagde título <h1>Olá Mundo!</h1>e pronto, agora sim, vai aparecer alguma coisa lá no site.

Código em jogoteca.py:

```
from flask import Flask


app = Flask(__name__)


@app.route('/inicio')
def ola():
    return '<h1>Olá Mundo!</h1>'    


app.run()COPIAR CÓDIGO
```

[07:49] E para rodar essa aplicação vamos clicar com o botão direito em cima do código e selecionar “Run Jogoteca” e vai começar a rodar o Jogoteca, vai ser exibido o terminal embaixo e ele vai estar dizendo em que endereço ele vai estar rodando isso, que no caso aqui é o endereço da nossa homeque é http://127.0 0.1:5000/, podemos abrir essa página clicando em cima aqui e vai abrir no navegador.

[08:21] Está aqui, abriu no navegador a página, só que deu um problema, ele deu um not found. O que aconteceu foi que colocamos uma rota para ele, estipulamos uma rota de ser barra início, /inicio, então ele ficou confuso, não sabe para onde que ele tem que ir, então vamos colocar no navegador “127.0.0.1:5000/inicio” e dar um “Enter”, e finalmente apareceu o “Olá mundo”.

[08:53] Então agora, já conseguimos colocar nossa aplicação no ar, ela já está funcionando, já está inclusive conversando conosco, dando um "olá" para nós. Então no próximo vídeo vamos adentrar um pouco mais no projeto e aprimorar um pouco mais. Então fica aí para o próximo vídeo!



6- Para saber mais: Instalação Flask

Caso ainda tenha ficado alguma dúvida a respeito da instalação do Flask, temos um artigo dedicado especialmente às boas práticas de uso do framework. Indo desde a criação de um diretório para o projeto ao código de instalação do pacote Flask.
- Artigo Flask: Instalação

Um ponto importante do artigo é a criação de um ambiente virtual ao se trabalhar com um projeto. No caso da utilização da IDE PyCharm, já temos a oportunidade da criação de um ambiente virtual juntamente com a criação do projeto.

7- A ferramenta PIP

Durante o curso utilizaremos várias ferramentas que nos ajudarão a criar a nossa app de Jogoteca. O Python tem uma ferramenta muito útil chamada pip. Em um dos vídeos, inclusive, utilizamos o pip3. Qual é a função desta ferramenta?

O pip instala pacotes de um repositório na internet.
O pip é o gerenciador de pacotes do Python e acesso o índice de pacotes Python (pypi).

8- Para saber mais: definindo versões com PIP

O pip é uma ferramenta muito prática para instalar pacotes Python de terceiros. Com ele, conseguimos fazer definições de versão como vimos no vídeo.
```
pip install flask==2.0.2
```

Existem mais formas de definir ou restringir versões a serem instaladas no seu ambiente. Vamos ver alguns exemplos:

- ~=: versão compatível - pode ser qualquer versão mais atual que não quebre compatibilidade com a definida.
```
# pegaria a 2.0.2 que é última versão compatível com a 2.0.0
pip3 install flask~=2.0.0 
```

- ==: versão exata - define uma versão fixa que deve ser instalada (como vimos no vídeo).
- !=: exclusão de versão - define a versão que não é para instalar, pegando assim a mais atual sem ser a definida.
- <=, >=: versão maior ou igual e menor ou igual - ajuda a restringir versões, inclusive a definida.
- <, >: versão maior ou menor - ajuda a restringir versões, excluindo a definida.

09 - Mostrando página HTML

[00:00] Então já criamos a aplicação, já colocamos no ar e inclusive criamos uma rota para ela início, e ela está se comunicando conosco até aqui dizendo um "olá mundo". Só que ainda está meio crua, toda a página assim, ainda está faltando um pouco de estrutura e quando eu falo de estrutura, me refiro a HTML, que vai dar uma visualização melhor para o site.

[00:22] Vamos voltar lá para o projeto e vamos ver onde está o HTML, está na linha 7, colocamos só para que pudéssemos exibir esse "olá mundo", só que isso não é o ideal, o ideal é que tenhamos uma pasta separada com arquivos HTMLs e fazer a ligação desses arquivos HTMLs com essa página Python, ao invés de colocar o HTML direto no código.

[00:45] Logo, quando estamos mexendo com Flask, existe uma padronização de sempre usarmos uma pasta chamada templates. Então vamos criar essa pasta no projeto com o botão direito do mouse "New" e em seguida "Directory", criamos um diretório chamado templates, então essa é a padronização que temos do Flask.

[01:12] E em templates vou fazer o seguinte, vou criar um arquivo HTML com nome de lista em cima da pasta templates selecionando o botão direito do mouse "New" e depois "HTML File" e vamos nomear de "lista". Então, temos um arquivo lista, esse código que já vem pré-pronto, mas não vamos usar e podemos remover, vamos usar um código que já tenho, que já está pronto para continuarmos com o curso e vamos criar esse arquivo lista.html com esse HTML.

Código lista.html:

```
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
            <h1>Jogoteca</h1>
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

[01:41] Está aqui o HTML, mas como vamos fazer conexão desse arquivo lá com o arquivo do Python? Então vamos voltar para o Jogoteca, em jogoteca.py, então a primeira coisa que vamos fazer é remover '<h1>Olá Mundo!</h1>', porque será substituído.

[01:59] Como que trazemos o HTML (lista.html) para o arquivo do Python (jogoteca.py)? Vamos usar um helper do Flask chamado render template. Então vamos chamar ele primeiro, vamos importar ele após o import do Flask, render_template, ele já até completou para nós, e vamos chamar ele após o return, render_template() e dentro do render template vamos passar o nome do arquivo HTML que queremos, e o Flask já sabe por causa dessa padronização que está na pasta templates então só precisamos passar o nome mesmo, que no caso seria, lista.html. E é isso.

```
from flask import Flask, render_template

app = Flask(__name__)

@app.route('/inicio')
def ola():
    return render_template('lista.html')    

app.run()
```

[02:49] Então vamos salvar, "Ctrl S”, e rodar de novo a nossa Jogoteca, que no caso aqui seria “Ctrl + F5”, ou clicando aqui nessa seta verde da lateral esquerda em abaixo de "Run" que também funciona, então estamos rodando de volta. Agora voltando para a aplicação no navegador e dar um refresh, note que já está aqui toda a informação, já temos aqui uma lista de jogos que já está pronto lá daquele HTML.

[03:20] Assim, o site já está ficando um pouco melhor, já está se ajeitando melhor, só que ainda tem um problema, porque se voltarmos no arquivo HTML, e se eu quisesse por exemplo mudar o título da Jogoteca, na linha 11, não quero colocar Jogoteca, quero que fique Jogos, porque se formos lá no site, está escrito Jogoteca e quero que seja exibido "jogos", Jogoteca é o nome do site, quero que fique o nome Jogos.

[03:46] Eu teria que acessar lá o nosso código e alterar aqui direto no HTML, isso não é uma boa prática, quero fazer alterações direto em jogoteca.py, vamos aprender como faríamos isso na próxima aula.



10- Criação de aplicação com página web

Usando flask, com poucas linhas, se torna possível criar uma aplicação que mostra conteúdo no browser, seja com html ou texto.

Assinale a alternativa correta:

Para mostrar uma página html no flask basta usar a função render_template com o nome do arquivo html que deve estar na pasta convencionada.

Se o nome do arquivo html que queremos usar na nossa aplicação fosse formulario.html, então o código ficaria:
```
render_template(‘formulario.html’)
```

11 - Para saber mais: definindo portas para aplicação

Nem sempre queremos rodar nossa aplicação na porta 5000 ou mesmo deixar o nosso endereço como 127.0.0.1.

Se eu quiser usar a porta 8080 para aplicação ou até mesmo permitir acessos externos à aplicação definindo o host como 0.0.0.0, como devo proceder?

Quando executamos nossa aplicação Flask utilizamos uma instância do Flask e chamamos o método run. Perceba que quando fazemos isto no vídeo não passamos nenhum parâmetro para este método.

Para definir a porta como 8080 e o host como 0.0.0.0 devemos chamar o run da seguinte maneira.

```
# trecho da app
app.run(host='0.0.0.0', port=8080)
```

Observação: não utilizar estas definições para produção, estas opções foram preparadas para ajudar no ambiente de desenvolvimento.

12- Faça como eu fiz: criando uma aplicação

Chegou a hora de implementar o que vimos na aula!

1) Abra o PyCharm e crie seu projeto. No curso demos o nome de "jogoteca", então não se esqueça de selecionar o Python 3 como interpretador.

2) Crie um arquivo Python com nome de jogoteca.

3) Abra o terminal e escreva a linha abaixo para instalar o flask:

```
pip install flask==2.0.2
```

4) No arquivo Python que criamos, importe o flask no topo do arquivo, conforme abaixo:

```
from flask import Flask
```

5) Crie uma variável que receberá um novo objeto sendo instanciado, conforme o código abaixo:

```
from flask import Flask

app = Flask(__name__)
```

6) Adicione a linha de código abaixo para rodar sua aplicação, veja a parte final do nosso código.

```
from flask import Flask

app = Flask(__name__)

app.run()
```

7) Complemente seu código Python definindo um caminho(/inicio) e logo abaixo função (utilizamos o nome Ola para a função teste), veja abaixo:

```
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

```
from flask import Flask, render_template

app = Flask(__name__)

@app.route('/inicio')
def ola():
    return '<h1>Olá Mundo!</h1>'

app.run()
```

10) Crie uma pasta chamada templates e em seguida crie um arquivo HTML dentro dela com o conteúdo abaixo (no curso utilizamos o nome lista.html):

Conteúdo HTML

```
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

```
from flask import Flask, render_template

app = Flask(__name__)

@app.route('/inicio')
def ola():
    return render_template('lista.html');

app.run()
```

Execute e veja que agora temos uma lista sendo mostrada pelo navegador!

02 - Listando jogos usando o Flask

1 - Projeto da aula anterior

2- Adicionando conteúdo dinâmico

[00:00] Então no último vídeo expliquei que não era uma boa prática ficarmos alterando as coisas aqui direto no HTML, então aqui no nosso caso, eu quero ir lá no site, e não quero mais ver Jogoteca no título, quero ver Jogos escrito, sendo uma lista de jogos e quero que seja jogos.

[00:16] Com conhecimento que temos até então, teríamos que vir no HTML e alterar na linha 11, tirar esse "Jogoteca" desse título e digitar "Jogos", só que se mudarmos de ideia no futuro? Se quisermos mudar de volta, então não está muito dinâmico, e é essa palavra-chave aqui, precisamos dinamizar o nosso código cada vez mais.

[00:35] Para dinamizar o código o ideal seria que colocássemos uma variável e passar o valor da variável através do jogoteca.py, então vamos fazer isso, como faríamos isso dentro de um código HTML? Porque colocar variável isso é coisa de linguagem de programação, como que faríamos para colocar código Python no HTML?

[00:55] O Flask ele tem essa diretiva que é essa dupla chaves para abrir e dupla chaves para fechar ('{{}}'), e essa diretiva ela existe em outras linguagens de programação também inclusive e vamos usar ela para colocar código Python aqui dentro.

[01:10] No nosso caso agora, vamos colocar só uma variável, então vou criar um nome de uma variável na linha 11, pode ser título, {{titulo}}, criei essa variável, como que passamos o valor dessa variável?

```
<h1>{{titulo}}</h1>
```

[01:26] E aqui que vem o render template no arquivo jogoteca.py, ele vai fazer isso por nós, e ele faz isso quando colocamos um outro parâmetro para ele, vamos colocar vírgula dentro desse “lista.html”, do lado colocamos uma vírgula e vamos digitar "título", então vamos criar essa variável return render_template(’lista.html’, titulo=’Jogos’), e inserir o nome que queremos que é Jogos.

[01:58] Ele vai passar esse valor desta variável "título" em específico, para “lista.html”, ele vai fazer essa comunicação por nós, vou dar um “Ctrl + S” em ambos os arquivos e vou dar um rerun embaixo na seta verde, “Ctrl + F5”, já fiz o rerun, vamos lá para o site e vamos recarregar o site. E pronto, alterou para "Jogos".

[02:24] Então agora já temos mudado o título, mas vamos tentar dar uma aprimorada nessa lista de jogos, temos uma lista de três jogos a princípio e esses três jogos, eu acabei de falar que não era legal colocar os valores de questões que podemos querer mudar no futuro no arquivo HTML e se formos observarmos em jogoteca.py, estamos com os nomes dos jogos no arquivo HTML, na linha 21, 24 e 27, God of War, Skyrim e Valorant, como podemos fazer para dinamizar essa parte? Seria interessante colocarmos em render_template também, então no próximo vídeo vamos fazer exatamente isso.



3 - Passando variáveis para o HTML

Qual a diferença de criar/renderizar um template estático para mostrar um html com dados do servidor?

A diferença é que no caso da página com conteúdo do servidor eu preciso passar um parâmetro nomeado para a função render_template. E na HTML eu preciso usar um delimitador para imprimir o valor.
Passando este parâmetro nomeado é possível acessar a variável pelo nome no HTML.

4 - Pegando lista do servidor

[00:00] Então mudamos aquela questão do título e faltou agora dinamizarmos essa questão dos jogos, porque se formos ver o nome dos jogos eles ainda estão no nosso arquivo HTML, isso não é interessante, poderíamos dinamizar isso, poderíamos então, criar no arquivo Python vários nomes de jogos que a partir daqui pega uma variável, são colocados em uma variável no render template, e são passados para o nosso arquivo HTML.

[00:25] Então eu poderia chegar no arquivo lista.htlm, na linha 21, no God of War e apagar ele e digitar a dupla chaves, e podemos inserir uma variável <td>{{jogo1}}</td>, e em jogoteca.py, na linha 7, podemos criar no jogo1 = ’Tetris’, e passamos o jogo1 como parâmetro no render template também.

[00:58] Só que todo jogo novo que eu faria eu teria que fazer isso de novo, será que não daria para colocar todos os jogos que eu vou criar aqui dentro de uma lista e depois usar um for para passar todos eles lá no HTML? É isso que eu vou fazer, é isso que eu vou tentar fazer, então vou criar uma lista na linha 7, lista = [], vou colocar então "Tetris", vou ser um old school, vou colocar "Skyrim" e "Crash", então criei essa lista, lista = [‘Tetris’, ‘Skyrim’, ‘Crash’].

[01:39] E em render_template eu passaria a lista jogos, vou criar a variável jogos e, então eu vou colocar return render_template(‘lista.html’, titulo=’Jogos’, jogos=lista), então essa variável jogos vai fazer referência a lista, e eu vou passar essa lista para o meu arquivo HTML.

[02:10] Só que como que eu vou fazer uma estrutura for dentro do HTML? Eu já falei que essa dupla chaves, já ajuda a colocar código Python aqui dentro, mas quando vamos fazer uma estrutura de repetição, precisamos usar uma outra diretiva.

[02:26] Então vamos lá, primeiro que eu vou apagar esses dois blocos de código que não vamos precisar da linha 23 à 28, só vamos precisar de um agora, para que vamos repetir ele várias vezes, e o que vamos fazer, é vamos usar uma chaves e um porcentagem, e vai ser essa a diretiva, chaves e porcentagem, {%%}, então vou inserir na linha 20.

[02:51] E dentro entre as porcentagens vamos escrever como se fosse um for normal, {% for jogo in jogos %} e isso vai se repetir várias vezes e na linha 22 só preciso colocar jogo e não mais jogo1, e a chave dupla mantém, então só para fazer a estrutura de repetição eu vou precisar dessa chave porcentagem, para colocar a variável eu coloco essa dupla chaves.

[03:19] E na linha 24 depois de </try>, vou precisar inserir uma coisa que não tem no Python, mas que precisa ter nesse caso, fechar esse for. Então vou fechar ele com {%endfor%} e pronto, agora a estrutura está bem feita, então agora eu vou dar um salvar e vamos testar, vamos ver se funcionou tudo isso que eu fiz.

[03:45] Então vamos ir lá no nosso site e vamos recarregar, ainda não funcionou porque eu não dei o return, então vou no Jogoteca, dou um “Ctrl + F5”, e vou rodar de volta a coisa toda, vou lá no meu site e vou recarregar a página, e pronto, aqui recarregou e mostrou direitinho, aqui Tetris, Skyrim e Crash.

[04:11] Então é isso, só que suponho que ainda está meio estranho, vamos lá no nosso código e vamos ficar colocando a quantidade de jogos que queremos na lista? Tem uma estrutura em Python que é um pouco melhor para fazer isso, uma classe. Então no próximo vídeo vamos começar a explorar um pouco orientação a objetos.



5 - Deixando valores dinâmicos

João pegou um projeto freelancer de Flask para fazer alterações para um site.

A primeira alteração é definir que o atributo href de link que está no html deve vir do servidor.

O trecho de código do html está abaixo.

```
<!-- inicio do trecho - página home.html -->
<p>A instituição mostra suas apostilas <a href="http://www.alura.com.br/apostilas">aqui</a></p>
<!-- fim do trecho -->
```

O código Python no servidor está assim:

```
# inicio do trecho Python

link_de_apostilas = 'http://www.alura.com.br/apostilas'

@app.route('/home')
def principal():
    return render_template('home.html')

# fim trecho servidor
```

Marque as alternativas corretas para dizer como deve ser alterado o código:

```
<!-- inicio do trecho - página home.html -->
<p>A instituição mostra suas apostilas <a href="{{ link }}">aqui</a></p>
<!-- fim do trecho -->
```
Esta opção está fazendo uso da diretiva ou delimitador '{{ }}' para acessar a variável que está configurada no render_template do servidor.

```
# inicio do trecho Python

link_de_apostilas = 'http://www.alura.com.br/apostilas'

@app.route('/home')
def principal():
    return render_template('home.html', link=link_de_apostilas)

# fim trecho servidor
```
Basta adicionar as variáveis como parâmetro para o render_template.

6 - Deixando mais orientado a objetos

[00:00] Então agora vamos utilizar a estrutura de classe e de orientação a objeto, ao paradigma de orientação a objeto no projeto. E por que vamos fazer isso? Por que não continuamos usando a lista normal aqui com o nome jogos? Por que vamos tornar tão complexo assim, colocar orientação a objeto?

[00:19] Porque queremos associar outras características a cada jogo em específico que formos criar, então queremos saber, por exemplo, qual que é a categoria do jogo Tetris, qual que é o console do jogo Tetris, e para fazer isso não existe nenhuma outra estrutura melhor do que uma classe.

[00:35] Então vamos criar uma classe em jogoteca.py para nós, um class Jogo: def __init__(self, nome, categoria, console): sendo nome, categoria e console parâmetros, pronto e na próxima linha vou terminar de associar as variáveis então self.nome = nome, self.categoria = categoria e self.console = console, a classe está criada.

[01:31] E agora precisamos instanciar os objetos, precisamos fazer os jogos mesmo, então eu vou começar na linha 13 após o def ola(): com o jogo1, primeiro vou apagar essa lista, podemos reutilizar, então vou deixar os nomes dos jogos separados, então vamos criar um objeto jogo1 = Jogo() e eu vou colocar o ’Tetris’, de novo, a categoria que ele se encaixa é ’Puzzle’, e o console dele é o ’Atari’.

```
jogo1= Jogo ('Tetris', 'Puzzle', 'Atari')
```

[02:13] E um jogo2 = Jogo(), eu vou colocar ’God of War’,, categoria vou colocar ’Rack n Slash’,, e eu vou colocar como console o ’PS2’, e dentro da lista na linha 16 reaproveitamos ela e colocamos lista = [jogo1, jogo2] está certo então, temos a nossa lista.

[03:05] E vamos colocar para rodar, vamos dar um “Ctrl + S” para salvar e vamos dar um rerun, “Ctrl + F5” e agora vamos lá no site e recarregamos também, deu problema aqui, ele está mostrando um monte de código aqui, que é isso? O que é isso aqui?

[03:27] Essa daqui é a referência do nosso objeto na memória do computador, mas, porque ele está dizendo isso para nós e não está dizendo as informações do jogo? Porque está faltando coisa aqui, alteramos aqui nosso arquivo o jogoteca.py, mas não alteramos lista.html, então é isso que está faltando, precisamos alterar aqui também para dar certo no site, então vamos fazer isso no próximo vídeo.



7 - Mostrando atributos na view

[00:00] Então no último vídeo tentamos trazer as informações dos objetos que criamos, dos jogos que criamos para a nossa página, mas acabou não dando muito certo, no lugar das informações acabou vindo essa referência que está sendo exibida na tela do site, sendo a referência da alocação de memória que o computador fez para os objetos, que são os jogos em jogoteca.py, o jogo Tetris e o God of War, mas não é isso que queremos, queremos as informações. Para consertarmos isso, temos que mudar no código do “lista.html”, porque já mudamos tudo que tínhamos para mudar no Jogoteca.

[00:34] Então vamos em lista.html e na linha 22, na estrutura de repetição a variável jogo, colocamos ponto, nome <td>{{ jogo.nome }}</td>, esse ponto nome vai ser aquilo que vai acessar a informação do nome no objeto, então vamos dar um “Ctrl + S” e um rerun na parte inferior na seta verde e vamos lá para a página, vou atualizar a página e pronto, resolvi o problema do nome, fantástico.

```
<td>{{ jogo.nome }}</td>
```

[01:00] Só que tem uma questão, porque usei a estrutura de classe, não uma lista simples e não ficar na lista simples, porque queria adicionar mais informação para cada jogo, para cada objeto que eu criasse, e aqui não tem, aqui só tem um nome, eu quero que apareça a categoria, quero que apareça o console.

[01:20] Então vamos lá, vamos voltar no nosso código em lista.html e vamos ver se tem um jeito de fazermos isso aparecer, e, na verdade, tem, só temos que criar duas novas colunas no código HTML, e para isso vamos copiar aqui esse código de dentro da nossa estrutura de repetição na linha 22,<td>{{ jogo.nome }}</td>, vou colar duas vezes nas próximas linhas e o “nome” vamos alterar para “categoria” <td>{{ jogo.categoria }}</td> e o debaixo para “console” <td>{{ jogo.console }}</td> e pronto.

```
<td>{{ jogo.nome }}</td>
<td>{{ jogo.categoria }}</td>
<td>{{ jogo.console }}</td>
```

[01:56] Isso aqui ele já vai estar acessando, só que eu também tenho que alterar em cima na linha 16, porque preciso alterar o título de cada coluna, então aqui só tem a coluna de nome, então eu vou fazer um “Ctrl + C” em <th>Nome</th> e colar nas duas próximas linhas, e aqui no nome da linha 17, vamos alterar para categoria <th>Categoria</th> e embaixo vou colocar <th>Console</th>, pronto, nosso código HTML já está alterado e já é para funcionar.

[02:26] Mas vamos lá em jogoteca.py e vamos criar um jogo, só para aumentar a quantidade de jogos que temos. Então vou criar um jogo, jogo3 = Jogo() e vou colocar como nome do jogo ’Mortal Kombat’,, categoria, ,’Luta’, e console vou colocar ’PS2’ também.

```
jogo3= Jogo ('Mortal Kombat', 'Luta', 'PS2')
```

[03:13] Então vou dar um rerun, vou para a nossa página e atualizar ela, e deu certo, está aparecendo o "nome", está aparecendo a "categoria", está aparecendo o "console" e está sendo exibido de todos os jogos, com exceção do último jogo que colocamos, porque se voltarmos para o código, acabei não adicionando na nossa lista na linha 16, o jogo 3, então ele não está pegando, vamos acrescentar jogo3, agora sim, tudo isso vai funcionar, vou dar um rerun, voltar para o site e atualizar nossa página, e agora está aqui, "Mortal Kombat", "luta", "PS2".

```
lista = [jogo1, jogo2, jogo3]
```

[03:48] Contudo, se percebermos, ainda está meio chato de fazer um jogo, de incluir um jogo, porque a proposta era que conseguíssemos incluir um novo jogo a partir do próprio site, não ter que ficar indo lá toda hora no código alterar, desse jeito, se mostrarmos esse site para um amigo nosso, ele nunca ia conseguir, então nos próximos vídeos vamos criar uma página, criar uma nova rota, para criar jogos no site, então até lá.

8 - Executando lógicas na view

No mesmo projeto, João precisa fazer uma validação na sua página para saber se existe alguma apostila para mostrar no site.

Caso existam apostilas ele deve mostrar a mensagem, 'Temos X apostilas no nosso site.', onde X é a quantidade de apostilas. Se não tiver nenhuma apostila na lista ele deve mostrar a mensagem: 'Nenhuma apostila aqui...'

O código do servidor está assim:

```
# inicio do trecho Python
lista_apostilas = ['HTML, CSS e Javascript', 'Java para Web']

@app.route('/apostilas')
def apostilas_online():
    return render_template('apostilas.html', lista=lista_apostilas)

# fim trecho
```

Dê uma olhada nos códigos abaixo e diga qual código resolve a tarefa do João.

```
<!-- inicio do trecho - página home.html -->
{% if lista %}
  <p>Temos {{ len(lista) }} apostilas no nosso site. </p>
{% else %}
  <p>Nenhuma apostila aqui... </p>
{% endif %}
<!-- fim do trecho -->
```
Esta alternativa está usando corretamente os delimitadores para imprimir a quantidade de apostilas e também para processar o código da lógica.

9 - Para saber mais: Filtrando dados de templates

O Jinja2 é o motor de templates do Flask. Ele nos ajuda com diversos helpers enquanto projetamos nossos HTML de forma mais dinâmica.

Um exemplo de facilidade que temos nos templates é a ideia de filtrar um conteúdo que vem do servidor, o conteúdo de uma variável que será impressa no HTML.

Temos um trecho de código da nossa aplicação aqui:

```
<h1>{{  titulo  }}</h1>
```

Imagine que precisamos fazer todo título de página ser iniciado com letra maiúscula no nosso template. Podemos fazer o seguinte, no trecho de código que imprime o título.

```
<h1>{{  titulo|title  }}</h1>
```

Muito tranquilo de fazer esta melhoria, não é? Tem vários outros filtros que podem ajudar, como:

- upper: colocar os caracteres em caixa alta;
- round: arredondar números;
- trim: remover espaços do início e do fim do texto;
- default('texto exibido por padrão') - quando queremos mostrar algo, caso a variável esteja vazia ou nula.

Tipos de Delimitadores do Jinja2:

- {%....%}: usado para inserir estruturas Python dentro de um arquivo html;
- {{....}}: usado para facilitar a exibição de código python como um output em um template HTML. Alternativa: {% print(....) %};
- {#....#}: usado para adicionar comentários que não serão exibidos no output do template HTML.

10 - Faça como eu fiz: mostrando jogos do servidor

hegou o momento de implementar o que vimos nos vídeos!

Clicando no link a seguir, você consegue fazer o download dos arquivos da Aula 01!

1) Abra seu arquivo lista.html no PyCharm.

2) Utilize a diretiva do flask para usar um conteúdo dinâmico e modifique o título Jogoteca conforme abaixo:

```
<h1>{{ titulo }}</h1>
```

3) Abra o arquivo jogoteca e passe mais um parâmetro para o render_template, que será o conteúdo que será utilizado no HTML, veja abaixo:

```
from flask import Flask, render_template

app = Flask(__name__)

@app.route('/inicio')
def ola():
    return render_template('lista.html', titulo='Jogos')

app.run()
```

4) Rode a aplicação e veja que agora o título é dinâmico!

Agora vamos deixar mais conteúdo dinâmico...

5) Dentro de ola crie uma lista de jogos, veja abaixo:

```
from flask import Flask, render_template

app = Flask(__name__)

@app.route('/inicio')
def ola():
    lista = ['Tetris', 'Skyrim', 'Crash']
    return render_template('lista.html', titulo='Jogos')

app.run()
```

6) Agora passe essa lista como parâmetro do render_template:

```
from flask import Flask, render_template

app = Flask(__name__)

@app.route('/inicio')
def ola():
    lista = ['Tetris', 'Skyrim', 'Crash']
    return render_template('lista.html', titulo='Jogos', jogos=lista)

app.run()
```

7) Volte para seu HTML e delete as tags <tr>, deixando apenas uma e modifique para pegar o nome do jogo dinamicamente, utilizando o jinja para escrever Python em HTML:

```
 <tbody>
{% for jogo in jogos %}    
                <tr>
                    <td>{{ jogo }}</td>
                </tr>
{% endfor %}
</tbody>
```

Obs: Repare que a diretiva utilizada é diferente!

8) Reinicie sua aplicação e verifique se tudo correu como esperado.

Neste momento temos uma lista exibida. Abaixo vamos fazer aparecer mais informações do Jogo com um objeto.

9) Crie uma classe Jogo no arquivo jogoteca, veja abaixo:

```
from flask import Flask, render_template

class Jogo:
    def __init__(self, nome, categoria, console):
        self.nome = nome
        self.categoria = categoria
        self.console = console

app = Flask(__name__)

@app.route('/inicio')
def ola():
    lista = ['Tetris', 'Skyrim', 'Crash']
    return render_template('lista.html', titulo='Jogos', jogos=lista)

app.run()
```

10) Crie os objetos dentro de ola e modifique a variável lista para armazenar os três objetos criados:

```
from flask import Flask, render_template

app = Flask(__name__)

class Jogo:
    def __init__(self, nome, categoria, console):
        self.nome = nome
        self.categoria = categoria
        self.console = console

@app.route('/inicio')
def ola():
    jogo1 = Jogo('Tetris', 'Puzzle', 'Atari')
    jogo2 = Jogo('God of War', 'Hack n Slash', 'PS2')
    jogo3 = Jogo('Mortal Kombat', 'Luta', 'PS2')
    lista = [jogo1, jogo2, jogo3]
    return render_template('lista.html', titulo='Jogos', jogos=lista)

app.run()
```

11) Teste sua aplicação e repare que será exibida uma mensagem de erro.

Bom, faltou editar o HTML que mostra a lista. Vamos fazer isso!

12) Abra seu arquivo HTML e modifique conforme abaixo para obter a saída desejada.

```
<thead>
    <tr>
        <th>Nome</th>
        <th>Categoria</th>
        <th>Console</th>
    </tr>
</thead>
<tbody>
{% for jogo in jogos %}    
                <tr>
                    <td>{{ jogo.nome }}</td>
                    <td>{{ jogo.categoria }}</td>
                    <td>{{ jogo.console }}</td>
                </tr>
{% endfor %}
</tbody>
```

Observação: Repare que, dessa vez, acessamos o conteúdo de nome, categoria e console do objeto em questão.

13) Dê um refresh na sua aplicação e veja a mudança, teste adicionando mais jogos.



11 - Revisando o que fizemos

[00:00] Então vamos recapitular um pouco do que já aprendemos, já aprendemos as estruturas essenciais do Flask, para podermos instanciar, originar uma aplicação, colocar uma aplicação no ar mesmo, então aprendemos, como colocar uma variável, usar a função Flask mesmo para dentro de uma variável, fazer a aplicação rodar de fato e colocar ela no ar.

[00:23] Aprendemos também um pouco da organização dentro do Flask, que existe uma padronização de uma pasta templates para se colocar os arquivos HTML, e falando em arquivo HTML, aprendemos a fazer a ponte entre esse arquivo HTML, arquivos HTML em geral, e arquivo Python que é o arquivo mãe, que é através do helper que é o Flask nos dá que é o render template e esse render template permite que coloquemos variáveis, valores de variáveis, que são passadas para o arquivo HTML.

[00:54] Então no arquivo HTML também aprendemos que tem como inserirmos código Python dentro do arquivo HTML, então com essa dupla chaves ({{}}) podemos colocar as variáveis, ou podemos através dessa chave porcentagem ({%%}), colocar estruturas de repetição dentro, e isso é muito interessante.

[01:17] Fizemos também uma ponte com orientação objetos dentro do nosso código, então adicionamos uma classe onde estamos aprimorando ao invés de usar variáveis padrões, estamos usando uma classe, estamos usando uma instanciação de um objeto que é muito importante para um projeto dessa proporção que estamos fazendo agora.

[01:39] E também aprendemos como criar uma rota em jogoteca.py e muitas outras virão ainda ao decorrer desse projeto, então essa parte é muito importante. Nas próximas aulas vamos aprender a como criar uma página para podermos criar um jogo, a partir do nosso próprio site, então até lá!



03 - Criação de um novo jogo

1- Projeto da aula anterior

2- Criar um novo jogo

[00:00] Então vamos continuar com o projeto e vamos começar relembrando o que aconteceu na última aula. Vimos que temos uma lista no site já de jogos, isso é bem legal, só que toda vez que precisamos cadastrar um novo jogo, precisamos ir lá acessar o código, instanciar um novo objeto e fazer tudo por lá, e não é bem o que queremos, queremos é acessar o site e poder cadastrar um jogo pelo site.

[00:22] Então queremos acessar uma nova rota na URL http://127.0.0.1:5000/novo e ter um formulário de cadastro que colocamos o nome do jogo e o jogo seja cadastrado de fato, então vamos fazer isso acontecer. Vamos no código da jogoteca.py, no projeto e temos que começar criando um novo template, criando um novo arquivo HTML, porque precisamos de uma nova rota afinal de contas, uma nova página.

[00:52] Então vamos à pasta de templates, vamos clicar em cima dela, escolher "new" e depois "HTML File" e vamos criar um novo arquivo HTML nomeado “novo”, vai ser um novo jogo toda vez, vou apagar o código que gerou automaticamente e já tenho pronto um novo template.

Código do arquivo novo.html:

```
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
      <form>
        <fieldset>
          <div class="form-group">
            <label for="nome">Nome</label>
            <input type="text" id="nome" name="nome" class="form-control">
          </div>
          <div class="form-group">
            <label for="categoria">Categoria</label>
            <input type="text" id="categoria" name="categoria" class="form-control">
          </div>
          <div class="form-group">
            <label for="console">Console</label>
            <input type="text" id="console" name="console" class="form-control">
          </div>
          <button type="submit" class="btn btn-primary btn-salvar">Salvar</button>
        </fieldset>
      </form>
    </div>
</body>
</html>
```

[01:13] Então já um novo template e já tenho o suficiente para conseguirmos fazer essa página. Só que temos que voltar aqui em jogoteca.py e criar uma nova rota para acessarmos esse template, da mesma forma que fizemos com a página de início, também temos que fazer um direcionamento para essa página HTML, uma ponte.

[01:37] Então vamos fazer uma nova rota, é só colocar da mesma forma que a anterior, então vou digitar @app.route() e vou colocar o nome dessa rota ’/novo’, e criar uma função que vai gerar essa página, que vai levar essa página, vou colocar o nome dessa função de def novo(): também, colocar o mesmo nome, é tranquilo, dá certo, e já vou colocar aqui um return render_template() e dentro do render_template vou passar o nome do arquivo html ’novo_html’.

[02:21] E se formos nesse template novo (novo.html) na linha 11, ele também tem aquela variável dinâmica do título, então em jogoteca.py eu vou colocar um título também personalizado para ele, e eu vou colocar aqui como sendo (‘novo.html’, titulo=’Novo Jogo), o título que eu quero que apareça ali na página.

```
@app.route(’/novo’)
def novo():
    return render_template(’novo_html’, titulo=’Novo Jogo')
```

[02:49] Então já está pronta a nova rota, vamos dar um rerun e ver como ficou no site. Está funcionando certo, tem um formulário já, com o título “Novo jogo”, então vamos cadastrar um novo jogo, vamos experimentar, vou digitar: Need For Speed, categoria "corrida", e vou colocar em console PS2.

[03:22] Então está tudo tudo preenchido, então vou selecionar o botão "Salvar" e vamos ver o que acontece, aí continua na mesma, não deu nenhuma mensagem, estranho, e observe a URL vamos ver todas as informações do formulário preenchido, está escrito: "Need for Speed", categoria corrida, console PS2, está tudo isso. Não é uma coisa muito segura, não é uma coisa que gostaríamos que aparecesse toda vez que preenchemos o formulário a coisa vai tudo para o URL.

[03:55] E mais do que isso, se eu for na URL e digitar \inicio e tentar acessar início, que é onde fica a nossa lista, não consta o jogo que acabamos de inserir no formulário, então ainda tem algumas coisas para resolvermos, vamos ver isso no próximo vídeo.



3 - Montando um formulário no Flask

[00:00] No último vídeo vimos que se colocarmos aqui as informações de um novo jogo para inserir na nossa lista, esse novo jogo acaba não aparecendo na nossa lista, acaba não sendo processado pelo servidor, e mais do que isso, essas informações acabam aparecendo aqui na URL, isso é bem estranho, por que isso acontece?

[00:18] Porque se lembrarmos lá de http, de requisições, lembramos que tem dois tipos de métodos, o get e o post, e quando que utilizamos o método get? Quando queremos puxar alguma informação do nosso servidor, e a utilizamos o post quando queremos informar alguma coisa para o servidor, passar alguma informação para que ele processe da maneira dele, e é isso que estamos tentando fazer, queremos passar uma informação, a informação de um novo jogo para que o servidor processe, para que o Flask lá processe.

[00:48] E é isso que não está acontecendo no site, porque o que está acontecendo aqui é que como padrão está configurado o método get, e é isso que faz com que as informações apareçam aqui na URL e nada seja mandado para o servidor e o jogo não apareça na lista.

[01:05] Então vamos consertar isso, vamos colocar o método certo, mas antes, vamos dar uma revisada no que está acontecendo quando colocamos as informações no formulário. Temos o navegador e vamos passar as informações de um novo jogo para o formulário do navegador, e ele vai ir de uma forma de requisição para o servidor, já sabemos que ele vai com o método post e ele faz isso através da página que criamos que a barra novo, /novo, a rota /novo, então ele vai fazer isso através dessa rota que criamos lá no nosso arquivo do jogoteca.py.

[01:44] Só que o servidor precisa processar e precisa responder isso para o navegador de alguma forma, e precisamos criar então alguma coisa para que o servidor faça esse processamento, ele não vai fazer sozinho, temos que configurar isso e vamos fazer isso através da página “Criar” da nova rota que vamos criar.

[02:03]Então essa rota que vamos criar, que se chama “Criar”, vai ser responsável por fazer esse processamento desse novo jogo, desse novo item, então é isso que vamos fazer.

[02:14] Aqui em novo.html, vamos alterar essa questão do método na linha 13, vamos alterar de get para post definitivamente para que ele empurre as informações para o servidor, vamos ir na tag form e vamos colocar métodos <form method= “post”> duas aspas e o Pycharm até oferece para nós duas opções, então eu vou colocar post, ele já fez essa alteração.

```
 <form method= “post”>
        <fieldset>
          <div class="form-group">
            <label for="nome">Nome</label>
            <input type="text" id="nome" name="nome" class="form-control">
          </div>
```

[02:40] Só que por enquanto do jeito que está, ele é só um formulário que pega as informações não joga para nenhum lugar, ele está fazendo o post, está enviando para o servidor, mas para onde? Ele ainda não está especificado no código, e é isso que vou colocar agora, vou colocar uma especificação action =”/criar” e o caminho que quero que ele vá, que é o barra criar /criar, eu quero que ele vá para essa nova rota que eu vou criar, que é a rota barra criar /criar.

```
 <form action="/criar" method= “post”>
        <fieldset>
          <div class="form-group">
            <label for="nome">Nome</label>
            <input type="text" id="nome" name="nome" class="form-control">
          </div>
```

[03:09] Então aqui está tudo certo, pronto e agora vamos lá na jogoteca.py e vamos criar essa nova rota, que é a criar que é a rota que vai processar esse novo item, então vamos criar uma nova rota aqui da mesma forma que fizemos as duas anteriores, @app.route(’/criar’), muito bem.

[03:36] Vou colocar uma função de nome criar, mesmo nome, def criar(): essa função vai gerar a rota. Como que vou fazer agora para pegar as informações lá do formulário? O formulário já está enviando as informações para essa rota, mas preciso capturar essa informação, isso vamos fazer através de um helper do Flask chamado request, que vamos escrever lá na primeira linha do código, ele vai nos ajudar a pegar essas informações do formulário.

```
@app.route('criar')
def criar():
```

[04:08] Então na função "Criar" vou colocar, primeiro vou ver o nome daquilo que eu estou pegando, então eu vou lá no novo.html, vou no formulário na linha 16 e ver as informações que eu estou pegando, no input, temos um nome que é o nome do jogo, está como nome, também tem uma outra que o nome é categoria e outra coluna que o nome é console.

[04:32] Então são essas três informações que quero, um nome, a categoria e o console desse item, e vejo justamente nessa tag do nome, isso é importante, essa vai ser a referência que o request vai utilizar para capturar as informações, dessa tag assim, name.

[04:50] Então vamos voltar lá em jogoteca.py e vamos colocar, nome = request.form[‘nome’] com isso ele já vai localizar lá por aquela tag do HTML onde que está o nome, e vou fazer a mesma coisa para todos os outros, categoria = request.form[‘categoria’], e o último que é console, console = request.form[‘console’], ele já capturou todas as informações que preciso.

```
@app.route('criar')
def criar():
    nome = request.form['nome’]
    categoria = request.form[‘categoria’]
    console = request.form[‘console’]
```

[06:07] E agora como que vamos fazer isso criando um objeto, vamos criar o objeto jogo com essas informações "nome","categoria" e "console": jogo = Jogo(nome, categoria, console), pronto criei o objeto da classe que está na linha 4, que já definimos o jogo, criei então esse novo jogo.

[06:42] Agora preciso adicionar ele na lista, então vou seguir nessa função criar() e colocar lista.append, que é um dos métodos de Python para adicionar alguma coisa dentro de uma lista, então vou colocar lista que está lá em cima na linha 16, lista.append(jogo), esse novo jogo que acabamos de criar.

```
@app.route('criar')
def criar():
    nome = request.form['nome’]
    categoria = request.form[‘categoria’]
    console = request.form[‘console’]
    jogo = Jogo(nome, categoria, console)
    lista.append(jogo)
```

[07:08] Só que tem um problema, porque se formos lá em cima na linha 16, vamos ver que essa lista não é global, está dentro de uma função, e não estamos referenciando essa função na que acabamos de criar.

[07:18] Então, vamos pegar toda essa lista dentro da função ola() que é formada da linha 13 a 16, vamos remover ela daqui e colocar ela aqui em cima como um fator global.

```
from flask import Flask, render_template, request

class Jogo:
    def __init__(self, nome, categoria, console):
        self.nome = nome
        self.categoria = categoria
        self.console = console

jogo1= Jogo ('Tetris', 'Puzzle', 'Atari')
jogo2= Jogo ('God of War', 'Hack n Slash', 'PS2')
jogo3= Jogo ('Mortal Kombat', 'Luta', 'PS2')
lista = [jogo1, jogo2, jogo3]

app = Flask(__name__)
```

[07:41] Isso porque toda vez que geramos essa página, a página de início, não temos que ficar gerando toda vez uma nova lista, ela já vai ficar gravada, e agora como fator global consigo referenciar ela na lista abaixo.

[08:02] Só que ainda não terminou, porque esse criar conseguiu fazer todo esse processamento de pegar as informações do jogo e adicionar à lista, mas precisamos mostrar essa lista, então vamos fazer aqui um return e utilizar render_template: return render_template().

[08:22] Então vamos colocar as informações, queremos que apareça qual página? A lista, ’lista.html’,, vamos fornecer o título = ‘Jogos’, e vamos fornecer a lista jogos = lista, estou fazendo da mesma forma que fiz na parte de cima, então quando pela primeira vez renderizamos a /inicio, peguei a mesma coisa. Então estou renderizando a página do lista.html, com título de jogos, e eu estou passando para ele a lista que ele deve mostrar, e é isso.

```
@app.route('criar')
def criar():
    nome = request.form['nome’]
    categoria = request.form[‘categoria’]
    console = request.form[‘console’]
    jogo = Jogo(nome, categoria, console)
    lista.append(jogo)
    return render_template('lista.html', titulo='Jogos', jogos=lista)
```

[09:14] Então criamos essa nova rota de criar, vamos salvar e rodar novamente a aplicação. Agora vamos voltar no site e checar para ver se está tudo certo, essa página era antiga que estávamos, vou recarregar e inserir /novo na URL de volta, pronto, e agora vou preencher o formulário com: Need for Speed, corrida, PS2.

[9:39] Vamos ver se agora vai funcionar, salvar, e olha só ele retornou um erro aqui, method not allowed, o que isso significa? Método não permitido, mas não alteramos o método lá no arquivo novo.html? Por que ele está dizendo que o método não é permitido? Tem mais algo que temos que alterar ali no nosso código e isso vamos ver no próximo vídeo.



4 - Criando o formulário

Quando criarmos um formulário no Flask, é preciso definir um HTML com a tag <form> para tal.

Identifique abaixo quais informações são necessárias para que o meu request seja bem sucedido e as minhas informações não fiquem expostas na barra de endereços.


É necessário informar o método POST e passar uma rota no atributo action.
A rota direciona a requisição para um caminho configurado no servidor e o método é importante para encapsular os dados do meu formulário, não mostrando na barra de endereços.

5- Resolvendo um POST no servidor

[00:00] Recebemos esse erro method not allowed, o que isso significa? Já alteramos lá o método na nossa página novo.html, já alteramos de get para post, então por que está dando esse erro? Basicamente é porque nos esquecemos de alterar em um lugar específico, que é no arquivo jogoteca.py.

[00:23] Na nova rota criar, o Flask como padrão coloca que a rota só aceita o método get, então temos que informar para ele que também deve aceitar o método post, assim vamos inserir methods, vamos do lado da nossa rota /criar e colocamos uma vírgula e o methods, e dentro desse methods inserimos uma lista onde vamos digitar "POST" em letras maiúsculas `@app.router(‘/criar’, methods=[‘POST’,])` e pronto, agora vamos fornecer para ele aquilo que precisa para conseguir rodar a aplicação.

```
@app.route('criar', methods=['POST',])
def criar():
    nome = request.form['nome’]
    categoria = request.form[‘categoria’]
    console = request.form[‘console’]
    jogo = Jogo(nome, categoria, console)
    lista.append(jogo)
        return render_template('lista.html', titulo='Jogos', jogos=lista)
```

[00:59] Vamos salvar e um rerun, “Ctrl + F5”, e finalmente vamos na aplicação e tentar mais uma vez. Então vou colocar no formulário do site "Need for Speed", "corrida", "PS2", selecionar "salvar" e deu certo. Conseguimos colocar, inserir mais um jogo na lista.

[01:26] Mas vocês não acham que estamos dando muito rerun na aplicação? Toda vez que vamos lá no código e fazemos uma alteração, temos que dar “Ctrl + S” para salvar e ir no terminal dar “Ctrl + F5” para restartar a aplicação do zero.

[01:40] Isso não é muito profissional, tem uma maneira mais profissional e fluido de fazermos a aplicação entender que estamos realizando alterações e em tempo real fazer a sua atualização, que é ativando o debugger.

[01:57] Então vamos ir no app.run() em jogoteca.py, no final do código, digitar dentro dos parênteses app.run(debug = True), assim já vamos ativar o nosso debug, então vamos dar um rerun pela última vez no terminal na aplicação, rerun e pronto.

```
@app.route('criar', methods=['POST',])
def criar():
    nome = request.form['nome’]
    categoria = request.form[‘categoria’]
    console = request.form[‘console’]
    jogo = Jogo(nome, categoria, console)
    lista.append(jogo)
    return render_template('lista.html', titulo='Jogos', jogos=lista)

app.run(debug = True)
```

[02:18] Ele oferece no canto inferior no terminal, que ele já restartou a aplicação "Restarting with stat" e já colocou que o status do debbuger está ativo "Debugger is active", mas o que isso vai fornecer para nós na prática? Vamos fazer alguma alteração no código, vamos aplicar uma melhoria no código para fazer esse teste dessa nova alteração que fizemos de iniciar o debbuger.

[02:45] Vamos ir na rota início, que criamos lá quando começamos a aplicação, podemos alterar o nome da nossa função, ao invés de colocar a função "Olá", vamos usar o nome da função de def index(), já que é um nome padrão para toda página de início que fazemos, de página de início mesmo de web, colocamos o nome de index, então vamos deixar o nome da função de index.

[03:13] E no ’/inicio’, quando acessamos a primeira página de uma aplicação na web, é ’/inicio’ que acessamos, é um nome, a rota da página é /inicio? Não exatamente, é basicamente só barra, é a primeira página da aplicação, então é só `@app.router(‘/’)`.

[03:32] Então fizemos essas duas alterações, alteramos o nome da função ola() para index() e para barra (/) o que antes era ('/inicio'), isso vai deixar a aplicação até mais fluida, mais bonita.

```
@app.route('/')
def index():
    return render_template('lista.html', titulo='Jogos', jogos=lista)
```

[03:43] Então vamos fazer um teste, vou selecionar “Ctrl + S”, e note no terminal, o debugger já entendeu que existe alguma alteração no código e ele mesmo já restartou a aplicação, então isso vai aumentar a velocidade de desenvolvimento da aplicação bastante. Vamos voltar na aplicação e testar para ver se essa melhoria foi legal, vamos ver se dá algum problema.

[04:11] Então vamos selecionar refresh no site e note que retornou um erro, uma caixa para confirmar reenvio de formulário. Por que confirmar reenvio de formulário? É porque ainda estamos na página /criar, isso não é interessante, queremos ver a lista de jogos, e nossa lista de jogos está na página agora barra ('/'), não é mais barra início, /inicio, é só a barra /.

[04:33] Assim acontece que ele continua na página criar e essa página era só para ser uma página de processamento do servidor, uma rota de processamento do servidor, não para ele continuar aqui talvez.

[04:47] Outra a página criar ela recebe post, não o get, então está acontecendo alguma coisa estranha, ele não tem que ficar na página criar.

[04:57] A página criar tem que servir como uma página de meio-termo, então criamos a página novo, ela envia um formulário para a página criar, que processa as informações que são recebidas do formulário do novo, no servidor, e essa página criar ela tem que nos redirecionar para página da lista, que é a página barra.

[05:19] Então tem que ser uma página de meio-termo, não pode ser uma página que continua, porque quando damos o refresh, vai acontecer aquela mesma questão, ainda está com informação do formulário antigo e pode gerar algum problema, assim vamos fazer isso acontecer, vamos tornar ela uma página apenas intermediária, vamos ver isso no próximo vídeo.



6 - Configurando o servidor para as requisições

Usando o protocolo HTTP, conseguimos passar informações de um formulário pela Web. No caso do Flask, queremos receber informações e tratar usando Python.

Quais opções são necessárias para enviar dados de um formulário para o servidor usando o método POST?


Preciso ter uma função com uma rota configurada igual ao atributo action do formulário.
Se não for igual ou não configurar a action a requisição não vai chegar no local desejado.

É necessário definir o método POST como um método aceito pela rota.
Se não definirmos o método POST na configuração o request não vai chegar na função definida no Flask pois o único método aceito será o GET. Veja abaixo um exemplo abaixo de como permitir requisições POST:
```
@app.route('/caminho', methods=['POST',])
```

É preciso importar o objeto request que fornece um atributo form com meus campos.
O objeto request tem um dicionário (form) com todos os valores do formulário.

7 - Recarregando automaticamente

Para poupar um pouco de tempo e não precisarmos ficar reiniciando o servidor toda vez que fazemos uma alteração no código, existe uma forma de atualizar o contexto da aplicação de forma automática.

Qual configuração devemos fazer para conseguir este comportamento?

Devemos passar um parâmetro nomeado (debug=True) ao chamar o método run do objeto da aplicação.
Desta forma, sempre que salvamos os arquivos da nossa aplicação a IDE consegue atualizar o contexto da aplicação que está rodando com as nossas alterações.



8 - Faça como eu fiz: Adicionando jogos


Clicando no link a seguir, você consegue fazer o download dos arquivos da Aula 02!

1) Crie um novo arquivo HTML, no curso utilizamos o nome novo.html e cole o código abaixo:

```
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
      <form>
        <fieldset>
          <div class="form-group">
            <label for="nome">Nome</label>
            <input type="text" id="nome" name="nome" class="form-control">
          </div>
          <div class="form-group">
            <label for="categoria">Categoria</label>
            <input type="text" id="categoria" name="categoria" class="form-control">
          </div>
          <div class="form-group">
            <label for="console">Console</label>
            <input type="text" id="console" name="console" class="form-control">
          </div>
          <button type="submit" class="btn btn-primary btn-salvar">Salvar</button>
        </fieldset>
      </form>
    </div>
</body>
</html>
```

2) Crie uma nova rota para exibir esse HTML:

```
from flask import Flask, render_template

class Jogo:
    def __init__(self, nome, categoria, console):
        self.nome = nome
        self.categoria = categoria
        self.console = console

app = Flask(__name__)

@app.route('/inicio')
def ola():
    jogo1 = Jogo('Tetris', 'Puzzle', 'Atari')
    jogo2 = Jogo('God of War', 'Hack n Slash', 'PS2')
    jogo3 = Jogo('Mortal Kombat', 'Luta', 'PS2')
    lista = [jogo1, jogo2, jogo3]
    return render_template('lista.html', titulo='Jogos', jogos=lista)

@app.route('/novo')
def novo():
    return render_template('novo.html', titulo='Novo Jogo')
app.run()
```

3) Reinicie sua aplicação e teste a rota /novo.

Aqui já dá pra ver o formulário!

4) Modifique o HTML da página novo.html, mais especificamente a tag form, mudando suas propriedades action e method olhe abaixo:

```
inicio do html...

<form action="/criar" method="post">
        <fieldset>
          <div class="form-group">
            <label for="nome">Nome</label>
            <input type="text" id="nome" name="nome" class="form-control">
          </div>
          <div class="form-group">
            <label for="categoria">Categoria</label>
            <input type="text" id="categoria" name="categoria" class="form-control">
          </div>
          <div class="form-group">
            <label for="console">Console</label>
            <input type="text" id="console" name="console" class="form-control">
          </div>
          <button type="submit" class="btn btn-primary btn-salvar">Salvar</button>
        </fieldset>
      </form>

final do html...
```

5) Adicione uma rota no código e importe o helper do flask request (veja primeira linha), conforme abaixo:

```
from flask import Flask, render_template, request

class Jogo:
    def __init__(self, nome, categoria, console):
        self.nome = nome
        self.categoria = categoria
        self.console = console

app = Flask(__name__)

@app.route('/inicio')
def ola():
    jogo1 = Jogo('Tetris', 'Puzzle', 'Atari')
    jogo2 = Jogo('God of War', 'Hack n Slash', 'PS2')
    jogo3 = Jogo('Mortal Kombat', 'Luta', 'PS2')
    lista = [jogo1, jogo2, jogo3]
    return render_template('lista.html', titulo='Jogos', jogos=lista)

@app.route('/novo')
def novo():
    return render_template('novo.html', titulo='Novo Jogo')

@app.route('/criar')
def criar():
    nome = request. form['nome']
    categoria = request. form['categoria']
    console = request. form['console']
    jogo = Jogo(nome, categoria, console)

app.run()
```

6) Retire a criação da lista de dentro do escopo da função ola, veja o código abaixo:

```
from flask import Flask, render_template, request

class Jogo:
    def __init__(self, nome, categoria, console):
        self.nome = nome
        self.categoria = categoria
        self.console = console

jogo1 = Jogo('Tetris', 'Puzzle', 'Atari')
jogo2 = Jogo('God of War', 'Hack n Slash', 'PS2')
jogo3 = Jogo('Mortal Kombat', 'Luta', 'PS2')
lista = [jogo1, jogo2, jogo3]

app = Flask(__name__)

@app.route('/inicio')
def ola():
    return render_template('lista.html', titulo='Jogos', jogos=lista)

@app.route('/novo')
def novo():
    return render_template('novo.html', titulo='Novo Jogo')

@app.route('/criar')
def criar():
    nome = request. form['nome']
    categoria = request. form['categoria']
    console = request. form['console']
    jogo = Jogo(nome, categoria, console)

app.run()
```

7) Utilize essa lista global para adicionar o jogo que veio através do request, olhe abaixo a função criar:

```
from flask import Flask, render_template, request

class Jogo:
    def __init__(self, nome, categoria, console):
        self.nome = nome
        self.categoria = categoria
        self.console = console

jogo1 = Jogo('Tetris', 'Puzzle', 'Atari')
jogo2 = Jogo('God of War', 'Hack n Slash', 'PS2')
jogo3 = Jogo('Mortal Kombat', 'Luta', 'PS2')
lista = [jogo1, jogo2, jogo3]

app = Flask(__name__)

@app.route('/inicio')
def ola():
    return render_template('lista.html', titulo='Jogos', jogos=lista)

@app.route('/novo')
def novo():
    return render_template('novo.html', titulo='Novo Jogo')

@app.route('/criar')
def criar():
    nome = request. form['nome']
    categoria = request. form['categoria']
    console = request. form['console']
    jogo = Jogo(nome, categoria, console)
    lista.append(jogo)
    return render_template('lista.html', titulo='Jogo', jogos=lista)

app.run()
```

8) Reinicie e teste sua aplicação, repare que teremos um erro, que vamos resolver logo em seguida.

9) Modifique a rota /criar para receber o método post (padrão do flask é get), veja o código abaixo:

```
from flask import Flask, render_template, request

class Jogo:
    def __init__(self, nome, categoria, console):
        self.nome = nome
        self.categoria = categoria
        self.console = console

jogo1 = Jogo('Tetris', 'Puzzle', 'Atari')
jogo2 = Jogo('God of War', 'Hack n Slash', 'PS2')
jogo3 = Jogo('Mortal Kombat', 'Luta', 'PS2')
lista = [jogo1, jogo2, jogo3]

app = Flask(__name__)

@app.route('/inicio')
def ola():
    return render_template('lista.html', titulo='Jogos', jogos=lista)

@app.route('/novo')
def novo():
    return render_template('novo.html', titulo='Novo Jogo')

@app.route('/criar', methods=['POST',])
def criar():
    nome = request. form['nome']
    categoria = request. form['categoria']
    console = request. form['console']
    jogo = Jogo(nome, categoria, console)
    lista.append(jogo)
    return render_template('lista.html', titulo='Jogo', jogos=lista)

app.run()
```

10) Reinicie sua app e veja que agora está tudo ok!

11) Resolva o problema de reiniciar a aplicação toda hora modificando a última linha do código, renomeie a função ola para index e altere sua rota para /, veja abaixo:

```
from flask import Flask, render_template, request

class Jogo:
    def __init__(self, nome, categoria, console):
        self.nome = nome
        self.categoria = categoria
        self.console = console

jogo1 = Jogo('Tetris', 'Puzzle', 'Atari')
jogo2 = Jogo('God of War', 'Hack n Slash', 'PS2')
jogo3 = Jogo('Mortal Kombat', 'Luta', 'PS2')
lista = [jogo1, jogo2, jogo3]

app = Flask(__name__)

@app.route('/')
def index():
    return render_template('lista.html', titulo='Jogos', jogos=lista)

@app.route('/novo')
def novo():
    return render_template('novo.html', titulo='Novo Jogo')

@app.route('/criar', methods=['POST',])
def criar():
    nome = request. form['nome']
    categoria = request. form['categoria']
    console = request. form['console']
    jogo = Jogo(nome, categoria, console)
    lista.append(jogo)
    return render_template('lista.html', titulo='Jogo', jogos=lista)

app.run(debug=True)
```
Observação: Repare que se você fez essas alterações (função index e rota /) após mudar a última linha, e reiniciar a aplicação, agora o flask irá restaurar sua app automaticamente toda vez que você salvar alguma alteração utilizando CMD + S ou CTRL + S no Pycharm.

9 - Revisando o que fizemos

[00:00] Vamos dar uma recapitulada em tudo que fizemos nessa aula, então nessa aula finalmente conseguimos criar um formulário que se colocarmos as informações de um jogo, e clicar em "salvar", ele vai realmente levar isso para lista, e vai conseguir adicionar esse novo item na nossa lista, e isso é interessante.

[00:18] Fizemos isso através da criação de uma rota chamada “criar”, que é a rota que justamente vai processar isso lá do lado do servidor, então a partir dessa página "novo", enviamos, através do formulário uma requisição post, enviamos as informações para o servidor que vai processar elas nessa rota "novo", então fomos lá no código em jogoteca.py e criamos uma rota que vai puxar as informações lá do novo.html.

[00:47] Lembrando que também tivemos que fazer aquela correção que apareceram aqueles problemas do método estar errado a princípio, então alteramos para o método post tanto em novo.html, quanto no jogoteca.py, que adicionamos o método post também.

[01:05] Adicionamos também um debug, então acionamos ele, colocamos como o status como ativo e isso vai facilitar nossa vida durante o processo de desenvolvimento, basta dar um salvar e o debugger sabe que tem alguma coisa mudada e já reinicia a aplicação para nós.

[01:25] Fizemos o teste justamente alterando a rota que antes era "início" para uma rota "barra", e isso também deixou o nosso site mais coerente com o restante da web que existe, a primeira página que acessamos de um site sempre a página barra, então por enquanto é isso que fizemos e eu te aguardo para próxima aula para continuarmos com nosso projeto.



04 - Melhorando o código e a usabilidade

1 - Projeto da aula anterior

2- Redirecionando para outra página

[00:00] Na última aula vimos que deu esse problema de confirmar reenvio de formulário, quando vamos dar um recarregar na página do site continua na rota criar, e pega as informações antigas do formulário, e não é interessante ficar nessa rota criar.

[00:16] É interessante que essa rota criar seja meio-termo entre o novo e a rota inicial, que é a barra ('/'), que é a que apresenta lista, então seria interessante que o "criar" seja só essa rota de processamento daquilo que o servidor está recebendo a partir do formulário do novo.

[00:36] Então vamos lá, ao invés de recarregarmos a página e ela ficar aqui, ela tem que ser redirecionada lá para página do barra, a página inicial.

[00:53] Então vamos fazer isso indo na rota criar em jogoteca.py e apagar essa parte que é render_template, e ao invés do render_template, vamos usar a função return redirect que é uma função helper que temos do Flask e podemos ir na primeira linha do código fazer a importação e puxar ela redirect, e embaixo usamos para fazer o redirecionamento dela para a rota barra. ('/').

```
from flask import Flask, render_template, request, redirect

@app.route('/criar', methods=['POST',])
def criar():
    nome = request. form['nome']
    categoria = request. form['categoria']
    console = request. form['console']
    jogo = Jogo(nome, categoria, console)
    lista.append(jogo)
    return redirect('/')

app.run(debug=True)
```

[01:30] E fazendo esse redirecionamento para a rota barra, agora não precisamos mais ter que nos preocupar com aquele erro que deu no início, então vou dar um “Ctrl + S” aqui e o nosso debuggerestá funcionando, só com esse savejá reiniciou a aplicação, vamos voltar para a nossa aplicação e vamos tentar mais uma vez.

[01:51] Na verdade temos que começar do zero, vamos para a página novo na URL (127.0.0.1:5000/novo), vamos tentar adicionar no formulário, "Need for Speed", "corrida", "PS2" e selecionar "salvar", deu certo, não deu erro no formulário, mas antes já não estava dando erro.

[02:08] Só que percebam na URL (127.0.0.1:5000)que não ficou na página criar, isso antes acontecia, agora está na página barra ('/'), então se eu der um refresh, recarregar a página, continua não dando mais erro.

[02:22] Nossa aplicação já está ficando bem legal, já está funcionando tudo, agora já conseguimos adicionar um jogo novo e isso é bem interessante, só que tem uma coisa incomodando.

[02:34] A aparência dela não está uma coisa legal, quer dizer, está jogado esse título “jogos” está grande, aí tem esse nome das colunas que está meio misturado, esse "Need for speed", não está tão separado de corrida, e até o próprio layoutse formos ver do novo, quando vamos criar, não está um layoutlegal também, então será que tem um jeito mais fácil de conseguirmos fazer um layoutbonito e rápido? Vamos ver isso no próximo vídeo.

3 - Redirecionando

Jonas tem um problema para resolver na sua aplicação Flask. O cliente pediu para ele criar uma rota de livros que verifique se o livro desejado existe no servidor. Se o livro existir, informações sobre o livro deverão ser exibidas. Caso contrário, ele deve mostrar a página de apostilas.

Ele já tem a função para a rota de livros:

```
@app.route('/livro', methods=['POST',])
def livro():
    encontrado = achar_livro(request.form['nome_do_livro'])
    return render_template('livro.html', livro=encontrado)
```

Como ele deve fazer a lógica para mostrar a página de apostilas reutilizando a rota já criada anteriormente?

```
@app.route('/livro', methods=['POST',])
def livro():
    encontrado = achar_livro(request.form['nome_do_livro'])
    if encontrado: 
        return render_template('livro.html', livro=encontrado)
    else:
        return redirect('/apostilas')
```
Neste caso usamos o redirect para chamar a rota já configurada de apostilas.

4 - Estilizando com Bootstrap

Você pode acessar o site do bootstrap usada para essa aula neste link


[00:00] Então o site está ficando legal igual vimos no último vídeo, mas está um pouco feio, a aparência não está muito legal, inclusive está começando a alterar, a incomodar a funcionalidade do site, porque se formos analisar o último jogo que inserimos na lista, o "Need for Speed", não sabemos direito onde que o "nome" termina e a "categoria" começa, está tudo muito junto, isso está alterando a funcionalidade do site, é ruim de se ver isso.

[00:33] Assim precisamos colocar algum estilo, precisamos fazer a aparência do site ficar mais amigável, e quando falo em estilo, eu falo em CSS, mas será que teria uma maneira de colocarmos um estilo no site sem adentrar muito no mundo do CSS, a verdade é que felizmente tem sim.

[00:53] Existe um framework chamado bootstrap que nos oferece um arquivo de CSS que faz uma estilização mínima no nosso site, que já vai corrigir esses pequenos problemas funcionais do site.

[01:07] Então vamos ao navegador, no Google, e procurar por "bootstrap", já é essa primeira página que aparece no mecanismo de busca que é o “getbootstrap.com” esse é o site oficial deles, então vamos já na página de download no canto superior direito da tela e selecionar download.

[01: 27] É importante aqui, a versão que vou utilizar para esse projeto a versão 5.1 e é essa que eu recomendo que vocês utilizem também, mas é importante que vocês notem também que se a versão que vão usar não vai ser uma versão Beta.

[1:41] Justamente a versão Beta é uma versão que ainda não está totalmente pronta, então essa versão 5.1, a 4.6, são versões estáticas já que já estão consolidadas, é difícil acontecer algum erro por causa dela. Então vamos sempre nos atentar a esse fato, se não tiver o Beta, vamos pegar uma versão estática, uma versão que já está pronta.

[02:08] Então vamos um pouco mais para baixo, e tem vários métodos de download do Bootstrap, eu poderia descer a página no instalador de pacotes o npm, e utilizar esse comando $ npm install bootstrap para instalar o Bootstrap, poderia, mas o que eu vou fazer vai ser fazer o download desse pacote "Compiled CSS and JS" que já vem um compilado do CSS e do JavaScript, não vamos utilizar JavaScript, só vamos pegar do CSS, mas eu vou fazer o download do pacote completo.

[02:34] Portanto, vou fazer o download, vai vir um arquivo zipado, é isso que quero, então eu vou abrir ele e extrair ele na minha pasta de downloads mesmo.

[02:49] Então está aqui, minha pasta de downloads com o arquivo zipado e ele já extraído dentro, então vou acessar a página do arquivo do Bootstrap e vai ter duas pastas dentro, CSS e JavaScript, como eu disse, JavaScript não vamos usar, vamos usar CSS, então vamos selecionar a pasta CSS, e a aqui vai ter inúmeras pastas e arquivos, e o que vamos usar vai ser esse "bootstrap.css", é essa que vamos pegar.

[03:18] Então vou clicar em "bootstrap.css" e copiar, um “Ctrl + C”, a princípio vai ser isso, e vamos voltar para o nosso código em jogoteca.py porque vamos inserir esse arquivo CSS, esse novo estilo que vamos colocar, então vamos lá no projeto, está aqui o projeto.

[03:36] Então como vamos inserir aqui? Assim como o Flask tem essa padronização quando se trata de páginas HTML, criar uma pasta chamada templates, também existe a mesma coisa quando falamos de estilos CSS, então o que vamos fazer vai ser é clicar com o botão direito do mouse em "jogoteca" do lado esquerdo e selecionar "New" e depois "Directory", para criar um diretório, com o nome de static.

[04:01] Essa é a padronização que o Flask que dá para arquivos de tipo de estilo CSS, então vou criar essa nova pasta “static”, e dentro dela eu vou colar o nosso arquivo “bootstrap.css”, dar clique em cima dela, e selecionei “Ctrl + V” para colar, então vou clicar no botão "ok", é isso mesmo que eu quero e pronto.

[04:32] Aqui eu já tenho aqui na pasta “static”, o “bootstrap.css” e daí ele já vem todo um arquivo com uma estilização já pré pronta para nós que vai servir para corrigir aqueles pequenos problemas que a temos lá que está chegando a pegar na funcionalidade, a falta de estilo está chegando a pegar na funcionalidade, a falta de personalidade.

[04:55] Então vou até fechar o “bootstrap.css” porque não vamos mexer nessa pasta, ela já está pronta para nós, então como que faço para esse estilo ser aplicado na minha página HTML? Eu vou vir aqui nas páginas HTML, novo.html e lista.html, e eu vou adicionar um link de stylesheet.

[05:13] Então eu vou na tag head e embaixo do título eu vou acrescentar uma nova tag, que é a tag de link que eu vou colocar uma relação de stylesheet já aparece para nós <link rel=”stylesheet” e agora inserir a referência, href=””, que vai ser justamente o caminho para se chegar nesse “bootstrap.css”, e o caminho que temos que colocar é o caminho das pastas.

[05:50] Então eu vou primeiro colocar dois pontos (..), que significa ir para pasta mais acima, ../static/ e agora o nome do arquivo que é bootstrap.css, e pronto temos já a referência, vou fechar a tag (>) e já estaria conseguindo puxar o estilo personalizado do bootstrap.

```
<link rel="stylesheet" href="../static/bootstrap.css">
```

[06:23] Só que não quero fazer isso só nesta página, quero fazer isso em todas as páginas HTML, então não vou fazer só na página "novo", vou fazer na "lista" também, então vou fazer “Ctrl + C” nessa linha que eu acabei de escrever, vou ir lá na lista.html e também vou adicionar aqui na tag head, logo abaixo do título, vou adicionar essa minha linha de link de stylesheet, que vai fazer essa ligação do estilo CSS com as páginas HTML. E pronto, vou dar um save para rodar de novo a aplicação.

[07:09] Agora vou à aplicação e dar um refresh e vamos ver o que acontece, note que já mudou, e agora nossa lista está bem melhor, agora já temos um título que já fica mais centralizado, temos os nomes das colunas separados dos próprios itens, eu já tenho uma separação, então tudo já está mais no seu lugar, também.

[07:37] Vamos dar uma analisada na página /novo. Aqui também temos um formulário um pouco melhor, então já deu uma boa melhorada na estrutura do site, isso é bem interessante.

[07:49] Só que tem uma questão, se voltarmos lá no código vamos ver que tem uma questão, eu estou utilizando esse estilo bootstrap, mas vamos supor que no futuro quero fazer meu próprio estilo, eu queira realmente estudar um pouco de CSS, fazer meu próprio estilo, ou de repente pegar outra biblioteca já pronta com CSS, e eu quero trocar esse daqui.

[08:13] Todas as páginas que eu tiver essa linha de código do link que eu fiz um “Ctrl + C”, que eu fiz um copiar e colar, eu vou ter que fazer isso todas as vezes, vou ter que vir aqui alterar o nome bootstrap em todas as pastas HTML, isto está meio ruim, não é uma boa prática de código termos que ficar fazendo “Ctrl + C”, “Ctrl + V” em outros arquivos, e não é uma boa prática termos que ficar voltando para alterar, então vamos ver no próximo vídeo uma maneira de contornarmos isso e deixar o nosso código um pouco mais dinâmico.



5 - Adicionando CSS

O cliente do João reclamou que as páginas do projeto de Jonas estão muito cruas e ficou na dúvida se, no fim, as telas ficarão daquele jeito. João, que não sabe muito sobre front-end, nem web design, decidiu adicionar o Bootstrap na aplicação.

Ele já fez parte do trabalho, que é adicionar o CSS na pasta convencionada (static). Só falta incluir o CSS (bootstrap.css) no HTML, que está na pasta templates. Selecione a opção que resolve a inclusão do CSS.


Adicionar no head do html a seguinte linha:
```
<link rel="stylesheet" href="../static/bootstrap.css">
```

Basta colocar um link com o caminho relativo saindo da pasta templates e entrando na pasta static.

6- Reutilizando partes do template

[00:00] No último vídeo vimos que existe um código duplicado nos arquivos HTML, acabamos de inserir uma linha que é o link que vai fazer essa ligação com arquivo CSS, e que não é interessante ter código duplicado porque se quisermos alterar algo no futuro vamos ter que ficar alterando em todos os arquivos em que esse código está duplicado.

[00:21] Só que se prestarmos atenção, não é só essa única linha duplicada no novo.html e no lista.html, toda essa parte inicial, desde do doctype, até essa primeira div, depois do body, essa div do título, tudo isso existe também no lista.html.

[00:41] Então selecionei essa parte e se você comparar com essa parte do código em lista.html, é a mesma coisa, assim existe bastante código duplicado e não é uma boa notícia, queremos dinamizar mais o código.

[00:55] Será que não tem uma maneira de deixar mais dinâmico? Será que não tem como criar uma forma de pegar todo esse código que é comum entre as nossas páginas HTML e deixar em um lugar específico? A verdade é que tem como fazermos isso e vamos fazer agora.

[01:10] A primeira coisa que vamos fazer é criar uma pasta HTML, vamos na nossa pasta “templates” do lado esquerdo e criar um arquivo HTML chamado template.html, pronto e criamos uma página, zerada, e o que vamos fazer nessa página é colar o código comum, aquele código que vimos que está realmente duplicado, o que eu já deixei selecionado, que eu estava mostrando para vocês.

[01:45] Então vamos dar um “Ctrl + C” nesse código, ir em templates.html e dar um “Ctrl + V”, esse é o código duplicado, só que tem umas tags que precisamos pegar, o fechamento delas, as tags de fechamento. Então, vamos voltar em novo.html e ver quais são as tags que fecham, são essas três últimas também damos um “Ctrl + C” nelas, e vamos voltar em template e colocar elas no final do código, arrumar a indentação.

Código em templates.html:

```
<!DOCTYPE html>
<html>
    <head>
    <meta charset="utf-8">
    <meta name="viewport" content="width=device-width, initial-scale=1">
    <title>Jogoteca</title>
        <link rel="stylesheet" href="../static/bootstrap.css">
</head>
<body>
    <div class="container">
      <div class="page-header">
          <h1>{{ titulo }}</h1>
      </div>



        </div>
    </body>
</html
```

[02:17] Essa parte inicial e essa parte final do nosso código do templates.html é a parte comum que existe em todos os arquivos HTML, o novo.html e o lista.html, e no meio é onde que tem o conteúdo diferenciado, o conteúdo que vai vir ali, que vai dar o fator único para cada página HTML.

[02:38] Então o que vamos fazer é usar uma diretiva, que é aquela chaves e porcentagem {% block conteudo %}, e vamos indicar que existe um bloco de conteúdo no meio, e também temos que fechar esse bloco, então também vou inserir, {% endblock %} e com essa diretiva, com esse código, vamos indicar que existe um conteúdo, travamos ele com essa variável de conteúdo.

```
{% block conteudo %}  {% endblock %}
```

[03:10] Então tranquilo, já temos o código duplicado nesse arquivo templates.html, então o que vamos fazer é voltar em novo.html, e agora que já temos o código duplicado lá, podemos remover daqui.

[03:34] E eu vou indicar que esse daqui é aquele bloco de conteúdo, esse código é o bloco que quero que seja envolto pelo conteúdo do template.html, então eu vou ir na primeira linha em novo.html e vou de novo, colocar a diretiva {% block conteudo %}, aqui, e eu vou lá embaixo onde pegamos o fechamento das tags e fechar esse bloco também, então {% endblock %}.

[04:10] Fechei esse bloco de conteúdo, só que isso não é suficiente, porque tenho que dar indicação da onde que quero que ele pegue o conteúdo que vai envolver ele, então eu tenho que dizer da onde que ele está pegando esse conteúdo estendido.

[04:26] Então é por isso que vou colocar em cima do início desse bloco, de novo a diretiva e depois extends {% extends e eu vou colocar o nome do arquivo html que é o template {% extends “template.html” %}, e eu fecho a diretiva e pronto, isso já vai ser o suficiente para ele puxar esse conteúdo que vai ser o envoltório do nosso código.

```
{% extends “template.html” %}
{% block conteudo %}

{% endblock %}
```

[05:05] Então vamos lá, vou dar um “Ctrl + S” para salvar e testar para ver como é que ficou essa página novo.html, para ver se teve alguma alteração. Vamos lá na nossa aplicação, na página “127.0.0.1:5000/novo", e eu vou acessar e dar refresh. Não aconteceu nada, e é para não acontecer nada, é para a aplicação continuar funcionando, e de fato está funcionando, não tivemos nenhuma alteração na página HTML e tornamos essa página “novo” mais eficiente.

[05:33] Vamos fazer o mesmo processo para página lista.html, vou tirar tudo o que for duplicado, também as tags de fechamento no final, e eu vou ir no novo.html e copiar esse código que é o código que torna ele um bloco de conteúdo e pega a extensão e o endblock também e colar em lista.html, vou ir ao final e colocar, pronto.

[06:02] Então vou dar um “Ctrl + S” novamente, está tudo certo, vou voltar no site e experimentar para ver a página inicial com a lista, e deu certo. Deu certo essa dinamização que fizemos, assim agora o código ficou bem melhor, só que ainda existem algumas boas práticas extras que podemos aprender, quando estamos criando novos templates e é isso que vamos ver na próxima aula.



7 - Evitando re-trabalho

Luiza começou a desenvolver e tem pouco tempo em Python e está usando o flask para criar seu primeiro projeto (talvez como você).

Durante o desenvolvimento ela criou diversas páginas HTML e adicionou estilo a todas estas páginas, mas agora ela quer adicionar a lib Materialize.css no projeto e não está querendo editar todos os arquivos de HTML que já criou.

De que formas a solução de templates (Jinja2) do Flask pode ajudá-la?

Ela poderia mexer sempre em um único lugar e refletir em todas as páginas.
Se criarmos um template pai para todas as páginas herdarem, é possível alterar somente este template refletindo nas outras páginas.


Ela conseguiria reduzir a repetição de código que gera problemas na hora de dar manutenção no projeto.
Quando fazemos herança de templates conseguimos diminuir e muito o código repetido no projeto.

8 - Gerando URLs dinâmicas

[00:00] Já tornamos o código um pouco mais dinâmico, mas ainda tem algumas questões de boas práticas que podemos ver. Vamos voltar em template.html e analisar a linha que já tínhamos colocado, é a linha que insere o estilo de CSS nas páginas HTML, sendo a <link rel="stylesheet" href="../static/bootstrap.css">.

[00:21] Observamos que nessa linha temos o que relaciona o stylesheet e temos o href que nos dá o endereço de onde está aquela pasta CSS que precisamos, e os dois (../) que fazem com que ele suba na primeira pasta, que é a jogoteca. Assim ele vai lá no diretório jogoteca com esses dois pontos, depois ele acessa a pasta static e depois ele procura um arquivo chamado "bootstrap.css" através desta pasta static que ele já acessou.

[00:57] Então existe um caminho completo e a partir desse caminho ele consegue encontrar o que precisamos, isso é interessante, mas não é exatamente uma boa prática, infelizmente, porque conforme vamos desenvolvendo o projeto a complexidade de hierarquias de pastas pode aumentar, porque de acordo com o padrão do Flask preciso colocar todos os meus estilos CSS na pasta “static”, sim, mas na parte “static”, posso ter várias outras pastas para organizar melhor os meus estilos.

[01:31] Logo pode ser que eu queira colocar “bootstrap” em outra subpasta dentro do “static”, ou então criar uma pasta com os estilos que eu mesmo criei.

[01:43] E aqui em templates.html a mesma coisa, tem também o Flask como padrão tem que ter essa pasta “templates”, mas na pasta “templates” posso ter várias outras pastas com denominações, uma organização que possa julgar melhor, então a hierarquia de pastas começa a ficar mais complicada.

[02:01] Portanto, colocar um caminho assim que diz exatamente da onde que ele tem que sair, da onde que ele tem que chegar se torna um pouco inviável conforme o projeto vai atingindo uma certa complexidade.

[02:13] Então que o que temos que fazer para deixar isso com uma melhor aparência, é usar uma função que o Flask disponibiliza para nós que é a função url_for, só que para conversarmos com o Flask no arquivo HTML, temos que usar a diretiva que é a chaves, chaves e essa função aqui vai nos ajudar.

```
<link rel="stylesheet" href={{ url_for }}>
```

[02:46] Dentro da função vou colocar, primeiramente, a pasta inicial onde se encontra esse arquivo CSS, que no caso é pasta “static”, como é padronizado que todos os arquivos CSS estão na pasta “static”, então isso é questão de padronização mesmo, sempre vai estar na pasta “static”, pelo menos os arquivos CSS, então basta colocarmos static aqui mesmo.

```
<link rel="stylesheet" href= {{ url_for('static') }} >
```

[03:12] Agora colocamos o arquivo que queremos que seja encontrado dentro dessa pasta, então vamos colocar filename=’bootstrap.css’ e pronto, assim ele vai encontrar o bootstrap, não importando em quantas páginas ele está inserido dentro de uma hierarquia complexa, contanto que ele esteja na pasta “static” e o nome dele seja bootstrap essa função vai encontrar a url que é o endereço que vai levar até ele.

```
<link rel="stylesheet" href= {{ url_for('static', filename=’bootstrap.css) }} >
```

[04:00] Então vamos salvar e testar, vamos lá na aplicação para ver se alguma coisa dá errado, e não, acabei de dar um refresh, não deu nada errado, pelo menos não nessa rota "novo", vamos ver na rota inicial, estou dando um refresh e nada está acontecendo e isso é um bom sinal porque nada era para acontecer mesmo, então dessa forma acabamos dinamizando um pouco mais, acabamos facilitando a mão de obra que teríamos caso precisássemos alterar algo no código.

[04:33] A aplicação está ficando bem interessante, contudo, agora, se eu tentar entrar e inserir um novo jogo, qualquer pessoa pode entrar, qualquer pessoa pode acessar essa URL de barra novo (/novo), eu queria que só amigos meus conseguissem fazer um cadastro de um novo jogo, queria que só pessoas que já tivessem um cadastro tivessem um usuário propriamente dito, pudessem criar um jogo e inserir ele nessa lista e, por enquanto, qualquer pessoa pode acessar mesmo, então como que fazemos para criar então esses usuários? Isso que vamos ver na próxima aula.



9 - Melhorando mais o projeto

Luiza refatora seu projeto, que tinha várias páginas. Depois da refatoração ficou com uma organização diferente.

Ela criou uma pasta para cada grupo de páginas e um template para cada grupo.

```
projeto
    - static
        > Materialize.css
    - templates
        > template.html
        - pessoas
            > pessoas.html
            > novo.html
            > template_pessoa.html
        - carros
            > carros.html
            > template_carro.html
```


Após fazer esta alteração, ela percebeu que ainda com o template e a herança de trechos de HTML deu um trabalhão para modificar os caminhos relativos para acessar o CSS. Que bom que temos a função url_for() que o Flask fornece para ajudar.

Responda como vai ficar o código que inclui o CSS corretamente e reduza esse retrabalho de alterar os caminhos relativos.


No template precisamos modificar para:
```
<link rel="stylesheet" href="{{ url_for('static', filename='Materialize.css') }}">
```
Estamos passando os parâmetros esperados. Lembre-se de passar o parâmetro nomeado "filename" sempre que quiser um arquivo específico.

10 - Faça como eu fiz: reduzindo a duplicação nos templates

Vamos fazer o que foi visto nos vídeos?

Clicando no link a seguir, você consegue fazer o download dos arquivos da aula 03!

1) Modifique o código da função criar, removendo o render_template e utilizando o redirect no return(lembre-se de importar o redirect no topo do código), veja abaixo:

```
from flask import Flask, render_template, request, redirect

class Jogo:
    def __init__(self, nome, categoria, console):
        self.nome = nome
        self.categoria = categoria
        self.console = console

jogo1 = Jogo('Tetris', 'Puzzle', 'Atari')
jogo2 = Jogo('God of War', 'Hack n Slash', 'PS2')
jogo3 = Jogo('Mortal Kombat', 'Luta', 'PS2')
lista = [jogo1, jogo2, jogo3]

app = Flask(__name__)

@app.route('/')
def index():
    return render_template('lista.html', titulo='Jogos', jogos=lista)

@app.route('/novo')
def novo():
    return render_template('novo.html', titulo='Novo Jogo')

@app.route('/criar', methods=['POST',])
def criar():
    nome = request. form['nome']
    categoria = request. form['categoria']
    console = request. form['console']
    jogo = Jogo(nome, categoria, console)
    lista.append(jogo)
    return redirect('/')

app.run(debug=True)
```

2) Salve as alterações para que sua app seja reiniciada e teste as mudanças.

3) Faça o download deste bootstrap.css. Para que não ocorram incompatibilidades.

4) Crie a pasta padrão do flask, chamada static, copie o arquivo bootstrap.css e coloque-o nessa pasta.

5) No arquivo novo.html, adicione a tag link, dentro da tag head, veja a tag link abaixo:

```
<link rel="stylesheet" href="../static/bootstrap.css">
```

Repita esse passo para todos os arquivos HTML, salve as alterações e veja o resultado.

6) Crie um arquivo template.html e remova a parte duplicada dos arquivos HTML, seu arquivo template.html deve ter o seguinte conteúdo:

```
<!DOCTYPE html>
<html>
  <head>
    <meta charset="utf-8">
    <meta name="viewport" content="width=device-width, initial-scale=1">
    <title>Jogoteca</title>
    <link rel="stylesheet" href="../static/bootstrap.css">
  </head>
  <body>
    <div class="container">
        <div class="page-header">
            <h1>{{ titulo }}</h1>
        </div>
    </div>
</body>
</html>
```

7) Ainda no arquivo template.html utilize a diretiva do jinja para adicionar o conteúdo dos outros arquivos. Verifique abaixo:

```
<!DOCTYPE html>
<html>
  <head>
    <meta charset="utf-8">
    <meta name="viewport" content="width=device-width, initial-scale=1">
    <title>Jogoteca</title>
    <link rel="stylesheet" href="../static/bootstrap.css">
  </head>
  <body>
    <div class="container">
        <div class="page-header">
            <h1>{{ titulo }}</h1>
        </div>
        {% block conteudo %}{% endblock %}
    </div>
</body>
</html>
```

8) Remova o conteúdo indesejado dos outros arquivos HTML e inclua as diretivas. Confira como eles devem ficar abaixo:

novo.html

```
{% extends "template.html" %}
{% block conteudo %}
      <form action="/criar" method="post">
        <fieldset>
          <div class="form-group">
            <label for="nome">Nome</label>
            <input type="text" id="nome" name="nome" class="form-control">
          </div>
          <div class="form-group">
            <label for="categoria">Categoria</label>
            <input type="text" id="categoria" name="categoria" class="form-control">
          </div>
          <div class="form-group">
            <label for="console">Console</label>
            <input type="text" id="console" name="console" class="form-control">
          </div>
          <button type="submit" class="btn btn-primary btn-salvar">Salvar</button>
        </fieldset>
      </form>
{% endblock %}
```

lista.html

```
{% extends "template.html"%}
{% block conteudo %}
    <table class="table table-striped table-responsive table-bordered">
        <thead>
            <tr>
                <th>Nome</th>
                <th>Categoria</th>
                <th>Console</th>
            </tr>
        </thead>
        <tbody>
        {% for jogo in jogos %}
                        <tr>
                            <td>{{ jogo.nome }}</td>
                            <td>{{ jogo.categoria }}</td>
                            <td>{{ jogo.console }}</td>
                        </tr>
        {% endfor %}
        </tbody>
    </table>
{% endblock %}
```

9) Abra o arquivo template.html e utilize a função url_for para gerar uma url dinâmica para o conteúdo, veja abaixo:

```
<!DOCTYPE html>
<html>
  <head>
    <meta charset="utf-8">
    <meta name="viewport" content="width=device-width, initial-scale=1">
    <title>Jogoteca</title>
    <link rel="stylesheet" href="{{ url_for('static', filename='bootstrap.css') }}">
  </head>
  <body>
    <div class="container">
        <div class="page-header">
            <h1>{{ titulo }}</h1>
        </div>
        {% block conteudo %}{% endblock %}
    </div>
</body>
</html>
```

10) Verifique se sua aplicação manteve o estilo do bootstrap!

11 - Revisando o que fizemos

[00:00] Vamos recapitular tudo que fizemos nessa aula, então nessa aula adicionamos um pouco mais de vida no nosso site adicionando realmente uma aparência, um estilo novo para ele, então ele está bem mais bonito do que estava na aula passada e fizemos isso através da adição do “bootstrap.css”, assim criamos essa pasta “static”, onde colocamos o bootstrap, então a pasta "static" é padronizada de acordo com Flask para colocarmos estilos CSS.

[00:35] Percebemos também que existia vários trechos de códigos duplicados nos arquivos “novo.html” e “lista.html”, para dinamizarmos um pouco mais criamos a pasta “template.html” em que colocamos tudo aquilo que fosse comum nos códigos HTML

[00:54] Fizemos um sistema de herança em que a “lista.html” herda do template.html aquilo que é duplicado, aquilo que é um código que acaba aparecendo tanto no “novo.html” quanto no “lista.html”, fizemos isso a partir dessas diretivas e desses comandos extends e block do Flask, isso é bem interessante, acabou dinamizando bastante o código.

[01:14] E por final viemos até o “template.html” e vimos que colocar URLs, colocar endereços completos no template não é interessante, porque a hierarquia da aplicação, pode ficar cada vez mais complexa conforme o projeto avança. Então aprendemos um pouco sobre essa url_for(), que é uma função que nos ajuda a encontrar caminhos de arquivos que precisamos encontrar.

[01:44] Então tudo isso contribuiu para o projeto ficar bem melhor, bem mais dinâmico e mais bonito também, então vamos para a próxima aula, vamos continuar estudando.



05 - Autenticando usuários com sessão do Flask

1 - Projeto da aula anterior

2 - Raciocínio de segurança

[00:00] Na última aula demos uma repaginada no visual do site agora ele está ficando bem mais bonito e também está bem funcional, já conseguimos adicionar novos itens na lista de jogos, novos jogos, e isso é interessante.

[00:14] Só que, por enquanto, qualquer pessoa que vem na URL e coloca “127.0.0.1:5000/novo” consegue adicionar um novo item, então eu posso vir e colocar "Valorant", "FPS", como categoria e no console "PC", selecionar "salvar" e pronto, isso vai ser adicionado na lista.

[00:36] Seria interessante que só pessoas que tivessem logadas no nosso site conseguissem fazer isso, seria legal se tivéssemos uma camada de segurança no site, que o site fizesse uma verificação para ver se a pessoa está logada, para ver se ela não está logada e para ver se ali em uma etapa de login as credenciais dela estão corretas, então adicionar realmente essa camada de segurança.

[01:01] Vamos fazer isso adicionando um pouco mais de complexidade na aplicação, ela vai ficar legal, mas antes vamos tentar entender como que vai ser esse raciocínio então, do que vamos fazer.

[01:13] Então vamos lá, temos a rota “/novo” barra novo, essa rota é aquela que utilizamos para colocar novos itens na lista, novos jogos, então o que vamos fazer vai ser adicionar uma etapa de verificação para ver se a pessoa que vai adicionar um novo jogo está logada ou não, se ela tiver logada, então ela vai conseguir colocar um novo item na lista, se ela não estiver logada ela vai ser encaminhada para uma página que ainda vamos criar para uma rota que vamos criar, “/login”.

[01:43] Nessa “/login” vamos ter um formulário, com um campo para usuário, um campo para senha, igual temos em muitos sites e o site vai ter uma etapa de autenticação, em que lá o servidor vai ver se as credenciais daquela pessoa que está tentando acessar, fornecidas na rota “/login”, se estão corretas mesmo, e se estiverem essa pessoa vai ser reencaminhada para página “/novo” e conseguir adicionar um novo item na lista.

[02:17] Se as credenciais dela estiverem incorretas, então ela vai voltar para página “/login” e vai ficar nesse loop infinito até conseguir colocar as credenciais certas, é o que acontece realmente em muitos sites.

[02:32] O que vamos fazer nessa parte de autenticação é adicionar uma rota intermediária igual fizemos lá no “/criar”, se vocês se lembram, então vamos ter essa rota intermediária que vai servir justamente para o servidor, para o Flask, processar essa autenticação, para ele entender se a pessoa está colocando as informações de forma correta na rota “/login”, no formulário.

[03:00] Então, mas é muita coisa que eu já falei aqui, mas vamos por partes, vamos coisa por coisa e por enquanto vamos nos concentrar nessa parte de “/login” e “/autenticar”. Vamos criar essas rotas e ver como elas vão funcionar, mas fazer tudo isso no próximo vídeo, até lá!



3 - Criando tela de login

[00:00] Então vamos criar essas novas rotas o “/login” e o “/autenticar”, vamos lá, vou aumentar um pouco o tamanho desse código, estamos no “jogoteca.py” e começar criando essa nova rota “/login” que precisamos.

[00:15] Da mesma forma que fizemos as outras, @app.route(), vamos colocar o nome que é ’/login’, e em seguida colocamos a função que vai instanciar a página, que vamos colocar o nome de login def login(): e depois fazemos aquele return com o render template :return render_template(‘’), e dentro vamos colocar o nome de uma página que ainda não criamos, que é a página ’login.html’ porque precisa ter o formulário para colocarmos as credenciais.

```
@app.route('/login')
def login():
    return render_template('login.html')
```

[00:59] Então vamos criar essa login.html, vamos na pasta templates, clicar com botão direito e criar um novo arquivo html nomeado login.html, já tem código que vem automático que vou apagar, e vou adicionar um código que já tenho.

Código login.html:

```
<!DOCTYPE html>
<html>
  <head>
    <meta charset="utf-8">
    <meta name="viewport" content="width=device-width, initial-scale=1">
    <title>Jogoteca</title>
    <link rel="stylesheet" href="{{ url_for('static', filename='bootstrap.css') }}">
  </head>
  <body>
    <div class="container">
        <h1>Faça seu login</h1>
        <form method="POST" action="/autenticar">
            <p><label>Nome de usuário:</label> <input class="form-control" type="text" name="usuario" required></p>
            <p><label>Senha:</label> <input class="form-control" type="password" name="senha" required></p>
            <p><button class="btn btn-primary" type="submit">Entrar</button></p>
        </form>
    </div>
</body>
</html>
```

[01:25] Então agora já era para estar funcionando, vou dar “Ctrl + S” para salvar, agora vamos à aplicação e checar, vou inserir na URL “/login”, e perceba que já temos um formulário para preenchermos as informações.

[01:41] Então vou testar, vou digitar "Bruno", a senha "1234" e selecionar “Enter”, vamos ver o que acontece, deu um erro "Not Found", está quebrado, e ele está tentando acessar uma página que é a “/autenticar” e não está acontecendo nada, está meio quebrado, mas ele já está indo na “/autenticar”?

[02:02] Vamos dar uma olhada lá no código, o login.html, a questão é que já inseri aquele trecho de código que já tínhamos visto, que era mudando o método para post e enviando as informações do formulário para o “/autenticar”, na linha 12, assim ele já está enviando para o “/autenticar” que ainda não temos, então vamos criar essa nova rota.

[02:23] Vamos digitar `@app.route(‘/autenticar’)e criar a função que instancia a página que é a função autenticar,def autenticar():`, só que antes de escrevermos a função, vamos tentar entender o que a rota “/autenticar” ela tem que fazer.

[03:00] Ela tem que fazer duas coisas, tem que verificar se as credenciais da pessoa que está tentando acessar se estão corretas, de fato, e precisa redirecionar a pessoa para as devidas páginas, se a autenticação der certo, se as credenciais da pessoa estiverem corretas, então ela tem que ser encaminhada para página da lista, para ela visualizar a lista.

[03:26] E se der errado, então ela tem que ser encaminhada para página de login novamente, para ficar naquele loop até conseguir acertar as credenciais, vamos lá, vamos fazer um if, por enquanto, vamos fazer essa autenticação apenas da senha.

[03:43] Então vamos colocar uma senha mestra, que a pessoa tem que acertar de qualquer forma, não importando o usuário dela, vamos inserir a senha if ’alohomora’, vamos lá, se alohomora, se a senha mestra é igual aquela que a pessoa está fornecendo para nós, então vamos colocar == request.form, já vimos essa função request pega as informações do formulário e agora temos que colocar o nome que é a referência para senha, então vamos voltar no login.html na linha 14, vamos ver na tag da senha, o nome dela é senha.

[04:30] Então vamos voltar para jogoteca.py, vamos colocar aspas simples e senha [‘senha’]:, então se alohomora for igual ao que o formulário está nos enviando, que a pessoa nos informou, ela está correta, então o credenciamento deu certo, e, portanto ela tem que ser enviada, tem que ser redirecionada, return redirect(‘/’), para a página barra ('/'), que é onde está a lista.

[05:07] Mas se não der certo, então eu tenho que ser redirecionado para página de login novamente, então else: return redirect(‘/login’), então, isso que tem que acontecer. Vamos selecionar “Ctrl + S” e ver se está funcionando. Voltando para aplicação, vou tentar acessar o caminho, “/login” novamente, vou inserir “Bruno”, a senha “alohomora”, e deu um problema, method not allowed, só que já encontramos esse problema antes, se vocês estão lembrados.

```
@app.route('/autenticar', methods=['POST', ])
def autenticar():
    if 'alohomora' == request.form['senha']:
        return redirect('/')
    else:
        return redirect('/login')
```

[05:57] O que acontece é que temos que ir à rota autenticar em jogoteca.py, e especificar o método, falar que o método não é só get, é post também, então vamos à rota colocar methods=[‘POST’], e passa aquela lista de métodos incluindo o post, então vamos selecionar “Ctrl + S”, voltar para aplicação e tentar novamente.

```
@app.route('/autenticar', methods=['POST', methods=['POST',])
```

[06:28] Então vamos digitar “/login” na URL, no nome “Bruno” e senha “alohomora”, pronto, deu certo, ela veio para nós a lista com todos os jogos. Mas, vamos analisar e se eu errasse, o que iria acontecer? Vamos vir digitar “/login” novamente, vou inserir "Bruno" e a senha "1234", ele voltou para mesma página, o que teria que acontecer mesmo, vou ficar no loop infinito até eu acertar as credenciais.

[07:05] Mas está meio estranho o site, ele não retorna nenhum aviso quando consigo acessar a lista ou quando erro a credencial, isso não é legal, parece que o site não me dá nenhuma informação, parece que ficou parado no mesmo lugar no caso se eu errar, então seria interessante que ele me desse essa informação o que eu errei e o que eu não errei, é isso que vamos ver na próxima aula.



4 - Criando um formulário de login

Jonas precisa criar uma página de login para que algumas páginas sejam protegidas por senha. Para que o formulário fique funcional, ele tem que adicionar algumas informações no template.

As alternativas mostram o que é necessário para que ele consiga enviar um POST para uma rota configurada no servidor Flask, exceto:


Campos com atributo id preenchido.
Os atributos id não são necessários para identificar os campos no servidor, apenas o atributo name é suficiente.

5 - Guardando dados na sessão

00:00] Então queremos que a aplicação comece a reter as informações da pessoa que está logando, então o nome do usuário, por exemplo, porque se viermos na URL e digitar "/login" e tentar fazer o login, vou inserir meu nome e a senha certa, ele me traz para a página de lista só que não reteve a informação de que o nome é Bruno, nome do usuário que acabou de logar é Bruno, e ele não sabe que existe essa funcionalidade de estar logado.

[00:35] Além de não mostrar nenhuma mensagem dizendo que estou logado, então eu como usuário ficou meio perdido, será que deu certo a autenticação, será que não deu certo? Porque não é só porque estou na página de lista, que significa que deu tudo certo, então ele não mostra nenhuma mensagem, não se comunica muito conosco, não mostra se deu certo ou não deu certo o login.

[00:52] Então vamos fazer isso, vamos acrescentar essas coisas no código, voltando para o código em jogoteca.py, e para fazer para o Flask guardar informações temos um recurso chamado session, já vou importar então, ele nos permite reter informações por mais de um ciclo de request, e faz isso guardando as informações nos cookies do navegador.

```
from flask import Flask, render_template, request, redirect, session
```

[01:16] Então não é nem bem o servidor que guarda as informações, o Flask em si, mas sim os cookies do navegador, isso é bem interessante. Então, vamos aplicar o session na rota autenticar, e na primeira condição do if, já vamos invocar o session[], e dentro do session, vamos colocar uma chave, vamos colocar colchetes e criar uma chave para o array, chamado, session[ ’usuario_logado’ ] =, e aqui vamos atribuir o nome do usuário que está vindo lá do forms do “login.html”.

[02:01] Então vamos colocar = request.form[], e colocar o nome que está associado ao usuário lá no login.html, então vamos no login.html e o nome que está associado é usuário, então usuario, e pronto, já temos o nome do usuário salvo.

```
@app.route('/autenticar', methods=['POST', ])
def autenticar():
    if 'alohomora' == request.form['senha']:
        session['usuario_logado'] = request.form['usuario']
        return redirect('/')
    else:
        return redirect('/login')

app.run(debug=True)
```

[02:24] Então agora quero que mostre uma mensagem, dizendo que foi logado de forma bem sucedida, e vamos fazer isso através de uma função associada ao session, chamada flash(), essa função permite que coloquemos uma mensagem rápida e única para a pessoa, mostrando no site para o usuário.

[02:46] Então vamos inserir uma mensagem de, flash(’Usuário logado com sucesso!’), mas espera aí, então tenho o nome guardado no session, vou pegar essa informação, vou fazer uma concatenação no flash, já que o Python nos permite, vamos fazer uma concatenação, flash(session[‘usuario_logado’] + ‘logado com sucesso’), se o login for bem-sucedido vai aparecer que está o usuário foi logado com sucesso.

[03:25] E agora uma mensagem que caso falhe a autenticação, então vou colocar else: flash(‘Usuário não logado’), antes de darmos o “Ctrl + S” e botar para funcionar, temos que importar o flash da função flash também, em seguida, vamos dar um “Ctrl + S” finalmente para testar, voltando para a aplicação.

```
from flask import Flask, render_template, request, redirect, session, flash

@app.route('/autenticar', methods=['POST', ])
def autenticar():
    if 'alohomora' == request.form['senha']:
        session['usuario_logado'] = request.form['usuario']
        flash(request.form['usuario'] + ' logou com sucesso!')
        return redirect('/')
    else:
        flash('Usuário não logado.')
        return redirect('/login')

app.run(debug=True)
```

[03:58] Vou acessar a página de login e vou digitar o meu nome e vou colocar qualquer senha, para que dê errado, para analisar se vai dar certo, deu erro "RuntimeError", mas não dá forma que queríamos, apareceu um erro meio estranho, o que ele está dizendo é que precisamos de uma coisa chamada secret key, que é uma chave secreta mesmo, por que precisamos de uma chave secreta?

[04:23] Porque estamos guardando as informações no navegador, nos cookies do navegador, e pode ser que uma pessoa mal-intencionada, acesse a aplicação e tente alterar as informações guardadas no cookie, então precisamos adicionar uma camada de criptografia no site.

[04:39] Então precisamos retornar no código em jogoteca.py e adicionar essa chave secreta que vai dar essa criptografia. Logo depois do trecho que instância a aplicação, vamos digitar app.secret_key = ‘alura’, já tem aparece para nós, uma chave da sua escolha, vou colocar Alura e pronto, vou selecionar “Ctrl + S” para recarregar a aplicação.

```
app = Flask(__name__)
app.secret_key = 'alura'
```

[05:10] Voltando na aplicação, vamos tentar novamente fazer o login. Então “127.0.0.1:5000/login” vou digitar meu nome e qualquer senha para dar errado, vamos analisar se vai dar certo, porém do jeito errado agora.

[05:27] Então não aparece aquele erro, mas não apareceu a mensagem, tinha que aparecer uma mensagem dizendo que eu não consegui efetuar o login. Vamos analisar no código o motivo, o ponto é que alteramos tudo que precisávamos no jogoteca.py, mas não alteramos o arquivo login.html, e precisamos alterar, porque é no final das contas no HTML que vai aparecer a mensagem e é fácil fazer isso?

[05:56] Não é bem assim, eu gostaria de dizer que sim, mas não é, tem um trecho de código que precisamos colocar que é bem específico do Flask e retirei da documentação. Então vai estar pronto e vou colar esse trecho de código depois de <div class="container"> e indentar, ele adiciona toda uma complexidade utilizando alguma lógica do próprio HTML, então é esse código que vamos utilizar, garantindo que apareça as mensagens corretas na página HTML.

```
{% with messages = get_flashed_messages() %}
            {% if messages %} 
                <ul id="messages" class="list-unstyled">
                {% for message in messages %}
                    <li class="alert alert-success">{{ message }}</li>
                {% endfor %}
                </ul>
            {% endif %}
        {% endwith %}
```

[06:37] Então adicionei na página de login.html e vamos aproveitar e adicionar nas outras páginas HTML também, faremos isso alterando em template.html, lembra ser uma boa prática alterarmos diretamente no template, e vou colar o código logo após a <div class="container"> e vou indentar direito.

[07:16] Selecionando o “Ctrl + S” agora e vou tentar novamente ver se a aplicação vai funcionar, voltando para a aplicação, vou dar um “Enter”, perceba que já apareceu uma mensagem que veio do login antigo. Mas vou recarregar novamente e inserir meu nome, uma senha aleatória e vamos ver se vai dar certo. Não deu certo, mas agora do jeito certo mesmo e o usuário não foi logado, ele mostrou a mensagem para nós "Usuário não logado".

[07:48] Então vamos analisar o que acontece se colocarmos a senha certa, alohomora, é exibida a lista e mostra uma mensagem de “Bruno logado com sucesso!”, então deu certo colocar as mensagens, só que deixa eu perguntar uma coisa, será que faz sentido conseguirmos logar, mas não consegui deslogar? Então ainda não tem essa funcionalidade, ainda não conseguimos deslogar, e isso seria interessante.

[08:16] E também se eu for na etapa de “/novo” e tentar adicionar algum outro item, conseguimos adicionar outro item, deixa eu colocar "Valorant", "FPS" e "PC". Consegui adicionar com sucesso e isso é meio estranho, porque toda a ideia de colocarmos um login, uma camada de autenticação era que não conseguíssemos acessar essa página e restringisse essa página para nós, e até agora isso não está funcionando, então vamos verificar isso na próxima aula.



6 - Para saber mais: Sessions no Flask

Session é um recurso do Flask que permite um armazenamento temporário de dados que persiste as informações coletadas por mais de um ciclo de request.

Ciclo de Request



Isso é feito através do armazenamento dos dados no Client-side (Lado do cliente) da aplicação, ou seja, no navegador, através dos cookies.

A session consegue persistir os dados através de cryptographically-signed cookies (cookies assinados criptograficamente). Esses cookies são enviados a cada ciclo de request para o servidor, onde são processados da forma que a aplicação demanda.

É necessária a configuração de uma secret_key no servidor para a utilização da session . Isso é essencial para garantir uma maior segurança dos dados guardados nos cookies, já que uma pessoa má intencionada poderia acessar os cookies do navegador e mudar os seus dados armazenados.

A secret_key fornece um nível de assinatura criptográfica aos cookies. Isso significa que seu conteúdo não pode ser alterado. Porém, é importante ressaltar que a natureza criptográfica dos cookies não necessariamente impede a visualização dos dados.

Portanto, apesar de não ser recomendada a utilização de sessions para armazenamento de dados sensíveis e dependerem do tamanho máximo de armazenamento dos cookies (por volta de 4 KB), sessions se apresentam como um recurso poderoso do Flask, sendo rápidas de instanciar e fáceis de escalar.



7 - Colocando dados em sessão

Patrícia tem uma aplicação que cadastra receitas de bolo. Sempre que alguém cadastrar uma receita, ela quer que sua aplicação mostre a tela com todas as receitas e também mostrar a mensagem "A receita {nome_da_receita} foi salva com sucesso!"

O problema é que para mostrar o nome da receita na página com a listagem de receitas será necessário armazenar este nome na sessão, já que quando fazemos um redirect para a listagem perdemos as informações do request anterior.

Como ela pode inserir dados na sessão do Flask?


Importar o objeto session na aplicação e incluir uma nova chave neste objeto, que é um dicionário.
Este é o dicionário que guarda os itens de sessão. É o local ideal para armazenar o nome da receita.

8 - Para saber mais: Flash e Documentação

Interatividade com o usuário é algo muito importante para qualquer aplicação web. Sempre é interessante que o usuário receba feedbacks constantes de suas ações ao navegar pelo website.

No caso do projeto da Jogoteca, nós utilizamos um recurso do Flask chamado Flash. Esse recurso funciona com a utilização de cookies do navegador e nos permite mostrar mensagens curtas de forma eficiente na interface da nossa aplicação.

Para poder mostrar a mensagem na nossa página da aplicação é necessário alterar os templates HTML com a adição de um bloco de código já fornecido pela Documentação do Flask na seguinte página:

- Message Flashing

```
<!-- Bloco de código da documentação →
<title>My Application</title>
{% with messages = get_flashed_messages() %}
  {% if messages %}
    <ul class=flashes>
    {% for message in messages %}
      <li>{{ message }}</li>
    {% endfor %}
    </ul>
  {% endif %}
{% endwith %}
{% block body %}{% endblock %}
```

É natural que ao longo da utilização de uma tecnologia tenhamos que recorrer múltiplas vezes à sua documentação e, em muitos casos, a própria documentação já oferece soluções inteligentes para o uso de certos recursos da ferramenta em questão.

Encorajo que você consulte sempre que possível a documentação do Flask. Dessa forma, estará sempre evoluindo no seu conhecimento do framework diretamente da fonte.

- Documentação do Flask

9 - Recuperando dados da sessão na view

A Patrícia conseguiu incluir o nome da receita salva na sessão do Flask, mas infelizmente ela não configurou o secret_key da sessão, e o Flask não deixa ela continuar se não fizer isso.

Como ela pode configurar este secret_key para ter mais confiabilidade nos dados da sessão?


Depois de instanciar a classe Flask, pegar a instância e definir o atributo secret_key com um valor string que será usado para encriptar os dados da sessão.
Com essa configuração o Flask permite que o objeto session seja utilizado.

10 - Deslogar da sessão

[00:00] Vamos adicionar uma nova rota para podermos fazer o logout, porque até agora conseguimos fazer o login, mas não o logout, isso não faz muito sentido, então, vamos ao código em jogoteca.py adicionar essa nova rota.

[00:14] Então vamos à parte inferior mesmo para adicionar essa nova rota da mesma forma que fizemos as outras, "@app.route()", o nome da rota que será ’/logout’ e uma função para instanciar chamada def logout():.

[00:41] E o que vamos fazer? Como que fazemos o logout da aplicação, então o que define que realmente fizemos o login, fizemos o login quando o session guarda o nome do usuário, é isso que definimos como estar logado, então para fazermos o logout, precisamos tirar o nome do usuário do session.

[01:04] Então vamos fazer session[‘usuario_logado’] = None, isso vai fazer com que o session, fique vazio e não grave mais o nome do usuário, então vamos tirar, fazer o logout do usuário.

[01:33] E vamos colocar uma mensagem informando que flash(‘Logout efetuado com sucesso!’), e redirecionar para alguma página, vamos terminar fazendo um return redirect(‘/’) e redirecionar para página inicial mesmo, a página barra e pronto.

```
@app.route('/logout')
def logout():
    session['usuario_logado'] = None
    flash('Logout efetuado com sucesso!')
    return redirect('/')

app.run(debug=True)
```

[02:22] Então criamos a nova rota de logout, selecionando “Ctrl + S”, e vamos ver, vou dar um iniciar, na verdade, na parte inferior no ícone verde, e vamos analisar se deu certo no site. Farei o login primeiro, como o Bruno, senha alohomora, estou logado, agora eu quero fazer o logout, na URL vou digitar /logout, e pronto, a mensagem exibida é "logout efetuado com sucesso!".

[02:53] Então criamos uma rota para fazer o logout, só que ainda não aprimoramos a parte que estávamos falando sobre restrição, restringir determinadas rotas, porque ainda consigo ir em “/novo” e inserir um novo jogo e nada me impede de fazer isso, então vamos ver isso na próxima aula.



11 - Faça como eu fiz: fazendo autenticação

Este é o momento de implementarmos as funcionalidades que vimos no capítulo.

Clicando no link a seguir, você consegue fazer o download dos arquivos da aula 04

1) Crie uma rota para o login, veja como o código deve estar:

```
from flask import Flask, render_template, request, redirect

class Jogo:
    def __init__(self, nome, categoria, console):
        self.nome = nome
        self.categoria = categoria
        self.console = console

jogo1 = Jogo('Tetris', 'Puzzle', 'Atari')
jogo2 = Jogo('God of War', 'Hack n Slash', 'PS2')
jogo3 = Jogo('Mortal Kombat', 'Luta', 'PS2')
lista = [jogo1, jogo2, jogo3]

app = Flask(__name__)

@app.route('/')
def index():
    return render_template('lista.html', titulo='Jogos', jogos=lista)

@app.route('/novo')
def novo():
    return render_template('novo.html', titulo='Novo Jogo')

@app.route('/criar', methods=['POST',])
def criar():
    nome = request. form['nome']
    categoria = request. form['categoria']
    console = request. form['console']
    jogo = Jogo(nome, categoria, console)
    lista.append(jogo)
    return redirect('/')

@app.route('/login')
def login():
    return render_template('login.html')

app.run(debug=True)
```

2) Crie um novo arquivo HTML, usamos o nome login.html e cole o conteúdo abaixo:

```
<!DOCTYPE html>
<html>
  <head>
    <meta charset="utf-8">
    <meta name="viewport" content="width=device-width, initial-scale=1">
    <title>Jogoteca</title>
    <link rel="stylesheet" href="{{ url_for('static', filename='bootstrap.css') }}">
  </head>
  <body>
    <div class="container">
        <h1>Faça seu login</h1>
        <form method="POST" action="/autenticar">
            <p><label>Nome de usuário:</label> <input class="form-control" type="text" name="usuario" required></p>
            <p><label>Senha:</label> <input class="form-control" type="password" name="senha" required></p>
            <p><button class="btn btn-primary" type="submit">Entrar</button></p>
        </form>
    </div>
</body>
</html>
```

3) Teste a rota e veja se a tela de login será exibida.

4) Crie a rota de /autenticar, veja como o código deve ficar abaixo:

```
from flask import Flask, render_template, request, redirect

class Jogo:
    def __init__(self, nome, categoria, console):
        self.nome = nome
        self.categoria = categoria
        self.console = console

jogo1 = Jogo('Tetris', 'Puzzle', 'Atari')
jogo2 = Jogo('God of War', 'Hack n Slash', 'PS2')
jogo3 = Jogo('Mortal Kombat', 'Luta', 'PS2')
lista = [jogo1, jogo2, jogo3]

app = Flask(__name__)

@app.route('/')
def index():
    return render_template('lista.html', titulo='Jogos', jogos=lista)

@app.route('/novo')
def novo():
    return render_template('novo.html', titulo='Novo Jogo')

@app.route('/criar', methods=['POST',])
def criar():
    nome = request. form['nome']
    categoria = request. form['categoria']
    console = request. form['console']
    jogo = Jogo(nome, categoria, console)
    lista.append(jogo)
    return redirect('/')

@app.route('/login')
def login():
    return render_template('login.html')

@app.route('/autenticar', methods=['POST', ])
def autenticar():
    if 'alohomora' == request.form['senha']:
        return redirect('/')
    else:
        return redirect('/login')

app.run(debug=True)
```

5) Altere a função autenticar para trabalhar com session, não esqueça de importá-lo no início do código, implemente também a mensagem de confirmação de login, utilizando flash (importe o flash também!).

```
from flask import Flask, render_template, request, redirect, session, flash

class Jogo:
    def __init__(self, nome, categoria, console):
        self.nome = nome
        self.categoria = categoria
        self.console = console

jogo1 = Jogo('Tetris', 'Puzzle', 'Atari')
jogo2 = Jogo('God of War', 'Hack n Slash', 'PS2')
jogo3 = Jogo('Mortal Kombat', 'Luta', 'PS2')
lista = [jogo1, jogo2, jogo3]

app = Flask(__name__)

@app.route('/')
def index():
    return render_template('lista.html', titulo='Jogos', jogos=lista)

@app.route('/novo')
def novo():
    return render_template('novo.html', titulo='Novo Jogo')

@app.route('/criar', methods=['POST',])
def criar():
    nome = request. form['nome']
    categoria = request. form['categoria']
    console = request. form['console']
    jogo = Jogo(nome, categoria, console)
    lista.append(jogo)
    return redirect('/')

@app.route('/login')
def login():
    return render_template('login.html')

@app.route('/autenticar', methods=['POST', ])
def autenticar():
    if 'alohomora' == request.form['senha']:
        session['usuario_logado'] = request.form['usuario']
        flash(request.form['usuario'] + ' logou com sucesso!')
        return redirect('/')
    else:
        flash('Usuário não logado.')
        return redirect('/login')

app.run(debug=True)
```

6) Adicione uma secret key na sua app, logo abaixo da declaração do objeto Flask, veja abaixo:

```
from flask import Flask, render_template, request, redirect, session, flash

class Jogo:
    def __init__(self, nome, categoria, console):
        self.nome = nome
        self.categoria = categoria
        self.console = console

jogo1 = Jogo('Tetris', 'Puzzle', 'Atari')
jogo2 = Jogo('God of War', 'Hack n Slash', 'PS2')
jogo3 = Jogo('Mortal Kombat', 'Luta', 'PS2')
lista = [jogo1, jogo2, jogo3]

app = Flask(__name__)
app.secret_key = 'alura'      # Aqui!!!

@app.route('/')
def index():
    return render_template('lista.html', titulo='Jogos', jogos=lista)

@app.route('/novo')
def novo():
    return render_template('novo.html', titulo='Novo Jogo')

@app.route('/criar', methods=['POST',])
def criar():
    nome = request. form['nome']
    categoria = request. form['categoria']
    console = request. form['console']
    jogo = Jogo(nome, categoria, console)
    lista.append(jogo)
    return redirect('/')

@app.route('/login')
def login():
    return render_template('login.html')

@app.route('/autenticar', methods=['POST', ])
def autenticar():
    if 'alohomora' == request.form['senha']:
        session['usuario_logado'] = request.form['usuario']
        flash(request.form['usuario'] + ' logou com sucesso!')
        return redirect('/')
    else:
        flash('Usuário não logado.')
        return redirect('/login')

app.run(debug=True)
```

7) Abra o arquivo login.html e cole o código abaixo acima da tag h1, o arquivo deve ficar da seguinte forma:

```
<!DOCTYPE html>
<html>
  <head>
    <meta charset="utf-8">
    <meta name="viewport" content="width=device-width, initial-scale=1">
    <title>Jogoteca</title>
    <link rel="stylesheet" href="{{ url_for('static', filename='bootstrap.css') }}">
  </head>
  <body>
    <div class="container">
        {% with messages = get_flashed_messages() %}
            {% if messages %} 
                <ul id="messages" class="list-unstyled">
                {% for message in messages %}
                    <li class="alert alert-success">{{ message }}</li>
                {% endfor %}
                </ul>
            {% endif %}
        {% endwith %}

        <h1>Faça seu login</h1>
        <form method="POST" action="/autenticar">
            <p><label>Nome de usuário:</label> <input class="form-control" type="text" name="usuario" required></p>
            <p><label>Senha:</label> <input class="form-control" type="password" name="senha" required></p>
            <p><button class="btn btn-primary" type="submit">Entrar</button></p>
        </form>
    </div>
</body>
</html>
```

8) Copie o código adicionado em login e coloque no arquivo template.html, veja o resultado abaixo:

```
<!DOCTYPE html>
<html>
  <head>
    <meta charset="utf-8">
    <meta name="viewport" content="width=device-width, initial-scale=1">
    <title>Jogoteca</title>
    <link rel="stylesheet" href="{{ url_for('static', filename='bootstrap.css') }}">
  </head>
  <body>
    <div class="container">

        {% with messages = get_flashed_messages() %}
            {% if messages %} 
                <ul id="messages" class="list-unstyled">
                {% for message in messages %}
                    <li class="alert alert-success">{{ message }}</li>
                {% endfor %}
                </ul>
            {% endif %}
        {% endwith %}

        <div class="page-header">
            <h1>{{ titulo }}</h1>
        </div>
        {% block conteudo %}{% endblock %}
    </div>
</body>
</html>
```

9) Teste a funcionalidade e veja se está funcionando!

10) Crie uma rota para deslogar o usuário, veja a função no final do código:

```
from flask import Flask, render_template, request, redirect, session, flash

class Jogo:
    def __init__(self, nome, categoria, console):
        self.nome = nome
        self.categoria = categoria
        self.console = console

jogo1 = Jogo('Tetris', 'Puzzle', 'Atari')
jogo2 = Jogo('God of War', 'Hack n Slash', 'PS2')
jogo3 = Jogo('Mortal Kombat', 'Luta', 'PS2')
lista = [jogo1, jogo2, jogo3]

app = Flask(__name__)
app.secret_key = 'alura'     

@app.route('/')
def index():
    return render_template('lista.html', titulo='Jogos', jogos=lista)

@app.route('/novo')
def novo():
    return render_template('novo.html', titulo='Novo Jogo')

@app.route('/criar', methods=['POST',])
def criar():
    nome = request. form['nome']
    categoria = request. form['categoria']
    console = request. form['console']
    jogo = Jogo(nome, categoria, console)
    lista.append(jogo)
    return redirect('/')

@app.route('/login')
def login():
    return render_template('login.html')

@app.route('/autenticar', methods=['POST', ])
def autenticar():
    if 'mestra' == request.form['senha']:
        session['usuario_logado'] = request.form['usuario']
        flash(request.form['usuario'] + ' logou com sucesso!')
        return redirect('/')
    else:
        flash('Usuário não logado.')
        return redirect('/login')

@app.route('/logout')
def logout():
    session['usuario_logado'] = None
    flash('Logout efetuado com sucesso!')
    return redirect('/')

app.run(debug=True)
```

12 - Revisando o que fizemos

[00:00] Vamos recapitular tudo que fizemos nessa aula, então vamos no código. Criamos três novas rotas ao longo dessa aula, a rota de login que nos dá um formulário que podemos colocar credenciais e fazer o login.

[00:17] Também colocamos uma rota que é específica só para fazer autenticação desse login, e nessa rota utilizamos o session, sendo um atributo do Flask para guardar certas informações do usuário quando ele está fazendo o login nos cookies do navegador.

[00:35] Então isso é bem interessante, ele captura essas informações e nos permite usar mais tarde, como fizemos na mensagem que colocamos também caso o login for bem-sucedido, então colocamos mensagens para interagir mais com usuário quando está usando o site.

[00:52] E fizemos uma rota de logout também para podermos esquecer essa informação de usuário quando é interessante que esqueçamos, e fizemos algumas alterações nos HTMLs, o HTML de login que criamos também nessa aula, e adicionamos esse código para ser possível a mensagem, um código recomendado pela própria documentação para utilizarmos, e fizemos essa alteração também no template.

[01:21] E por enquanto é assim que está ficando a aplicação, cada vez mais vamos aumentando a complexidade dela, cada vez mais ela vai ficando mais interessante, então vejo você na próxima aula.



06 - Implementando autorização para criar jogos

1 - Projeto da aula anterior

2 - Protegendo uma rota

[00:00] Já demos uma aprimorada na segurança do website, porém, não exatamente, porque se eu ir à rota “/novo” para tentar acrescentar um novo item na lista, vou digitar "Skyrim" no nome, na categoria "RPG", no console "PC" e selecionar "salvar". Consegui adicionar um novo item na lista, porém, não estou logado, em nenhum momento realizei o login, então, uma pessoa aleatória consegue ainda adicionar jogos na lista e esse não era o intuito de todo o raciocínio de segurança.

[00:42] Se relembrarmos o que fizemos, já criamos a rota de “/login” e “/autenticar” que pede as informações de login, as credenciais e autêntica, analisando se elas estão corretas, inclusive criamos até uma rota extra, sendo a rota logout, porque se alguém faz login, ela tem que fazer logout.

[01:06] Só que faltou uma coisa, não temos uma etapa que verifica se a pessoa fez o login, de fato, ou não, para ela poder criar um item, para ela poder até acessar página “/novo”, então não temos essa etapa de verificação, não temos nada que analise se a pessoa está logada ou não, e que restrinja página de “/novo” caso ela não esteja.

[01:26] Vamos adicionar essa restrição no código em jogoteca.py, então na rota “/novo” vamos acrescentar alguma coisa, mas antes vamos relembrar como funciona o processo de login. Quando vamos fazer o login, no “/autenticar”, o que acontece é que criamos um objeto session onde dentro dele vai ter uma chave chamada “usuário logado”, que vai guardar o nome do usuário e isso significa que o usuário está logado, que é quando ele guarda essa informação.

[01:54] Então vamos à rota `@app.router(‘/novo’)e estabelecer uma condicional, assim:if ‘’usuario_logado’ not in session: return redirect(‘/login’)`, eu quero que ele retorne e seja jogado para página “/login”.

```
@app.route('/novo')
def novo():
    if 'usuario_logado' not in session:
        return redirect('/login')
    return render_template('novo.html', titulo='Novo Jogo')
```

[02:36] O que estou dizendo é que se não houver nenhuma chave chamada usuário logado na sessão, então significa que o usuário ainda não logou, que o usuário ainda não passou pelo processo de login e, portanto, quero que ele passe pelo processo de login, quero que seja redirecionado para rota “/login”.

[02:58] Entretanto, se pensarmos um pouco, esse não é o único caso que vamos ter para redirecionarmos a pessoa para “/login”, porque se formos analisar mais para baixo do código, temos a rota de logout, uma pessoa pode fazer logout e o que consideramos como logout é ir ao objeto, na session, na chave usuário logado e definir que ela vai ser None, definir o valor para ela de None, criamos um usuário logado e definimos o valor de None para ela, então também existe esse caso para acrescentarmos.

[03:30] Então vamos acrescentar caso de or session[‘usuario_logado’] == None, então se o usuário logado não estiver em seção, no objeto session, ou então se o objeto do usuário logado for igual a None quero que ele redirecione para a rota de “/login”.

```
@app.route('/novo')
def novo():
    if 'usuario_logado' not in session or session['usuario_logado'] == None:
        return redirect('/login')
    return render_template('novo.html', titulo='Novo Jogo')
```

[04:08] Vamos ver essa restrição funcionou, vou salvar esse código e vamos voltar para a aplicação, eu não efetuei o login, vou tentar acessar página de “/novo” e note, ele já me reencaminhou, ele não deixa fazer isso, ele me encaminhou para página de login.

[04:31] Então vou tentar novamente “/novo” e de novo ele me mandou para página de login, isso é bem interessante. Vou inserir minha credencial para fazer o login, senha alohomora, fui logado com sucesso, só que isso é meio estranho, porque queria acrescentar um novo item, só que assim que fui logado com sucesso ele me manda para página de lista, isso não é interessante, não é assim que acontece na maioria dos sites.

[05:01] Quando estou tentando acessar uma página e não estou autenticado, não estou logado, é normal que o site me mande para página de login, mas é normal também que assim que eu faço login, ele me mande para página que em, primeiro lugar, queria estar, sendo a página de “/novo”, e por enquanto ele está fazendo esse redirecionamento para página da lista, então isso não é interessante, o que vamos fazer no próximo vídeo, vai ser tentar consertar esse redirecionamento, te espero na próxima aula!



3  - Bloqueando quem não estiver logado

Trabalhando em equipe, Patrícia e João estão querendo proteger uma rota da aplicação de receitas que estão fazendo. João adiantou o trabalho e iniciou com uma lógica para inserir o usuário na sessão. Ficou assim:
```
@app.route('/autenticar')
def login():
    if request.form['login_usuario']:
        # guarda nome de usuário na sessão
        session['nome_usuario'] = request.form['login_usuario']
    return redirect('/criar-receita')

@app.route('/logout')
def sair():
    session['nome_usuario'] = None
    return redirect('/receitas')
```

Levando em consideração esta lógica, como podemos validar se o usuário está logado antes de mostrar o template de criar receita?

```
@app.route('/criar-receita')
def novo():
    if 'nome_usuario' not in session or session['nome_usuario'] is None:
        # não está logado
        return redirect('/login')
    return render_template('criar-receita.html')
```

Desta forma estamos verificando se existe algum nome de usuário salvo em sessão. Caso não tenha nenhum, ele redireciona para tela de login.

4 - Melhorando o fluxo de login

[00:00] Vamos melhorar um pouco o fluxo de login do site, porque vamos supor que eu sou uma pessoa que acabou de entrar no site, não fiz o login e nem nada ainda, e quero adicionar um novo item na lista.

[00:11] Então vou ir em “/novo”, vou tentar acessar, e ele não vai permitir e vai me redirecionar para rota de login, assim vou efetuar o meu login de forma correta e o ideal seria que ele me redirecionasse para página que queria em primeiro lugar, que é a página de "/novo", para poder adicionar um novo item, vamos ver se é isso que acontece.

[00:32] Eu vou digitar meu nome Bruno e a senha alohomora, e vou tentar entrar, entrei. Porém, ele me redirecionou para página principal, página de lista, não era isso que queria, eu queria que ele me direcionasse para página de "/novo", queria que ele capturasse essa informação da página que estava antes para saber qual página que teria que me redirecionar depois.

[00:55] Então vamos ver como que podemos fazer isso, será que usamos o session, não, eu acho que podemos usar uma outra forma de conseguirmos guardar essas informações, passar essas informações adiante.

[01:09] Vamos em jogoteca.py na rota "/novo", e o que podemos fazer é passar que se estou na página novo e eu for redirecionado para página de login, eu não esteja logado e for redirecionado para página de login, posso passar através de um recurso chamado query string as informações da próxima página que quero acessar.

[01:28] Assim eu fui tentar acessar na rota "/novo", eu não estou logado, então sou redirecionado para página de login, mas logo depois eu quero ser redirecionado para a página "/novo" novamente, para poder incluir o item.

[01:42] Então eu vou usar a query string, vou iniciar ela com interrogação, vou criar uma variável de proxima, onde vou colocar que quero ir para página de "/novo", return redirect(‘/login?proxima=novo’). Então adicionei isso para nós. E vamos ver como que ele vai ficar, como que essa coisa de query string funciona, então vou selecionar “Ctrl + S” e ver como que vai funcionar na prática.

```
@app.route('/novo')
def novo():
    if 'usuario_logado' not in session or session['usuario_logado'] == None:
        return redirect('/login?proxima=novo')
    return render_template('novo.html', titulo='Novo Jogo')
```

[02:08] Na aplicação, vou realizar o "/logout" primeiro e agora vou tentar acessar a página "/novo", mas ele não vai permitir porque não estou logado, assim serei redirecionado para página de login, vamos ver o que vai acontecer.

[02:22] Fui redirecionado e veio informação na URL que quero ir para próxima página http://127.0.0.1:5000/login?proxima=novo, que no caso vai ser "novo", ele pegou essas informações, como essa não é uma informação delicada que precisamos guardar a sete chaves, dá para passarmos na URL mesmo, é só a próxima página que queremos ir, então vamos fazer isso.

[02:44] Vamos voltar no código, estamos passando essa informação para rota de login, então vamos à rota de login, porque precisamos capturar essa informação, que está vindo na variável próximo.

[02:58] Vamos criar uma variável chamada "próxima", uma nova variável, e vamos capturar aquela informação da query string de alguma forma, vamos fazer isso usando a função request proxima = request., vai usar args. de argumentos, e vamos inserir o get para pegarmos a informação da query string e colocamos a informação de "novo" lá em "/novo" na variável próxima na query, então é o que vamos chamar nessa linhaproxima = request.args.get(‘proxima’).

```
@app.route('/login')
def login():
    proxima = request.args.get('proxima')
    return render_template('login.html')
```

[03:38] Então temos a informação da próxima página, guardada na variável nova que criamos dentro de login que é "próxima". Mas o que a rota login faz? Ela renderiza esse formulário que temos no login.html, então ela passa as informações para login.html e é isso que vamos fazer, vamos passar as informações que estão dentro dessa variável "próxima" para página de html.

[04:08] Vamos fazer isso criando uma outra variável "próxima", dentro do return render_template(‘login.html’, proxima=proxima, e atribuir a essa variável que temos "próxima" na linha anterior, e então o que estamos fazendo nessa parte? Estamos enviando as informações da próxima página agora para o HTML, o HTML do login.

```
@app.route('/login')
def login():
    proxima = request.args.get('proxima')
    return render_template('login.html', proxima=proxima)
```

[04:30] Então vamos acessar o login.html, está é a página de login no final do código e o que vamos fazer para capturar aquela informação que estamos passando em login? Precisamos criar um novo input, esse input vai receber as informações que estamos passando para cá.

[04:54] Então vou inserir <input>, vou criar um novo e colocar como atributo de tipo hidden para esse novo input <input type="hidden", ele não vai aparecer na página, mas ele vai guardar as informações que atribuímos para ele.

[05:16] Eu vou colocar como nome dele, name, vou colocar como name =’proxima’ e atribuir um valor para ele, o valor que quero que ele capture, assim vou inserir como valor aquilo que quero que ele pegue do arquivo.py, e como que fazemos para efetuar essa comunicação entre html e arquivo.py, já vimos, usamos aquela diretiva que é a dupla chaves, e vamos colocar dentro a variável que estávamos passando desde o início.

```
<input type="hidden" name="proxima" value="{{ proxima }}">
```

[05:53] Então criamos um novo input em login.html, escondido, que o usuário não vai visualizar, mas que vai guardar a informação que precisamos. Temos esse formulário, e o que acontece com as informações desse formulário? Ele pega e envia então através do método post para a rota de “/autenticar”, como podemos analisar na linha anterior <form method="POST" action="/autenticar">.

[06:13] Vamos na rota de “/autenticar” em jogoteca.py para pegar as informações desse input. O que vamos fazer é alterar esse redirect que acontece na rota de autenticar, porque não quero mais que ele envie para essa rota padrão que colocamos que é a rota barra ('/'), a rota da lista, quero que envie para última rota que é a “/novo”, que está contida em todo esse processo que estamos enviando agora para autenticar através do formulário.

[06:46] Então vou criar uma nova variável de proxima_pagina =, e puxar as informações do formulário através do request.form[‘’], e colocar dentro o nome do input que atribuímos, e o nome no caso era "próxima", então ele está capturando essa informação.

```
proxima_pagina = request.form['proxima']
```

[07:17] E no redirect o que vou fazer vai ser realizar uma formatação de string, em que vou colocar o nome da nossa próxima página, que no caso vai ser novo, vou digitar .format(), e dentro a variável "próxima_página", return redirect(‘/{}’ .format(proxima_pagina)).

```
proxima_pagina = request.form['proxima']
return redirect('/{}'.format(proxima_pagina)
```

[07:43] Então com isso ele vai adicionar o nome novo na rota do redirect, vou selecionar “Ctrl + S” e vamos ver se tudo isso vai funcionar, se vamos finalmente conseguir ver isso acontecendo no site Então vou voltar para página de início ('/'), quero acessar a página de "/novo" para incluir um novo item e sou direcionado para página de login e agora o correto seria que aqui assim que eu faço o meu login de forma correta, ele me envia de volta para página de "/novo", então vamos analisar se vai acontecer.

[08:21] Vou digitar meu nome e a credencial alohomora, então ele fez o login com sucesso e perceba ele me mandou para página de "/novo", então funcionou todo esse nosso processo, então fizemos essa grande alteração no código e deu tudo certo.

[08:43] Porém, vamos voltar no código em jogoteca.py e vamos ver uma coisa, porque se analisarmos estamos usando muitos caminhos no código de “/login”, “/novo”, toda vez que precisamos fazer um redirect, toda vez que vamos ao HTML e temos um action, temos um caminho que temos que levar, acontece que isso não é uma boa prática, tem uma maneira melhor de fazermos isso e vamos ver no próximo vídeo.



4 -  Melhorando o fluxo de login

[00:00] Vamos melhorar um pouco o fluxo de login do site, porque vamos supor que eu sou uma pessoa que acabou de entrar no site, não fiz o login e nem nada ainda, e quero adicionar um novo item na lista.

[00:11] Então vou ir em “/novo”, vou tentar acessar, e ele não vai permitir e vai me redirecionar para rota de login, assim vou efetuar o meu login de forma correta e o ideal seria que ele me redirecionasse para página que queria em primeiro lugar, que é a página de "/novo", para poder adicionar um novo item, vamos ver se é isso que acontece.

[00:32] Eu vou digitar meu nome Bruno e a senha alohomora, e vou tentar entrar, entrei. Porém, ele me redirecionou para página principal, página de lista, não era isso que queria, eu queria que ele me direcionasse para página de "/novo", queria que ele capturasse essa informação da página que estava antes para saber qual página que teria que me redirecionar depois.

[00:55] Então vamos ver como que podemos fazer isso, será que usamos o session, não, eu acho que podemos usar uma outra forma de conseguirmos guardar essas informações, passar essas informações adiante.

[01:09] Vamos em jogoteca.py na rota "/novo", e o que podemos fazer é passar que se estou na página novo e eu for redirecionado para página de login, eu não esteja logado e for redirecionado para página de login, posso passar através de um recurso chamado query string as informações da próxima página que quero acessar.

[01:28] Assim eu fui tentar acessar na rota "/novo", eu não estou logado, então sou redirecionado para página de login, mas logo depois eu quero ser redirecionado para a página "/novo" novamente, para poder incluir o item.

[01:42] Então eu vou usar a query string, vou iniciar ela com interrogação, vou criar uma variável de proxima, onde vou colocar que quero ir para página de "/novo", return redirect(‘/login?proxima=novo’). Então adicionei isso para nós. E vamos ver como que ele vai ficar, como que essa coisa de query string funciona, então vou selecionar “Ctrl + S” e ver como que vai funcionar na prática.

```
@app.route('/novo')
def novo():
    if 'usuario_logado' not in session or session['usuario_logado'] == None:
        return redirect('/login?proxima=novo')
    return render_template('novo.html', titulo='Novo Jogo')
```

[02:08] Na aplicação, vou realizar o "/logout" primeiro e agora vou tentar acessar a página "/novo", mas ele não vai permitir porque não estou logado, assim serei redirecionado para página de login, vamos ver o que vai acontecer.

[02:22] Fui redirecionado e veio informação na URL que quero ir para próxima página http://127.0.0.1:5000/login?proxima=novo, que no caso vai ser "novo", ele pegou essas informações, como essa não é uma informação delicada que precisamos guardar a sete chaves, dá para passarmos na URL mesmo, é só a próxima página que queremos ir, então vamos fazer isso.

[02:44] Vamos voltar no código, estamos passando essa informação para rota de login, então vamos à rota de login, porque precisamos capturar essa informação, que está vindo na variável próximo.

[02:58] Vamos criar uma variável chamada "próxima", uma nova variável, e vamos capturar aquela informação da query string de alguma forma, vamos fazer isso usando a função request proxima = request., vai usar args. de argumentos, e vamos inserir o get para pegarmos a informação da query string e colocamos a informação de "novo" lá em "/novo" na variável próxima na query, então é o que vamos chamar nessa linhaproxima = request.args.get(‘proxima’).

```
@app.route('/login')
def login():
    proxima = request.args.get('proxima')
    return render_template('login.html')
```

[03:38] Então temos a informação da próxima página, guardada na variável nova que criamos dentro de login que é "próxima". Mas o que a rota login faz? Ela renderiza esse formulário que temos no login.html, então ela passa as informações para login.html e é isso que vamos fazer, vamos passar as informações que estão dentro dessa variável "próxima" para página de html.

[04:08] Vamos fazer isso criando uma outra variável "próxima", dentro do return render_template(‘login.html’, proxima=proxima, e atribuir a essa variável que temos "próxima" na linha anterior, e então o que estamos fazendo nessa parte? Estamos enviando as informações da próxima página agora para o HTML, o HTML do login.

```
@app.route('/login')
def login():
    proxima = request.args.get('proxima')
    return render_template('login.html', proxima=proxima)
```

[04:30] Então vamos acessar o login.html, está é a página de login no final do código e o que vamos fazer para capturar aquela informação que estamos passando em login? Precisamos criar um novo input, esse input vai receber as informações que estamos passando para cá.

[04:54] Então vou inserir <input>, vou criar um novo e colocar como atributo de tipo hidden para esse novo input <input type="hidden", ele não vai aparecer na página, mas ele vai guardar as informações que atribuímos para ele.

[05:16] Eu vou colocar como nome dele, name, vou colocar como name =’proxima’ e atribuir um valor para ele, o valor que quero que ele capture, assim vou inserir como valor aquilo que quero que ele pegue do arquivo.py, e como que fazemos para efetuar essa comunicação entre html e arquivo.py, já vimos, usamos aquela diretiva que é a dupla chaves, e vamos colocar dentro a variável que estávamos passando desde o início.

```
<input type="hidden" name="proxima" value="{{ proxima }}">
```

[05:53] Então criamos um novo input em login.html, escondido, que o usuário não vai visualizar, mas que vai guardar a informação que precisamos. Temos esse formulário, e o que acontece com as informações desse formulário? Ele pega e envia então através do método post para a rota de “/autenticar”, como podemos analisar na linha anterior <form method="POST" action="/autenticar">.

[06:13] Vamos na rota de “/autenticar” em jogoteca.py para pegar as informações desse input. O que vamos fazer é alterar esse redirect que acontece na rota de autenticar, porque não quero mais que ele envie para essa rota padrão que colocamos que é a rota barra ('/'), a rota da lista, quero que envie para última rota que é a “/novo”, que está contida em todo esse processo que estamos enviando agora para autenticar através do formulário.

[06:46] Então vou criar uma nova variável de proxima_pagina =, e puxar as informações do formulário através do request.form[‘’], e colocar dentro o nome do input que atribuímos, e o nome no caso era "próxima", então ele está capturando essa informação.

```
proxima_pagina = request.form['proxima']
```

[07:17] E no redirect o que vou fazer vai ser realizar uma formatação de string, em que vou colocar o nome da nossa próxima página, que no caso vai ser novo, vou digitar .format(), e dentro a variável "próxima_página", return redirect(‘/{}’ .format(proxima_pagina)).

```
proxima_pagina = request.form['proxima']
return redirect('/{}'.format(proxima_pagina)
```

[07:43] Então com isso ele vai adicionar o nome novo na rota do redirect, vou selecionar “Ctrl + S” e vamos ver se tudo isso vai funcionar, se vamos finalmente conseguir ver isso acontecendo no site Então vou voltar para página de início ('/'), quero acessar a página de "/novo" para incluir um novo item e sou direcionado para página de login e agora o correto seria que aqui assim que eu faço o meu login de forma correta, ele me envia de volta para página de "/novo", então vamos analisar se vai acontecer.

[08:21] Vou digitar meu nome e a credencial alohomora, então ele fez o login com sucesso e perceba ele me mandou para página de "/novo", então funcionou todo esse nosso processo, então fizemos essa grande alteração no código e deu tudo certo.

[08:43] Porém, vamos voltar no código em jogoteca.py e vamos ver uma coisa, porque se analisarmos estamos usando muitos caminhos no código de “/login”, “/novo”, toda vez que precisamos fazer um redirect, toda vez que vamos ao HTML e temos um action, temos um caminho que temos que levar, acontece que isso não é uma boa prática, tem uma maneira melhor de fazermos isso e vamos ver no próximo vídeo.



5 - Recuperando dados da query string

Às vezes, precisamos trafegar informações na URL ao invés de mandar via POST num formulário. Neste caso, a informação é exposta no que chamamos de query string. Isto é, fica visível junto com a URL na barra de endereços do browser.

De que forma podemos recuperar informações passadas pela query string?


```
dados = request.args.get('info')
```
Nesse caso funciona, já que o args é um dicionário Python.

6 - Mais URLs dinâmicas

[00:00] Vamos adicionar um pouco mais de boas práticas no código, vamos dinamizar um pouco mais ele, e como vamos fazer isso então? Onde está faltando às boas práticas no código?

[00:11] Vamos pensar que a aplicação é natural que ela se desenvolva e ganhe mais complexidade, e com o passar do tempo vamos criando várias outras rotas, várias outras páginas para a aplicação, e pode ser que no futuro tenhamos que alterar a URL de algumas dessas rotas.

[00:30] Ao invés de colocar na rota de novo item de lista, temos que especificar mais, colocar "novo_item" ao invés de só "novo", pode ser que no futuro a aplicação tenha outros tipos de lista, por exemplo, uma lista de empresas de jogos, então vou inserir novo_jogo, para diferenciar de outra rota que faríamos para nova empresa, então é possível que no futuro tenhamos que alterar os nomes, as rotas dessas URLs.

[01:09] Mas o problema chega quando temos que fazer essa alteração, e temos que procurar no código, cada vez que fazemos uma referência a uma dessas rotas, por exemplo, nesse redirect para a página principal, a página barra ('/'), às vezes tenho que alterar o nome da página principal, para barra alguma coisa.

[01:30] E nesse caso teria que realizar essa alteração, ir no código em jogoteca.py manualmente e alterar para aquilo que fosse necessário, então como que dinamizamos isso para não precisarmos fazer essa alteração toda vez, vir manualmente e procurar cada lugar que fazemos o redirect para aquela rota específica? O que podemos fazer é utilizar aquela função que já utilizamos que é a url_for.

[01:54] Então vamos fazer a importação dessa função, a url_for e vamos utilizar nos redirects, vamos procurar um redirect. Tem esse redirect para a página principal ('/'), que mostra a lista, e o que vamos fazer vai ser apagar o que está dentro do redirect e colocar return redirect(url_for(‘index’)), e dentro vamos passar a função que instância essa página, que vai ser index, se analisarmos bem a página principal, a função que instância ela é a função index.

```
from flask import Flask, render_template, request, redirect, session, flash, url_for

return redirect(url_for('index'))
```

[02:40] É assim que vamos utilizar a url_for, vamos inserir a função que instância aquela página, vamos achar um outro redirect. O redirect para a página de login, novamente vamos incluir return redirect(url_for(‘login’)), e vamos colocar a função que instância a página de login, que é a função login mesmo, outro redirect para a página principal, e vamos colocar return redirect(url_for(’index’)).

[03:15] Então fizemos esse redirect, e o que sobrou é um redirect de cima que fizemos no último vídeo que passamos as informações por query_string, mas estamos fazendo redirect no final das contas para página de “/login”, então vamos ver como que vai funcionar com a função url_for.

[03:38] Vamos digitar return redirect(url_for(‘login’)), vamos colocar a página de login que é para onde queremos que ele vá, e da mesma forma que o render_template, aceita passarmos para ele algumas variáveis, com algumas informações dentro dessas variáveis, a url_for também aceita que façamos isso.

[03:57] Então vamos incluir uma variável chamada "próxima" , proxima, de próxima página e dentro dessa variável a própria url da página de "novo", que é o que queremos passar adiante, vamos colocar = url_for(‘novo’), que é a função que instancia a página de "novo" que temos.

```
 return redirect(url_for('login', proxima=url_for('novo')))
```

[04:23] Na parte debaixo do código, quando recebemos a página autenticar, precisamos alterar também, porque antes estávamos recebendo do formulário, estávamos recebendo a palavra "novo", e estávamos fazendo uma formatação de string com essa palavra "novo".

[04:44] Agora estamos recebendo a url inteira da página de "novo", então não precisamos mais fazer essa formatação, podemos remover e simplesmente inserir a variável que está com essa url pronta, return redirect(proxima_pagina), que é a "proxima_pagina".

```
 return redirect(proxima_pagina)
```

05:04] Fazemos essa alteração só no “jogoteca.py”? Não, porque se pensarmos bem, nas páginas de HTML temos um direcionamento para as páginas, nos HTMLs que tem formulários podemos ir e pegar, por exemplo, a de login.html, vamos encontrar no formulário uma definição de método *post*, e uma ação *action* que vai enviar as informações do formulário, para a página de autenticação (autenticar), nesse caso.

[05:39] E aqui também dá para fazermos essa coisa de dinamizar o código, o que vamos fazer vai ser apagar essa “/autenticar”, e dentro colocar a <form method=”POST” action=”{{ url_for(‘autenticar’) }}”>, e vamos passar dentro um nome da função que instancia a página de autenticação, que é autenticar, mas estamos utilizando um código Python no HTML, então vamos usar chaves duplas, que é o que precisamos para declarar no HTML, que é um código Python.

```
<h1> Faça seu login </h1>

<form method="POST" action="{{ url_for('autenticar') }}">
<input type="hidden" name="proxima" value="{{ proxima or url_for('index') }}">

</form>
```

[06:26] E agora deve funcionar, deve passar as informações do formulário para a página de autenticação, e não é só que precisamos alterar, porque não é apenas nesse código que temos o formulário, na página de novo.html também, assim, vamos à página de novo.html e também vamos realizar a alteração.

[06:49] Em action está indo para a página de criar, removemos "/criar" e inserimos as duplas chaves, e dentro vamos colocar form action= “{{ url_for(‘criar’) }}” method=”post”> e vamos colocar o nome da função que instancia a página criar, que é "criar". Conseguimos alterar com sucesso todo o código, em todos os lugares que utilizava esses caminhos de URL, vamos selecionar “Ctrl + S” e ver se a aplicação não quebrou, se continua funcionando, então vou recarregar a página do site.

```
<form action="{{ url_for('criar') }}" method="post">

</form>
```

[07:36] Está funcionando a princípio, vou colocar na URL “/novo”, ela me redirecionou, e ela passa de uma forma diferente as informações na URL, mas ainda está passando. Então vou efetuar a minha autenticação, alohomora, me trouxe para página de "/novo" novamente, o que estava fazendo antes e vou acessar a página de lista novamente, está redirecionando, está tudo funcionando como deveria e está coisa legal.

[08:09] Entretanto, vamos voltar no código e ver uma coisa, na jogoteca.py, por enquanto qualquer pessoa que tenha a senha mestra que definimos que é alohomora, pode entrar no site e fazer todo aquele processo de incluir um novo item.

[08:31] Então, é só vazar a senha e qualquer um pode entrar no site, isso não é legal, por isso, vamos adicionar alguns usuários no site, realmente cadastrar alguns usuários no servidor para podermos fazer esse processo de autenticação e credenciação de alguns usuários específicos, vamos ver isso na próxima aula.



7 - Usando urls dinâmicas para as rotas

Sempre que queremos referenciar a URL de uma rota, o Flask nos ajuda com seu helper url_for.

Isto é muito útil para que não tenhamos problemas com manutenção no futuro. Quais vantagens de usar o url_for para referenciar uma rota?


A aplicação não quebra se eu mudar uma URL de rota de '/' para '/outros'.
Se eu usar url_for não vou depender mais da url hardcoded no código. Desta forma, alterar uma rota não vai impactar na aplicação.

Não preciso mudar o código quando uma URL de rota for alterada.
Se uma rota for alterada eu continuo dependendo do nome da função ao invés da string da rota. Desta forma não é necessário alterar nada.

8 - Múltiplos usuários

[00:00] Faltou adicionar usuários na aplicação, porque até agora se formos ver na rota de autenticação, estamos fazendo uma autenticação somente com a senha, assim qualquer pessoa que coloca um nome de usuário, contanto que acerte a senha mestra que definimos no código vai acessar e incluir novos itens na lista.

[00:20] É interessante, assim, que tenhamos usuários específicos, cada um com seu nickname, nome e senha, informações específicas de cada um, e que consigamos validar essas informações de cada um especificamente.

[00:33] Então vamos fazer isso, vamos começar criando esses usuários, da mesma forma que fizemos com os jogos, vamos criar uma classe só para os usuários em jogoteca.py, class Usuario:, e uma função de inicialização, e como atributos eu vou colocar então, def __init__(self, nome, nickname, senha):, que vai ser o que o usuário vai usar para logar no site e senha, claro.

[01:16] E agora as atribuições self.nome = nome, self.nickname = nickname, self.senha = senha, e instanciar os objetos que vão ser os usuários, então vou colocar, usuario = Usuario(), com letra maiúscula que vai ser a referência da nossa classe para instanciar.

```
class Usuario:
    def __init__(self, nome, nickname, senha):
        self.nome = nome
        self.nickname = nickname
        self.senha = senha
```

[01:54] E vou pegar essa linha de código usuario = Usuario(), copiar e colar mais duas vezes, porque quero pelo menos uns três usuários, então vou digitar usuario1, usuario2 e usuario3, e vou criar uns usuários. Como primeiro lugar eu mesmo, Bruno Divino, e vou estabelecer como nickname, BD, as minhas iniciais, e colocar como senha aquela que já estamos usando, alohomora.

```
usuario1 = Usuario("Bruno Divino", "BD", "alohomora")
usuario2 = Usuario()
usuario3 = Usuario()
```

[02:26] Como o segundo usuário, vou colocar "Camila Ferreira", que é um nome fictício, como nickname "Mila" e senha "paozinho", e como terceiro usuário "Guilherme Louro", como nickname "Cake" e como senha "python_eh_vida", o Guilherme gosta bastante de Python.

```
class Usuario:
    def __init__(self, nome, nickname, senha):
        self.nome = nome
        self.nickname = nickname
        self.senha = senha

usuario1 = Usuario("Bruno Divino", "BD", "alohomora")
usuario2 = Usuario("Camila Ferreira", "Mila", "paozinho")
usuario3 = Usuario("Guilherme Louro", "Cake", "Python_eh_vida")
```

[03:10] Então temos três usuários já formados, vamos no raciocínio na parte do código de autenticação, e vamos alterar ele, agora já temos usuários, então vamos mudar um pouco, vou dar um “Enter”para criar um espaço depois de def autenticar(): e criar uma nova condicional.

[03:24] A primeira coisa que temos que pensar é em autenticar o nickname do usuário que está sendo fornecido para nós através do forms, então vamos fazer o if, vamos trazer a informação que está sendo fornecido para nós, pelo usuário que está tentando logar no site, if request.form[‘usuario’], ele está fornecendo um nickname dele lá, e temos que validar e para isso temos que checar se esse nickname que ele está nos dando existe dentro dos usuários que acabamos de criar.

[03:55] Então seria interessante que tivéssemos uma espécie de lista de usuários, in usuarios: em que podemos conferir se o nickname existe.

```
@app.route('/autenticar', methods=['POST', ])
def autenticar():
    if request.form['usuario'] in usuarios:
```

[03:57] Vamos voltar para a parte de cima do código para tentar fazer essa lista. Só que será que a lista é a estrutura mais adequada para nós? Tem uma estrutura do Python que é chamada dicionário, dictionary, que podemos usar e que pode ficar bem melhor.

[04:24] Assim vou criar essa lista usuarios = e abrir esse dicionário e começar incluindo os itens e cada item de um dicionário é composto de uma chave, quase como uma variável, e um valor que tem ali como apontamento a sua chave, então a chave aponta para o valor.

[04:50] Como chave vou colocar a chave de cada item, sendo o nickname daquele usuário específico, então vou colocar usuario1.nickname, para acessar o nickname dele, fazemos assim, utilizamos essa sintaxe para acessarmos o nickname de um objeto, de um atributo de um objeto, eu vou colocar o usuário e o atributo que quero acessar.

[05:17] E agora vou incluir dois pontos (':'), e colocar o valor, e o valor de cada item, vai ser o próprio objeto, usuários = { usuario1.nickname : usuario1, que vai ser o próprio objeto, então usuario1.nickname, o nickname aquele usuário vai ser a chave para levar ao próprio usuário, e farei isso com todos os itens.

```
usuarios = { usuario1.nickname : usuario1,
             usuario2.nickname : usuario2,
             usuario3.nickname : usuario3 }
```

[05:55] Então tenho um dicionário com todos os itens. Na parte de baixo do código em autenticar, quando for fazer essa procura para saber se existe esse nickname que está sendo oferecido pela pessoa que está tentando logar no site, vai procurar dentre as chaves contidas no dicionário e as chaves contidas no dicionário são equivalentes aos nicknames dos usuários, então isso vai funcionar.

[06:19] E a próxima coisa que temos que fazer no autenticar é autenticar a senha desse usuário, então vou colocar if request.form[‘senha’] == e puxar a senha e essa senha tem que ser igual a senha desse usuário que acabamos de autenticar.

[06:39] Então como é que vamos fazer para puxar esse objeto e a senha desse objeto que é esse usuário que estamos tentando autenticar. Vou inserir o dicionário e tentar acessar esse objeto através da chave do dicionário, e assim tenho que colocar ponto senha ('.senha'), para acessar a senha usuarios[].senha.

```
if request.form['senha'] == usuario[].senha:
```

[07:00] Dentro desses colchetes ('[]') preciso incluir a informação do nickname do usuário que estamos autenticando, que no caso se formos analisar na linha de cima é request.form[‘usuario]’, então if request.form[‘senha’] == usuarios.request.form[‘usuario’]].senha, agora temos uma linha de condicional que está muito comprida e é meio confuso isso e dentro também.

```
@app.route('/autenticar', methods=['POST', ])
def autenticar():
    if request.form['usuario'] in usuarios:
                if request.form[‘senha’] == usuarios.request.form[‘usuario’]].senha:
```

[07:35] Então pensa assim, agora estamos seguindo raciocínio, então faz sentido isso que acabamos de fazer. Mas talvez daqui um mês, dois meses que vamos conferir o código, vamos achar um pouco difícil de tentar entender o que fizemos, então o que vamos fazer aqui? Antes de fazermos essa última condicional vamos criar uma variável, usuario, e nessa variável incluir toda essa informação: usuarios.request.form[‘usuario’]].

[08:06] Que se formos analisar certo é a própria chave do dicionário que vai nos levar ao objeto (usuário) que queremos para conseguirmos a senha, e vou apagar esse segmento que já criamos a variável e colocar usuario.senha.

```
    if request.form['usuario'] in usuarios:
        usuario = usuarios[request.form['usuario']]
        if request.form['senha'] == usuario.senha:
```

[08:24] Então agora já temos uma checagem de senha e caso essa checagem der certo, o usuário vai ser finalmente logado e para ele ser logado, pelo o que já montamos, o nickname dele tem que ser salvo dentro do session.

[08:40] Vamos criar o session e instanciar o session, vou inserir "usuário_logado" da mesma forma que fizemos antes session[‘usuario_logado’] = e dentro dele usuario.nickname.

```
session['usuario_logado'] = usuario.nickname
```

[08:58] E agora a única coisa que está faltando é a mensagem de usuário, "usuário logado com sucesso", que já fizemos lá embaixo no flash e que inclusive é um trecho de código que não precisa de mudança, então vou selecionar um “Ctrl + C”, e colocar ele embaixo.

[09:17] Temos que mudar e melhorar um pouco essa parte do session usuário logado, podemos substituir por usuario.nickname.

Código com a mensagem

```
flash(usuario.nickname + ' logado com sucesso!')
            proxima_pagina = request.form['proxima']
            return redirect(proxima_pagina)
```

[09:35] Já temos a condição para caso o usuário consiga logar com sucesso e precisamos de uma condicional para caso ele não consiga, que é o else da parte de baixo, que também não tem uma mudança de código, então vou apagar todo esse código antigo que tínhamos if 'alohomora == request.form['senha']:', e subir esse else para o if.

```
 if request.form['usuario'] in usuarios:
        usuario = usuarios[request.form['usuario']]
        if request.form['senha'] == usuario.senha:
            session['usuario_logado'] = usuario.nickname
            flash(usuario.nickname + ' logado com sucesso!')
            proxima_pagina = request.form['proxima']
            return redirect(proxima_pagina)
    else:
        flash('Usuário não logado.')
        return redirect(url_for('login'))
```

[09:56] Então conseguimos mudar o raciocínio de autenticação. Vamos checar só o nome e o usuário no código, acho que está certo, vou selecionar “Ctrl + S”, e finalmente iremos testar na aplicação para ver se isso está funcionando.

[10:12] Então eu vou lá no site, e vamos testar para ver se está funcionando, a primeira coisa a fazer vai ser um logout para garantir que não estou logado agora e tentar colocar um novo item, e ele me mandar para página de login, porque eu não estou logado, e eu vou tentar logar com o perfil do Guilherme, que é o Cake, a senha dele é "python_eh_vida".

[10:44] Vamos ver se vai dar certo, vou apertar “Enter”, e pronto, o Cake está logado com sucesso, já conseguimos fazer o login, e vamos inserir um jogo, "Skyrim", "RPG" e "PC", vou selecionar "salvar" e foi inserido o novo jogo na lista e deu certo, conseguimos fazer esse login e agora podemos criar múltiplos usuários para a aplicação.

[11:09] A aplicação ficou fantástica, já temos uma aplicação bem encorpada, mas tem uma coisa que talvez podemos melhorar, que é o fato de que se eu for ao código em jogoteca.py e parar de rodar a aplicação ou rodar ela novamente, fazer um rerun e ir ao site e recarregar ele, perco todas as informações que tenho na lista, tudo acaba resetando.

[11:35] Temos uma forma de persistir os dados e isso vamos ver no próximo curso de Flask, então aguarda lá, entra no próximo curso, e vamos fazer isso juntos.



9 - Faça como eu fiz: autorização de usuários

Siga os passos abaixo para implementar o que foi visto nos vídeos!

Clicando no link a seguir, você consegue fazer o download dos arquivos da aula 05

1) Modifique a função novo para checar se o usuário está logado, veja como ela deve ficar abaixo:

```
@app.route('/novo')
def novo():
    if 'usuario_logado' not in session or session['usuario_logado'] == None:
        return redirect('/login')
    return render_template('novo.html', titulo='Novo Jogo')
```

2) Na mesma função, indique o próximo caminho que se deve seguir após o login, repare no redirect:

```
@app.route('/novo')
def novo():
    if 'usuario_logado' not in session or session['usuario_logado'] == None:
        return redirect('/login?proxima=novo')
    return render_template('novo.html', titulo='Novo Jogo')
```

3) Agora na função login, altere-a conforme abaixo:

```
@app.route('/login')
def login():
    proxima = request.args.get('proxima')
    return render_template('login.html', proxima=proxima)
```

4) Abra o arquivo login.html e adicione um input abaixo do form, veja como ficará abaixo:

```
<!DOCTYPE html>
<html>
  <head>
    <meta charset="utf-8">
    <meta name="viewport" content="width=device-width, initial-scale=1">
    <title>Jogoteca</title>
    <link rel="stylesheet" href="{{ url_for('static', filename='bootstrap.css') }}">
  </head>
  <body>
    <div class="container">
        {% with messages = get_flashed_messages() %}
            {% if messages %} 
                <ul id="messages" class="list_unstyled">
                {% for message in messages %}
                    <li class="alert alert-sucess">{{ message }}</li>
                {% endfor %}
                </ul>
            {% enfif %}
        {% endwith %}

        <h1>Faça seu login</h1>
        <form method="POST" action="/autenticar">
            <input type="hidden" name="proxima" value="{{ proxima }}">
            <p><label>Nome de usuário:</label> <input class="form-control" type="text" name="usuario" required></p>
            <p><label>Senha:</label> <input class="form-control" type="password" name="senha" required></p>
            <p><button class="btn btn-primary" type="submit">Entrar</button></p>
        </form>
    </div>
</body>
</html>
```

5) Altere a função da rota de /autenticar e modifique o redirect removendo a rota hardcoded, veja a função modificada abaixo:

```
@app.route('/autenticar', methods=['POST', ])
def autenticar():
    if 'alohomora' == request.form['senha']:
        session['usuario_logado'] = request.form['usuario']
        flash(request.form['usuario'] + ' logado com sucesso!')
        proxima_pagina = request.form['proxima']
        return redirect('/{}'.format(proxima_pagina)
    else:
        flash('Usuário não logado.')
        return redirect('/login')
```

6) Teste as modificações em seu navegador!

7) Se acessarmos diretamente a rota de login, temos um problema, nossa app nos leva para uma rota /None, para resolver isto modifique o input type hidden que foi colocado e teste a aplicação. Veja abaixo como deve ficar:

```
<input type="hidden" name="proxima" value="{{ proxima or '/' }}"
```

8) Modifique as funções de rota para utilizar o url_for, retirando as partes hardcoded (lembre-se de importar o url_for no topo do código)

```
from flask import Flask, render_template, request, redirect, session, flash, url_for

class Jogo:
    def __init__(self, nome, categoria, console):
        self.nome = nome
        self.categoria = categoria
        self.console = console

jogo1 = Jogo('Tetris', 'Puzzle', 'Atari')
jogo2 = Jogo('God of War', 'Hack n Slash', 'PS2')
jogo3 = Jogo('Mortal Kombat', 'Luta', 'PS2')
lista = [jogo1, jogo2, jogo3]

app = Flask(__name__)
app.secret_key = 'alura'

@app.route('/')
def index():
    return render_template('lista.html', titulo='Jogos', jogos=lista)

@app.route('/novo')
def novo():
    if 'usuario_logado' not in session or session['usuario_logado'] == None:
        return redirect(url_for('login', proxima=url_for('novo')))
    return render_template('novo.html', titulo='Novo Jogo')

@app.route('/criar', methods=['POST',])
def criar():
    nome = request. form['nome']
    categoria = request. form['categoria']
    console = request. form['console']
    jogo = Jogo(nome, categoria, console)
    lista.append(jogo)
    return redirect(url_for('index'))

@app.route('/login')
def login():
    proxima = request.args.get('proxima')
    return render_template('login.html', proxima=proxima)

@app.route('/autenticar', methods=['POST', ])
def autenticar():
    if 'alohomora' == request.form['senha']:
        session['usuario_logado'] = request.form['usuario']
        flash(request.form['usuario'] + ' logado com sucesso!')
        proxima_pagina = request.form['proxima']
        return redirect(proxima_pagina)
    else:
        flash('Usuário não logado.')
        return redirect(url_for('login'))

@app.route('/logout')
def logout():
    session['usuario_logado'] = None
    flash('Logout efetuado com sucesso!')
    return redirect(url_for('index'))

app.run(debug=True)
```

9) No arquivo login.html, modifique a tag form e o input type hidden, veja abaixo:

```
<form method="POST" action="{{ url_for('autenticar') }}">
<input type="hidden" name="proxima" value="{{ proxima or url_for('index') }}">
...
</form>
```

10) Agora no arquivo novo.html, modifique também a tag form para utilizar o url_for:

```
<form action="{{ url_for('criar') }}" method="post">
...
</form>
```

11) Teste sua app e veja se está tudo ok!

12) Crie uma classe Usuario para permitir multiplos usuários logados, faça um teste instanciando alguns usuários e crie uma lista para armazená-los, veja o código inteiro abaixo:

```
from flask import Flask, render_template, request, redirect, session, flash, url_for

class Jogo:
    def __init__(self, nome, categoria, console):
        self.nome = nome
        self.categoria = categoria
        self.console = console

jogo1 = Jogo('Tetris', 'Puzzle', 'Atari')
jogo2 = Jogo('God of War', 'Hack n Slash', 'PS2')
jogo3 = Jogo('Mortal Kombat', 'Luta', 'PS2')
lista = [jogo1, jogo2, jogo3]

class Usuario:
    def __init__(self, nome, nickname, senha):
        self.nome = nome
        self.nickname = nickname
        self.senha = senha

usuario1 = Usuario("Bruno Divino", "BD", "alohomora")
usuario2 = Usuario("Camila Ferreira", "Mila", "paozinho")
usuario3 = Usuario("Guilherme Louro", "Cake", "Python_eh_vida")

usuarios = { usuario1.nickname : usuario1,
             usuario2.nickname : usuario2,
             usuario3.nickname : usuario3 }

app = Flask(__name__)
app.secret_key = 'alura'

@app.route('/')
def index():
    return render_template('lista.html', titulo='Jogos', jogos=lista)

@app.route('/novo')
def novo():
    if 'usuario_logado' not in session or session['usuario_logado'] == None:
        return redirect(url_for('login', proxima=url_for('novo')))
    return render_template('novo.html', titulo='Novo Jogo')

@app.route('/criar', methods=['POST',])
def criar():
    nome = request. form['nome']
    categoria = request. form['categoria']
    console = request. form['console']
    jogo = Jogo(nome, categoria, console)
    lista.append(jogo)
    return redirect(url_for('index'))

@app.route('/login')
def login():
    proxima = request.args.get('proxima')
    return render_template('login.html', proxima=proxima)

@app.route('/autenticar', methods=['POST', ])
def autenticar():
    if 'alohomora' == request.form['senha']:
        session['usuario_logado'] = request.form['usuario']
        flash(request.form['usuario'] + ' logado com sucesso!')
        proxima_pagina = request.form['proxima']
        return redirect(proxima_pagina)
    else:
        flash('Usuário não logado.')
        return redirect(url_for('login'))

@app.route('/logout')
def logout():
    session['usuario_logado'] = None
    flash('Logout efetuado com sucesso!')
    return redirect(url_for('index'))

app.run(debug=True)
```

13) Modifique a função autenticar para checar se esse usuário existe na lista criada:

```
from flask import Flask, render_template, request, redirect, session, flash, url_for

class Jogo:
    def __init__(self, nome, categoria, console):
        self.nome = nome
        self.categoria = categoria
        self.console = console

jogo1 = Jogo('Tetris', 'Puzzle', 'Atari')
jogo2 = Jogo('God of War', 'Hack n Slash', 'PS2')
jogo3 = Jogo('Mortal Kombat', 'Luta', 'PS2')
lista = [jogo1, jogo2, jogo3]

class Usuario:
    def __init__(self, nome, nickname, senha):
        self.nome = nome
        self.nickname = nickname
        self.senha = senha

usuario1 = Usuario("Bruno Divino", "BD", "alohomora")
usuario2 = Usuario("Camila Ferreira", "Mila", "paozinho")
usuario3 = Usuario("Guilherme Louro", "Cake", "Python_eh_vida")

usuarios = { usuario1.nickname : usuario1,
             usuario2.nickname : usuario2,
             usuario3.nickname : usuario3 }

app = Flask(__name__)
app.secret_key = 'alura'

@app.route('/')
def index():
    return render_template('lista.html', titulo='Jogos', jogos=lista)

@app.route('/novo')
def novo():
    if 'usuario_logado' not in session or session['usuario_logado'] == None:
        return redirect(url_for('login', proxima=url_for('novo')))
    return render_template('novo.html', titulo='Novo Jogo')

@app.route('/criar', methods=['POST',])
def criar():
    nome = request. form['nome']
    categoria = request. form['categoria']
    console = request. form['console']
    jogo = Jogo(nome, categoria, console)
    lista.append(jogo)
    return redirect(url_for('index'))

@app.route('/login')
def login():
    proxima = request.args.get('proxima')
    return render_template('login.html', proxima=proxima)

@app.route('/autenticar', methods=['POST', ])
def autenticar():
    if request.form['usuario'] in usuarios:
        usuario = usuarios[request.form['usuario']]
        if request.form['senha'] == usuario.senha:
            session['usuario_logado'] = usuario.nickname
            flash(usuario.nickname + ' logado com sucesso!')
            proxima_pagina = request.form['proxima']
            return redirect(proxima_pagina)
    else:
        flash('Usuário não logado.')
        return redirect(url_for('login'))

@app.route('/logout')
def logout():
    session['usuario_logado'] = None
    flash('Logout efetuado com sucesso!')
    return redirect(url_for('index'))

app.run(debug=True)
```

12 - Conclusão 

[00:00] Parabéns por toda sua dedicação nos estudos, você assistiu cada vídeo, fez todos os exercícios, fez um projeto do zero até o final, e leu todos os Para Saber Mais, então agora você concluiu a sua jornada de aprendizagem nesse primeiro curso de Flask. Vamos dar uma revisada em tudo que você aprendeu desde o início.

[00:17] Então a primeira coisa que aprendemos é o que é o Flask propriamente dito, e porque que ele é um microframework, o que é ser um microframework e quais são as vantagens do Flask com relação a outros frameworks.

[00:29] Depois já colocamos a mão na massa para fazer o projeto, e você já começou a aprender como instância uma aplicação de forma rápida e eficiente utilizando o Flask, lá começamos fazendo as rotas com `@app.route` e fizemos várias.

[00:48] Em seguida aprendeu como integrar Python com HTML, que é uma coisa que o Flask faz muito bem, fazíamos com a função render_template, para tentar integrar com o HTML e também dentro do próprio HTML utilizávamos os atributos de dupla chaves, porcentagem ('{{%}}'), para fazer a comunicação e inserir alguma lógica de programação Python, no código HTML, então foi bem legal isso.

[01:17] E logo em depois você aprendeu então a como usar o paradigma de orientação a objetos no projeto, e deixar o nosso projeto um pouco mais complexo, um pouco mais encorpado, um pouco mais interessante.

[01:30] E a seguir você aprendeu também a como utilizar o Flask para ler alguns formulários da página web, como receber as informações do formulário, como processar eles utilizando o Flask como servidor.

[01:42] Para fazermos isso também precisávamos entender como resolvemos os métodos post e get dentro do Flask, então tínhamos que saber que as informações que estávamos recebendo do formulário estava vindo pelo método post para configurarmos como o Flask ia receber.

[02:01] E aprendemos um pouco sobre o debugger também, então você aprendeu que o debugger é uma ferramenta essencial para tornar mais rápido o fluxo de desenvolvimento como desenvolvedores mesmo, que o debugger faz essa coisa de entender que alteramos o código, quando alteramos o código, e atualizar automaticamente, isso faz com que poupemos tempo, não precise ficar dando reruns na aplicação o tempo todo, isso é bem interessante.

[02:27] Você também aprendeu como utilizar o Bootstrap, que é esse framework que possui um CSS pronto já para estilizarmos o site e impedir que o site tenha alguns erros de funcionalidade justamente porque o visual dele está um pouco ruim, e nesse processo de adicionar um CSS, você aprendeu como adicionar CSS então na aplicação utilizando Flask, com aquela pasta de static.

[02:50] E daí você aprendeu também a utilizar herança no HTML, o que é exatamente isso? Eu chamei de herança, aquela coisa que fizemos pegar o código duplicado, e colocar dentro de um arquivo chamado template, e esse código duplicado que era comum em todos os HTMLs, faz com que esses HTMLs herdem esse código duplicado em comum, então isso é bem interessante, é bem comum quando utilizamos o desenvolvimento com Flask.

[03:19] E falando em boas práticas de código, aprendemos como dinamizar os URLs, através daquela função url_for, aprendemos que não é interessante ficar utilizando, urls de caminhos de pastas ou até de rotas dentro do nosso código, que elas podem mudar com o tempo com a mudança da complexidade do projeto, então é interessante usar essa função.

[03:46] Aprendemos a guardar os dados dentro deste recurso que o Flask nos dá que é o session, que permite que guardemos dados e faz com que eles permaneçam durante um tempo, dentro dos cookies do navegador, isso permitiu que conseguíssemos fazer aquele processo de login que tanto queríamos no site.

[04:03] E também utilizamos as query string, que é essa forma de passar informação de uma página para outra, e que é muito interessante, que também é bem usual quando desenvolvemos com Flask, e até outros frameworks.

[04:19] Com isso, conseguimos finalmente desenvolver aquele projeto que propomos no início do curso, através da utilização da linguagem do Python e da utilização do framework Flask.

[04:29] Mas o que você pode fazer a partir de agora? O que você pode fazer é avançar para o próximo curso, vai ter mais um curso, em que vamos tornar essa a aplicação um pouco mais robusta, vamos olhar aquela questão da permanência dos dados, já que toda vez que fazemos um refresh na aplicação os itens de jogos desaparecem, então vamos dar uma analisada nisso no próximo curso.

[04:55] O que você pode fazer também é compartilhar nas redes sociais o que você fez até agora, isso é bem interessante, compartilhar no LinkedIn, no Twitter, no Instagram, tira um print, ou então grava um vídeo seu explicando como que está ficando seu projeto até agora, isso é interessante porque não só vai aumentar sua visibilidade na comunidade de tecnologia, mas vai contribuir para fazer com que a comunidade do Flask, do Python, da galera que ama essas tecnologias, aumente cada vez mais.

[05:24] Isso qualquer desenvolvedor, qualquer pessoa que gosta de tecnologia e que está na área, só tem a ganhar com isso, e também temos o Discord da Alura que é bem interessante de você entrar para discutir a respeito do seu projeto, então coloca lá no projeto que você fez, colocar as suas ideias, discute com a galera, discute com outros alunos, isso é sempre encorajador para outras pessoas que estão aprendendo agora e inclusive você pode tirar bastante das suas dúvidas, então parabéns novamente, e eu te vejo então no próximo curso.
