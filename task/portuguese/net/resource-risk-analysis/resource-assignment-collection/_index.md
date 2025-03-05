---
title: Coleção de atribuições de recursos em Aspose.Tasks
linktitle: Coleção de atribuições de recursos em Aspose.Tasks
second_title: API Aspose.Tasks .NET
description: Aprenda como gerenciar atribuições de recursos no Microsoft Project usando Aspose.Tasks for .NET. Tutorial passo a passo com exemplos de código.
type: docs
weight: 12
url: /pt/net/resource-risk-analysis/resource-assignment-collection/
---
## Introdução
Bem-vindo a este tutorial abrangente sobre como gerenciar atribuições de recursos no Microsoft Project usando Aspose.Tasks for .NET. Neste tutorial, nos aprofundaremos no processo passo a passo, garantindo que você tenha um conhecimento sólido de como manipular atribuições de recursos com eficiência. Quer você seja um desenvolvedor experiente ou esteja apenas começando, este guia orientará você em tudo o que você precisa saber.
## Pré-requisitos
Antes de mergulharmos no código, certifique-se de ter a seguinte configuração:
1.  Aspose.Tasks for .NET instalado: Certifique-se de ter o Aspose.Tasks for .NET instalado em seu ambiente de desenvolvimento. Caso contrário, você pode baixá-lo em[aqui](https://releases.aspose.com/tasks/net/).
2. Conhecimento básico de C#: Este tutorial pressupõe que você tenha um conhecimento básico da linguagem de programação C#.
3. Arquivo do Microsoft Project: Tenha um arquivo do Microsoft Project pronto para fins de teste. Se não tiver um, você pode criar um arquivo de amostra.

## Importar namespaces
Primeiro, vamos importar os namespaces necessários:
```csharp
    using Aspose.Tasks;
    using System;
    using System.Collections.Generic;
    
```
## Etapa 1: carregar o arquivo do projeto
Comece carregando o arquivo do Microsoft Project:
```csharp
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "TemplateResource2010.mpp");
```
## Etapa 2: adicionar tarefa e recurso
Agora, vamos adicionar uma tarefa e um recurso ao projeto:
```csharp
var task = project.RootTask.Children.Add("Task 1");
var resource = project.Resources.Add("Resource 1");
```
## Etapa 3: Atribuir recurso à tarefa
A seguir, atribuiremos o recurso à tarefa:
```csharp
var assignment = project.ResourceAssignments.Add(task, resource);
assignment.Set(Asn.Start, new DateTime(2019, 9, 23, 9, 0, 0));
assignment.Set(Asn.Work, project.GetWork(40));
assignment.Set(Asn.Finish, new DateTime(2019, 9, 27, 18, 0, 0));
```
## Etapa 4: trabalhando com diferentes tipos de tarefas
Você também pode trabalhar com atribuições que envolvam unidades ou custos:
```csharp
var assignmentWithUnits = project.ResourceAssignments.Add(task, resource, 1d);
var assignmentWithCost = project.ResourceAssignments.Add(task, resource);
// Defina propriedades para atribuições com unidades e custos de forma semelhante à mostrada na Etapa 3
```
## Etapa 5: imprimir tarefas
Imprima as tarefas do projeto:
```csharp
Console.WriteLine("Print assignments for the project: " + project.ResourceAssignments.ParentProject.Get(Prj.Name));
Console.WriteLine("Resource assignment count: " + project.ResourceAssignments.Count);
foreach (var resourceAssignment in project.ResourceAssignments)
{
    // Imprimir detalhes da tarefa
}
```
## Etapa 6: recuperar atribuição por UID
Você pode recuperar atribuições por UID:
```csharp
var assignmentByUid = project.ResourceAssignments.GetByUid(2);
Console.WriteLine("Assignment By Uid Start: " + assignmentByUid.Get(Asn.Start));
```
## Etapa 7: verifique o status somente leitura
Verifique se a coleção de atribuições de recursos é somente leitura:
```csharp
Console.WriteLine("Is resource assignment collection read-only?: " + project.ResourceAssignments.IsReadOnly);
```
## Etapa 8: converter coleção em lista e iterar
Converta a coleção em uma lista e itere sobre ela:
```csharp
List<ResourceAssignment> resourceAssignments = project.ResourceAssignments.ToList();
foreach (var ra in resourceAssignments)
{
    Console.WriteLine(ra.ToString());
}
```

## Conclusão
Parabéns! Você aprendeu como gerenciar atribuições de recursos no Microsoft Project usando Aspose.Tasks for .NET. Seguindo essas etapas, você pode manipular tarefas e recursos com eficiência, facilitando o gerenciamento de projetos.
## Perguntas frequentes
### P: Posso usar o Aspose.Tasks for .NET com diferentes versões de arquivos do Microsoft Project?
R: Sim, Aspose.Tasks for .NET oferece suporte a várias versões de arquivos do Microsoft Project, incluindo formatos MPP, MPT e XML.
### P: Existe uma versão de teste disponível antes de comprar o Aspose.Tasks for .NET?
 R: Sim, você pode obter uma avaliação gratuita do Aspose.Tasks for .NET em[aqui](https://releases.aspose.com/).
### P: Como posso obter suporte se encontrar algum problema ao usar o Aspose.Tasks for .NET?
 R: Você pode buscar suporte no fórum Aspose.Tasks[aqui](https://forum.aspose.com/c/tasks/15).
### P: Posso usar licenças temporárias para Aspose.Tasks for .NET?
 R: Sim, licenças temporárias estão disponíveis para fins de avaliação. Você pode obter um de[aqui](https://purchase.aspose.com/temporary-license/).
### P: Onde posso adquirir uma licença completa do Aspose.Tasks for .NET?
 R: Você pode comprar uma licença completa na loja online Aspose[aqui](https://purchase.aspose.com/buy).