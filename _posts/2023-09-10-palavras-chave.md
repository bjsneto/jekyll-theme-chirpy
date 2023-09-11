---
title: Palavras-chave vs Palavras-chave contextuais
author: bjsneto
date: 2023-09-10 20:55:00 +0800
categories: [Blogging, Tutorial]
tags: [palavras-chave c# .NET]
pin: true
img_path: '/posts/20180809'
---

## Palavras-chave

As palavras-chave são identificadores reservados pelo compilador que têm um significado especial e são traduzidos diretamente em instruções de código de máquina. Portanto, não é possível utilizá-las como nome de variáveis.

```c#
int void = 42; // Error CS1547 Keyword 'void' cannot be used in this context
int foreach = 42; // Error CS1519: Invalid token 'foreach' in class, struct, or interface member declaration
```

### Palavras-chave contextuais

As palavras-chave contextuais, também conhecidas como identificadores contextualmente reservados, são identificadores que têm significado em um contexto específico do programa, mas não são reservadas pelo compilador. Isso significa que você pode usá-las como nomes de variáveis, métodos ou nomes de classes.


```c#
string descending = "descendente";
string join = "juntar";
```

No entanto, utilizar palavras-chave contextuais como nomes de variáveis pode não ser uma boa ideia e pode ser considerado um [code smell](https://en.wikipedia.org/wiki/Code_smell){:target="_blank"} (algo que não parece certo em seu código), dificultando a manutenção, depuração e compreensão por parte de equipes novas em seu projeto.

Para obter uma lista completa de palavras-chave e palavras-chave contextuais, consulte a documentação das [Palavras-chave C#](https://learn.microsoft.com/en-us/dotnet/csharp/language-reference/keywords/).
