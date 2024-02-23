---
title: Tratamento de duração em Aspose.Tasks
linktitle: Tratamento de duração em Aspose.Tasks
second_title: API Aspose.Tasks .NET
description: Aprenda como lidar com durações de maneira eficaz no Aspose.Tasks for .NET com tutoriais passo a passo.
type: docs
weight: 30
url: /pt/net/calendar-scheduling/duration-handling/
---
## Introdução

Lidar com durações de forma eficaz é crucial em aplicações de gerenciamento de projetos. Aspose.Tasks for .NET fornece funcionalidade robusta para gerenciar durações com eficiência. Neste tutorial, exploraremos vários aspectos do tratamento de duração usando Aspose.Tasks for .NET.

## Pré-requisitos

Antes de mergulharmos no tutorial, certifique-se de ter os seguintes pré-requisitos:

1. Conhecimento básico de C#: Familiaridade com a linguagem de programação C# é essencial para compreender e implementar os exemplos.
2. Visual Studio: instale o Visual Studio IDE para criar e executar aplicativos .NET.
3.  Aspose.Tasks for .NET: Baixe e instale a biblioteca Aspose.Tasks for .NET. Você pode baixá-lo em[aqui](https://releases.aspose.com/tasks/net/).

## Importar namespaces

Primeiro, vamos importar os namespaces necessários para usar as funcionalidades do Aspose.Tasks:

```csharp
using Aspose.Tasks;
using System;
using System.Diagnostics.CodeAnalysis;


```

Vamos dividir cada exemplo em várias etapas em um formato de guia passo a passo:

## Atualizando Durações de Tarefas

### Etapa 1: carregar o arquivo do projeto

```csharp
var project = new Project(DataDir + "TaskDurations.mpp");
```

### Etapa 2: Obtenha a tarefa e a duração

```csharp
var task1 = project.RootTask.Children.GetById(1);
var duration1 = task1.Get(Tsk.Duration);
```

### Etapa 3: duração da atualização

```csharp
duration1 = duration1.Add(project.GetDuration(1, TimeUnitType.Day));
task1.Set(Tsk.Duration, duration1);
```

### Etapa 4: exibir duração atualizada

```csharp
Console.WriteLine("The duration of task 1: " + task1.Get(Tsk.Duration));
```

## Subtraindo durações de tarefas

### Etapa 1: carregar o arquivo do projeto

```csharp
var project = new Project(DataDir + "TaskDurations.mpp");
```

### Etapa 2: Obtenha a tarefa e a duração

```csharp
var task1 = project.RootTask.Children.GetById(1);
var duration1 = task1.Get(Tsk.Duration);
```

### Etapa 3: subtrair a duração

```csharp
duration1 = duration1.Subtract(project.GetDuration(1, TimeUnitType.Day));
task1.Set(Tsk.Duration, duration1);
```

### Etapa 4: exibir duração atualizada

```csharp
Console.WriteLine("The duration of task 1: " + task1.Get(Tsk.Duration));
```

## Convertendo Duração em TimeSpan

### Etapa 1: carregar o arquivo do projeto

```csharp
var project = new Project(DataDir + "TaskDurations.mpp");
```

### Etapa 2: Obtenha a tarefa e a duração

```csharp
var task = project.RootTask.Children.GetById(1);
var duration = task.Get(Tsk.Duration);
```

### Etapa 3: converter duração em TimeSpan

```csharp
Console.WriteLine("Time span of duration: " + duration.TimeSpan);
```

## Convertendo Duração em String

### Etapa 1: carregar o arquivo do projeto

```csharp
var project = new Project(DataDir + "TaskDurations.mpp");
```

### Etapa 2: Obtenha a tarefa e a duração

```csharp
var task = project.RootTask.Children.GetById(1);
var duration = task.Get(Tsk.Duration);
```

### Etapa 3: converter duração em string

```csharp
Console.WriteLine("The duration as a string: " + duration.ToString());
```

## Conclusão

Neste tutorial, cobrimos vários aspectos do tratamento de duração em Aspose.Tasks for .NET. Compreender e gerenciar eficazmente as durações é vital para o sucesso do gerenciamento de projetos. Aspose.Tasks fornece funcionalidades abrangentes para simplificar tarefas de gerenciamento de duração em seus aplicativos .NET.

## Perguntas frequentes

### Q1: O que é Aspose.Tasks para .NET?

A1: Aspose.Tasks for .NET é uma biblioteca poderosa para trabalhar com arquivos do Microsoft Project em aplicativos .NET.

### Q2: O Aspose.Tasks pode lidar com estruturas de projetos complexas?

A2: Sim, Aspose.Tasks pode lidar com estruturas de projetos complexas com facilidade, fornecendo APIs extensas para manipulação.

### Q3: O Aspose.Tasks for .NET é compatível com o .NET Core?

A3: Sim, Aspose.Tasks for .NET é compatível com .NET Core, permitindo que você o use em aplicativos de plataforma cruzada.

### Q4: O Aspose.Tasks oferece suporte à leitura e gravação de arquivos do Microsoft Project?

A4: Sim, Aspose.Tasks oferece suporte à leitura e gravação de arquivos do Microsoft Project em vários formatos, incluindo MPP, XML e MPX.

### Q5: Existe uma versão de teste disponível para Aspose.Tasks for .NET?

 A5: Sim, você pode obter uma avaliação gratuita do Aspose.Tasks for .NET em[aqui](https://releases.aspose.com/).