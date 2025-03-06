---
title: Repetição diária de trabalho em Aspose.Tasks
linktitle: Repetição diária de trabalho em Aspose.Tasks
second_title: API Aspose.Tasks .NET
description: Aprenda como criar tarefas recorrentes diárias em arquivos do Microsoft Project usando Aspose.Tasks for .NET. Aumente a produtividade e a organização sem esforço.
type: docs
weight: 26
url: /pt/net/calendar-scheduling/daily-work-repetition/
---
## Introdução

Aspose.Tasks for .NET é uma biblioteca poderosa que permite aos desenvolvedores manipular arquivos do Microsoft Project com facilidade. Entre seus inúmeros recursos está a capacidade de lidar com tarefas recorrentes com eficiência. Neste tutorial, nos aprofundaremos na funcionalidade Daily Work Repetition, que permite a criação de tarefas que se repetem diariamente dentro de um projeto.

## Pré-requisitos

Antes de mergulhar neste tutorial, certifique-se de ter o seguinte:

- Conhecimento básico de C# e .NET framework.
- Visual Studio instalado em seu sistema.
-  Biblioteca Aspose.Tasks para .NET. Você pode baixá-lo[aqui](https://releases.aspose.com/tasks/net/).
- Familiaridade com arquivos do Microsoft Project (.mpp).

## Importar namespaces

Antes de começarmos, certifique-se de importar os namespaces necessários:

```csharp
using Aspose.Tasks;
using System;
using System.Diagnostics.CodeAnalysis;


```

Vamos dividir o exemplo fornecido em várias etapas:

## Etapa 1: carregar o arquivo do projeto

Primeiro, carregue o arquivo do projeto usando o`Project` aula:

```csharp
var project = new Project(DataDir + "Project1.mpp");
```

## Etapa 2: definir parâmetros de tarefas recorrentes

Defina os parâmetros para a tarefa recorrente:

```csharp
var parameters = new RecurringTaskParameters
{
    TaskName = "New recurrent task",
    RecurrencePattern = new DailyRecurrencePattern
    {
        RecurrenceRange = new EndAfterRecurrenceRange
        {
            Start = new DateTime(2018, 1, 1, 8, 0, 0),
            OccurrenceNumber = 9
        },
        Repetition = new DailyWorkRepetition { RepetitionInterval = 1 }
    },
    Duration = project.GetDuration(1, TimeUnitType.Hour)
};
```

## Etapa 3: definir calendário e data de início da tarefa

Defina o calendário e a data de início da tarefa:

```csharp
parameters.SetCalendar(project, "Standard");
var task = project.RootTask.Children.Add(parameters);
task.Set(Tsk.Start, new DateTime(2020, 4, 27, 8, 0, 0));
```

## Conclusão

Neste tutorial, exploramos como utilizar Aspose.Tasks for .NET para criar tarefas recorrentes com repetição diária de trabalho. Seguindo essas etapas, você pode gerenciar com eficiência as tarefas em seus projetos, garantindo fluxo de trabalho e organização tranquilos.

## Perguntas frequentes

### Q1: Posso personalizar ainda mais o padrão de recorrência?

A1: Sim, você pode ajustar parâmetros como data de início, número de ocorrência e intervalo de repetição para adaptar o padrão de recorrência de acordo com suas necessidades.

### Q2: O Aspose.Tasks é compatível com diferentes versões do Microsoft Project?

A2: Sim, Aspose.Tasks oferece suporte a várias versões do Microsoft Project, garantindo compatibilidade e integração perfeita.

### P3: Como posso lidar com exceções ou modificações em tarefas recorrentes?

A3: Aspose.Tasks fornece funcionalidade robusta para gerenciar exceções e modificações em tarefas recorrentes, permitindo flexibilidade e personalização.

### Q4: Posso exportar o projeto para diferentes formatos?

A4: Com certeza, Aspose.Tasks oferece suporte para exportação de projetos para vários formatos, incluindo PDF, HTML, XML e muito mais, facilitando o compartilhamento e a colaboração.

### P5: O Aspose.Tasks oferece suporte técnico?

R5: Sim, Aspose.Tasks fornece suporte técnico abrangente por meio de seu fórum, onde você pode buscar assistência, compartilhar experiências e interagir com outros usuários.