---
title: Opções de salvamento de imagem do MS Project para Aspose.Tasks
linktitle: Opções de salvamento de imagem para Aspose.Tasks
second_title: API Aspose.Tasks .NET
description: Aprenda como salvar opções do MS Project como imagens usando Aspose.Tasks for .NET. Siga nosso guia passo a passo para uma integração perfeita.
weight: 11
url: /pt/net/saving-options/image-save-options/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Opções de salvamento de imagem do MS Project para Aspose.Tasks


## Introdução
No mundo do desenvolvimento de software, lidar com as tarefas do projeto de forma eficiente é crucial para um gerenciamento de projetos bem-sucedido. Aspose.Tasks for .NET oferece uma solução poderosa para desenvolvedores que trabalham com arquivos do Microsoft Project, permitindo-lhes manipular, converter e gerenciar tarefas de projeto perfeitamente em seus aplicativos .NET.
## Pré-requisitos
Antes de começar a usar o Aspose.Tasks for .NET para salvar as opções do MS Project como imagens, certifique-se de ter os seguintes pré-requisitos em vigor:
### 1. Instale Aspose.Tasks para .NET
Para começar, você precisa ter o Aspose.Tasks for .NET instalado em seu ambiente de desenvolvimento. Você pode baixar a biblioteca do[local na rede Internet](https://releases.aspose.com/tasks/net/) e siga as instruções de instalação fornecidas.
### 2. Obtenha uma licença (opcional)
 Embora o Aspose.Tasks for .NET possa ser usado sem licença no modo de avaliação, a obtenção de uma licença é recomendada para funcionalidade completa e para remover limitações de avaliação. Você pode adquirir uma licença do[página de compra](https://purchase.aspose.com/buy) ou opte por um[licença temporária](https://purchase.aspose.com/temporary-license/) para fins de teste.
### 3. Conhecimento básico de desenvolvimento C# e .NET
É necessário um conhecimento fundamental da linguagem de programação C# e do framework .NET para acompanhar os exemplos e integrar as funcionalidades do Aspose.Tasks em seus aplicativos de maneira eficaz.
## Importar namespaces
Antes de começarmos a salvar as opções do MS Project como imagens usando Aspose.Tasks for .NET, vamos garantir que importamos os namespaces necessários para nosso projeto C#:
```csharp
using Aspose.Tasks;
using System.Collections.Generic;
using System.Drawing;
using System.Drawing.Imaging;
using System.IO;

using Aspose.Tasks.Saving;
using Aspose.Tasks.Visualization;
```

## Etapa 1: configurar o caminho do diretório de documentos
Certifique-se de ter um diretório designado para seus documentos e defina o caminho adequadamente:
```csharp
String DataDir = "Your Document Directory";
```
## Etapa 2: carregar o arquivo do MS Project
 Inicialize um novo`Project` objeto carregando o arquivo MS Project:
```csharp
var project = new Project(DataDir + "EstimatedMilestoneTasks.mpp");
```
## Etapa 3: definir opções para salvar imagens
 Crie uma instância de`ImageSaveOptions` especifique as configurações desejadas:
```csharp
var options = new ImageSaveOptions(SaveFileFormat.Jpeg)
{
    RenderToSinglePage = false,
    StartDate = project.Get(Prj.StartDate),
    EndDate = project.Get(Prj.FinishDate),
    PageSize = PageSize.Letter
};
```
## Etapa 4: especifique as páginas para salvar
Se necessário, especifique as páginas a serem salvas. Neste exemplo, estamos adicionando a página 2:
```csharp
options.Pages.Add(2);
```
## Etapa 5: salve a imagem
Por fim, salve as páginas selecionadas como uma imagem com as opções especificadas:
```csharp
project.Save(DataDir + "SaveSelectedPagesImageSaveOptions_page2_out.jpeg", options);
```

## Conclusão
Aspose.Tasks for .NET simplifica o processo de trabalho com arquivos do MS Project, permitindo que os desenvolvedores manipulem facilmente as tarefas do projeto. Seguindo as etapas descritas neste tutorial, você pode salvar com eficiência as opções do MS Project como imagens em seus aplicativos .NET.
## Perguntas frequentes
### Q1: Posso usar Aspose.Tasks for .NET sem licença?
R: Sim, você pode usar Aspose.Tasks for .NET sem licença no modo de avaliação. No entanto, é recomendado obter uma licença para funcionalidade completa e remover limitações de avaliação.
### P2: Como posso obter uma licença temporária para testes?
 R: Você pode obter uma licença temporária para fins de teste no[página de licença temporária](https://purchase.aspose.com/temporary-license/).
### Q3: O Aspose.Tasks for .NET é compatível com outras estruturas .NET?
R: Sim, Aspose.Tasks for .NET é compatível com vários frameworks .NET, incluindo .NET Core e .NET Standard.
### Q4: Posso personalizar ainda mais as opções de salvamento de imagem?
R: Sim, você pode personalizar as opções de salvamento de imagens de acordo com seus requisitos específicos, como ajustar o tamanho da página, a resolução ou o formato de saída.
### P5: Onde posso encontrar suporte para Aspose.Tasks for .NET?
 R: Você pode encontrar suporte e assistência para Aspose.Tasks for .NET no site[fórum](https://forum.aspose.com/c/tasks/15).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
