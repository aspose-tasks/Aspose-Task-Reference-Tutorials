---
title: Modo de cálculo em Aspose.Tasks
linktitle: Modo de cálculo em Aspose.Tasks
second_title: API Aspose.Tasks .NET
description: Aprenda como gerenciar modos de cálculo de forma eficaz em Aspose.Tasks for .NET para agilizar o agendamento de projetos e dependências de tarefas.
weight: 29
url: /pt/net/advanced-features/calculation-mode/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Modo de cálculo em Aspose.Tasks

## Introdução

Aspose.Tasks for .NET é uma API poderosa que permite aos desenvolvedores trabalhar com arquivos do Microsoft Project programaticamente em seus aplicativos .NET. Um aspecto crucial do trabalho com arquivos de projeto é o gerenciamento dos modos de cálculo, que determinam como as tarefas e os cronogramas do projeto são calculados e atualizados. Neste tutorial, nos aprofundaremos nos vários modos de cálculo suportados pelo Aspose.Tasks for .NET e demonstraremos como usá-los de forma eficaz.

## Pré-requisitos

Antes de começar, certifique-se de ter o seguinte:

1. Visual Studio: certifique-se de ter o Visual Studio instalado em seu sistema.
2.  Aspose.Tasks for .NET: Baixe e instale a biblioteca Aspose.Tasks for .NET em[aqui](https://releases.aspose.com/tasks/net/).
3. Compreensão básica da programação C#: Familiarize-se com os conceitos de programação C#.

## Importar namespaces

Antes de começarmos a trabalhar com Aspose.Tasks for .NET, vamos importar os namespaces necessários:

```csharp
using Aspose.Tasks;
using System;


```

## Aplicando o modo de cálculo automático

### Etapa 1: criar uma nova instância do projeto

 Inicialize um novo`Project` objeto e definir seu`CalculationMode` propriedade para`CalculationMode.Automatic`.

```csharp
var project = new Project
{
   CalculationMode = CalculationMode.Automatic
};
```

### Etapa 2: definir a data de início do projeto e adicionar tarefas

Defina a data de início do projeto e adicione tarefas a ele.

```csharp
project.Set(Prj.StartDate, new DateTime(2015, 4, 15));
var task1 = project.RootTask.Children.Add("Task 1");
var task2 = project.RootTask.Children.Add("Task 2");
```

### Etapa 3: vincular tarefas

Estabeleça dependências entre tarefas.

```csharp
project.TaskLinks.Add(task1, task2, TaskLinkType.FinishToStart);
```

### Etapa 4: verifique as datas recalculadas

Verifique se as datas foram recalculadas automaticamente.

```csharp
Console.WriteLine("Task1 Start + 1 Equals Task2 Start : {0} ", task1.Get(Tsk.Start).AddDays(1).Equals(task2.Get(Tsk.Start)));
// Adicione mais verificações conforme necessário
```

## Aplicando o modo de cálculo manual

### Etapa 1: criar uma nova instância do projeto

 Inicialize um novo`Project` objeto e definir seu`CalculationMode` propriedade para`CalculationMode.Manual`.

```csharp
var project = new Project
{
   CalculationMode = CalculationMode.Manual
};
```

### Etapa 2: definir a data de início do projeto e adicionar tarefas

Defina a data de início do projeto e adicione tarefas a ele.

```csharp
project.Set(Prj.StartDate, new DateTime(2015, 4, 15));
var task1 = project.RootTask.Children.Add("Task 1");
var task2 = project.RootTask.Children.Add("Task 2");
```

### Etapa 3: verificar as propriedades da tarefa

Verifique se as propriedades da tarefa estão definidas corretamente no modo manual.

```csharp
Console.WriteLine("Task1.Id Equals 1 : {0} ", task1.Get(Tsk.Id).Equals(1));
// Adicione mais verificações conforme necessário
```

### Etapa 4: vincular tarefas e verificar datas

Vincule as tarefas e verifique se suas datas não são recalculadas.

```csharp
project.TaskLinks.Add(task1, task2, TaskLinkType.FinishToStart);
```

## Aplicando nenhum modo de cálculo

### Etapa 1: criar uma nova instância do projeto

 Inicialize um novo`Project` objeto e definir seu`CalculationMode` propriedade para`CalculationMode.None`.

```csharp
var project = new Project
{
   CalculationMode = CalculationMode.None
};
```

### Etapa 2: adicione uma nova tarefa

Adicione uma nova tarefa ao projeto.

```csharp
var task = project.RootTask.Children.Add("Task");
```

### Etapa 3: verificar as propriedades da tarefa

Verifique se as propriedades da tarefa não são calculadas automaticamente.

```csharp
Console.WriteLine("Task.Id Equals 0 : {0} ", task.Get(Tsk.Id).Equals(0));
// Adicione mais verificações conforme necessário
```

## Conclusão

Neste tutorial, exploramos os modos de cálculo disponíveis no Aspose.Tasks for .NET e aprendemos como aplicá-los em cenários práticos. Quer você precise do modo de cálculo automático, manual ou sem cálculo, o Aspose.Tasks oferece a flexibilidade para atender aos requisitos do seu projeto.

## Perguntas frequentes

### Q1: Posso alterar o modo de cálculo dinamicamente durante o tempo de execução?

A1: Sim, você pode alterar o modo de cálculo de um projeto a qualquer momento durante o tempo de execução, modificando o`CalculationMode` propriedade.

### Q2: O Aspose.Tasks oferece suporte a outros formatos de arquivo de gerenciamento de projetos além do Microsoft Project?

A2: Aspose.Tasks concentra-se principalmente nos formatos de arquivo do Microsoft Project, mas também suporta outros formatos como Primavera P6 XML, Primavera DB e Asta Powerproject XML.

### Q3: O Aspose.Tasks é adequado para projetos de pequena escala e de nível empresarial?

A3: Com certeza! Aspose.Tasks foi projetado para atender às necessidades de projetos de pequena escala e de nível empresarial com seus recursos abrangentes e APIs robustas.

### Q4: Posso integrar Aspose.Tasks com outras bibliotecas e estruturas .NET?

A4: Sim, você pode integrar perfeitamente o Aspose.Tasks com outras bibliotecas e estruturas .NET para aprimorar a funcionalidade de seus aplicativos.

### P5: Existe um fórum da comunidade ou canal de suporte disponível para usuários do Aspose.Tasks?

 A5: Sim, você pode visitar o[Fórum Aspose.Tasks](https://forum.aspose.com/c/tasks/15) para apoio e discussões da comunidade.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
