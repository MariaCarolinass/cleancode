# Código Limpo - Habilidades Práticas do Agile Software

Minhas anotações do livro "Código Limpo" / "Clean Code"

Autor do livro: Robert C. Martin

*******
Sumário
- [Capítulo 1 - Código Limpo](#capítulo-1---código-limpo)
- [Capítulo 2 - Nomes significativos](#capítulo-2---nomes-significativos)
- [Capítulo 3 - Funções](#capítulo-3---funções)
*******

## Capítulo 1 - Código Limpo

O código é a linguagem na qual expressamos nossos requisitos, que precisam estar bem especificados.

### Código ruim

Um código ruim é aquele que vai te fazer demorar mais tempo do que o normal para solucionar algo. Esse código está cheio de bugs que não foram corrigidos quando preciso e não foi codificado de forma legível. O código ruim vai fazer com que a produtividade do time caia, pois a cada implementação, novos problemas surgirão, assim criando uma bola de neve. 

Manter um código limpo nos torna programadores profissionais, mesmo que seja preciso adiar prazos para cumprir requisitos. A eficácia de ter um bom código é muito mais reconhecível.

### Somos autores do nosso código

Lembre-se de que o programador é o `@author` do código e a boa comunicação irá depender de quem escreve. São outros leitores que julgarão a maneira como nós estamos comunicando.

Além de escrever um bom código, mantenha-o limpo para que, com o tempo, não torne o código em ruim de novo. É preciso cultivar o bom código. 

**Como manter o código limpo:**

 - Troque o nome de uma variável por uma melhor.
 - Divida uma função que esteja um pouco grande demais.
 - Elimine um pouco de repetição do código.
 - Reduza uma instrução `if` aninhada.

## Capítulo 2 - Nomes significativos

Como escolher bons nomes para as nossas variáveis, funções, parâmetros, classes, pacotes, arquivos e etc? 

O nome de uma variável deve haver um **propósito** para ter sido escolhido, ele deve dizer para que existe, o que faz e como é usado. Se o nome precisa de um comentário para ser entendido, como no exemplo abaixo, então ele não mostra o seu propósito. 

    int a; // número de camisas vendidas no dia

A variável nomeada `a` declarada como um inteiro não me mostra o que esse inteiro é, pois, imagine não haver um comentário ao lado dela, `a` poderia ser qualquer número inteiro, onde não sabemos o que ele representa. Ela não me mostra que significa o número de camisas e nem muito menos me mostra que é o número de camisas vendidas no dia.

Vamos pensar, se tivermos um arquivo com 1000 linhas de código programadas e alguma função ao final do arquivo que precise da variável `a`, como vamos achá-la no meio de tanto código, como iremos lembrar o que `a` faz e qual o sentido que essa variável estaria dando ao nosso código.

### Nomes ruins

    public Boolean verificarCamisas() {
       int a = 6; // número de camisas vendidas no dia
       int b = 12; // número total de camisas
       return a == b;
    }

### Nomes melhores

    public Boolean verificarSeAtingiuTotalDeVendas() {
       int camisasVendidasNoDia = 6;
       int totalCamisas = 12;
       return camisasVendidasNoDia == totalCamisas;
    }

A escolha de bons nomes ao código torna mais fácil de entender o que está acontecendo, tanto para o próprio programador que está programando quanto para os futuros programadores que irão ler o código. 

Lembre-se de que nomes ruins podem ficar obsoletos, depois de alguns meses sem ver o código, alguns nomes podem não fazer mais sentido e esquecer para o que aquela variável foi criada.

**Pense em algumas questões na hora de declarar nomes:**

- O nome é explicativo para a variável? Qual a importância da variável? O que ela faz?
- O que vai acontecer na função?
- Se uma função retorna algo, como eu vou usar o que está sendo retornado?
- Se tiver uma lista, pense no que ela terá para escolher um bom nome.

### Evite informações erradas e faça distinções

Não passe dicas erradas que confundam o sentido do código. Algumas palavras podem parecer ser bons nomes, mas não são, porque podem apresentar outras interpretações e significados ao código. Por exemplo, `hp` não é um bom nome para armazenar o resultado da hipotenusa, pois é o nome de plataforma Unix. 

Evite criar variáveis muito genéricas, como abreviações que nem todos vão entender logo de cara do que se trata, variáveis com apenas uma letra ou uma letra e um número como `a1` e `a2`. Não utilize a palavra `list` (lista) em uma variável que não é uma lista para não haver confusões e não crie palavras redundantes demais no código, como criar várias funções para criar uma conta do usuário:

    criarContaUsuario();
    criarContaUsuarios();
    crirarContaInfoUsuarios();

Como irei saber qual dessas funções utilizar para criar a conta? 

O mesmo serve para a criação de classes, não crie uma classe chamada `Cliente` e outra `ClienteInfo`, dessa forma o código irá ficar bem confuso, principalmente a medida que ele irá crescendo. Também se torna redudante criar palavras como `variavelNome` ou `nomeString`. Não é necessário acrescentar a palavra `variavel` para uma variável e `string` para `nomeString`, até porque se `nomeString` recebe um número no formato de string estará havendo uma ambiguidade na escolha do nome.

Faça distinções em suas variáveis, se uma palavra já está sendo utilizada, por exemplo, `class` não crie outra variável chamada `klass`. Busque entender o motivo de criar outra variável com o mesmo significado de `class`, pensando no que essa nova variável irá significar.

**Algumas sugestões:**

- Cuidado ao usar nomes muito parecidos que possam ser difíceis de serem distinguidos. 
- Procure utilizar nomes que possam ser **claros** e **pronunciados**.
- Crie nomes passíveis de busca, lembre-se que criar uma variável chamada `e` pode ser dificil de encontrá-la novamente em um projeto muito grande, a não ser que `e` seja uma variável local para uma pequena função especícifica.

## Capítulo 3 - Funções
