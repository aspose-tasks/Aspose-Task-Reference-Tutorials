---
title: Trabalhando com coleção de linha de base em Aspose.Tasks
linktitle: Trabalhando com coleção de linha de base em Aspose.Tasks
second_title: API Aspose.Tasks .NET
description: Aprenda como gerenciar linhas de base no Aspose.Tasks for .NET com eficiência. Siga nosso tutorial abrangente para obter orientação passo a passo.
type: docs
weight: 20
url: /pt/net/advanced-features/working-with-baseline-collection/
---
## Introdução

Aspose.Tasks for .NET é uma biblioteca poderosa que permite aos desenvolvedores trabalhar perfeitamente com arquivos do Microsoft Project em seus aplicativos .NET. Entre seus muitos recursos, fornece suporte robusto para o gerenciamento de linhas de base em projetos. As linhas de base são essenciais para o gerenciamento de projetos, pois permitem comparar o plano original do projeto com o status atual, permitindo melhor acompanhamento e análise do progresso do projeto.

## Pré-requisitos

Antes de começarmos a trabalhar com coleções de linha de base em Aspose.Tasks, certifique-se de ter os seguintes pré-requisitos em vigor:

1. Visual Studio: instale o IDE do Visual Studio em seu sistema.
2.  Aspose.Tasks for .NET: Baixe e instale a biblioteca Aspose.Tasks for .NET do[Link para Download](https://releases.aspose.com/tasks/net/).
3. Compreensão básica de C#: Familiarize-se com a linguagem de programação C#.
4. Arquivo do Microsoft Project: tenha um arquivo do Microsoft Project (.mpp) pronto para fins de teste.

## Importar namespaces

Para começar a trabalhar com coleções de linha de base em Aspose.Tasks, você precisa importar os seguintes namespaces:

```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;


```

Agora, vamos dividir cada exemplo em várias etapas:

## Etapa 1: carregar o arquivo do projeto

Primeiro, carregue o arquivo do Microsoft Project usando Aspose.Tasks:

```csharp
// O caminho para o diretório de documentos.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "WorkWithBaselineCollection.mpp");
```

## Etapa 2: Obtenha recursos

A seguir, recupere o recurso desejado do projeto:

```csharp
var resource = project.Resources.GetByUid(1);
```

## Etapa 3: exibir informações de linha de base

Agora, exiba informações sobre as linhas de base associadas ao recurso:

```csharp
Console.WriteLine("Count of assignment baselines: " + resource.Baselines.Count);
Console.WriteLine("Parent Resource Name: " + resource.Baselines.ParentResource.Get(Rsc.Name));
```

## Etapa 4: iterar por meio de linhas de base

Itere através de cada linha de base associada ao recurso e imprima informações relevantes:

```csharp
foreach (var baseline in resource.Baselines)
{
    Console.WriteLine("Baseline Number: " + baseline.BaselineNumber);
    Console.WriteLine("Cost: " + baseline.Cost);
    Console.WriteLine("Work: " + baseline.Work);
    Console.WriteLine("BCWP: " + baseline.Bcwp);
    Console.WriteLine("BCWS: " + baseline.Bcws);
    Console.WriteLine();
}
```

## Etapa 5: remover linhas de base

Exclua todas as linhas de base associadas ao recurso:

```csharp
Console.WriteLine("Delete all baselines: ");
List<Baseline> baselines = resource.Baselines.ToList();
foreach (var baseline in baselines)
{
    Console.WriteLine("Delete baseline with name: " + baseline.BaselineNumber);
    resource.Baselines.Remove(baseline);
}
```

## Conclusão

Neste tutorial, exploramos como trabalhar com coleções de linha de base em Aspose.Tasks for .NET. Seguindo o guia passo a passo, você pode gerenciar facilmente linhas de base em seus aplicativos .NET, permitindo rastreamento e análise eficazes do projeto.

## Perguntas frequentes

### Q1: O Aspose.Tasks pode lidar com arquivos de projeto grandes?

A1: Sim, o Aspose.Tasks é otimizado para lidar com grandes arquivos de projeto com eficiência, garantindo um desempenho suave.

### Q2: O Aspose.Tasks é compatível com todas as versões do Microsoft Project?

A2: Aspose.Tasks oferece suporte a várias versões do Microsoft Project, garantindo compatibilidade em diferentes ambientes.

### Q3: Posso personalizar linhas de base em Aspose.Tasks?

A3: Sim, você pode personalizar linhas de base de acordo com os requisitos do seu projeto usando Aspose.Tasks for .NET.

### Q4: O Aspose.Tasks oferece suporte para plataformas em nuvem?

A4: Sim, Aspose.Tasks fornece suporte para integração com plataformas de nuvem populares, oferecendo flexibilidade na implantação.

### Q5: Existe um fórum da comunidade para usuários do Aspose.Tasks buscarem ajuda e compartilharem conhecimento?

 A5: Sim, você pode visitar o[Fórum Aspose.Tasks](https://forum.aspose.com/c/tasks/15) para se envolver com a comunidade e obter assistência de especialistas.