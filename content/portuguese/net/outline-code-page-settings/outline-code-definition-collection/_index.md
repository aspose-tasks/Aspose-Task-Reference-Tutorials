---
title: Coleção de definições de código de contorno em Aspose.Tasks .NET
linktitle: Coleção de definições de código de contorno em Aspose.Tasks
second_title: API Aspose.Tasks .NET
description: Aprenda como manipular definições de código de estrutura de tópicos em documentos do Microsoft Project usando Aspose.Tasks for .NET. Categorização dos dados do seu projeto sem esforço.
type: docs
weight: 13
url: /pt/net/outline-code-page-settings/outline-code-definition-collection/
---
## Introdução
Aspose.Tasks é uma biblioteca .NET poderosa projetada para manipular documentos do Microsoft Project com facilidade e eficiência. Um de seus principais recursos é a capacidade de trabalhar com definições de código de estrutura de tópicos, permitindo aos usuários organizar e categorizar os dados do projeto de forma eficaz. Neste tutorial, exploraremos como trabalhar com definições de código de estrutura de tópicos usando Aspose.Tasks for .NET.
## Pré-requisitos
Antes de mergulharmos no tutorial, certifique-se de ter o seguinte:
1. Compreensão básica de C#: A familiaridade com a linguagem de programação C# será benéfica.
2. Visual Studio: instale o Visual Studio ou qualquer outro ambiente de desenvolvimento C# preferido.
3.  Aspose.Tasks for .NET: Baixe e instale a biblioteca Aspose.Tasks for .NET em[aqui](https://releases.aspose.com/tasks/net/).

## Importar namespaces
Para começar, certifique-se de importar os namespaces necessários:
```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;

```
## Etapa 1: carregar um documento do Microsoft Project
Primeiramente, carregue um documento do Microsoft Project para começar a trabalhar com definições de código de estrutura de tópicos:
```csharp
// O caminho para o diretório de documentos.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "OutlineCodes.mpp");
```
## Etapa 2: acessar as definições de código de estrutura de tópicos
Agora, vamos acessar as definições do código de estrutura dentro do projeto:
```csharp
Console.WriteLine("Count of outline code definitions: " + project.OutlineCodes.Count);
foreach (var outlineCode in project.OutlineCodes)
{
	Console.WriteLine("Field Name: " + outlineCode.FieldName);
	Console.WriteLine("Alias: " + outlineCode.Alias);
	Console.WriteLine();
}
```
## Etapa 3: adicionar definições de código de contorno personalizado
Você pode adicionar definições de código de estrutura personalizadas da seguinte maneira:
```csharp
var outlineCodeDefinition = new OutlineCodeDefinition { FieldId = ((int)ExtendedAttributeTask.OutlineCode3).ToString("D"), Alias = "My Outline Code" };
if (!project.OutlineCodes.IsReadOnly)
{
    project.OutlineCodes.Add(outlineCodeDefinition);
}
```
## Etapa 4: modificar as definições do código de estrutura
Modifique facilmente as definições de código de estrutura existentes:
```csharp
var index = project.OutlineCodes.IndexOf(outlineCodeDefinition);
project.OutlineCodes[index].Alias = "New Alias";
```
## Etapa 5: remover definições de código de estrutura de tópicos
Remova as definições de código de estrutura de tópicos quando não forem mais necessárias:
```csharp
if (project.OutlineCodes.Contains(outlineCodeDefinition))
{
    project.OutlineCodes.Remove(outlineCodeDefinition);
}
```
## Etapa 6: salvar alterações
Finalmente, salve suas alterações no documento do projeto:
```csharp
project.Save(DataDir + "ModifiedOutlineCodes.mpp", SaveFileFormat.MPP);
```

## Conclusão
Concluindo, Aspose.Tasks for .NET fornece funcionalidade abrangente para gerenciar definições de código de estrutura em documentos do Microsoft Project. Seguindo as etapas descritas neste tutorial, você pode manipular com eficiência as definições de código de estrutura para organizar e categorizar os dados do seu projeto de maneira eficaz.
## Perguntas frequentes
### P: Posso adicionar diversas definições de código de estrutura a um único projeto?
 R: Sim, você pode adicionar diversas definições de código de estrutura a um projeto com base em seus requisitos. Basta usar o`Add` método para cada definição que você deseja incluir.
### P: É possível remover todas as definições de código de estrutura de um projeto de uma só vez?
 R: Sim, você pode limpar todas as definições de código de estrutura de um projeto usando o`Clear` método.
### P: O que acontece se eu tentar modificar uma definição de código de estrutura somente leitura?
R: Se uma definição de código de estrutura for somente leitura, você não poderá modificá-la diretamente. Você precisará verificar seu status somente leitura antes de tentar qualquer modificação.
### P: Há alguma limitação no número de definições de código de estrutura que posso adicionar a um projeto?
R: Aspose.Tasks for .NET não impõe nenhuma limitação específica ao número de definições de código de estrutura que você pode adicionar a um projeto. No entanto, considere as implicações de desempenho ao trabalhar com um grande número de definições.
### P: Posso usar definições de código de estrutura de tópicos para agrupar tarefas com base em critérios personalizados?
R: Sim, as definições de código de estrutura permitem categorizar tarefas com base em critérios personalizados, proporcionando flexibilidade na organização dos dados do projeto.## Código-fonte completo