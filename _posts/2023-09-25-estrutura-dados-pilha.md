---
title: Estrutura de Dados - Pilha
author: bjsneto
date: 2023-09-21 20:55:00 +0800
categories: [Blogging, Tutorial]
tags: [Estrutura de Dados, C#, Pilha, Stack]
pin: true
math: true
mermaid: true
image:
  path: /assets/img/posts/stack.webp
  lqip: data:image/webp;base64,
  alt: Estrutura de Dados Pilha (Stack)
---

## A Pilha 

A pilha, sem dúvida, é uma das estruturas de dados mais importantes no campo da ciência da computação e, ao mesmo tempo, simples de entender e implementar.

Vemos essa estrutura de dados no nosso dia a dia, como empilhar livros em uma prateleira, caixas em um armazém e até mesmo contêineres empilhados. Na ciência da computação, a encontramos no histórico do navegador, ao desfazer ou refazer uma alteração em um texto com Ctrl + Z e Ctrl + Y, ou no histórico de operações de uma calculadora, entre outras aplicações. A pilha segue o conceito de LIFO (Last In, First Out), que em português significa "último a entrar, primeiro a sair."

## Operações com Pilha
A pilha suporta 4 operações básicas:

- `Push`: Um novo elemento é colocado no topo da pilha.

- `Pop`: Remove o elemento do topo da pilha.

- `Top (ou Peek)`: Permite acessar o elemento no topo da pilha sem removê-lo.

- `isEmpty`: Verifica se a pilha está vazia.

- `Size (ou tamanho)`: Essa operação retorna o número de elementos na pilha no momento.

## Agora, embarquemos na implementação em C#.

No C#, temos uma classe que representa uma coleção no namespace `System.Collections`, e essa classe simplifica todas as operações relacionadas à pilha.

## Criando a Pilha

Para criar uma pilha em C# com a classe Stack, temos três construtores:

- `Stack()`: Que cria uma nova instância vazia da classe com capacidade padrão.

- `Stack(ICollection)`: Que cria uma nova instância da classe com elementos de outra coleção com a mesma capacidade da coleção copiada.

- `Stack(Int32)`: Que cria uma nova instância da classe que está vazia e tem um espaço inicial específico ou o espaço inicial padrão, o que for maior.

## Inserindo elementos na Pilha com Push

O método Push insere um elemento no topo da pilha, podendo esse ser nulo.

```c#
public virtual void Push (object? obj);
```

```c#
using System;
using System.Collections;

public class Program {

  public static void Main() {

    Stack frutas = new Stack();
    frutas.Push("Banana");
    frutas.Push("Maçã");
    frutas.Push("Melancia");
    foreach(var fruta in frutas) {
      Console.WriteLine("Fruta: {0}", fruta);
    }

  }
}
```
**Saída**:

* Fruta: Melancia
* Fruta: Maçã
* Fruta: Banana


## Removendo elementos na Pilha com Pop

O método Pop remove um elemento do topo da pilha, alterando assim o seu tamanho, ao contrário do método  [Peek()](#pegando-elementos-do-topo-da-pilha-com-peek) que apenas recupera o elemento do topo sem alterar o tamanho da pilha.

```c#
public virtual object? Pop ();
```

```c#
using System;
using System.Collections;

public class Program {

  public static void Main() {

    Stack frutas = new Stack();
    frutas.Push("Banana");
    frutas.Push("Maçã");
    frutas.Push("Melancia");
    var fruta = frutas.Pop();
    Console.WriteLine("Fruta: {0}", fruta);

  }
}
```

**Saída**:

* Fruta: Melancia


## Pegando elementos do topo da Pilha com Peek

O método Peek retorna o elemento do topo da pilha sem modificar o tamanho da pilha, ao contrário do método Pop que retorna e remove o elemento do topo da pilha.

```c#
public virtual object? Peek ();
```

```c#
using System;
using System.Collections;
public class Program {
  public static void Main() {
    Stack frutas = new Stack();
    frutas.Push("Banana");
    frutas.Push("Maçã");
    frutas.Push("Melancia");
    var fruta_top = frutas.Peek();
    Console.WriteLine("Qual a fruta está no topo da pilha: {0}", fruta_top);
    foreach(var fruta in frutas) {
      Console.WriteLine("Fruta: {0}", fruta);
    }
  }
}
```

**Saída**:

* Qual a fruta está no topo da pilha: Melancia
* Fruta: Melancia
* Fruta: Maçã
* Fruta: Banana

## Verificando se a pilha está vazia

A classe Stack do C# não tem um método isEmpty, mas ainda sim podemos verificar se a pilha está vazia com a propriedade Count que retorna o número de elementos que compõe a pilha, ou seja, o tamanho e caso seja igual a zero, a pilha estará vazia. 


```c#
public virtual int Count { get; }
```

```c#
using System;
using System.Collections;
public class Program {
  public static void Main() {
    Stack frutas = new Stack();
    frutas.Push("Banana");
    frutas.Push("Maçã");
    frutas.Push("Melancia");
    frutas.Pop();
    frutas.Pop();
    frutas.Pop();
    if (frutas.Count == 0) {
      Console.WriteLine("A Pilha está vazia");
    } else {
      Console.WriteLine("A Pilha contém {0} elemento(s)", frutas.Count);
    }

  }
}
```

**Saída**:

* A Pilha está vazia

**Referências**: [https://learn.microsoft.com/pt-br/dotnet/api/system.collections.stack?view=net-7.0](https://learn.microsoft.com/pt-br/dotnet/api/system.collections.stack?view=net-7.0){:target="_blank"}