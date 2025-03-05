---
title: Personalize colunas do gráfico de Gantt com Aspose.Tasks
linktitle: Colunas do gráfico de Gantt em Aspose.Tasks
second_title: API Aspose.Tasks .NET
description: Aprenda como personalizar colunas do gráfico de Gantt no Aspose.Tasks for .NET para exibir informações de tarefas específicas com eficiência.
type: docs
weight: 21
url: /pt/net/tasks-project-management/gantt-chart-columns/
---
## Introdução
Os gráficos de Gantt são uma ferramenta fundamental no gerenciamento de projetos, fornecendo uma representação visual de tarefas, cronogramas e recursos. Aspose.Tasks for .NET oferece recursos poderosos para manipular gráficos de Gantt, incluindo a personalização de colunas para exibir informações de tarefas específicas. Neste tutorial, exploraremos como trabalhar com colunas do gráfico de Gantt usando Aspose.Tasks for .NET.
## Pré-requisitos
Antes de começarmos, certifique-se de ter o seguinte:
1.  Instalação: Aspose.Tasks for .NET instalado em seu sistema. Caso contrário, baixe e instale-o em[aqui](https://releases.aspose.com/tasks/net/).
2. Ambiente de desenvolvimento .NET: conhecimento prático de C# e da estrutura .NET.
3. Arquivo de projeto de amostra: tenha um arquivo de exemplo do Microsoft Project (`.mpp`) útil para experimentar. Se não tiver um, você pode criar um projeto simples no MS Project e salvá-lo.

## Importar namespaces
Primeiro, você precisa importar os namespaces necessários para trabalhar com Aspose.Tasks for .NET:
```csharp
    using Aspose.Tasks;
    using System;
    using System.Collections.Generic;
    using System.Globalization;
    
    using Aspose.Tasks.Saving;
    using Aspose.Tasks.Visualization;
```
## Etapa 1: carregar o arquivo do projeto
 Carregue o arquivo do projeto usando o`Project` classe fornecida por Aspose.Tasks:
```csharp
// O caminho para o diretório de documentos.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "Project2.mpp");
var task = project.RootTask.Children.GetById(1);
```
## Etapa 2: definir colunas do gráfico de Gantt
Defina as colunas que deseja exibir no gráfico de Gantt. Você pode especificar campos integrados ou criar campos personalizados:
```csharp
var columns = new List<ViewColumn>
{
    new GanttChartColumn(20, Field.TaskUniqueID),
    new GanttChartColumn("Name", 150, Field.TaskName),
    new GanttChartColumn("Start", 100, Field.TaskStart),
    new GanttChartColumn("End", 100, Field.TaskFinish),
    new GanttChartColumn("R-Initials", 100, Field.TaskResourceInitials),
    new GanttChartColumn("R-Names", 100, Field.TaskResourceNames),
    new GanttChartColumn("Work", 50, Field.TaskWork),
    new GanttChartColumn(
        "Cost", 
        80,
        delegate(Task t)
        {
            return t.Get(Tsk.Cost).ToString(CultureInfo.InvariantCulture);
        }),
    new GanttChartColumn(
        "Actual Cost", 
        80,
        delegate(Task t)
        {
            return t.Get(Tsk.ActualCost).ToString(CultureInfo.InvariantCulture);
        },
        Field.TaskActualCost)
};
```
## Etapa 3: iterar nas colunas
Itere sobre as colunas definidas para acessar suas propriedades e exibir informações:
```csharp
foreach (var column in columns)
{
    var col = (GanttChartColumn)column;
    Console.WriteLine("Column Name: " + col.Name);
    Console.WriteLine("Column Field: " + col.Field);
    Console.WriteLine("Column Text: " + col.GetColumnText(task));
    Console.WriteLine();
}
```
## Etapa 4: salvar o gráfico de Gantt em CSV
Salve o gráfico de Gantt com colunas definidas em um arquivo CSV:
```csharp
var options = new CsvOptions
{
    View = new ProjectView(columns)
};
project.Save(DataDir + "WorkWithGanttChartColumn_out.csv", options);
```
Seguindo essas etapas, você pode trabalhar efetivamente com colunas do gráfico de Gantt no Aspose.Tasks for .NET, permitindo personalizar e exibir informações de tarefas conforme necessário.

## Conclusão
Dominar a manipulação das colunas do gráfico de Gantt no Aspose.Tasks for .NET abre possibilidades infinitas para adaptar os recursos visuais de gerenciamento de projetos às suas necessidades específicas. Seguindo as etapas descritas neste tutorial, você pode lidar com informações de tarefas com eficiência e melhorar a clareza e a organização do projeto.
## Perguntas frequentes
### P: Posso criar colunas personalizadas no Aspose.Tasks for .NET?
R: Sim, você pode definir colunas personalizadas para exibir atributos de tarefas específicos de acordo com os requisitos do seu projeto.
### P: O Aspose.Tasks for .NET é compatível com todas as versões de arquivos do Microsoft Project?
R: Aspose.Tasks for .NET oferece suporte a várias versões de arquivos do Microsoft Project, garantindo compatibilidade em diferentes ambientes de projeto.
### P: Como posso lidar com estruturas de projetos complexas com Aspose.Tasks for .NET?
R: Aspose.Tasks for .NET fornece APIs e recursos abrangentes para gerenciar estruturas de projetos complexos, oferecendo flexibilidade e escalabilidade.
### P: Há alguma limitação quanto ao número de colunas que posso adicionar a um gráfico de Gantt?
R: Aspose.Tasks for .NET oferece amplas opções de personalização, permitindo adicionar um número significativo de colunas aos gráficos de Gantt sem limitações.
### P: Onde posso encontrar suporte e recursos adicionais para Aspose.Tasks for .NET?
R: Você pode explorar a documentação, os fóruns da comunidade e os canais de suporte fornecidos pelo Aspose.Tasks for .NET para acessar recursos e assistência abrangentes.