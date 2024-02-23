---
title: Coleção MS Project de códigos de contorno em Aspose.Tasks
linktitle: Coleção de códigos de contorno em Aspose.Tasks
second_title: API Aspose.Tasks .NET
description: Aprenda como coletar códigos de estrutura de tópicos do Microsoft Project usando Aspose.Tasks for .NET. Este tutorial abrangente fornece instruções passo a passo.
type: docs
weight: 11
url: /pt/net/outline-code-page-settings/outline-code-collection/
---
## Introdução
Neste tutorial, exploraremos como coletar códigos de estrutura de tópicos do Microsoft Project usando Aspose.Tasks for .NET. Dividiremos o processo em instruções passo a passo para garantir clareza e compreensão.
## Pré-requisitos
Antes de começarmos, certifique-se de ter o seguinte:
1. Visual Studio: instale o Visual Studio em seu sistema.
2.  Aspose.Tasks for .NET: Baixe e instale Aspose.Tasks for .NET em[aqui](https://releases.aspose.com/tasks/net/).
3. Compreensão básica da programação C#: A familiaridade com C# será benéfica.

## Importar namespaces
Primeiramente, importe os namespaces necessários para acessar a funcionalidade Aspose.Tasks em seu projeto C#.
```csharp
    using Aspose.Tasks;
    using System;
    
    using Aspose.Tasks.Util;
```
## Etapa 1: carregar o arquivo do projeto
 Comece carregando o arquivo do Microsoft Project usando o`Project` aula.
```csharp
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "OutlineCodes2003.mpp");
```
## Etapa 2: coletar códigos de contorno
Crie um coletor para reunir os códigos de estrutura das tarefas do projeto.
```csharp
var collector = new ChildTasksCollector();
TaskUtils.Apply(project.RootTask, collector, 0);
```
## Etapa 3: iterar por meio de tarefas e códigos de estrutura de tópicos
Itere pelas tarefas coletadas e pelos códigos de estrutura de tópicos, imprimindo seus detalhes.
```csharp
for (var i = 0; i < collector.Tasks.Count; i++)
{
    var current = collector.Tasks[i];
    if (current.Get(Tsk.Id) == 0)
    {
        continue;
    }
    Console.WriteLine("Print outline codes for the " + current.Get(Tsk.Name) + " task.");
    Console.WriteLine("Count of outline codes: " + current.OutlineCodes.Count);
    foreach (var outlineCode in current.OutlineCodes)
    {
        Console.WriteLine("Field Id: " + outlineCode.FieldId);
        Console.WriteLine("Value Id: " + outlineCode.ValueId);
        Console.WriteLine("Value Guid: " + outlineCode.ValueGuid);
        Console.WriteLine();
    }
}
```
## Etapa 4: adicionar definição de código de contorno personalizado
Adicione uma definição de código de estrutura personalizada ao projeto.
```csharp
var outlineCodeDefinition = new OutlineCodeDefinition { FieldId = ((int)ExtendedAttributeTask.OutlineCode3).ToString("D"), Alias = "My Outline Code" };
project.OutlineCodes.Add(outlineCodeDefinition);
```
## Etapa 5: criar e inserir código de estrutura de tópicos
Crie um código de estrutura de tópicos e insira-o em uma tarefa.
```csharp
var value = new OutlineValue { Type = OutlineValueType.Text, Value = "Val1", Description = "Descr1", ValueId = 1 };
outlineCodeDefinition.Values.Add(value);
var codeOne = new OutlineCode { FieldId = outlineCodeDefinition.FieldId, ValueId = 1, ValueGuid = value.ValueGuid.ToString("D").ToUpperInvariant() };
var task = project.RootTask.Children.GetByUid(2);
task.OutlineCodes.Add(codeOne);
```
## Etapa 6: manipular códigos de contorno
Manipule os códigos de estrutura conforme necessário, como inserir, remover ou limpar.
```csharp
// Exemplo de manipulação
// ,
// Insira o código com 2 na posição correta
task.OutlineCodes.Insert(2, code2);
// Verifique se o código foi inserido
Console.WriteLine("Is outline codes contains the inserted value: " + task.OutlineCodes.Contains(code2));
```

## Conclusão
Neste tutorial, aprendemos como coletar códigos de estrutura de tópicos do Microsoft Project usando Aspose.Tasks for .NET. Seguindo essas etapas, você pode gerenciar com eficácia os códigos básicos em seus projetos, melhorando a organização e a clareza.
## Perguntas frequentes
### P: Posso usar Aspose.Tasks for .NET com outras linguagens de programação?
R: Sim, o Aspose.Tasks for .NET tem como alvo principal a plataforma .NET, mas também fornece suporte para outras linguagens de programação por meio do Aspose.Tasks for Cloud.
### P: Há alguma limitação no tamanho dos arquivos do projeto que o Aspose.Tasks for .NET pode suportar?
R: Aspose.Tasks for .NET pode lidar com arquivos grandes do projeto com eficiência, mas o desempenho pode variar dependendo da complexidade e do tamanho do arquivo.
### P: O Aspose.Tasks for .NET é compatível com as versões mais recentes do Microsoft Project?
R: Sim, Aspose.Tasks for .NET oferece suporte a várias versões do Microsoft Project, incluindo as mais recentes.
### P: Posso personalizar o formato de saída ao trabalhar com Aspose.Tasks for .NET?
R: Com certeza, Aspose.Tasks for .NET oferece amplas opções para personalizar o formato de saída de acordo com suas necessidades.
### P: Onde posso encontrar suporte ou recursos adicionais para Aspose.Tasks for .NET?
 R: Você pode visitar o[Fórum Aspose.Tasks](https://forum.aspose.com/c/tasks/15) para qualquer assistência ou dúvida sobre Aspose.Tasks for .NET.