---
title: Dominando as máscaras de código WBS com Aspose.Tasks para .NET
linktitle: Coleção de máscaras de código WBS em Aspose.Tasks
second_title: API Aspose.Tasks .NET
description: Aprimore o gerenciamento de projetos com Aspose.Tasks for .NET. Aprenda a criar, gerenciar e transferir máscaras de código WBS sem esforço neste tutorial abrangente.
type: docs
weight: 15
url: /pt/net/view-wbs-code-configuration/wbs-code-mask-collection/
---
## Introdução
No mundo dinâmico do gerenciamento de projetos, organizar tarefas de forma eficiente é crucial. Aspose.Tasks for .NET fornece uma solução poderosa para gerenciar códigos de estrutura analítica do projeto (EAP) sem esforço. Neste tutorial, nos aprofundaremos na coleção de máscaras de código WBS, explorando como implementá-las e manipulá-las usando Aspose.Tasks for .NET.
## Pré-requisitos
Antes de embarcarmos nesta jornada de codificação, certifique-se de ter os seguintes pré-requisitos em vigor:
- Conhecimento prático da linguagem de programação C#.
-  Aspose.Tasks for .NET instalado em seu ambiente de desenvolvimento. Se não, baixe-o[aqui](https://releases.aspose.com/tasks/net/).
- Um editor de código como o Visual Studio para uma experiência de codificação perfeita.
## Importar namespaces
Para começar, vamos importar os namespaces necessários:
```csharp
    using Aspose.Tasks;
    using System;
    using System.Collections.Generic;
    
```
## 1. Inicializar projeto e definição de código WBS
```csharp
var project = new Project();
project.WBSCodeDefinition = new WBSCodeDefinition();
project.WBSCodeDefinition.GenerateWBSCode = true;
project.WBSCodeDefinition.VerifyUniqueness = true;
project.WBSCodeDefinition.CodePrefix = "CRS-";
```
## 2. Definir máscaras de código WBS
Limpe quaisquer máscaras de código existentes e adicione novas:
```csharp
project.WBSCodeDefinition.CodeMaskCollection.Clear();
var mask1 = new WBSCodeMask();
mask1.Length = 2;
mask1.Separator = "-";
mask1.Sequence = WBSSequence.OrderedNumbers;
project.WBSCodeDefinition.CodeMaskCollection.Add(mask1);
var mask2 = new WBSCodeMask();
mask2.Length = 1;
mask2.Separator = "-";
mask2.Sequence = WBSSequence.OrderedUppercaseLetters;
project.WBSCodeDefinition.CodeMaskCollection.Add(mask2);
```
## 3. Exibir informações de máscaras de código
```csharp
Console.WriteLine("WBS Code mask's count: " + project.WBSCodeDefinition.CodeMaskCollection.Count);
Console.WriteLine("Is WBS Code mask collection read-only?: " + project.WBSCodeDefinition.CodeMaskCollection.IsReadOnly);
Console.WriteLine("Masks: ");
Console.WriteLine();
foreach (var wbsMask in project.WBSCodeDefinition.CodeMaskCollection)
{
    Console.WriteLine("Length: " + wbsMask.Length);
    Console.WriteLine("Level: " + wbsMask.Level);
    Console.WriteLine("Separator: " + wbsMask.Separator);
    Console.WriteLine("Sequence: " + wbsMask.Sequence);
    Console.WriteLine();
}
```
## 4. Adicione tarefas ao projeto
```csharp
var task1 = project.RootTask.Children.Add("Task 1");
task1.Children.Add("Task 2");
project.Recalculate();
```
## 5. Recuperar informações da tarefa
```csharp
IEnumerable<Task> childTasks = project.RootTask.SelectAllChildTasks();
foreach (var childTask in childTasks)
{
    Console.WriteLine("Task name: " + childTask.Get(Tsk.Name));
    Console.WriteLine("Task WBS code: " + childTask.Get(Tsk.WBS));
}
```
## 6. Manipule máscaras de código
Remova uma máscara de código e verifique se ela foi removida:
```csharp
project.WBSCodeDefinition.CodeMaskCollection.Remove(mask2);
if (project.WBSCodeDefinition.CodeMaskCollection.Contains(mask2))
{
    throw new InvalidOperationException("WBS code mask wasn't removed.");
}
```
## 7. Copie máscaras de código para outro projeto
```csharp
var otherProject = new Project();
otherProject.WBSCodeDefinition = new WBSCodeDefinition();
otherProject.WBSCodeDefinition.GenerateWBSCode = true;
otherProject.WBSCodeDefinition.VerifyUniqueness = true;
otherProject.WBSCodeDefinition.CodePrefix = "CRS-";
var masks = new WBSCodeMask[project.WBSCodeDefinition.CodeMaskCollection.Count];
project.WBSCodeDefinition.CodeMaskCollection.CopyTo(masks, 0);
foreach (var mask in masks)
{
    otherProject.WBSCodeDefinition.CodeMaskCollection.Add(mask);
}
```
## 8. Exibir máscaras de código em outro projeto
```csharp
List<WBSCodeMask> wbsMasks = otherProject.WBSCodeDefinition.CodeMaskCollection.ToList();
foreach (var wbsMask in wbsMasks)
{
    Console.WriteLine("Length: " + wbsMask.Length);
    Console.WriteLine("Level: " + wbsMask.Level);
    Console.WriteLine("Separator: " + wbsMask.Separator);
    Console.WriteLine("Sequence: " + wbsMask.Sequence);
    Console.WriteLine();
}
```
## 9. Adicione tarefas ao outro projeto
```csharp
var otherTask1 = otherProject.RootTask.Children.Add("Other task 1");
otherTask1.Children.Add("Other task 2");
otherProject.Recalculate();
```
## 10. Exibir códigos WBS no outro projeto
```csharp
Console.WriteLine("Print WBS codes of the other project: ");
IEnumerable<Task> otherChildTasks = otherProject.RootTask.SelectAllChildTasks();
foreach (var childTask in otherChildTasks)
{
    Console.WriteLine("Task name: " + childTask.Get(Tsk.Name));
    Console.WriteLine("Task WBS code: " + childTask.Get(Tsk.WBS));
}
```
## Conclusão
Com Aspose.Tasks for .NET, gerenciar códigos WBS torna-se uma tarefa fácil. Este tutorial abordou a criação, manipulação e transferência de máscaras de código WBS, fornecendo um guia completo para aprimorar sua experiência de gerenciamento de projetos.
## Perguntas frequentes
### P: Posso usar Aspose.Tasks for .NET com outras linguagens de programação?
R: Aspose.Tasks oferece suporte principalmente a linguagens .NET, mas você pode explorar opções de interoperabilidade com outras linguagens.
### P: Existe uma versão de teste disponível para Aspose.Tasks for .NET?
 R: Sim, você pode baixar a versão de teste[aqui](https://releases.aspose.com/).
### P: Como procuro ajuda ou relato problemas com Aspose.Tasks for .NET?
 R: Visite o[Fórum Aspose.Tasks](https://forum.aspose.com/c/tasks/15) para apoio e discussões.
### P: Qual é a finalidade dos códigos EAP no gerenciamento de projetos?
R: Os códigos EAP ajudam a organizar e estruturar as tarefas do projeto de forma hierárquica, fornecendo uma abordagem sistemática ao planejamento do projeto.
### P: Posso personalizar o formato dos códigos WBS no Aspose.Tasks for .NET?
R: Com certeza, você tem controle total sobre o formato e a estrutura dos códigos WBS usando Aspose.Tasks for .NET.