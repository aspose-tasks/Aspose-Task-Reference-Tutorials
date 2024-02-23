---
title: Usando algoritmo de árvore em Aspose.Tasks
linktitle: Usando algoritmo de árvore em Aspose.Tasks
second_title: API Aspose.Tasks .NET
description: Aprenda como manipular efetivamente hierarquias de tarefas em seus projetos .NET usando o algoritmo de árvore Aspose.Tasks.
type: docs
weight: 13
url: /pt/net/advanced-concepts/tree-algorithm/
---
## Introdução

Aspose.Tasks for .NET fornece funcionalidades poderosas para trabalhar com tarefas, recursos e cronogramas de gerenciamento de projetos. Um desses recursos é o Algoritmo Árvore, que permite aos usuários manipular hierarquias de tarefas com eficiência. Neste tutorial, exploraremos como utilizar o algoritmo de árvore em Aspose.Tasks for .NET para reunir trabalhos comuns e atualizar valores de trabalho dentro de um projeto.

## Pré-requisitos

Antes de começarmos, certifique-se de ter os seguintes pré-requisitos em vigor:

1. Visual Studio: certifique-se de ter o Visual Studio instalado em seu sistema.
2.  Aspose.Tasks for .NET: Baixe e instale Aspose.Tasks for .NET em[aqui](https://releases.aspose.com/tasks/net/).
3. Compreensão básica de C#: É necessária familiaridade com a linguagem de programação C# para acompanhar os exemplos.

## Importar namespaces

Em seu projeto C#, importe os namespaces necessários para trabalhar com as funcionalidades do Aspose.Tasks:

```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.Util;

```

Agora, vamos dividir cada exemplo em várias etapas:

## Etapa 1: carregar o arquivo do projeto

```csharp
var project = new Project(DataDir + "Project1.mpp");
```

 Carregue o arquivo do projeto na memória usando o`Project` aula.

## Etapa 2: definir a hierarquia de tarefas

```csharp
var root = project.RootTask.Children.Add("Project Management");
var summary = root.Children.Add("Manage iteration");
var task = summary.Children.Add("Acquire staff");
```

Defina a hierarquia de tarefas adicionando tarefas pai e filho.

## Etapa 3: definir propriedades da tarefa

```csharp
task.Set(Tsk.Start, new DateTime(1999, 5, 3, 9, 0, 0));
task.Set(Tsk.Duration, project.GetDuration(8 * 14, TimeUnitType.Hour));
task.Set(Tsk.Finish, project.Get(Prj.Calendar).GetFinishDateByStartAndWork(task.Get(Tsk.Start), task.Get(Tsk.Duration)));
```

Defina propriedades como data de início, duração e data de término das tarefas.

## Etapa 4: adicionar recurso

```csharp
var resource = project.Resources.Add("Project Manager");
resource.Set(Rsc.Type, ResourceType.Work);
project.ResourceAssignments.Add(task, resource);
```

Adicione recursos ao projeto e atribua-os às tarefas conforme necessário.

## Etapa 5: Aplicar Algoritmo de Árvore

```csharp
var acc = new WorkAccumulator();
TaskUtils.Apply(summary, acc, 0);
```

 Inicialize o`WorkAccumulator` class e aplique o Algoritmo de Árvore para reunir trabalhos comuns.

## Etapa 6: atualizar o trabalho da tarefa

```csharp
var summaryWork = acc.Work.ToDouble();
summary.Set(Tsk.Work, project.GetWork(summaryWork));
summary.Set(Tsk.RemainingWork, project.GetWork(summaryWork));
```

Atualize os valores de trabalho das tarefas com base nas informações coletadas.

## Conclusão

Neste tutorial, aprendemos como utilizar o algoritmo de árvore em Aspose.Tasks for .NET para manipular hierarquias de tarefas de maneira eficaz. Seguindo o guia passo a passo, você pode gerenciar com eficiência tarefas e recursos em seus projetos.

## Perguntas frequentes

### Q1: O que é Aspose.Tasks para .NET?

A1: Aspose.Tasks for .NET é uma API poderosa que permite aos desenvolvedores manipular arquivos do Microsoft Project programaticamente usando C#.

### Q2: Posso baixar uma avaliação gratuita do Aspose.Tasks for .NET?

 A2: Sim, você pode baixar uma avaliação gratuita do Aspose.Tasks for .NET em[aqui](https://releases.aspose.com/).

### Q3: Onde posso encontrar documentação para Aspose.Tasks for .NET?

 A3: Você pode encontrar a documentação do Aspose.Tasks for .NET[aqui](https://reference.aspose.com/tasks/net/).

### Q4: Como posso obter suporte para Aspose.Tasks for .NET?

 A4: Para suporte relacionado ao Aspose.Tasks for .NET, você pode visitar o[Fórum Aspose.Tasks](https://forum.aspose.com/c/tasks/15).

### P5: Existe uma licença temporária disponível para fins de teste?

 R5: Sim, você pode obter uma licença temporária para fins de teste em[aqui](https://purchase.aspose.com/temporary-license/).