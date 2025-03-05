---
title: Lidando com salvamento de imagens em Aspose.Tasks
linktitle: Lidando com salvamento de imagens em Aspose.Tasks
second_title: API Aspose.Tasks .NET
description: Aprenda como salvar imagens em Aspose.Tasks for .NET usando orientações passo a passo. Integre perfeitamente a funcionalidade de salvamento de imagens em seus aplicativos .NET.
type: docs
weight: 10
url: /pt/net/advanced-concepts/image-saving/
---
## Introdução

Neste tutorial, nos aprofundaremos no processo de manipulação de salvamento de imagens no Aspose.Tasks for .NET. Aspose.Tasks é uma API poderosa que permite aos desenvolvedores manipular arquivos do Microsoft Project programaticamente. Uma tarefa comum ao trabalhar com arquivos de projeto é a necessidade de salvar imagens, que podem incluir tabelas, gráficos ou outros elementos visuais. Descreveremos o processo passo a passo, garantindo clareza e compreensão do começo ao fim.

## Pré-requisitos

Antes de começarmos, certifique-se de ter os seguintes pré-requisitos:

1. Visual Studio: certifique-se de ter o Visual Studio instalado em seu sistema.
2.  Aspose.Tasks for .NET: Baixe e instale Aspose.Tasks for .NET em[aqui](https://releases.aspose.com/tasks/net/).
3. Compreensão básica de C#: Familiarize-se com os fundamentos da linguagem de programação C#.

## Importar namespaces

Primeiro, vamos importar os namespaces necessários para o nosso projeto:

```csharp
using Aspose.Tasks;
using System.Collections.Generic;
using System.IO;

using Aspose.Tasks.Saving;
using Aspose.Tasks.Visualization;
```

## Etapa 1: Crie um objeto de projeto

Comece criando um objeto Project a partir do seu arquivo do Microsoft Project:

```csharp
var project = new Project("Project1.mpp");
```

## Etapa 2: definir opções para salvar

Defina as opções de salvamento do seu projeto, especificando as páginas e outras configurações:

```csharp
var options = GetSaveOptions(1);
```

## Etapa 3: salve o projeto como HTML

Salve o projeto como HTML com as opções especificadas:

```csharp
project.Save("document_out.html", options);
```

## Etapa 4: implementar retorno de chamada para salvar imagem

Implemente a interface ImageSavingCallback para lidar com o salvamento de imagens:

```csharp
private class ResourcePrefixForNestedResources : IImageSavingCallback
{
    public void ImageSaving(ImageSavingArgs args)
    {
        // A lógica de salvamento de imagem vai aqui
    }
}
```

## Etapa 5: salve as imagens no diretório especificado

Dentro do método ImageSaving, especifique a lógica para salvar as imagens no diretório desejado:

```csharp
if (args.FileName.EndsWith("png"))
{
    // Salvar recursos aninhados
}
else
{
    // Economize recursos regulares
}
```

## Etapa 6: especifique as opções de salvamento

Especifique as opções de salvamento, incluindo retornos de chamada para CSS, fontes e imagens:

```csharp
public static HtmlSaveOptions GetSaveOptions(int pageNumber)
{
    var options = new HtmlSaveOptions
    {
        // Especifique as opções de salvamento aqui
    };

    var program = new ResourcePrefixForNestedResources();
    options.FontSavingCallback = program;
    options.CssSavingCallback = program;
    options.ImageSavingCallback = program;

    return options;
}
```

## Conclusão

Concluindo, lidar com o salvamento de imagens no Aspose.Tasks for .NET envolve definir opções de salvamento e implementar retornos de chamada para gerenciar o processo de salvamento de forma eficaz. Seguindo as etapas descritas neste tutorial, você pode integrar perfeitamente a funcionalidade de salvamento de imagens em seus aplicativos .NET.

## Perguntas frequentes

### Q1: Posso usar Aspose.Tasks para manipular arquivos de projeto em outros formatos além de HTML?

A1: Sim, Aspose.Tasks suporta vários formatos, como PDF, XLSX e MPP.

### P2: O Aspose.Tasks fornece suporte para integração de armazenamento em nuvem?

A2: Sim, Aspose.Tasks oferece APIs para trabalhar com serviços populares de armazenamento em nuvem, como Amazon S3 e Google Drive.

### Q3: O Aspose.Tasks é compatível com .NET Core?

A3: Sim, Aspose.Tasks é compatível com .NET Core, permitindo desenvolver aplicativos multiplataforma.

### Q4: Posso personalizar a aparência das imagens salvas?

A4: Sim, você pode personalizar a aparência das imagens salvas modificando a lógica de salvamento da imagem nos métodos de retorno de chamada.

### Q5: O Aspose.Tasks oferece versões de teste para fins de avaliação?

 A5: Sim, você pode obter uma avaliação gratuita do Aspose.Tasks em[aqui](https://releases.aspose.com/).