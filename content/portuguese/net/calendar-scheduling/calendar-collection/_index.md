---
title: Gerenciando coleção de calendários em Aspose.Tasks
linktitle: Gerenciando coleção de calendários em Aspose.Tasks
second_title: API Aspose.Tasks .NET
description: Aprenda como gerenciar coleções de calendário em Aspose.Tasks for .NET com eficiência. Crie, modifique e manipule calendários com facilidade.
type: docs
weight: 11
url: /pt/net/calendar-scheduling/calendar-collection/
---
## Introdução

Neste tutorial, exploraremos como gerenciar coleções de calendário em Aspose.Tasks for .NET. Os calendários desempenham um papel crucial no gerenciamento de projetos, definindo dias úteis, feriados e exceções. Aspose.Tasks fornece funcionalidade robusta para manipular calendários em seus projetos.

## Pré-requisitos

Antes de começarmos, certifique-se de ter o seguinte:

1. Visual Studio: Instale o Visual Studio ou qualquer outro IDE compatível para desenvolvimento .NET.
2.  Aspose.Tasks for .NET: Baixe e instale Aspose.Tasks for .NET em[aqui](https://releases.aspose.com/tasks/net/).
3. Compreensão básica de C#: A familiaridade com a linguagem de programação C# será benéfica.

## Importar namespaces

Primeiro, vamos importar os namespaces necessários para trabalhar com Aspose.Tasks:

```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;

using Aspose.Tasks.Saving;

```

## Criando um novo calendário

###  Etapa 1: inicializar um novo`Project` object.
```csharp
var project = new Project();
```

### Etapa 2: adicione calendários à coleção de calendários do projeto.
```csharp
project.Calendars.Add("Calendar");
var newCalendar = project.Calendars.Add("Parent");
project.Calendars.Add("Child", newCalendar);
```

### Etapa 3: percorra os calendários e exiba seus nomes.
```csharp
foreach (var calendar in project.Calendars)
{
    Console.WriteLine("Calendar Name: " + calendar.Name);
}
```

## Substituindo um calendário por um novo calendário

### Etapa 1: carregue um projeto existente.
```csharp
var project = new Project(DataDir + "Project5.mpp");
```

### Passo 2: Remova o calendário existente (se existir).
```csharp
var calendar = project.Calendars.GetByName("TestCalendar");
if (calendar != null)
{
    project.Calendars.Remove(calendar);
}
```

### Etapa 3: adicione um novo calendário.
```csharp
project.Calendars.Add("New Calendar");
project.Save(OutDir + "ReplaceCalendarWithNewCalendar_out.mpp", SaveFileFormat.Mpp);
```

## Obtendo calendário por nome ou ID

### Passo 1: Carregue o projeto.
```csharp
var project = new Project(DataDir + "Project5.mpp");
```

### Etapa 2: recuperar calendários por nome ou UID.
```csharp
var calendarByName = project.Calendars.GetByName("TestCalendar");
var calendarByUid = project.Calendars.GetByUid(4);
```

### Etapa 3: exibir detalhes do calendário.
```csharp
Console.WriteLine("Calendar Name: " + calendarByName.Name);
Console.WriteLine("Calendar Name: " + calendarByUid.Name);
Console.WriteLine("Are calendars equals: " + calendarByName.Equals(calendarByUid));
```

## Iterando em calendários

### Passo 1: Carregue o projeto.
```csharp
var project = new Project(DataDir + "Project5.mpp");
```

### Etapa 2: recupere a contagem de calendários.
```csharp
Console.WriteLine("Number of calendars in the project: " + project.Calendars.Count);
```

### Etapa 3: itere sobre a coleção de calendários e os nomes de exibição.
```csharp
List<Calendar> calendars = project.Calendars.ToList();
foreach (var calendar in calendars)
{
    Console.WriteLine("Calendar Name: " + calendar.Name);
}
```

## Fazendo um calendário padrão

### Etapa 1: inicialize um novo projeto.
```csharp
var project = new Project();
```

### Passo 2: Defina um novo calendário e torne-o padrão.
```csharp
var calendar = project.Calendars.Add("New Standard Calendar");
Calendar.MakeStandardCalendar(calendar);
```

### Etapa 3: Salve o projeto.
```csharp
project.Save(OutDir + "MakeAStandardCalendar_out.xml", SaveFileFormat.Xml);
```

## Conclusão

Gerenciar coleções de calendários no Aspose.Tasks for .NET é essencial para um gerenciamento de projetos eficaz. Com as funcionalidades fornecidas, você pode criar, modificar e manipular calendários com eficiência de acordo com os requisitos do seu projeto.

## Perguntas frequentes

### Q1: Posso criar dias úteis personalizados em Aspose.Tasks?

A1: Sim, você pode criar dias úteis personalizados adicionando exceções aos calendários.

### P2: É possível importar calendários de arquivos do Microsoft Project?

A2: Com certeza, Aspose.Tasks oferece suporte à importação de calendários de arquivos do Microsoft Project.

### P3: Como posso remover um calendário específico de um projeto?

A3: Você pode remover um calendário obtendo-o da coleção e ligando para o`Remove` método.

### Q4: O Aspose.Tasks oferece suporte à exportação de calendários para diferentes formatos?

A4: Sim, Aspose.Tasks permite exportar calendários para vários formatos como XML, MPP, etc.

### P5: Posso personalizar o horário de trabalho para dias específicos em um calendário?

A5: Certamente, você pode definir horários de trabalho para dias individuais usando exceções no calendário.