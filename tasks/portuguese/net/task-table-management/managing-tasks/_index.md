---
title: Gerenciando tarefas em Aspose.Tasks
linktitle: Gerenciando tarefas em Aspose.Tasks
second_title: API Aspose.Tasks .NET
description: Explore o guia completo sobre gerenciamento de tarefas com Aspose.Tasks for .NET. Aprenda a adicionar, exibir partes divididas, mover, obter/definir propriedades e muito mais.
weight: 15
url: /pt/net/task-table-management/managing-tasks/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Gerenciando tarefas em Aspose.Tasks

## Introdução
Se você é um desenvolvedor .NET que deseja gerenciar tarefas em seus projetos com eficiência, o Aspose.Tasks for .NET oferece uma solução robusta. Este tutorial irá guiá-lo através de vários aspectos do gerenciamento de tarefas usando Aspose.Tasks, oferecendo instruções passo a passo e exemplos de código. Esteja você adicionando tarefas, exibindo partes divididas, movendo tarefas sob o mesmo pai, obtendo/definindo propriedades de tarefas, iterando atribuições de tarefas, lendo linhas de base de tarefas ou excluindo tarefas, este guia tem o que você precisa.
## Pré-requisitos
Antes de mergulhar no tutorial, certifique-se de ter os seguintes pré-requisitos em vigor:
1. Biblioteca Aspose.Tasks for .NET: certifique-se de ter a biblioteca Aspose.Tasks for .NET instalada. Você pode baixá-lo[aqui](https://releases.aspose.com/tasks/net/).
2. Diretório de documentos: Configure um diretório onde os documentos do seu projeto serão armazenados.
## Importar namespaces
Em seu projeto .NET, inclua os namespaces necessários para trabalhar com Aspose.Tasks:
```csharp

    using Aspose.Tasks;
    using System;
    using System.Collections.Generic;
    using System.Diagnostics.CodeAnalysis;
    using System.Linq;
    
    using Aspose.Tasks.Saving;
    using Aspose.Tasks.Util;
```
## 1. Adicionando uma tarefa a um projeto
```csharp
// Crie um novo projeto
var project = new Project();
// Adicionar uma tarefa
var task = project.RootTask.Children.Add("Task1");
task.Set(Tsk.Start, new DateTime(2012, 8, 23, 8, 0, 0));
task.Set(Tsk.Duration, project.GetDuration(24, TimeUnitType.Hour));
task.Set(Tsk.ActualStart, new DateTime(2012, 8, 23, 8, 0, 0));
// Salve o projeto
project.Save(DataDir + "CreateNewTask_out.xml", SaveFileFormat.Xml);
```
## 2. Exibindo as partes divididas da tarefa
```csharp
// Carregar um projeto com tarefas divididas
var project = new Project(DataDir + "ViewSplitTasks.mpp");
// Acessar uma tarefa
var task = project.RootTask.Children.GetById(4);
// Exibir peças divididas
var collection = task.SplitParts;
foreach (var splitPart in collection)
{
    Console.WriteLine("Start: " + splitPart.Start + "\nFinish: " + splitPart.Finish + "\n");
}
```
## 3. Movendo uma tarefa sob o mesmo pai
```csharp
try
{
    // Carregar um projeto
    var project = new Project(DataDir + "MoveTask.mpp");
    // Mova tarefas com id 5 antes da tarefa com id 3
    var task = project.RootTask.Children.GetById(5);
    task.MoveToSibling(3);
    // Salve o projeto modificado
    project.Save(DataDir + "MoveTaskUnderSameParent_out.mpp", SaveFileFormat.Mpp);
}
catch (NotSupportedException ex)
{
    Console.WriteLine(ex.Message + "\nPlease apply a valid Aspose.Tasks License.");
}
```
## 4. Obtendo/definindo propriedades da tarefa
```csharp
// Crie um novo projeto
var project = new Project();
// Adicione uma tarefa e defina propriedades
var task = project.RootTask.Children.Add();
task.Set(Tsk.Name, "Task1");
task.Set(Tsk.Start, new DateTime(2020, 3, 31, 8, 0, 0));
task.Set(Tsk.Finish, new DateTime(2020, 3, 31, 17, 0, 0));
// Coletar e exibir propriedades de tarefas
var collector = new ChildTasksCollector();
TaskUtils.Apply(project.RootTask, collector, 0);
foreach (var tsk in collector.Tasks)
{
    Console.WriteLine("Task Id: {0}", tsk.Get(Tsk.Id));
    Console.WriteLine("Task Uid: {0}", tsk.Get(Tsk.Uid));
    Console.WriteLine("Task Name: {0}", tsk.Get(Tsk.Name));
    Console.WriteLine("Task Start: {0}", tsk.Get(Tsk.Start));
    Console.WriteLine("Task Finish: {0}", tsk.Get(Tsk.Finish));
}
```
## 5. Iterando as atribuições da tarefa
```csharp
// Carregar um projeto com atribuições
var project = new Project(DataDir + "BudgetWorkAndCost.mpp");
// Colete e exiba atribuições de tarefas
var collector = new ChildTasksCollector();
TaskUtils.Apply(project.RootTask, collector, 0);
foreach (var task in collector.Tasks)
{
    foreach (var assignment in task.Assignments)
    {
        Console.WriteLine(assignment.ToString());
    }
}
```
## 6. Lendo as linhas de base da tarefa
```csharp
// Crie um novo projeto
var project = new Project();
// Adicione uma tarefa e defina uma linha de base
var task = project.RootTask.Children.Add("Task");
project.SetBaseline(BaselineType.Baseline);
// Exibir duração da linha de base da tarefa
foreach (var baseline in task.Baselines)
{
    Console.WriteLine("Baseline duration is 1 day: {0}", baseline.Duration.ToString().Equals("1 day"));
    Console.WriteLine("BaselineStart is same as Task Start: {0}", baseline.Start.Equals(task.Get(Tsk.Start)));
    Console.WriteLine("BaselineFinish is same as Task Finish: {0}", baseline.Finish.Equals(task.Get(Tsk.Finish)));
}
```
## 7. Excluindo uma tarefa
```csharp
// Crie um novo projeto
var project = new Project();
// Adicionar uma tarefa
var task = project.RootTask.Children.Add("Task");
//Exibir o número de tarefas antes e depois da exclusão
Console.WriteLine("Number of tasks: " + project.RootTask.Children.Count);
// Exclua a tarefa
task.Delete();
Console.WriteLine("Number of tasks: " + project.RootTask.Children.Count);
```
## Conclusão
Gerenciar tarefas no Aspose.Tasks for .NET é um processo contínuo com os exemplos fornecidos. Quer você seja um desenvolvedor experiente ou esteja apenas começando, a incorporação dessas técnicas aprimorará suas capacidades de gerenciamento de projetos.
## perguntas frequentes
### P: O Aspose.Tasks é compatível com todos os frameworks .NET?
R: Sim, Aspose.Tasks oferece suporte a vários frameworks .NET, garantindo compatibilidade com seu ambiente de desenvolvimento.
### P: Como posso obter uma licença temporária para Aspose.Tasks?
 R: Você pode obter uma licença temporária de 30 dias em[aqui](https://purchase.aspose.com/temporary-license/).
### P: Há alguma limitação ao trabalhar com tarefas divididas no Aspose.Tasks?
 R: As tarefas divididas são um recurso poderoso e você pode encontrar documentação detalhada[aqui](https://reference.aspose.com/tasks/net/).
### P: Posso personalizar as propriedades da tarefa além do que é mostrado nos exemplos?
R: Absolutamente! Aspose.Tasks oferece amplas opções de personalização para propriedades de tarefas. Verifique a documentação para mais detalhes.
### P: Como obtenho suporte para Aspose.Tasks?
 R: Visite o[Fórum Aspose.Tasks](https://forum.aspose.com/c/tasks/15) para apoio e discussões da comunidade.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
