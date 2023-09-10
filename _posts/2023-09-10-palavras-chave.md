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

Palavras-chave são identificadores reservados pelo compilador que têm um significado especial e são traduzidos diretamente para instruções de código de máquina. Por tando não é possível utilizá-las como nome da variáveis

```c#
int void = 42; // Error CS1547 Keyword 'void' cannot be used in this context
int foreach = 42; // Error CS1519: Invalid token 'foreach' in class, struct, or interface member declaration
```

### Palavras-chave contextuais

Palavras-chave contextuais também conhecidas como identificadores contextualmente reservados, são identificadores que têm significado em um contexto específico do programa, mas não são reservados pelo compilador. Isso significa que você pode usá-las como nomes de variáveis, métodos ou nome de classes.


```c#
string descending = "descendente";
string join = "juntar";
```

Porém, usar palavras-chaves contextuais como nome de variável pode não ser uma boa ideia e pode um [code smell](https://en.wikipedia.org/wiki/Code_smell){:target="_blank"} (algo não cheira bem no seu código) e dificultar manutembilidade, depuração e entendimento por partes de equipes novas no seu projeto. 

Para obter uma lista completa de palavras-chave e Palavras-chave contextuais, consulte a documentação [Palavras-chave C#](https://learn.microsoft.com/en-us/dotnet/csharp/language-reference/keywords/)