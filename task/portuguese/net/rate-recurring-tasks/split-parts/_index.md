---
title: Manipulando partes divididas do MS Project em Aspose.Tasks
linktitle: Manipulação de peças divididas em Aspose.Tasks
second_title: API Aspose.Tasks .NET
description: Aprenda como lidar com partes divididas do MS Project de forma eficiente com Aspose.Tasks for .NET. Aprimore seu fluxo de trabalho de gerenciamento de projetos.
type: docs
weight: 18
url: /pt/net/rate-recurring-tasks/split-parts/
---

## Introdução
O gerenciamento de partes divididas do MS Project pode ser um aspecto crucial do gerenciamento de projetos ao usar o Aspose.Tasks for .NET. Neste tutorial, exploraremos como lidar com peças divididas de maneira eficaz usando orientação passo a passo.
## Pré-requisitos
Antes de mergulhar no tutorial, certifique-se de ter os seguintes pré-requisitos:
1.  Instalação do Aspose.Tasks for .NET: Baixe e instale o Aspose.Tasks for .NET do[local na rede Internet](https://releases.aspose.com/tasks/net/).
   
2. Compreensão básica de C#: A familiaridade com a linguagem de programação C# será benéfica.

## Importar namespaces
No seu código C#, certifique-se de importar os namespaces necessários:
```csharp
    using Aspose.Tasks;
    using System;
    
```

## Etapa 1: Criando uma Instância de Projeto
```csharp
var project = new Project();
```
 Crie uma nova instância do`Project` aula.
## Etapa 2: Definir datas de início e término do projeto
```csharp
project.Set(Prj.StartDate, new DateTime(2000, 3, 15, 8, 0, 0));
project.Set(Prj.FinishDate, new DateTime(2000, 3, 21, 17, 0, 0));
```
Defina as datas de início e término do projeto.
## Etapa 3: adicionar uma tarefa
```csharp
var task = project.RootTask.Children.Add("Task1");
```
Adicione uma nova tarefa ao projeto.
## Etapa 4: definir propriedades da tarefa
```csharp
task.Set(Tsk.IsManual, false);
task.Set(Tsk.Start, new DateTime(2000, 3, 15, 8, 0, 0));
task.Set(Tsk.Duration, project.GetDuration(3));
```
Defina propriedades como status manual, data de início e duração da tarefa.
## Passo 5: Adicionando Atribuições de Recursos
```csharp
var assignment = project.ResourceAssignments.Add(task, project.Resources.Add("r1"));
```
Adicione atribuições de recursos à tarefa.
## Etapa 6: definir propriedades de atribuição
```csharp
assignment.Set(Asn.Start, new DateTime(2000, 3, 15, 8, 0, 0));
assignment.Set(Asn.Work, task.Get(Tsk.Work));
assignment.Set(Asn.Finish, new DateTime(2000, 3, 19, 17, 0, 0));
```
Defina propriedades como data de início, trabalho e data de término da tarefa.
## Etapa 7: Gerando dados em fases
```csharp
assignment.TimephasedDataFromTaskDuration(project.Get(Prj.Calendar));
```
Gere dados faseados no tempo para a tarefa com base no calendário do projeto.
## Passo 8: Dividindo a Tarefa
```csharp
assignment.SplitTask(new DateTime(2000, 3, 16, 8, 0, 0), new DateTime(2000, 3, 17, 17, 0, 0), project.Get(Prj.Calendar));
```
Divida a tarefa em várias partes dentro do prazo especificado.
## Etapa 9: Iterando em partes divididas
```csharp
Console.WriteLine("Number of split parts: " + task.SplitParts.Count);
foreach (var splitPart in task.SplitParts)
{
    Console.WriteLine("  Split Part Start: " + splitPart.Start);
    Console.WriteLine("  Split Part Finish: " + splitPart.Finish);
    Console.WriteLine();
}
```
Itere sobre as partes divididas da tarefa e imprima suas datas de início e término.

## Conclusão
O manuseio eficaz das partes divididas do MS Project no Aspose.Tasks for .NET é crucial para a eficiência do gerenciamento de projetos. Seguindo as etapas descritas neste tutorial, você pode gerenciar facilmente tarefas divididas e aprimorar seu fluxo de trabalho de gerenciamento de projetos.
## Perguntas frequentes
### P: Posso usar Aspose.Tasks for .NET com outras estruturas .NET?
R: Sim, Aspose.Tasks for .NET é compatível com vários frameworks .NET, incluindo .NET Core e .NET Standard.
### P: Existe uma avaliação gratuita disponível para Aspose.Tasks for .NET?
 R: Sim, você pode obter uma avaliação gratuita em[aqui](https://releases.aspose.com/).
### P: O Aspose.Tasks for .NET oferece suporte ao gerenciamento de recursos?
R: Sim, o Aspose.Tasks for .NET permite gerenciar os recursos do projeto com eficiência.
### P: Posso personalizar calendários de projetos usando Aspose.Tasks for .NET?
R: Com certeza, você pode personalizar calendários de projetos de acordo com os requisitos do seu projeto.
### P: Onde posso encontrar suporte para Aspose.Tasks for .NET?
 R: Você pode encontrar suporte e assistência no site[Fórum Aspose.Tasks](https://forum.aspose.com/c/tasks/15).