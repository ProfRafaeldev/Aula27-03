# Guia de Introdução à Programação com Portugol Web

---

## Sumário
1. [Aula 1: Variáveis e Entrada/Saída de Dados](#aula-1-variáveis-e-entradasaída-de-dados)
2. [Aula 2: Estruturas Condicionais (`se` e `senao`)](#aula-2-estruturas-condicionais-se-e-senao)
3. [Aula 3: Seleção Múltipla (`escolha` e `caso`)](#aula-3-seleção-múltipla-escolha-e-caso)
4. [Aula 4: Estruturas de Repetição (`para`, `enquanto`, `faca-enquanto`)](#aula-4-estruturas-de-repetição-para-enquanto-faca-enquanto)
5. [Aula 5: Vetores (Arrays)](#aula-5-vetores-arrays)

---

## Aula 1: Variáveis e Entrada/Saída de Dados

Nesta aula, aprenderemos a declarar variáveis para armazenar informações e a interagir com o usuário.

### Tipos de Dados Utilizados
* **`cadeia`**: Textos e palavras.
* **`inteiro`**: Números inteiros (sem casas decimais).
* **`real`**: Números quebrados (com casas decimais).

### Exemplo de Código

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
```

## Aula 2: Estruturas Condicionais (se e senao)

As estruturas condicionais permitem que o programa tome decisões baseadas em regras lógicas.

### Exemplo de Código: Verificador de Maioridade

```portugol
programa {
  funcao inicio() {
    inteiro idade

    escreva("Idade: ")
    leia(idade)

    // Se a idade for maior ou igual a 18
    se (idade >= 18) {
      escreva("Você é maior de idade.")
    } 
    // Caso contrário
    senao {
      escreva("Você é menor de idade.")
    }
  }
}
```

## Aula 3: Seleção Múltipla (escolha e caso)

Quando temos muitas opções para testar, a estrutura escolha é mais organizada do que vários se/senao juntos.

>Dica: Se você quiser testar textos (cadeia) em vez de números, lembre-se de usar aspas duplas: caso "Brasil":.

### Exemplo de Código: Menu de Países

```portugol
programa {
  funcao inicio() {
    inteiro pais

    escreva("Escolha um país (1 para Brasil, 2 para EUA): ")
    leia(pais)

    escolha (pais) {
      caso 1:
        escreva("Brasil")
        pare // Interrompe a leitura após encontrar o caso

      caso 2:
        escreva("EUA")
        pare
      
      caso contrario:
        escreva("Digite um valor válido!")
    }
  }
}
```

## Aula 4: Estruturas de Repetição (para, enquanto, faca-enquanto)

Os laços de repetição (loops) servem para executar um bloco de código várias vezes sem precisar reescrevê-lo.

> Nota de Sintaxe: O comando escreva("\n") serve para pular uma linha no console de saída.

### 1. O Laço 'para'

Ideal para quando sabemos exatamente quantas vezes o código deve rodar.
Estrutura: 'para( início ; condição ; incremento )x'

```portugol
programa {
  funcao inicio() {
    inteiro contador

    para (contador = 1; contador <= 10; contador++) {
      escreva(contador, "\n")
    }
  }
}
```

### 2. O Laço 'enquanto'

Ideal para quando o código deve rodar enquanto uma condição for verdadeira. O teste da condição é feito no início.

```portugol
programa {
  funcao inicio() {
    inteiro contador = 1

    enquanto (contador <= 9) {
      escreva(contador, "\n")
      contador++ // Incrementa +1 ao contador
    }
  }
}
```

### 3. O Laço 'faca...enquanto'

Semelhante ao enquanto, mas garante que o código seja executado pelo menos uma vez, pois o teste é feito no final.

```portugol
programa {
  funcao inicio() {
    inteiro contador = 1

    faca {
      escreva(contador, "\n")
      contador++
    } enquanto (contador <= 8)
  }
}
```

### Desafio Prático: Tabuadas

Podemos juntar o laço para com operações matemáticas para automatizar o cálculo de tabuadas!

```portugol
programa {
  funcao inicio() {
    inteiro contador
    inteiro tabuadaDeTres = 3
    inteiro tabuadaDeCinco = 5

    escreva("--- TABUADA DO 3 ---\n")
    para (contador = 1; contador <= 10; contador++) {
      escreva(contador * tabuadaDeTres, "\n")
    }

    escreva("\n--- TABUADA DO 5 ---\n")
    para (contador = 1; contador <= 10; contador++) {
      escreva(contador, " x ", tabuadaDeCinco, " = ", contador * tabuadaDeCinco, "\n")
    }
  }
}
```

## Aula 5: Vetores (Arrays)

Vetores são variáveis que conseguem guardar uma lista ordenada de dados sob um mesmo nome. Para acessar uma gaveta específica do vetor, usamos o seu índice (que sempre começa no 0).

### 1. Manipulando Notas e Textos manualmente
```portugol
programa {
  funcao inicio() {
    // Vetor do tipo Real (Números decimais) com 4 posições
    real notas[4]
    notas[0] = 7.1
    notas[1] = 8.6
    notas[2] = 9.9
    notas[3] = 10.0

    escreva("A nota na última posição é: ", notas[3], "\n\n")

    // Vetor do tipo Cadeia (Texto) com 3 posições lidas por um laço 'para'
    cadeia paises[3]
    inteiro contador

    paises[0] = "Brasil"
    paises[1] = "EUA"
    paises[2] = "Portugal"

    escreva("Lista de países:\n")
    para (contador = 0; contador < 3; contador++) {
      escreva(paises[contador], "\n")
    }
  }
}
```

### 2. Aplicação Real: Média Aritmética Dinâmica

Aqui o programa pede as notas ao usuário, soma todas elas usando um acumulador dentro do laço para, calcula a média e diz se a turma está aprovada.
```portugol
programa {
  funcao inicio() {
    real nota[4]
    real media = 0.0
    real soma = 0.0
    inteiro contador

    // Leitura das notas e acumulação da soma
    para (contador = 0; contador < 4; contador++) {
      escreva("Digite a nota do aluno ", contador + 1, ": ")
      leia(nota[contador])
      soma = nota[contador] + soma
    }

    media = soma / 4
    escreva("\nMédia da turma: ", media, "\n")

    // Verificação da média
    se (media < 7.0) {
      escreva("Resultado: Turma abaixo da média.\n")
    } senao {
      escreva("Resultado: Turma acima da média.\n")
    }
  }
}
```