---
title: Gerenciando linha de base de atribuição em Aspose.Tasks
linktitle: Gerenciando linha de base de atribuição em Aspose.Tasks
second_title: API Aspose.Tasks .NET
description: Aprenda como gerenciar linhas de base de atribuições de forma eficiente com Aspose.Tasks for .NET, garantindo um rastreamento preciso do progresso e desempenho do projeto.
type: docs
weight: 14
url: /pt/net/advanced-features/assignment-baseline/
---
## Introdução

Ao trabalhar em tarefas de gerenciamento de projetos, o gerenciamento das linhas de base das atribuições é crucial para acompanhar o progresso com precisão. Aspose.Tasks for .NET fornece um conjunto abrangente de ferramentas para lidar com linhas de base de atribuição com eficiência. Neste tutorial, nos aprofundaremos no processo de gerenciamento de linhas de base de atribuição passo a passo.

## Pré-requisitos

Antes de começarmos, certifique-se de ter os seguintes pré-requisitos:

- Conhecimento básico da linguagem de programação C#.
- Visual Studio instalado em seu sistema.
- Biblioteca Aspose.Tasks for .NET adicionada ao seu projeto. Você pode baixá-lo em[aqui](https://releases.aspose.com/tasks/net/).
- Acesso a um arquivo de projeto em formato MPP.

## Importar namespaces

Para começar a trabalhar com Aspose.Tasks, você precisa importar os namespaces necessários para o seu projeto C#. Adicione os seguintes namespaces no início do seu arquivo C#:

```csharp
using Aspose.Tasks;
using System;


```

## Etapa 1: carregar o projeto e definir a linha de base

 Primeiramente, carregue o arquivo do projeto usando o`Project` classe de Aspose.Tasks. Em seguida, defina o tipo de linha de base para o projeto usando o comando`SetBaseline` método.

```csharp
// O caminho para o diretório de documentos.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "AssignmentBaseline2007.mpp");
project.SetBaseline(BaselineType.Baseline);
```

## Etapa 2: Leia as informações básicas da atribuição

Itere cada atribuição de recurso no projeto e recupere informações de linha de base para cada atribuição.

```csharp
foreach (var assignment in project.ResourceAssignments)
{
    foreach (var baseline in assignment.Baselines)
    {
        Console.WriteLine("Baseline Start: " + baseline.Start);
        Console.WriteLine("Baseline Finish: " + baseline.Finish);
        Console.WriteLine("Baseline Number: " + baseline.BaselineNumber);
        Console.WriteLine("Bcwp: " + baseline.Bcwp);
        Console.WriteLine("Bcws: " + baseline.Bcws);
        Console.WriteLine("Cost: " + baseline.Cost);
        Console.WriteLine("Work: " + baseline.Work);
        if (baseline.TimephasedData != null)
        {
            foreach (var td in baseline.TimephasedData)
            {
                Console.WriteLine("TD Start: " + td.Start);
                Console.WriteLine("TD Finish: " + td.Finish);
                Console.WriteLine("TD Timephased Data Type: " + td.TimephasedDataType);
                Console.WriteLine();
            }
        }

        Console.WriteLine();
    }

    Console.WriteLine();
}
```

## Etapa 3: verificar a igualdade da linha de base

Compare as informações básicas para diferentes tarefas usando vários métodos de comparação fornecidos pelo Aspose.Tasks.

```csharp
var assn1 = project.ResourceAssignments.GetByUid(5);
var assn2 = project.ResourceAssignments.GetByUid(7);

var assignmentBaseline1 = assn1.Baselines.ToList()[0];
var assignmentBaseline2 = assn2.Baselines.ToList()[0];

// Verifique a igualdade da linha de base
Console.WriteLine("Are baselines equal: " + assignmentBaseline1.Equals(assignmentBaseline2));

// Verifique a comparação da linha de base
Console.WriteLine("Is baseline 1 less than baseline 2: " + (assignmentBaseline1 < assignmentBaseline2));

// Exibir códigos hash de linha de base
Console.WriteLine("Assignment baseline 1 hashcode: " + assignmentBaseline1.GetHashCode());
Console.WriteLine("Assignment baseline 2 hashcode: " + assignmentBaseline2.GetHashCode());
```

## Conclusão

gerenciamento de linhas de base de atribuições é parte integrante do gerenciamento de projetos, permitindo o acompanhamento preciso do progresso e do desempenho. Com Aspose.Tasks for .NET, o gerenciamento de linhas de base de atribuição torna-se simplificado e eficiente, fornecendo aos desenvolvedores ferramentas poderosas para aprimorar os fluxos de trabalho de gerenciamento de projetos.

## Perguntas frequentes

### Q1: O Aspose.Tasks pode lidar com várias linhas de base para uma única tarefa?

A1: Sim, Aspose.Tasks oferece suporte a várias linhas de base para cada tarefa, permitindo um rastreamento abrangente do progresso do projeto ao longo do tempo.

### Q2: O Aspose.Tasks é compatível com vários formatos de arquivo de projeto além do MPP?

A2: Sim, Aspose.Tasks oferece suporte a uma ampla variedade de formatos de arquivo de projeto, incluindo XML, MPX e MPP, garantindo compatibilidade com várias ferramentas de gerenciamento de projeto.

### Q3: Posso modificar as informações de linha de base programaticamente usando Aspose.Tasks?

A3: Com certeza, Aspose.Tasks fornece APIs extensas para modificar informações de linha de base dinamicamente de acordo com os requisitos do projeto, oferecendo flexibilidade e controle sobre os processos de gerenciamento de projetos.

### Q4: O Aspose.Tasks oferece documentação e recursos de suporte para desenvolvedores?

A4: Sim, os desenvolvedores podem acessar documentação, tutoriais e fóruns abrangentes no site Aspose.Tasks, facilitando a integração e solução de problemas sem problemas.

### Q5: Existe uma versão de teste disponível para Aspose.Tasks for .NET?

 A5: Sim, os desenvolvedores podem obter uma versão de avaliação gratuita do Aspose.Tasks for .NET em[aqui](https://releases.aspose.com/), permitindo-lhes avaliar seus recursos e capacidades antes de tomar uma decisão de compra.