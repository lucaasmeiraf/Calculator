This is my Calculator.js Project. I know, it's simple but usefull I promisse ;)

You know how a caculator works so I'm just gonna leave my step-by-step of how I plan my projects, I use to write all my toughts and then judge if it is possible or not, maybe 'possible' isn't the word but I like to thing of time and insite my barin a just start to question myself, 'is it worth it?'.

I'm a Brazilian guy so the steps are on my country language, hope you like it!

 CALCULATOR PROJECT

 Projeto prático - Calculadora

Parte 1:

Selecionar elementos na tela
- Main
- :root ( css )
- Input
- Input do resultado

A calculadora não deve permitir que o usuário digite letras:
- Criar um array com os caracteres aceitos

De início vamos criar um evento para o input da seguinte forma, quando uma tecla for pressionada, o input só irá gravar se for um caracter aceito. Também precisa previnir o comportamente padrão do evento.

- usar o array.includes()

Para apagar com o backspace é preciso criar uma condicional, de a tecla pressionada por backspace então deverá apagar o último caracter inserido.

- usar value.slice(0, -1) para apagar o último caracter do valor do input

Criar também uma condicional para o Enter, assim que pressionado deve mostrar o resultado.

- Chamar a função calculate() ao pressionar o enter

Feito isso, vamos precisar adicionar o evento em cada botão da calculadora selecionando todos pela className. Agora iteramos a nodeList (elementos html que possuem a mesma classe, os botões da calculadora) usando o forEach para adicionar o evento de click em cada um, para pegar o valor desse elemento html e inserir no input.

Podemos criar agora o evento click do Clear, para limpar o campo do input e também é possível chamar a função focus() para focar no elemento input depois de limpar.

Adicionar evento de click para o sinal de igual, para calcular o valor chamando a função calculate().

Na função calculate vamos usa a função eval(), ela serve para avaliar a operação que está sendo feita dentro do input, sem que precisemos fazer na mão o cálculo de cada operação. eval() interpreta o valor do input como um dado javascript. Depois basta colocar o valor no input do resultado.

Parte 2:

Para realizar a troca do tema é preciso adicionar o evento de click ao themeSwitcher para que ele verifique se o dataset do main está como Dark, caso esteja é preciso acessar o root(css) e setar o estilo com o setProperty(o que deseja trocar, novo valor), caso esteja o contrário é preciso mudar para o dark. Lembrando que precisa trocar o valor do dataset.theme.

Precisamos adicionar um evento de click para o botão de copiar. Primeiro pegamos o elemento botão pelo evento pois ao copiar precisaremos mudar a mensagem do botão, depois temos que ver se o texto do botão está como 'Copy' e caso esteja precisa trocar o valor para copiado e mudar o css(já tem uma classe 'success' configurada no styles.css então só precisa adicionar uma classe ao elemento button), caso não esteja é preciso remover a classe do elemento.

- Para copiar, utilizaremos o Navigator para pegarmos a função clipBoard e gravar o valor do resultado no clipboard do navegador(ctrl+c).

Para finalizar é preciso configurar a mensagem e cor de erro quando o cálculo não for válido. Vamos simplesmente acessar a função de cálculo e setar no começo o valor do input resultado como 'ERROR' e adicionar a classe error já criada. Depois disso, abaixo do resultado é preciso remover a classe de error.

- Funciona da seguinte forma, ao executar a função ele ira deixar o valor error como padrão, mas se o cálculo 'eval()' for validado, o código seguirá então por isso retiramos a classe. Caso contrário se o eval não validar, a função para na hora então aparecerá a mensagem de error.

