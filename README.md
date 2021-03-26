# Entendendo o babel

Resumidamente iremos definir o Babel com uma biblioteca que serve basicamente para converter o nosso código JS de uma forma que todos os navegadores e toda a estrutura do projeto consiga entender os códigos.

## Porque disso?

O Java Script é uma linguagem que se atualiza muito e tem varias funcionalidades. Como o React por exemplo que a própria escrita de html fica dentro do código Java Script que os navegadores não entendem. Então o Babel tem a função de interpretar nosso código e converter de uma forma que todos os navegadores entendam.

Dentro do pro site do babel(babeljs.io), conseguimos visualizar isso melhor.

Uma nova funcionalidade da linguagem Java Script é o Nullish coalescing operator(Operador de coalescência nula) que a gente consegue fazer uma verificação em uma propriedade do objeto para verificar se ela é nula antes de acessar Sub-propriedades do mesmo objeto.

![Entendendo%20o%20babel%200df04c04e2424d88974725840bc06525/Untitled.png](Entendendo%20o%20babel%200df04c04e2424d88974725840bc06525/Untitled.png)

Confuso né?

mas basicamente como mostra no exemplo a baixo quando passamos user.name? o '?' simboliza essa verificação.

Caso tentarmos acessar o [user.name](http://user.name) isso ira nos retornar o valor do objeto, no entanto se tentarmos acessar o address que é uma propriedade que não existe isso vai nos gerar um erro, porém se passarmos o '?' na propriedade address que não existe no nosso objeto, ele não ira tentar verificar sub-propriedades dentro desse mesmo objeto e se fossemos checar isso sem o babel e de uma forma que todos os navegadores entendam necessitaria de mais linhas de códigos.

## Configurando na pratica!

vamos instalar no nosso projeto o Babel.

-Criar uma pasta a e abrir no vscode, após isso executar o comando

yarn init

após isso adicionar o babel com o seguinte comando(para usar o yarn basta olhar o site)

[Home](https://yarnpkg.com)

yarn add @babel/core @babel/cli @babel/preset-env -D

## Basicamente os pacotes fazem o seguinte!

-core (Onde fica 99% das funcionalidades do babel)

-cli (nosso terminal consegue executar comandos próprios do babel)

-preset-env (Identifica qual ambiente estamos executando o código JS)

Agora com o babel adicionado no projeto vamos criar um arquivo na raiz do projeto

babel.config.js

com o seguinte conteudo.

![Entendendo%20o%20babel%200df04c04e2424d88974725840bc06525/code.png](Entendendo%20o%20babel%200df04c04e2424d88974725840bc06525/code.png)

Agora iremos adicionar um arquivo index.js com o seguinte conteudo.

![Entendendo%20o%20babel%200df04c04e2424d88974725840bc06525/code%201.png](Entendendo%20o%20babel%200df04c04e2424d88974725840bc06525/code%201.png)

Após abriremos o terminal e executaremos o seguinte comando.

yarn babel src/index.js -o dist/bundle.js

Fazendo isso o babel ira gerar um arquivo bundle.js dentro de uma pasta dist na raiz do projeto. E ele terá convertido nosso código pra uma forma que todos os navegadores entendam 

![Entendendo%20o%20babel%200df04c04e2424d88974725840bc06525/code%202.png](Entendendo%20o%20babel%200df04c04e2424d88974725840bc06525/code%202.png)