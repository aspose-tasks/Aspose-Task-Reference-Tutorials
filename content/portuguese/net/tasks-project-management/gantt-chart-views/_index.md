---
title: Dominando as visualizações do gráfico de Gantt em Aspose.Tasks
linktitle: Visualizações do gráfico de Gantt em Aspose.Tasks
second_title: API Aspose.Tasks .NET
description: Aprenda como personalizar visualizações de gráfico de Gantt em arquivos do Microsoft Project usando Aspose.Tasks for .NET. Guia passo a passo para gerenciamento eficiente de projetos.
type: docs
weight: 22
url: /pt/net/tasks-project-management/gantt-chart-views/
---
## Introdução
Os gráficos de Gantt são ferramentas poderosas usadas no gerenciamento de projetos para visualizar tarefas, cronogramas e dependências. Aspose.Tasks for .NET fornece recursos robustos para trabalhar com visualizações de gráfico de Gantt em arquivos do Microsoft Project. Neste tutorial, exploraremos como utilizar Aspose.Tasks para manipular visualizações de gráficos de Gantt, personalizar sua aparência e salvá-los como arquivos PDF.
## Pré-requisitos
Antes de prosseguir, certifique-se de ter os seguintes pré-requisitos em vigor:
### 1. Instalação do Aspose.Tasks para .NET
 Certifique-se de ter instalado o Aspose.Tasks para .NET. Você pode baixar a biblioteca em[aqui](https://releases.aspose.com/tasks/net/) siga as instruções de instalação fornecidas na documentação[aqui](https://reference.aspose.com/tasks/net/).
### 2. Arquivo do Microsoft Project
Prepare um arquivo do Microsoft Project (`Project2.mpp`) que você usará para trabalhar com visualizações de gráfico de Gantt.
### 3. Conhecimento básico de C# e .NET Framework
Este tutorial pressupõe que você tenha um conhecimento básico da linguagem de programação C# e do .NET framework.
## Importar namespaces
Antes de começar a trabalhar com visualizações de gráfico de Gantt em Aspose.Tasks, você precisa importar os namespaces necessários para seu código C#. Veja como você pode fazer isso:

```csharp
using Aspose.Tasks;
using System;
using System.Diagnostics.CodeAnalysis;
using System.Drawing;
using System.Linq;

using Aspose.Tasks.Saving;
using Aspose.Tasks.Visualization;
using Aspose.Tasks;
using System.Drawing;
```

Vamos dividir o código de exemplo fornecido em várias etapas e explicar cada etapa detalhadamente:
## Etapa 1: carregar o arquivo do projeto
```csharp
var project = new Project(DataDir + "Project2.mpp");
```
Esta etapa envolve carregar o arquivo do Microsoft Project (`Project2.mpp` ) em uma instância do`Project` aula.
## Etapa 2: definir data de status
```csharp
project.Set(Prj.StatusDate, project.Get(Prj.StartDate));
```
Aqui, definimos a data de status do projeto como a data de início.
## Etapa 3: acessar a visualização do gráfico de Gantt
```csharp
var view = (GanttChartView)project.Views.ToList()[0];
```
Acessamos a visualização do gráfico de Gantt do projeto. Aspose.Tasks permite acessar visualizações como gráfico de Gantt, diagrama de rede e uso de tarefas.
## Etapa 4: personalizar a visualização do gráfico de Gantt
Agora, vamos personalizar vários aspectos da visualização do gráfico de Gantt:
### Definir arredondamento da barra
```csharp
view.BarRounding = false;
```
Isto define se as barras no gráfico de Gantt serão arredondadas para o dia mais próximo.
### Definir tamanho da barra
```csharp
view.BarSize = GanttBarSize.BarSize24;
```
Isso determina a altura das barras de Gantt no gráfico.
### Ocultar barras cumulativas
```csharp
view.HideRollupBarsWhenSummaryExpanded = true;
```
Especifica se as barras de rollup serão ocultadas ao expandir tarefas de resumo.
### Definir cor do horário de folga
```csharp
view.NonWorkingTimeColor = Color.Azure;
```
Define a cor do horário de folga no gráfico de Gantt.
### Arregaçar barras de Gantt
```csharp
view.RollUpGanttBars = true;
```
Especifique se as barras do gráfico de Gantt devem ser acumuladas.
### Mostrar divisões de barra
```csharp
view.ShowBarSplits = true;
```
Determina se as divisões de tarefas no gráfico de Gantt devem ser mostradas.
### mostrar desenhos
```csharp
view.ShowDrawings = true;
```
Especifica se os desenhos no gráfico de Gantt devem ser mostrados.
### Porcentagem do tamanho da escala de tempo
```csharp
view.TimescaleSizePercentage = 10;
```
Define uma porcentagem para ajustar o espaçamento entre unidades na camada de escala de tempo.
## Etapa 5: Salvar visualização do gráfico de Gantt como PDF
```csharp
project.Save(DataDir + "WorkWithGanttChartViews_out.pdf", SaveFileFormat.Pdf);
```
Por fim, salvamos a visualização do gráfico de Gantt personalizado como um arquivo PDF.
## Conclusão
Neste tutorial, aprendemos como trabalhar com visualizações de gráfico de Gantt em Aspose.Tasks for .NET. Seguindo as etapas fornecidas, você pode manipular e personalizar com eficiência os gráficos de Gantt de acordo com os requisitos do seu projeto.
## Perguntas frequentes
### P: Posso personalizar ainda mais a aparência das barras do gráfico de Gantt?
R: Sim, Aspose.Tasks oferece amplas opções para personalizar a aparência das barras do gráfico de Gantt, incluindo cores, formas e tamanhos.
### P: O Aspose.Tasks é compatível com diferentes versões de arquivos do Microsoft Project?
R: Sim, Aspose.Tasks oferece suporte a várias versões de arquivos do Microsoft Project, incluindo formatos MPP, MPT e XML.
### P: Posso exportar visualizações de gráficos de Gantt para formatos diferentes de PDF?
R: Com certeza, Aspose.Tasks suporta a exportação de visualizações de gráficos de Gantt para vários formatos, incluindo PNG, JPEG e XPS.
### P: O Aspose.Tasks oferece suporte para algoritmos complexos de agendamento de projetos?
R: Sim, Aspose.Tasks fornece algoritmos de agendamento avançados para lidar com cronogramas de projetos complexos de maneira eficaz.
### P: Existe um fórum da comunidade onde posso procurar ajuda ou compartilhar minhas experiências com o Aspose.Tasks?
 R: Sim, você pode visitar o[Fórum Aspose.Tasks](https://forum.aspose.com/c/tasks/15) para interagir com outros usuários, fazer perguntas e encontrar soluções para suas dúvidas.