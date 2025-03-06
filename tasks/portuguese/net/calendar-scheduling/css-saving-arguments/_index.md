---
title: CSS salvando argumentos em Aspose.Tasks
linktitle: CSS salvando argumentos em Aspose.Tasks
second_title: API Aspose.Tasks .NET
description: Aprenda como salvar argumentos CSS em Aspose.Tasks for .NET para personalizar a saída HTML. Aprimore a apresentação com configurações CSS personalizadas.
weight: 20
url: /pt/net/calendar-scheduling/css-saving-arguments/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# CSS salvando argumentos em Aspose.Tasks

## Introdução

Neste tutorial, nos aprofundaremos no processo de salvar argumentos CSS usando Aspose.Tasks for .NET. Cascading Style Sheets (CSS) são cruciais para definir a apresentação de elementos HTML. Aspose.Tasks nos permite manipular e salvar esses atributos CSS de forma eficiente.

## Pré-requisitos

Antes de começarmos, certifique-se de ter os seguintes pré-requisitos em vigor:

1.  Instalação: Certifique-se de ter instalado o Aspose.Tasks for .NET. Você pode baixá-lo no[local na rede Internet](https://releases.aspose.com/tasks/net/).

2. Conhecimento básico: Recomenda-se familiaridade com o ambiente de desenvolvimento C# e .NET.

## Importar namespaces

Para começar, importe os namespaces necessários:

```csharp
using Aspose.Tasks;
using System.Collections.Generic;
using System.IO;

using Aspose.Tasks.Saving;
using Aspose.Tasks.Visualization;

```
## Etapa 1: definir retornos de chamada para salvar CSS

Primeiramente, definimos os métodos de retorno de chamada de salvamento CSS para lidar com o salvamento de arquivos CSS:

```csharp
private class ResourcePrefixForNestedResources : ICssSavingCallback
{
    public void CssSaving(CssSavingArgs args)
    {
        // Implemente sua lógica de salvamento de CSS aqui
    }
}
```

## Etapa 2: implementar retornos de chamada para salvar fontes e imagens

Em seguida, implemente os métodos de retorno de chamada para salvar fontes e imagens de forma semelhante:

```csharp
public void FontSaving(FontSavingArgs args)
{
    // Implemente sua lógica de salvamento de fontes aqui
}

public void ImageSaving(ImageSavingArgs args)
{
    // Implemente sua lógica de salvamento de imagem aqui
}
```

## Etapa 3: configurar opções de salvamento

Agora, configure as opções de salvamento de HTML para utilizar os retornos de chamada implementados:

```csharp
public static HtmlSaveOptions GetSaveOptions(int pageNumber)
{
    var options = new HtmlSaveOptions
    {
        //Configurar opções de salvamento de HTML
    };

    var program = new ResourcePrefixForNestedResources();
    options.FontSavingCallback = program;
    options.CssSavingCallback = program;
    options.ImageSavingCallback = program;

    return options;
}
```

## Etapa 4: Salvar projeto com CSS personalizado

Por fim, salve seu projeto com as configurações CSS personalizadas:

```csharp
var project = new Project("Project1.mpp");
var options = ResourcePrefixForNestedResources.GetSaveOptions(1);
project.Save("document_out.html", options);
```

## Conclusão

Neste tutorial, exploramos como salvar argumentos CSS usando Aspose.Tasks for .NET. Ao definir retornos de chamada de salvamento de CSS e configurar opções de salvamento de HTML, podemos manipular com eficiência os atributos CSS de acordo com nossos requisitos.

## Perguntas frequentes

### Q1: O que é Aspose.Tasks para .NET?

A1: Aspose.Tasks for .NET é uma API .NET poderosa que permite aos desenvolvedores trabalhar com arquivos do Microsoft Project programaticamente.

### Q2: Posso personalizar atributos CSS ao salvar arquivos HTML com Aspose.Tasks?

A2: Sim, você pode definir retornos de chamada de salvamento de CSS para personalizar atributos CSS de acordo com suas necessidades.

### Q3: O Aspose.Tasks for .NET é compatível com todas as versões de arquivos do Microsoft Project?

A3: Aspose.Tasks for .NET oferece suporte a várias versões de arquivos do Microsoft Project, garantindo compatibilidade em diferentes ambientes.

### Q4: Onde posso encontrar documentação abrangente para Aspose.Tasks for .NET?

A4: Você pode consultar o[documentação](https://reference.aspose.com/tasks/net/) para obter informações detalhadas e exemplos.

### P5: O Aspose.Tasks for .NET oferece suporte para desenvolvedores?

 A5: Sim, você pode obter suporte da comunidade Aspose.Tasks por meio do[fórum](https://forum.aspose.com/c/tasks/15).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
