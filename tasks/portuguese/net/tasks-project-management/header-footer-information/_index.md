---
title: Extraia informações de cabeçalho e rodapé com Aspose.Tasks
linktitle: Informações de cabeçalho e rodapé em Aspose.Tasks
second_title: API Aspose.Tasks .NET
description: Aprenda a extrair informações de cabeçalho e rodapé de arquivos do MS Project usando Aspose.Tasks for .NET. Solução fácil, eficiente e amigável ao desenvolvedor.
weight: 29
url: /pt/net/tasks-project-management/header-footer-information/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Extraia informações de cabeçalho e rodapé com Aspose.Tasks

## Introdução
Aspose.Tasks for .NET é uma biblioteca poderosa que permite aos desenvolvedores manipular arquivos do Microsoft Project com facilidade. Neste tutorial, aprenderemos como recuperar informações de cabeçalho e rodapé de arquivos do MS Project usando Aspose.Tasks.
## Pré-requisitos
Antes de começarmos, certifique-se de ter os seguintes pré-requisitos:
1. Visual Studio: instale o Visual Studio em seu sistema.
2.  Aspose.Tasks for .NET: Baixe e instale a biblioteca Aspose.Tasks for .NET em[aqui](https://releases.aspose.com/tasks/net/).
3. Conhecimento básico de C#: Familiaridade com a linguagem de programação C#.

## Importar namespaces
Primeiro, você precisa importar os namespaces necessários para o seu projeto C#. Isso permitirá que você acesse as classes e métodos fornecidos pela biblioteca Aspose.Tasks.
```csharp
    using Aspose.Tasks;
    using System;
    
```
## Etapa 1: inicializar o objeto do projeto
 Para começar, você precisa inicializar um`Project` objeto carregando um arquivo MS Project existente.
```csharp
// O caminho para o diretório de documentos.
string DataDir = "Your Document Directory";
var project = new Project(DataDir + "Blank2010.mpp");
```
## Etapa 2: recuperar informações de cabeçalho e rodapé
 Depois de carregar o arquivo do projeto, você pode recuperar as informações de cabeçalho e rodapé usando o comando`PageInfo` propriedade.
```csharp
var info = project.DefaultView.PageInfo;
// Informações do cabeçalho
Console.WriteLine("Header left text: {0} ", info.Header.LeftText);
Console.WriteLine("Header left image: {0} ", info.Header.LeftImage);
Console.WriteLine("Header left image size: {0} ", info.Header.LeftImageSize);
Console.WriteLine("Header center text: {0} ", info.Header.CenteredText);
Console.WriteLine("Header center image: {0} ", info.Header.CenteredImage);
Console.WriteLine("Header center image size: {0} ", info.Header.CenteredImageSize);
Console.WriteLine("Header right text: {0} ", info.Header.RightText);
Console.WriteLine("Header right image: {0} ", info.Header.RightImage);
Console.WriteLine("Header right image size: {0} ", info.Header.RightImageSize);
// Informações do rodapé
Console.WriteLine();
Console.WriteLine("Footer left text: {0} ", info.Footer.LeftText);
Console.WriteLine("Footer left image: {0} ", info.Footer.LeftImage);
Console.WriteLine("Footer left image size: {0} ", info.Footer.LeftImageSize);
Console.WriteLine("Footer center text: {0} ", info.Footer.CenteredText);
Console.WriteLine("Footer center image: {0} ", info.Footer.CenteredImage);
Console.WriteLine("Footer center size: {0} ", info.Footer.CenteredImageSize);
Console.WriteLine("Footer right text: {0} ", info.Footer.RightText);
Console.WriteLine("Footer right image: {0} ", info.Footer.RightImage);
Console.WriteLine("Footer right image size: {0} ", info.Footer.RightImageSize);
```
Seguindo essas etapas simples, você pode recuperar facilmente informações de cabeçalho e rodapé de arquivos do MS Project usando Aspose.Tasks for .NET.

## Conclusão
Neste tutorial, exploramos como extrair informações de cabeçalho e rodapé de arquivos do MS Project usando Aspose.Tasks for .NET. Essa poderosa biblioteca simplifica a tarefa de trabalhar com arquivos de projeto em aplicativos C#, fornecendo aos desenvolvedores ferramentas robustas para manipulação.
### Perguntas frequentes
### Posso modificar as informações de cabeçalho e rodapé usando Aspose.Tasks?
Sim, você pode modificar as informações de cabeçalho e rodapé programaticamente usando Aspose.Tasks for .NET.
### O Aspose.Tasks oferece suporte a outros formatos de arquivo de projeto além do MS Project?
Sim, Aspose.Tasks oferece suporte a vários formatos de arquivo de projeto, incluindo MPP, XML e MPX.
### Existe um teste gratuito disponível para Aspose.Tasks?
 Sim, você pode baixar uma avaliação gratuita do Aspose.Tasks em[aqui](https://releases.aspose.com/).
### Onde posso encontrar documentação para Aspose.Tasks?
 Você pode encontrar a documentação para Aspose.Tasks[aqui](https://reference.aspose.com/tasks/net/).
### Como posso obter suporte para Aspose.Tasks?
 Você pode obter suporte para Aspose.Tasks visitando o[Fórum Aspose.Tasks](https://forum.aspose.com/c/tasks/15).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
