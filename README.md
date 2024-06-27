# Código Limpo - Habilidades Práticas do Agile Software

Minhas anotações do livro "Código Limpo" / "Clean Code"

Autor do livro: Robert C. Martin

## Capítulo 1 - Código Limpo

O código é a linguagem na qual expressamos nossos requisitos. Os requisitos precisam estarem bem específicados.

### Código ruim

Um código ruim é aquele que vai te fazer demorar mais tempo do que o normal para solucionar algo. Esse código está cheio de bugs que não foram corrigidos quando preciso e não foi codificado de forma legível. O código ruim vai fazer com que a produtividade do time caia, pois a cada implementação, novos problemas surgirão, assim criando uma bola de neve. 

Manter um código limpo nos torna programadores profissionais, mesmo que seja preciso adiar prazos para cumprir requisitos. A eficácia de ter um bom código é muito mais reconhecível.

### Somos autores do nosso código

Lembre-se de que o programador é o `@author` do código e a boa comunicação irá depender de quem escreve. São outros leitores que julgarão a maneira como nós estamos comunicando.

Além de escrever um bom código, mantenha-o limpo para que, com o tempo, não torne o código em ruim de novo. É preciso cultivar o bom código. 

 - Troque o nome de uma variável por uma melhor.
 - Divida uma função que esteja um pouco grande demais.
 - Elimine um pouco de repetição do código.
 - Reduza uma instrução `if` aninhada.

## Capítulo 2 - Nomes significativos

Como escolher bons nomes para as nossas variáveis, funções, parâmetros, classes, pacotes, arquivos e etc? O nome de uma variável deve haver um **propósito** para ter sido escolhido, ele deve dizer para que existe, o que faz e como é usado. Se o nome precisa de um comentário para ser entendido, então ele não mostra o seu propósito. 

    int a; // número de camisas vendidas no dia

A variável nomeada `a` declarada como um inteiro não me mostra o que esse inteiro é, pois, imagine não haver um comentário ao lado dela, `a` poderia ser qualquer número inteiro, onde não sabemos o que ele representa. Ela não me mostra que significa o número de camisas e nem muito menos me mostra que é o número de camisas vendidas no dia.

Vamos pensar, se tivermos um arquivo com 1000 linhas de código programadas e alguma função ao final do arquivo que precise da variável `a`, como vamos achá-la no meio de tanto código, como iremos lembrar o que `a` faz e qual o sentido que essa variável estaria dando ao nosso código.
