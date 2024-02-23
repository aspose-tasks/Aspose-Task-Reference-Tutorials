---
title: Lidando com linhas de progresso do MS Project com Aspose.Tasks
linktitle: Tratamento de linhas de progresso em Aspose.Tasks
second_title: API Aspose.Tasks .NET
description: Aprenda como manipular linhas de progresso em arquivos do MS Project usando Aspose.Tasks for .NET, aprimorando a visualização e o gerenciamento do projeto.
type: docs
weight: 15
url: /pt/net/project-management-integration/progress-lines/
---
## Introdução
Microsoft Project (MS Project) é uma ferramenta poderosa para gerenciamento de projetos, permitindo aos usuários acompanhar vários aspectos de seus projetos. Uma característica crucial do MS Project é a capacidade de visualizar linhas de progresso, o que ajuda as partes interessadas a compreender o status e a trajetória do projeto. Neste tutorial, exploraremos como lidar com linhas de progresso no MS Project usando a biblioteca Aspose.Tasks para .NET.
## Pré-requisitos
Antes de começarmos, certifique-se de ter o seguinte:
1. Visual Studio: instale o Visual Studio ou qualquer outro ambiente de desenvolvimento .NET preferido.
2.  Aspose.Tasks for .NET: Baixe e instale Aspose.Tasks for .NET em[aqui](https://releases.aspose.com/tasks/net/).
3. Conhecimento básico de C#: Familiaridade com a linguagem de programação C# será benéfica.

## Importando Namespaces
Para começar, vamos importar os namespaces necessários:
```csharp
using Aspose.Tasks;
using System;
using System.Drawing;

using Aspose.Tasks.Saving;
using Aspose.Tasks.Visualization;
```
Agora, vamos detalhar cada etapa do tratamento das linhas de progresso:
## Etapa 1: carregar o arquivo do projeto
```csharp
// O caminho para o diretório de documentos.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "Project2.mpp");
project.Set(Prj.StatusDate, project.Get(Prj.StartDate));
```
 Aqui, carregamos o arquivo MS Project`Project2.mpp` e defina sua data de status.
## Etapa 2: definir a visualização do gráfico de Gantt
```csharp
var view = (GanttChartView)project.Views.ToList()[0];
```
Convertemos a visualização do projeto em um gráfico de Gantt para manipulação posterior.
## Etapa 3: Definir Linhas de Progresso
```csharp
view.ProgressLines = new ProgressLines();
var progressLines = view.ProgressLines;
```
Inicializamos as linhas de progresso para a visualização do gráfico de Gantt.
## Etapa 4: definir as configurações da linha de progresso
```csharp
progressLines.BeginAtDate = project.Get(Prj.StatusDate);
progressLines.BeginAtProjectStart = true;
progressLines.DateFormat = DateLabel.DayDddd;
progressLines.DisplayAtCurrentDate = true;
progressLines.DisplayAtRecurringIntervals = true;
progressLines.DisplaySelected = true;
progressLines.IsBaselinePlan = false;
progressLines.Font = new FontDescriptor("Arial", 10);
progressLines.LineColor = Color.Aquamarine;
progressLines.LinePattern = LinePattern.Dashed;
progressLines.OtherLineColor = Color.Azure;
progressLines.OtherLinePattern = LinePattern.Dotted;
progressLines.OtherProgressPointColor = Color.Red;
progressLines.OtherProgressPointShape = GanttBarEndShape.Circle;
progressLines.ProgressPointColor = Color.Orange;
progressLines.ProgressPointShape = GanttBarEndShape.Diamond;
progressLines.RecurringInterval = new RecurringInterval();
progressLines.RecurringInterval.Interval = Interval.Daily;
progressLines.RecurringInterval.DailyDayNumber = 1;
progressLines.ShowDate = true;
```
Aqui, definimos várias propriedades para as linhas de progresso, como cor da linha, padrão, fonte, etc.
## Etapa 5: verifique a configuração das linhas de progresso
```csharp
// Configurações de linhas de progresso de saída
Console.WriteLine("Begin At Date: " + progressLines.BeginAtDate);
Console.WriteLine("Begin At Project Start: " + progressLines.BeginAtProjectStart);
// Saída de outras configurações...
```
Geramos as configurações das linhas de progresso definidas para verificação.
## Etapa 6: salve o arquivo do projeto
```csharp
project.Save(DataDir + "WorkWithProgressLines_out.mpp", SaveFileFormat.Mpp);
```
Finalmente, salvamos o arquivo do projeto modificado com linhas de progresso.

## Conclusão
Neste tutorial, aprendemos como lidar com linhas de progresso do MS Project usando Aspose.Tasks for .NET. Seguindo essas etapas, você pode personalizar e visualizar com eficácia as linhas de progresso em seus arquivos do MS Project de forma programática.
## Perguntas frequentes
### P: Posso personalizar ainda mais a aparência das linhas de progresso?
R: Sim, você pode ajustar várias propriedades, como cor da linha, padrão e fonte, para atender às suas necessidades.
### P: O Aspose.Tasks oferece suporte a outros recursos de gerenciamento de projetos?
R: Sim, Aspose.Tasks fornece amplo suporte para manipulação de vários aspectos dos arquivos do MS Project, incluindo tarefas, recursos e calendários.
### P: Posso integrar Aspose.Tasks com outras bibliotecas .NET?
R: Com certeza, o Aspose.Tasks foi projetado para se integrar perfeitamente com outras bibliotecas .NET, permitindo que você aprimore ainda mais seus aplicativos de gerenciamento de projetos.
### P: Existe um fórum da comunidade para suporte do Aspose.Tasks?
 R: Sim, você pode encontrar recursos úteis e buscar assistência no fórum Aspose.Tasks.[aqui](https://forum.aspose.com/c/tasks/15).
### P: O Aspose.Tasks oferece licenças temporárias para fins de avaliação?
 R: Sim, você pode obter uma licença temporária para avaliação em[aqui](https://purchase.aspose.com/temporary-license/).