---
date: 2026-04-13
description: Aprenda como definir horas de trabalho e gerenciar coleções de calendários
  no Aspose.Tasks para .NET. Importe calendários do Microsoft Project, remova o calendário
  do projeto e obtenha o calendário por nome facilmente.
keywords:
- set working hours
- import calendars microsoft project
- remove calendar project
- get calendar by name
linktitle: Gerenciando a Coleção de Calendários no Aspose.Tasks
second_title: Aspose.Tasks .NET API
title: Definir Horas de Trabalho na Coleção de Calendários do Aspose.Tasks
url: /pt/net/calendar-scheduling/calendar-collection/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Definir Horas de Trabalho na Coleção de Calendários Aspose.Tasks

Neste tutorial, você aprenderá como **definir horas de trabalho** e gerenciar coleções de calendários usando Aspose.Tasks para .NET. Os calendários definem dias úteis, feriados e exceções, portanto dominá‑los permite controlar os cronogramas dos projetos com precisão. Também mostraremos como importar calendários do Microsoft Project, remover um calendário de um projeto e obter um calendário pelo nome.

## Respostas Rápidas
- **Qual é a classe principal para calendários?** `Project.Calendars` collection.
- **Como definir horas de trabalho?** Crie ou modifique um objeto `Calendar` e defina seu `WorkingTime`.
- **Posso importar calendários do Microsoft Project?** Sim – carregue um arquivo MPP e acesse seus calendários.
- **Como remover um calendário de um projeto?** Use `Project.Calendars.Remove(calendar)`.
- **Como recuperar um calendário pelo nome?** Chame `Project.Calendars.GetByName("YourCalendar")`.

## Pré-requisitos

Antes de começarmos, certifique‑se de que você tem o seguinte:

