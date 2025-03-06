---
title: Gerenciando coleções de projetos em Aspose.Tasks
linktitle: Gerenciando coleção de grupo em Aspose.Tasks
second_title: API Aspose.Tasks .NET
description: Aprenda como gerenciar coleções do MS Project com eficiência usando Aspose.Tasks for .NET. Siga nosso guia passo a passo.
weight: 26
url: /pt/net/tasks-project-management/group-collection/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Gerenciando coleções de projetos em Aspose.Tasks

## Introdução
Neste tutorial, exploraremos como gerenciar coleções de grupo do MS Project usando Aspose.Tasks for .NET. Gerenciar coleções de grupos é crucial para organizar e manipular tarefas e recursos de forma eficiente em seu projeto.
## Pré-requisitos
Antes de prosseguir com este tutorial, certifique-se de ter os seguintes pré-requisitos:
1.  Biblioteca Aspose.Tasks for .NET: Baixe e instale a biblioteca Aspose.Tasks for .NET do[Link para Download](https://releases.aspose.com/tasks/net/).
2. Conhecimento básico de C#: Familiarize-se com os fundamentos da linguagem de programação C#, pois este tutorial envolve codificação em C#.
3. Ambiente de desenvolvimento: configure um ambiente de desenvolvimento como Visual Studio ou qualquer outro IDE que suporte desenvolvimento .NET.

## Importar namespaces
Primeiro, vamos importar os namespaces necessários para trabalhar com as funcionalidades do Aspose.Tasks em nosso código C#.

```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;

```
## Etapa 1: carregar o projeto
```csharp
// O caminho para o diretório de documentos.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "ReadGroupDefinitionData.mpp");
```
Esta etapa envolve carregar o arquivo MS Project no objeto de projeto Aspose.Tasks, permitindo-nos realizar operações nele.
## Etapa 2: Iterar em grupos de tarefas
```csharp
Console.WriteLine("Print task groups of {0} project: ", project.Get(Prj.Name));
Console.WriteLine("Task Group Count: " + project.TaskGroups.Count);
foreach (var group in project.TaskGroups)
{
    Console.WriteLine("Index: " + group.Index);
    Console.WriteLine("Name: " + group.Name);
    Console.WriteLine("Show In Menu: " + group.ShowInMenu);
    Console.WriteLine();
}
```
Aqui, iteramos nos grupos de tarefas do projeto, imprimindo detalhes como índice, nome e visibilidade no menu de cada grupo.
## Etapa 3: iterar em grupos de recursos
```csharp
Console.WriteLine("Project resource group count: " + project.ResourceGroups.Count);
foreach (var group in project.ResourceGroups)
{
    Console.WriteLine("Resource group Index: " + group.Index);
    Console.WriteLine("Resource group Name: " + group.Name);
    Console.WriteLine("Resource group ShowInMenu" + group.ShowInMenu);
}
```
Da mesma forma, esta etapa itera sobre grupos de recursos, exibindo seu índice, nome e visibilidade no menu.
## Etapa 4: limpar e copiar grupos para outro projeto
```csharp
var otherProject = new Project(DataDir + "Blank2010.mpp");
// Limpar grupos de outros projetos
otherProject.TaskGroups.Clear();
// Copiar grupos para outro projeto
var groups = new Group[project.TaskGroups.Count];
project.TaskGroups.CopyTo(groups, 0);
foreach (var group in groups)
{
    otherProject.TaskGroups.Add(group);
}
```
Aqui, limpamos os grupos de outro projeto e depois copiamos os grupos do projeto original para ele.
## Etapa 5: adicionar um grupo de tarefas personalizado
```csharp
var customGroup = new Group
{
    Name = "Custom Group",
    ShowInMenu = true
};
if (!otherProject.TaskGroups.Contains(customGroup))
{
    if (!otherProject.TaskGroups.IsReadOnly)
    {
        otherProject.TaskGroups.Add(customGroup);
    }
}
```
Nesta etapa, criamos um grupo de tarefas personalizado e o adicionamos ao outro projeto, caso ainda não esteja presente.
## Etapa 6: remover todos os grupos
```csharp
List<Group> groupsToDelete = otherProject.TaskGroups.ToList();
foreach (var group in groupsToDelete)
{
    otherProject.TaskGroups.Remove(group);
}
```
Finalmente, removemos todos os grupos do outro projeto.

## Conclusão
Gerenciar coleções de grupos do MS Project no Aspose.Tasks for .NET é essencial para organizar e manipular dados do projeto com eficiência. Seguindo as etapas descritas neste tutorial, você pode lidar com eficiência com grupos de tarefas e recursos em seus projetos, melhorando o gerenciamento geral do projeto.
## Perguntas frequentes
### O Aspose.Tasks for .NET é compatível com todas as versões do MS Project?
Aspose.Tasks for .NET oferece suporte a várias versões do Microsoft Project, incluindo 2003, 2007, 2010, 2013, 2016 e 2019.
### Posso personalizar propriedades de grupo usando Aspose.Tasks for .NET?
Sim, você pode personalizar as propriedades do grupo, como nome e visibilidade, usando Aspose.Tasks for .NET.
### O Aspose.Tasks for .NET oferece compatibilidade entre plataformas?
Aspose.Tasks for .NET tem como alvo principal o .NET framework, mas pode ser usado em cenários de plataforma cruzada com .NET Core e .NET Standard.
### Como posso obter suporte para Aspose.Tasks for .NET?
 Você pode obter suporte para Aspose.Tasks for .NET por meio do[Fórum Aspose.Tasks](https://forum.aspose.com/c/tasks/15).
### Existe uma versão de teste disponível para Aspose.Tasks for .NET?
 Sim, você pode baixar uma versão de avaliação gratuita do Aspose.Tasks for .NET em[local na rede Internet](https://releases.aspose.com/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
