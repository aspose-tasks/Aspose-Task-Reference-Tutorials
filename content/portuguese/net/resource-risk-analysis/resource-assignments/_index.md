---
title: Lidando com atribuições de recursos do MS Project em Aspose.Tasks
linktitle: Tratamento de atribuições de recursos em Aspose.Tasks
second_title: API Aspose.Tasks .NET
description: Aprenda como lidar com atribuições de recursos do MS Project com eficiência usando Aspose.Tasks for .NET. Este abrangente fornece orientação passo a passo para desenvolvedores.
type: docs
weight: 11
url: /pt/net/resource-risk-analysis/resource-assignments/
---
## Introdução
Neste tutorial, nos aprofundaremos em como lidar com atribuições de recursos do Microsoft Project de forma eficiente usando Aspose.Tasks for .NET. Aspose.Tasks é uma API poderosa que permite aos desenvolvedores manipular arquivos do Microsoft Project programaticamente. Seguindo essas etapas, você aprenderá como gerenciar atribuições de recursos de maneira eficaz em seus aplicativos .NET.
## Pré-requisitos
Antes de começarmos, certifique-se de ter os seguintes pré-requisitos:

## Importar namespaces
Primeiramente, você precisa importar os namespaces necessários para utilizar as funcionalidades do Aspose.Tasks em seu projeto .NET. Isso inclui:

```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;

using Aspose.Tasks.Saving;
using Aspose.Tasks.Util;
```
Agora vamos dividir o exemplo fornecido em várias etapas para uma compreensão abrangente de como lidar com atribuições de recursos do MS Project usando Aspose.Tasks.
## Etapa 1: definir as configurações do projeto e do calendário
Para começar, crie uma nova instância do Project e defina as configurações de calendário do projeto:
```csharp
var project = new Project();
var calendar = project.Get(Prj.Calendar);
project.Set(Prj.StartDate, new DateTime(2000, 3, 15, 8, 0, 0));
project.Set(Prj.FinishDate, new DateTime(2000, 4, 21, 17, 0, 0));
```
## Etapa 2: adicionar uma tarefa ao projeto
A seguir, adicione uma nova tarefa à tarefa raiz do projeto:
```csharp
var task = project.RootTask.Children.Add("Task1");
task.Set(Tsk.Duration, project.GetDuration(3));
```
## Etapa 3: Criar Atribuição de Recursos e Gerar Dados Faseados no Tempo
Agora, crie uma nova atribuição de recurso para a tarefa e gere dados divididos em fases:
```csharp
var assignment = project.ResourceAssignments.Add(task, null);
assignment.TimephasedDataFromTaskDuration(calendar);
```
## Etapa 4: divida a tarefa
Divida a tarefa em várias partes, fornecendo datas de início e término:
```csharp
assignment.SplitTask(new DateTime(2000, 3, 16, 8, 0, 0), new DateTime(2000, 3, 16, 17, 0, 0), calendar);
assignment.SplitTask(new DateTime(2000, 3, 18, 8, 0, 0), new DateTime(2000, 3, 18, 17, 0, 0), calendar);
```
## Etapa 5: definir o contorno do trabalho
Defina o tipo de contorno de trabalho para a tarefa:
```csharp
assignment.Set(Asn.WorkContour, WorkContourType.Contoured);
```
## Etapa 6: salve o projeto
Por fim, salve o arquivo do projeto com as alterações feitas:
```csharp
project.Save(DataDir + "CreateSplitTasks_out.xml", SaveFileFormat.Xml);
```
## Conclusão
Concluindo, lidar com atribuições de recursos do Microsoft Project usando Aspose.Tasks for .NET é um processo simples. Seguindo as etapas descritas neste tutorial, você pode gerenciar com eficiência atribuições de recursos em seus aplicativos .NET.
## Perguntas frequentes
### O Aspose.Tasks pode lidar com estruturas de projetos complexas?
Sim, Aspose.Tasks fornece funcionalidades abrangentes para lidar com estruturas de projetos complexos com eficiência.
### O Aspose.Tasks é compatível com diferentes versões do Microsoft Project?
Sim, Aspose.Tasks oferece suporte a várias versões do Microsoft Project, garantindo compatibilidade em diferentes ambientes.
### Posso personalizar atribuições de recursos com base em requisitos específicos?
Com certeza, Aspose.Tasks oferece amplas opções de personalização para atribuições de recursos para atender às necessidades específicas do projeto.
### O Aspose.Tasks oferece suporte à exportação de dados do projeto para outros formatos?
Sim, Aspose.Tasks permite exportar dados do projeto para diversos formatos como XML, PDF e HTML, entre outros.
### O suporte técnico está disponível para usuários do Aspose.Tasks?
Sim, a Aspose fornece suporte técnico dedicado por meio de seu fórum e outros canais para auxiliar os usuários com quaisquer dúvidas ou problemas.