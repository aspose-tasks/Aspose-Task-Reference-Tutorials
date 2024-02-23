---
title: Colete MS Project de peças divididas em Aspose.Tasks
linktitle: Coleção de partes divididas em Aspose.Tasks
second_title: API Aspose.Tasks .NET
description: Aprenda como coletar partes divididas no MS Project usando Aspose.Tasks for .NET. Este tutorial abrangente orienta você pelo processo passo a passo.
type: docs
weight: 19
url: /pt/net/rate-recurring-tasks/split-part-collection/
---
## Introdução
Neste tutorial, nos aprofundaremos em como coletar partes divididas no MS Project usando Aspose.Tasks for .NET. Dividir tarefas em partes pode ser um aspecto crucial do gerenciamento de projetos, e Aspose.Tasks fornece métodos convenientes para lidar com isso de forma eficiente.
## Pré-requisitos
Antes de começarmos, certifique-se de ter os seguintes pré-requisitos:
1. Instalação do Aspose.Tasks for .NET: Certifique-se de ter instalado o Aspose.Tasks for .NET. Você pode baixá-lo em[aqui](https://releases.aspose.com/tasks/net/).
2. Conhecimento básico de C#: A familiaridade com a linguagem de programação C# será benéfica, pois escreveremos trechos de código em C#.

## Importar namespaces
No seu projeto C#, inclua os namespaces necessários:
```csharp
using Aspose.Tasks;
using System;
using System.Diagnostics.CodeAnalysis;

```

## Etapa 1: configure seu projeto
Primeiro, crie um novo projeto em seu IDE preferido e certifique-se de que Aspose.Tasks for .NET seja referenciado corretamente.
## Etapa 2: inicializar o objeto do projeto
```csharp
// O caminho para o diretório de documentos.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "Splits.mpp");
```
Inicialize um novo objeto Project com o caminho para o arquivo do MS Project.
## Etapa 3: recuperar a tarefa e iterar nas partes divididas
```csharp
var task = project.RootTask.Children.GetById(1);
// Iterar sobre partes divididas
Console.WriteLine("Iterate over split parts");
Console.WriteLine("Split parts count:" + task.SplitParts.Count);
foreach (var splitPart in task.SplitParts)
{
    Console.WriteLine("Start: " + splitPart.Start);
    Console.WriteLine("Finish: " + splitPart.Finish);
}
```
Recupere a tarefa do projeto e repita suas partes divididas, imprimindo suas datas de início e término.
## Etapa 4: Divida a parte por índice
```csharp
// Obtenha a peça por índice
var split = task.SplitParts[0];
Console.WriteLine("Split start: " + split.Start);
```
Recupere uma parte dividida específica por índice e imprima sua data de início.

## Conclusão
O gerenciamento de partes divididas em arquivos do MS Project pode aumentar significativamente a eficiência do gerenciamento de projetos. Aspose.Tasks for .NET simplifica esse processo, fornecendo APIs intuitivas para lidar com tarefas divididas perfeitamente.
## Perguntas frequentes
### P: Posso dividir tarefas dinamicamente durante o tempo de execução?
R: Sim, você pode dividir tarefas programaticamente usando Aspose.Tasks for .NET.
### P: O Aspose.Tasks oferece suporte a todas as versões de arquivos do MS Project?
R: Aspose.Tasks oferece suporte a várias versões de arquivos do MS Project, garantindo compatibilidade entre diferentes plataformas.
### P: Existe uma versão de avaliação disponível para fins de teste?
 R: Sim, você pode obter uma versão de avaliação gratuita em[aqui](https://releases.aspose.com/) para avaliação.
### P: Como posso obter licenças temporárias para meus projetos?
 R: Licenças temporárias podem ser adquiridas de[aqui](https://purchase.aspose.com/temporary-license/) para uso de curto prazo.
### P: Onde posso procurar ajuda ou suporte em relação ao Aspose.Tasks?
 R: Você pode visitar o fórum Aspose.Tasks[aqui](https://forum.aspose.com/c/tasks/15) para buscar ajuda da comunidade ou da equipe de suporte do Aspose.