---
title: Manipulação de critérios de grupo do MS Project em Aspose.Tasks
linktitle: Critérios de grupo em Aspose.Tasks
second_title: API Aspose.Tasks .NET
description: Explore como manipular arquivos do MS Project programaticamente em .NET usando Aspose.Tasks. Recupere exemplos passo a passo de informações sobre grupos de tarefas e critérios.
type: docs
weight: 27
url: /pt/net/tasks-project-management/group-criteria/
---
## Introdução
Aspose.Tasks for .NET é uma API poderosa que facilita o trabalho com arquivos do Microsoft Project em seus aplicativos .NET. Esteja você desenvolvendo software de gerenciamento de projetos ou precise manipular os dados do projeto de forma programática, o Aspose.Tasks oferece um conjunto abrangente de recursos para atender às suas necessidades.
## Pré-requisitos
Antes de mergulhar no tutorial, certifique-se de ter os seguintes pré-requisitos:
### 1. Conhecimento de C# e .NET Framework
A familiaridade com a linguagem de programação C# e o .NET Framework é essencial para compreender e implementar os exemplos fornecidos neste tutorial.
### 2. Instalação do Aspose.Tasks para .NET
 Certifique-se de ter o Aspose.Tasks for .NET instalado em seu ambiente de desenvolvimento. Você pode baixar a biblioteca em[aqui](https://releases.aspose.com/tasks/net/) e siga as instruções de instalação fornecidas.
### 3. Ambiente de Desenvolvimento Integrado (IDE)
Tenha um IDE como o Visual Studio instalado em seu sistema para escrever e executar código C#.

## Importar namespaces
Para começar, importe os namespaces necessários em seu código C#:
```csharp
    using Aspose.Tasks;
    using System;
    using System.Collections.Generic;
    
```
## Etapa 1: carregar um arquivo do Microsoft Project
Primeiro, especifique o caminho para o arquivo do Microsoft Project:
```csharp
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "ReadGroupDefinitionData.mpp");
```
 substituir`"Your Document Directory"` com o caminho para o arquivo do seu projeto.
## Etapa 2: recuperar informações dos grupos de tarefas
A seguir, recupere informações sobre grupos de tarefas no projeto:
```csharp
Console.WriteLine("Task Groups Count: " + project.TaskGroups.Count);
var group = project.TaskGroups.ToList()[1];
Console.WriteLine("Task Group Name: " + group.Name);
Console.WriteLine("Task Group Criteria count: " + group.GroupCriteria.Count);
```
Este trecho de código imprime a contagem total de grupos de tarefas, recupera o segundo grupo de tarefas, seu nome e a contagem de critérios que ele contém.
## Etapa 3: recuperar informações de critério do grupo de tarefas
Agora, vamos nos aprofundar nos detalhes de um critério específico dentro do grupo de tarefas:
```csharp
var criterion = group.GroupCriteria.ToList()[0];
Console.WriteLine("Task Criterion Index: " + criterion.Index);
Console.WriteLine("Task Criterion Field: " + criterion.Field);
Console.WriteLine("Task Criterion GroupOn: " + criterion.GroupOn);
Console.WriteLine("Task Criterion Cell Color: " + criterion.CellColor);
Console.WriteLine("Task Criterion Font Color: " + criterion.FontColor);
Console.WriteLine("Task Criterion Group Interval: " + criterion.GroupInterval);
Console.WriteLine("Task Criterion Start At: " + criterion.StartAt);
```
Este segmento exibe várias propriedades do critério, como índice, campo, informações de agrupamento, cor da célula, cor da fonte, intervalo de grupo e ponto inicial.
## Etapa 4: recuperar informações da fonte do critério
Por último, obtenha detalhes do critério relacionados à fonte:
```csharp
Console.WriteLine("Font Name: " + criterion.Font.FontFamily);
Console.WriteLine("Font Size: " + criterion.Font.Size);
Console.WriteLine("Font Style: " + criterion.Font.Style);
Console.WriteLine("Ascending/Descending: " + criterion.Ascending);
```
Esta etapa imprime o nome da fonte, tamanho, estilo e se o critério está classificado em ordem crescente ou decrescente.

## Conclusão
Neste tutorial, exploramos como usar Aspose.Tasks for .NET para recuperar informações sobre grupos de tarefas e critérios de um arquivo do Microsoft Project. Seguindo o guia passo a passo, você pode trabalhar de forma eficiente com dados do projeto de forma programática em seus aplicativos .NET.
## Perguntas frequentes
### Aspose.Tasks pode lidar com arquivos grandes do Microsoft Project?
Aspose.Tasks é otimizado para lidar com arquivos grandes de projetos com eficiência, garantindo alto desempenho e confiabilidade.
### O Aspose.Tasks é compatível com todas as versões do Microsoft Project?
Sim, Aspose.Tasks oferece suporte a várias versões do Microsoft Project, garantindo compatibilidade entre diferentes formatos de arquivo.
### Posso manipular dados do projeto usando Aspose.Tasks?
Com certeza, Aspose.Tasks oferece amplas funcionalidades para manipular dados do projeto, incluindo tarefas, recursos, calendários e muito mais.
### O Aspose.Tasks oferece suporte para diferentes plataformas .NET?
Sim, Aspose.Tasks oferece suporte a várias plataformas .NET, incluindo .NET Framework, .NET Core e .NET Standard.
### Existe um fórum da comunidade para Aspose.Tasks onde posso procurar assistência?
 Sim, você pode visitar o[Fórum Aspose.Tasks](https://forum.aspose.com/c/tasks/15) para fazer perguntas, compartilhar conhecimento e colaborar com outros usuários.