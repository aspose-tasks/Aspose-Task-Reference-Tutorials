---
title: Gerenciar coleção de atributos do MS Project em Aspose.Tasks
linktitle: Gerenciando coleção estendida de atributos em Aspose.Tasks
second_title: API Aspose.Tasks .NET
description: Aprenda como gerenciar com eficiência atributos estendidos do MS Project usando Aspose.Tasks for .NET. Manipule perfeitamente os atributos da tarefa com orientação passo a passo.
type: docs
weight: 12
url: /pt/net/tasks-project-management/extended-attribute-collection/
---
## Introdução
Você está procurando gerenciar com eficiência os atributos estendidos do MS Project usando Aspose.Tasks for .NET? Neste tutorial, guiaremos você pelo processo passo a passo. Vamos mergulhar!
## Pré-requisitos
Antes de começarmos, certifique-se de ter o seguinte:
1. Visual Studio: instale o Visual Studio em seu sistema.
2.  Aspose.Tasks for .NET: Baixe e instale Aspose.Tasks for .NET em[aqui](https://releases.aspose.com/tasks/net/).
3. Conhecimento básico de C#: Familiarize-se com os fundamentos da linguagem de programação C#.

## Importar namespaces
Comece importando os namespaces necessários para o seu projeto:
```csharp
    using Aspose.Tasks;
    using System;
    
```
## Etapa 1: carregar o arquivo do projeto
Primeiro, carregue o arquivo MS Project usando o seguinte trecho de código:
```csharp
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "ReadTaskExtendedAttributes.mpp");
```
## Etapa 2: acessar tarefas e atributos estendidos
Acesse uma tarefa específica e seus atributos estendidos:
```csharp
var task = project.RootTask.Children.GetById(1);
```
## Etapa 3: limpar atributos estendidos
Limpe os atributos estendidos existentes, se necessário:
```csharp
if (!task.ExtendedAttributes.IsReadOnly && task.ExtendedAttributes.Count > 0)
{
    task.ExtendedAttributes.Clear();
}
```
## Etapa 4: criar definições de atributos estendidos
Crie definições para novos atributos estendidos:
```csharp
var taskDefinition1 = ExtendedAttributeDefinition.CreateTaskDefinition(CustomFieldType.Start, ExtendedAttributeTask.Start7, "Start 7");
var taskDefinition2 = ExtendedAttributeDefinition.CreateTaskDefinition(CustomFieldType.Finish, ExtendedAttributeTask.Finish7, "Finish 7");
project.ExtendedAttributes.Add(taskDefinition1);
project.ExtendedAttributes.Add(taskDefinition2);
```
## Etapa 5: Iterar sobre atributos estendidos da tarefa
Iterar sobre atributos estendidos da tarefa:
```csharp
Console.WriteLine("Iterate over task extended attributes of " + task.Get(Tsk.Name) + " task: ");
foreach (var attribute in task.ExtendedAttributes)
{
    Console.WriteLine("Attribute FieldId: " + attribute.FieldId);
    Console.WriteLine("Attribute Value: " + attribute.DateValue);
    Console.WriteLine();
}
```
## Etapa 6: adicionar atributos estendidos
Adicione novos atributos estendidos à tarefa:
```csharp
var extendedAttribute1 = taskDefinition1.CreateExtendedAttribute();
extendedAttribute1.DateValue = new DateTime(2020, 4, 14, 8, 0, 0);
if (task.ExtendedAttributes.IndexOf(extendedAttribute1) < 0)
{
    task.ExtendedAttributes.Insert(0, extendedAttribute1);
}
var extendedAttribute2 = taskDefinition2.CreateExtendedAttribute();
extendedAttribute2.DateValue = new DateTime(2020, 4, 14, 17, 0, 0);
task.ExtendedAttributes.Add(extendedAttribute2);
```
## Etapa 7: trabalhar com atributos estendidos
Execute operações em atributos estendidos conforme necessário.
## Etapa 8: remover atributos estendidos
Remova atributos estendidos por índice ou condicionalmente:
```csharp
task.ExtendedAttributes.RemoveAt(0);
task.ExtendedAttributes.Remove(extendedAttribute2);
```
## Etapa 9: copiar atributos para outra tarefa
Copie atributos para outra tarefa dentro do mesmo projeto ou de um projeto diferente:
```csharp
var otherProject = new Project();
var otherTask = otherProject.RootTask.Children.Add("Other task");
foreach (var attribute in attributes)
{
    otherTask.ExtendedAttributes.Add(attribute);
}
```

## Conclusão
gerenciamento de coleções de atributos estendidos do MS Project torna-se perfeito com Aspose.Tasks for .NET. Seguindo as etapas descritas neste tutorial, você pode lidar com atributos estendidos com eficiência, aprimorando seus recursos de gerenciamento de projetos.
## Perguntas frequentes
### P: Posso manipular atributos estendidos em vários projetos?
R: Sim, você pode copiar atributos estendidos entre tarefas em projetos diferentes usando Aspose.Tasks for .NET.
### P: Existem limitações quanto ao número de atributos estendidos por tarefa?
R: Aspose.Tasks for .NET não impõe limitações inerentes ao número de atributos estendidos por tarefa.
### P: Posso criar campos de atributos estendidos personalizados?
R: Absolutamente! Aspose.Tasks for .NET permite que você defina campos de atributos estendidos personalizados, adaptados aos requisitos do seu projeto.
### P: O Aspose.Tasks for .NET oferece suporte à leitura e gravação em arquivos do MS Project de várias versões?
R: Sim, Aspose.Tasks for .NET oferece suporte a formatos de arquivo MS Project em diferentes versões.
### P: Existe uma versão de teste disponível para Aspose.Tasks for .NET?
 R: Sim, você pode baixar uma avaliação gratuita em[aqui](https://releases.aspose.com/).