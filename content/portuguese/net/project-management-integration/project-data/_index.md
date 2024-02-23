---
title: Dominando os dados do projeto com Aspose.Tasks
linktitle: Trabalhando com dados do projeto em Aspose.Tasks
second_title: API Aspose.Tasks .NET
description: Aprenda como manipular dados do Microsoft Project usando Aspose.Tasks em .NET. Crie tarefas, adicione recursos e salve projetos com facilidade.
type: docs
weight: 16
url: /pt/net/project-management-integration/project-data/
---
## Introdução
Neste tutorial, exploraremos como trabalhar com dados do Microsoft Project usando a biblioteca Aspose.Tasks para .NET. Aspose.Tasks fornece recursos poderosos para manipular arquivos de projeto, incluindo criação de tarefas, adição de recursos, configuração de propriedades e salvamento de projetos em vários formatos.
## Pré-requisitos
Antes de começar, certifique-se de ter o seguinte:
1.  Instalação da biblioteca Aspose.Tasks: Baixe e instale a biblioteca Aspose.Tasks em[aqui](https://releases.aspose.com/tasks/net/).
2. Ambiente de desenvolvimento: certifique-se de ter um ambiente de desenvolvimento .NET configurado.
3. Conhecimento básico de C#: Familiaridade com a linguagem de programação C# será benéfica.

## Importar namespaces
Antes de trabalhar com Aspose.Tasks, importe os namespaces necessários para o seu projeto:
```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;
using System.Data.SqlClient;
using System.Diagnostics;
using System.Diagnostics.CodeAnalysis;
using System.Drawing.Printing;
using System.IO;
using System.Text;
using System.Text.RegularExpressions;
using Aspose.Tasks.Connectivity;

using Aspose.Tasks.Saving;
using Aspose.Tasks.Visualization;
```

## Etapa 1: inicializar o objeto do projeto
```csharp
// O caminho para o diretório de documentos.
String DataDir = "Your Document Directory";
var project = new Project();
```
 Esta linha inicializa uma nova instância do`Project` class, que representa um arquivo do Microsoft Project.
## Passo 2: Definir Propriedades do Projeto
```csharp
project.Set(Prj.WorkFormat, TimeUnitType.Hour);
project.Set(Prj.NewTasksAreManual, false);
```
Estas linhas demonstram como definir propriedades do projeto, como formato de trabalho e modo de criação de tarefas.
## Etapa 3: adicionar tarefas
```csharp
var task1 = project.RootTask.Children.Add("Task 1");
```
Aqui, uma nova tarefa chamada “Tarefa 1” é adicionada à tarefa raiz do projeto.
## Etapa 4: definir propriedades da tarefa
```csharp
task1.Set(Tsk.Start, new DateTime(2020, 2, 5, 8, 0, 0));
task1.Set(Tsk.Duration, project.GetDuration(8, TimeUnitType.Hour));
task1.Set(Tsk.Finish, new DateTime(2020, 2, 5, 17, 0, 0));
```
Estas linhas definem a data de início, duração e data de término da "Tarefa 1".
## Passo 5: Adicionando Recursos
```csharp
var workResource = project.Resources.Add("Work Resource");
workResource.Set(Rsc.Type, ResourceType.Work);
```
Esta parte demonstra como adicionar um recurso de trabalho ao projeto.
## Passo 6: Atribuindo Recursos às Tarefas
```csharp
var workResourceAssignment = project.ResourceAssignments.Add(task1, workResource);
workResourceAssignment.Set(Asn.Start, new DateTime(2020, 2, 5, 8, 0, 0));
workResourceAssignment.Set(Asn.Work, project.GetWork(8));
workResourceAssignment.Set(Asn.Finish, new DateTime(2020, 2, 5, 17, 0, 0));
```
Estas linhas mostram como atribuir o recurso de trabalho adicionado anteriormente à "Tarefa 1" com datas específicas de início, trabalho e término.
## Passo 7: Salvando Projeto
```csharp
project.Save(DataDir + "ProjectCreation_out.xml", SaveFileFormat.Xml);
```
Finalmente, o projeto é salvo no formato de arquivo XML do Microsoft Project.

## Conclusão
Neste tutorial, aprendemos como trabalhar com dados do Microsoft Project usando a biblioteca Aspose.Tasks no .NET. Seguindo o guia passo a passo, você pode manipular arquivos de projeto, adicionar tarefas, recursos, atribuir recursos a tarefas e salvar projetos em vários formatos.
## Perguntas frequentes
### P: O Aspose.Tasks pode lidar com estruturas de projetos complexas?
R: Sim, Aspose.Tasks fornece suporte abrangente para estruturas de projetos complexos, permitindo gerenciar tarefas, recursos e atribuições com eficiência.
### P: O Aspose.Tasks é compatível com diferentes versões do Microsoft Project?
R: Aspose.Tasks oferece suporte a uma ampla variedade de versões do Microsoft Project, garantindo compatibilidade em diferentes ambientes.
### P: Posso integrar Aspose.Tasks com outras bibliotecas .NET?
R: Com certeza, o Aspose.Tasks integra-se perfeitamente com outras bibliotecas .NET, proporcionando flexibilidade em seus projetos de desenvolvimento.
### P: O Aspose.Tasks oferece suporte para algoritmos de agendamento de projetos?
R: Sim, Aspose.Tasks inclui algoritmos de agendamento avançados para ajudá-lo a otimizar os cronogramas do projeto e a utilização de recursos.
### P: Existe um fórum da comunidade para usuários do Aspose.Tasks?
 R: Sim, você pode encontrar recursos úteis e interagir com outros usuários do Aspose.Tasks no site.[Fórum Aspose.Tasks](https://forum.aspose.com/c/tasks/15).