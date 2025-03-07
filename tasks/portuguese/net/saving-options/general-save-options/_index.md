---
title: Dominando as opções de salvamento do MS Project para Aspose.Tasks
linktitle: Opções gerais de salvamento para Aspose.Tasks
second_title: API Aspose.Tasks .NET
description: Aprenda a salvar arquivos do MS Project com eficiência usando Aspose.Tasks for .NET. Personalize facilmente as opções de saída para seus projetos.
weight: 17
url: /pt/net/saving-options/general-save-options/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Dominando as opções de salvamento do MS Project para Aspose.Tasks

## Introdução
Aspose.Tasks for .NET oferece recursos poderosos para manipular arquivos do Microsoft Project programaticamente. Neste tutorial, nos aprofundaremos nas complexidades de salvar arquivos do MS Project usando várias opções fornecidas pelo Aspose.Tasks. Especificamente, vamos nos concentrar nas opções gerais de salvamento disponíveis para Aspose.Tasks, permitindo que você adapte a saída aos seus requisitos específicos.
## Pré-requisitos
Antes de começarmos, certifique-se de ter os seguintes pré-requisitos:
1.  Instalação do Aspose.Tasks for .NET: Baixe e instale o Aspose.Tasks for .NET do[Link para Download](https://releases.aspose.com/tasks/net/).
2. Compreensão básica do .NET Framework: A familiaridade com os conceitos de programação .NET é benéfica.

## Importando Namespaces
Antes de mergulhar no código, importe os namespaces necessários:
```csharp
    using Aspose.Tasks;
    using System;
    using System.Collections.Generic;
    using System.Diagnostics.CodeAnalysis;
    using System.Drawing;
    using System.Linq;
    
    using Aspose.Tasks.Saving;
    using Aspose.Tasks.Util;
    using Aspose.Tasks.Visualization;
```

## Etapa 1: carregar o arquivo do projeto
Primeiramente, você precisa carregar o arquivo MS Project usando Aspose.Tasks:
```csharp
var project = new Project("Your Document Directory/CreateProject2.mpp");
```
## Etapa 2: definir opções para salvar
 Defina as opções de salvamento de acordo com suas necessidades. Neste exemplo, estamos usando`Spreadsheet2003SaveOptions`:
```csharp
var options = new Spreadsheet2003SaveOptions();
```
## Etapa 3: personalizar colunas de visualização
Você pode personalizar colunas de visualização, como gráfico de Gantt, visualização de recursos e visualização de atribuição. Veja como adicionar colunas a cada uma:
```csharp
var ganttChartColumn = new GanttChartColumn("WBS", 100, delegate(Task task) { return task.Get(Tsk.WBS); });
options.View.Columns.Add(ganttChartColumn);
var resourceViewColumn = new ResourceViewColumn("Cost center", 100, delegate(Resource resource) { return resource.Get(Rsc.CostCenter); });
options.ResourceView.Columns.Add(resourceViewColumn);
var assignmentViewColumn = new AssignmentViewColumn("Notes", 200, delegate(ResourceAssignment assignment) { return assignment.Get(Asn.NotesText); });
options.AssignmentView.Columns.Add(assignmentViewColumn);
```
## Passo 4: Salve o Projeto com Opções
Finalmente, salve o projeto com as opções especificadas:
```csharp
project.Save("Your Document Directory/UsingSpreadsheet2003SaveOptions_out.xml", options);
```

## Conclusão
Dominar as opções gerais de salvamento do MS Project com Aspose.Tasks for .NET permite que você personalize com eficiência o formato de saída de acordo com as necessidades do seu projeto.
## Perguntas frequentes
### P: O Aspose.Tasks é compatível com diferentes versões de arquivos do MS Project?
R: Sim, Aspose.Tasks oferece suporte a várias versões de arquivos do MS Project, garantindo compatibilidade em diferentes ambientes.
### P: Posso experimentar o Aspose.Tasks antes de comprar?
 R: Sim, você pode explorar o Aspose.Tasks com uma avaliação gratuita disponível[aqui](https://releases.aspose.com/).
### P: Onde posso encontrar documentação para Aspose.Tasks?
 R: Documentação detalhada pode ser encontrada[aqui](https://reference.aspose.com/tasks/net/), fornecendo orientação abrangente sobre o uso dos recursos do Aspose.Tasks.
### P: Como posso obter licenças temporárias para Aspose.Tasks?
 R: Licenças temporárias estão disponíveis para fins de avaliação[aqui](https://purchase.aspose.com/temporary-license/).
### P: Onde posso buscar suporte para consultas relacionadas ao Aspose.Tasks?
 R: Você pode participar do fórum da comunidade Aspose.Tasks[aqui](https://forum.aspose.com/c/tasks/15)para obter assistência de especialistas e colegas desenvolvedores.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