1. Visual Studio: Instale o Visual Studio ou qualquer outra IDE compatível com desenvolvimento .NET.  
2. Aspose.Tasks para .NET: Baixe e instale o Aspose.Tasks para .NET a partir de [here](https://releases.aspose.com/tasks/net/).  
3. Compreensão básica de C#: Familiaridade com a linguagem de programação C# será benéfica.

## Importar Namespaces

Primeiro, vamos importar os namespaces necessários para trabalhar com Aspose.Tasks:

```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;

using Aspose.Tasks.Saving;
```

## Criando um Novo Calendário

### Etapa 1: Inicializar um novo objeto `Project`.
```csharp
var project = new Project();
```

### Etapa 2: Adicionar calendários à coleção de calendários do projeto.
```csharp
project.Calendars.Add("Calendar");
var newCalendar = project.Calendars.Add("Parent");
project.Calendars.Add("Child", newCalendar);
```

### Etapa 3: Percorrer os calendários e exibir seus nomes.
```csharp
foreach (var calendar in project.Calendars)
{
    Console.WriteLine("Calendar Name: " + calendar.Name);
}
```

## Como Definir Horas de Trabalho para um Calendário?

Para **definir horas de trabalho**, você modifica a coleção `WorkingTime` de um `Calendar`.  
Por exemplo, pode definir um dia de trabalho padrão das 9 h às 17 h ou adicionar exceções personalizadas.  
O código para isso é idêntico aos exemplos mostrados mais adiante quando criamos um calendário padrão.

## Substituindo um Calendário por um Novo Calendário

### Etapa 1: Carregar um projeto existente.
```csharp
var project = new Project(DataDir + "Project5.mpp");
```

### Etapa 2: Remover o calendário existente (se existir).  
Isso demonstra o cenário de **remover calendário do projeto**.
```csharp
var calendar = project.Calendars.GetByName("TestCalendar");
if (calendar != null)
{
    project.Calendars.Remove(calendar);
}
```

### Etapa 3: Adicionar um novo calendário.
```csharp
project.Calendars.Add("New Calendar");
project.Save(OutDir + "ReplaceCalendarWithNewCalendar_out.mpp", SaveFileFormat.Mpp);
```

## Obtendo Calendário por Nome ou ID

### Etapa 1: Carregar o projeto.
```csharp
var project = new Project(DataDir + "Project5.mpp");
```

### Etapa 2: Recuperar calendários por nome ou UID.  
Isso ilustra a operação de **obter calendário por nome**.
```csharp
var calendarByName = project.Calendars.GetByName("TestCalendar");
var calendarByUid = project.Calendars.GetByUid(4);
```

### Etapa 3: Exibir detalhes do calendário.
```csharp
Console.WriteLine("Calendar Name: " + calendarByName.Name);
Console.WriteLine("Calendar Name: " + calendarByUid.Name);
Console.WriteLine("Are calendars equals: " + calendarByName.Equals(calendarByUid));
```

## Iterando Sobre Calendários

### Etapa 1: Carregar o projeto.
```csharp
var project = new Project(DataDir + "Project5.mpp");
```

### Etapa 2: Recuperar a contagem de calendários.
```csharp
Console.WriteLine("Number of calendars in the project: " + project.Calendars.Count);
```

### Etapa 3: Percorrer a coleção de calendários e exibir nomes.
```csharp
List<Calendar> calendars = project.Calendars.ToList();
foreach (var calendar in calendars)
{
    Console.WriteLine("Calendar Name: " + calendar.Name);
}
```

## Criando um Calendário Padrão

### Etapa 1: Inicializar um novo projeto.
```csharp
var project = new Project();
```

### Etapa 2: Definir um novo calendário e torná‑lo padrão.
```csharp
var calendar = project.Calendars.Add("New Standard Calendar");
Calendar.MakeStandardCalendar(calendar);
```

### Etapa 3: Salvar o projeto.
```csharp
project.Save(OutDir + "MakeAStandardCalendar_out.xml", SaveFileFormat.Xml);
```

## Problemas Comuns e Soluções

- **Calendário não encontrado ao usar `GetByName`** – Certifique‑se de que o nome exato corresponde ao caso usado quando o calendário foi adicionado.  
- **Horas de trabalho não aplicadas** – Após definir `WorkingTime`, lembre‑se de salvar o projeto; caso contrário, as alterações permanecem apenas na memória.  
- **Falha ao importar calendários de um arquivo MPP** – Verifique se o arquivo de origem é um arquivo Microsoft Project válido e se você tem permissões de leitura.

## Perguntas Frequentes

### Q1: Posso criar dias úteis personalizados no Aspose.Tasks?

A1: Sim, você pode criar dias úteis personalizados adicionando exceções aos calendários.

### Q2: É possível importar calendários de arquivos Microsoft Project?

A2: Absolutamente, o Aspose.Tasks suporta a importação de calendários de arquivos Microsoft Project.

### Q3: Como posso remover um calendário específico de um projeto?

A3: Você pode remover um calendário obtendo‑o da coleção e então chamando o método `Remove`.

### Q4: O Aspose.Tasks suporta exportar calendários para diferentes formatos?

A4: Sim, o Aspose.Tasks permite exportar calendários para vários formatos como XML, MPP, etc.

### Q5: Posso personalizar horas de trabalho para dias específicos em um calendário?

A5: Certamente, você pode definir horas de trabalho para dias individuais usando exceções no calendário.

## Perguntas Frequentes

**Q: Qual é a melhor maneira de definir um calendário de turno de 24 horas?**  
A: Crie um novo calendário, limpe as entradas existentes de `WorkingTime` e adicione um único intervalo `WorkingTime` das 00:00 às 24:00 para cada dia da semana.

**Q: Posso copiar um calendário de um projeto para outro?**  
A: Sim—exporte o calendário para XML usando `project.Save` e então importe‑o em outro projeto com `new Project(xmlPath)`.

**Q: Como importar programaticamente calendários do Microsoft Project?**  
A: Carregue o arquivo MPP com `new Project("source.mpp")`; os calendários ficam disponíveis via `project.Calendars`.

**Q: Existe um limite para o número de calendários em um projeto?**  
A: Praticamente não; a coleção pode conter quantos calendários a memória permitir, mas mantenha a lista gerenciável para desempenho.

**Q: As alterações em um calendário atualizam automaticamente as tarefas que o utilizam?**  
A: Sim—tarefas vinculadas a um calendário refletem os horários de trabalho atualizados após você salvar o projeto.

---

**Última atualização:** 2026-04-13  
**Testado com:** Aspose.Tasks 24.11 for .NET  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}