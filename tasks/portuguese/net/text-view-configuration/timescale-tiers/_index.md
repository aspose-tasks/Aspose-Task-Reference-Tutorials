---
title: Configurando níveis de escala de tempo do gráfico de Gantt em Aspose.Tasks
linktitle: Configurando camadas de escala de tempo em Aspose.Tasks
second_title: API Aspose.Tasks .NET
description: Explore Aspose.Tasks for .NET para configurar camadas de escala de tempo em sua visualização Gantt Chart para visualização precisa da linha do tempo do projeto. #Aspose.Tasks #Projeto MS
type: docs
weight: 16
url: /pt/net/text-view-configuration/timescale-tiers/
---
## Introdução
No cenário dinâmico do gerenciamento de projetos, a visualização eficaz é crucial para a compreensão de cronogramas e prazos. Aspose.Tasks for .NET fornece um conjunto de ferramentas poderoso e, neste tutorial, exploraremos como configurar camadas de escala de tempo para representação ideal na visualização do gráfico de Gantt. Siga estas instruções passo a passo para aprimorar a visualização do seu projeto.
## Pré-requisitos
Antes de mergulhar no tutorial, certifique-se de ter o seguinte:
- Conhecimento básico de C# e .NET.
-  Biblioteca Aspose.Tasks para .NET instalada. Você pode baixá-lo[aqui](https://releases.aspose.com/tasks/net/).
- Um ambiente de desenvolvimento configurado para desenvolvimento de aplicativos .NET.
## Importar namespaces
```csharp
    using Aspose.Tasks;
    using System;
    
    using Aspose.Tasks.Saving;
    using Aspose.Tasks.Visualization;
```
Agora, vamos analisar cada etapa do exemplo fornecido.
## Etapa 1: inicializar o projeto e adicionar links de tarefas
```csharp
// O caminho para o diretório de documentos.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "CreateProject1.mpp");
project.TaskLinks.Add(project.RootTask.Children.Add("Task 1"), project.RootTask.Children.Add("Task 2"));
```
Aqui, criamos um projeto e estabelecemos links de tarefas entre a “Tarefa 1” e a “Tarefa 2”.
## Etapa 2: configurar a visualização do gráfico de Gantt
```csharp
var view = (GanttChartView)project.DefaultView;
```
Acesse a visualização Gráfico de Gantt para personalização.
## Etapa 3: ajustar o nível intermediário da escala de tempo
```csharp
view.MiddleTimescaleTier = new TimescaleTier();
view.MiddleTimescaleTier.Unit = TimescaleUnit.Weeks;
view.MiddleTimescaleTier.Count = 1;
view.MiddleTimescaleTier.Label = DateLabel.WeekDddDd;
view.MiddleTimescaleTier.Alignment = HorizontalStringAlignment.Center;
view.MiddleTimescaleTier.ShowTicks = true;
view.MiddleTimescaleTier.UsesFiscalYear = true;
```
Personalize a camada intermediária da escala de tempo para exibir semanas com rótulos e alinhamento específicos.
## Etapa 4: adicionar o nível superior da escala de tempo
```csharp
view.TopTimescaleTier = new TimescaleTier(TimescaleUnit.Months, 1);
```
Adicione uma camada superior de escala de tempo para representar meses.
## Etapa 5: personalizar as datas do nível intermediário
```csharp
view.TopTimescaleTier.DateTimeConverter = date =>
    new[] { "Янв.", "Фев.", "Мар.", "Апр.", "Май", "Июнь", "Июль", "Авг.", "Сен.", "Окт.", "Ноя.", "Дек." }[date.Month - 1];
```
Personalize os rótulos dos meses para melhor visualização.
## Etapa 6: definir o cronograma do projeto
```csharp
project.Set(Prj.TimescaleStart, new DateTime(2012, 7, 30));
project.Set(Prj.TimescaleFinish, new DateTime(2012, 10, 6));
```
Defina o cronograma do projeto para controlar o cronograma geral.
## Etapa 7: salve o projeto com escala de tempo personalizada
```csharp
var pdfSaveOptions = new PdfSaveOptions
{
    Timescale = Timescale.DefinedInView
};
project.Save(DataDir+ "CustomizeTimescaleTierLabels_out.pdf", pdfSaveOptions);
```
Salve o projeto com as configurações de escala de tempo definidas.
## Conclusão
Concluindo, a configuração de camadas de escala de tempo no Aspose.Tasks for .NET permite uma representação mais personalizada e visualmente atraente dos cronogramas do projeto. Essas etapas permitem que você crie uma visualização do Gráfico de Gantt que atenda precisamente às suas necessidades de gerenciamento de projetos.
## Perguntas frequentes
### Posso usar Aspose.Tasks com outras bibliotecas .NET?
Sim, Aspose.Tasks integra-se perfeitamente com outras bibliotecas .NET, oferecendo flexibilidade em sua pilha de desenvolvimento.
### Existe uma licença temporária disponível para fins de teste?
 Sim, você pode obter uma licença temporária[aqui](https://purchase.aspose.com/temporary-license/) para avaliação.
### Existem opções adicionais de personalização para a visualização do Gráfico de Gantt?
Com certeza, Aspose.Tasks oferece amplas opções de personalização para a visualização do Gráfico de Gantt para atender a diversos requisitos do projeto.
### Posso renderizar escalas de tempo em formatos diferentes?
Certamente, você pode explorar vários formatos e estilos de representação da escala de tempo para melhor se adequar ao contexto do seu projeto.
### Existe um fórum da comunidade para suporte do Aspose.Tasks?
 Sim, visite o[Fórum Aspose.Tasks](https://forum.aspose.com/c/tasks/15) para apoio e discussões da comunidade.