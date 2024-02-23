---
title: Trabalhando com Atribuição em Aspose.Tasks
linktitle: Trabalhando com Atribuição em Aspose.Tasks
second_title: API Aspose.Tasks .NET
description: Aprenda como gerenciar atribuições de projeto em .NET usando Aspose.Tasks. Explore diferentes contornos para agendamento de recursos.
type: docs
weight: 13
url: /pt/net/advanced-features/working-with-assignment/
---
## Introdução

Neste tutorial, exploraremos como trabalhar com atribuições no Aspose.Tasks for .NET. As atribuições são cruciais no gerenciamento de projetos, pois alocam recursos às tarefas, ajudando no agendamento e no acompanhamento do progresso. Vamos nos concentrar na geração de dados em fases de atribuição de recursos com vários contornos usando Aspose.Tasks.

## Pré-requisitos

Antes de começarmos, certifique-se de ter os seguintes pré-requisitos:

1.  Instalação do Aspose.Tasks for .NET: Baixe e instale a biblioteca Aspose.Tasks for .NET do[Link para Download](https://releases.aspose.com/tasks/net/).
2. Compreensão básica de C# e .NET Framework: É necessária familiaridade com a linguagem de programação C# e os conceitos do .NET framework para acompanhar.

## Importar namespaces

Certifique-se de importar os namespaces necessários para seu projeto C#:

```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.Saving;
using Aspose.Tasks.Util;

```

## Etapa 1: crie um projeto e uma tarefa

Vamos começar criando um novo projeto e adicionando uma tarefa a ele. Defina a data de início, duração e data de término da tarefa:

```csharp
var project = new Project();
project.Set(Prj.StartDate, new DateTime(2000, 1, 3, 8, 0, 0));
project.Set(Prj.FinishDate, new DateTime(2000, 1, 7, 17, 0, 0));

var task = project.RootTask.Children.Add("Task");
task.Set(Tsk.Start, new DateTime(2000, 1, 3, 8, 0, 0));
task.Set(Tsk.Duration, project.GetDuration(8, TimeUnitType.Hour));
task.Set(Tsk.Finish, new DateTime(2000, 1, 3, 17, 0, 0));
```

## Etapa 2: adicionar um recurso e atribuir à tarefa

A seguir, adicione um recurso ao projeto e atribua-o à tarefa criada anteriormente:

```csharp
var resource = project.Resources.Add("Resource");

var resourceAssignment = project.ResourceAssignments.Add(task, resource);
resourceAssignment.Set(Asn.Start, new DateTime(2000, 1, 3, 8, 0, 0));
resourceAssignment.Set(Asn.Work, project.GetWork(8));
resourceAssignment.Set(Asn.Finish, new DateTime(2000, 1, 3, 17, 0, 0));
```

## Etapa 3: gerar dados faseados no tempo com contornos diferentes

Agora, vamos gerar dados faseados no tempo com diferentes contornos para a atribuição de recursos:

```csharp
Console.WriteLine("Flat contour");

var collection = task.GetTimephasedData(project.Get(Prj.StartDate), project.Get(Prj.FinishDate));
foreach (var td in collection)
{
	Console.WriteLine(td.Start.ToShortDateString() + " " + td.Value);
}
```

## Etapa 4: alterar contornos e gerar dados

Podemos alterar o tipo de contorno e gerar dados em fases de acordo. aqui estão alguns exemplos:

```csharp
// Alterar contorno
resourceAssignment.Set(Asn.WorkContour, WorkContourType.Turtle);
// Gere dados divididos em fases e imprima
// Repita este passo para outros tipos de contorno
```

## Conclusão

Neste tutorial, aprendemos como trabalhar com atribuições em Aspose.Tasks for .NET. Exploramos a geração de dados faseados no tempo de atribuição de recursos com vários contornos. Esse conhecimento pode ser imensamente útil em cenários de gerenciamento de projetos.

## Perguntas frequentes

### Q1: Posso usar Aspose.Tasks para agendar tarefas em meu aplicativo .NET?

A1: Sim, Aspose.Tasks fornece APIs abrangentes para agendamento e gerenciamento de tarefas em aplicativos .NET.

### Q2: Existe uma avaliação gratuita disponível para Aspose.Tasks?

 A2: Sim, você pode aproveitar uma avaliação gratuita em[aqui](https://releases.aspose.com/).

### Q3: Há alguma limitação no número de tarefas ou recursos no Aspose.Tasks?

A3: Aspose.Tasks não impõe nenhuma limitação ao número de tarefas ou recursos que você pode gerenciar em seus projetos.

### Q4: Posso personalizar os contornos para atribuições de recursos em Aspose.Tasks?

A4: Sim, conforme demonstrado neste tutorial, você pode definir vários contornos como tartaruga, sino, pico, etc., de acordo com os requisitos do seu projeto.

### P5: Onde posso encontrar suporte para consultas relacionadas ao Aspose.Tasks?

 A5: Você pode encontrar suporte no[Fórum Aspose.Tasks](https://forum.aspose.com/c/tasks/15) onde especialistas e membros da comunidade se envolvem ativamente em discussões.