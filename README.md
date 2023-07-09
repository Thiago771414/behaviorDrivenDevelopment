# Behavior-Driven Development BDD

O Behavior-Driven Development (BDD) é uma metodologia que visa melhorar a colaboração e a comunicação entre os desenvolvedores, especialistas de negócio e demais partes interessadas. Em vez de se concentrar apenas nos testes técnicos, o BDD concentra-se em descrever o comportamento esperado do software em termos de cenários de uso e resultados desejados.
No BDD, os cenários são escritos em uma linguagem natural (geralmente utilizando a sintaxe Gherkin), que é compreensível tanto para desenvolvedores quanto para pessoas não técnicas. Os cenários descrevem o comportamento do sistema em termos de exemplos concretos, o que ajuda a esclarecer os requisitos e a garantir que o software atenda às expectativas do negócio.

Esses cenários são então automatizados por meio de testes, que verificam se o software está se comportando corretamente de acordo com os requisitos definidos. Esses testes automatizados fornecem documentação viva e garantem que o software continue funcionando conforme esperado, mesmo com mudanças futuras.

O BDD também promove uma abordagem colaborativa entre as partes interessadas, ajudando a evitar mal-entendidos e a criar um consenso sobre o comportamento esperado do software.

exemplo ilustrativo de como aplicar a prática do Behavior-Driven Development (BDD) em um cenário simples utilizando a sintaxe Gherkin:

```csharp
Funcionalidade: Calcular média de uma lista de números
  Como um usuário
  Eu quero calcular a média de uma lista de números
  Para obter o valor médio dos números

Cenário: Calcular média de uma lista vazia
  Dado uma lista vazia de números
  Quando eu calcular a média
  Então o resultado deve ser 0

Cenário: Calcular média de uma lista com números positivos
  Dado uma lista de números [10, 20, 30, 40, 50]
  Quando eu calcular a média
  Então o resultado deve ser 30

Cenário: Calcular média de uma lista com números negativos
  Dado uma lista de números [-5, -10, -15, -20]
  Quando eu calcular a média
  Então o resultado deve ser -12.5
```
Nesse exemplo, utilizamos a sintaxe Gherkin para descrever o comportamento esperado do software em termos de cenários de uso e resultados desejados. Os cenários são escritos em uma linguagem natural compreensível tanto para desenvolvedores quanto para pessoas não técnicas.

Esses cenários podem ser automatizados utilizando uma ferramenta de BDD, como o SpecFlow ou o Cucumber, que permite vincular os passos descritos nos cenários com implementações de testes.

A implementação dos testes automatizados pode ser feita utilizando uma biblioteca de testes adequada à sua linguagem de programação preferida. Nesse caso, vamos utilizar o Xunit para criar os testes automatizados:
```csharp
// Camada de Testes

namespace MeuProjeto.Tests
{
    // Bibliotecas necessárias para escrever os testes
    using Xunit;

    public class CalculadoraTests
    {
        [Fact]
        public void CalcularMedia_DeveRetornarMediaCorreta()
        {
            // Arrange
            var numeros = new[] { 10, 20, 30, 40, 50 };
            var calculadora = new Calculadora();

            // Act
            var media = calculadora.CalcularMedia(numeros);

            // Assert
            Assert.Equal(30, media);
        }

        [Fact]
        public void CalcularMedia_DeveRetornarZeroParaListaVazia()
        {
            // Arrange
            var numeros = new int[0];
            var calculadora = new Calculadora();

            // Act
            var media = calculadora.CalcularMedia(numeros);

            // Assert
            Assert.Equal(0, media);
        }

        [Fact]
        public void CalcularMedia_DeveRetornarMediaCorretaParaNumerosNegativos()
        {
            // Arrange
            var numeros = new[] { -5, -10, -15, -20 };
            var calculadora = new Calculadora();

            // Act
            var media = calculadora.CalcularMedia(numeros);

            // Assert
            Assert.Equal(-12.5, media);
        }
    }
}
```
Neste exemplo, utilizamos a biblioteca Xunit para escrever os testes automatizados que verificam se a implementação da classe Calculadora está calculando corretamente a média de uma lista de números.

## Livro
![Imagem](https://m.media-amazon.com/images/I/51YTqGVOD7L._SY425_.jpg)
