# 📖 Guia de Introdução à Programação com Portugol Web

Bem-vindo ao guia prático de Portugol! Este material foi desenvolvido para ajudar você a dar os primeiros passos na lógica de programação utilizando a ferramenta **Portugol Web**.

---

## 📑 Sumário
1. [Aula 1: Variáveis e Entrada/Saída de Dados](#aula-1-variáveis-e-entradasaída-de-dados)
2. [Aula 2: Estruturas Condicionais (`se` e `senao`)](#aula-2-estruturas-condicionais-se-e-senao)
3. [Aula 3: Seleção Múltipla (`escolha` e `caso`)](#aula-3-seleção-múltipla-escolha-e-caso)
4. [Aula 4: Estruturas de Repetição (`para`, `enquanto`, `faca-enquanto`)](#aula-4-estruturas-de-repetição-para-enquanto-faca-enquanto)
5. [Aula 5: Vetores (Arrays)](#aula-5-vetores-arrays)

---

## Aula 1: Variáveis e Entrada/Saída de Dados

Nesta aula, aprenderemos a declarar variáveis para armazenar informações e a interagir com o usuário.

### 📝 Tipos de Dados Utilizados
* **`cadeia`**: Textos e palavras.
* **`inteiro`**: Números inteiros (sem casas decimais).
* **`real`**: Números quebrados (com casas decimais).

### 💻 Exemplo de Código

```portugol
programa {
  funcao inicio() {
    // 1. Declaração das variáveis
    cadeia nome
    inteiro idade
    real altura

    // 2. Entrada de dados pelo usuário
    escreva("Qual seu nome: ")
    leia(nome)

    escreva("Qual sua idade: ")
    leia(idade)

    escreva("Qual sua altura: ")
    leia(altura)

    // 3. Saída de dados na tela (Concatenação)
    escreva("Seu nome é ", nome, ", sua idade é ", idade, " e sua altura é ", altura)
  }
}