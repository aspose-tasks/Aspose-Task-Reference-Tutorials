---
title: Dominando as visualizações de uso de tarefas em Aspose.Tasks para .NET
linktitle: Configurando visualizações de uso de tarefas em Aspose.Tasks
second_title: API Aspose.Tasks .NET
description: Explore Aspose.Tasks for .NET e aprenda como configurar visualizações de uso de tarefas. Personalize as configurações de escala de tempo e aprimore os recursos visuais de gerenciamento de projetos.
type: docs
weight: 24
url: /pt/net/task-table-management/task-usage-views/
---
## Introdução
No domínio do gerenciamento de projetos, visualizar o uso das tarefas é fundamental para um planejamento e execução eficazes. Aspose.Tasks for .NET fornece uma solução robusta para renderizar visualizações de uso de tarefas, permitindo personalizar configurações de escala de tempo e formatos de apresentação. Neste tutorial, percorreremos as etapas para configurar visualizações de uso de tarefas usando Aspose.Tasks.
## Pré-requisitos
Antes de mergulhar no tutorial, certifique-se de ter os seguintes pré-requisitos em vigor:
1.  Aspose.Tasks para .NET: certifique-se de ter a biblioteca Aspose.Tasks integrada ao seu projeto .NET. Você pode baixá-lo[aqui](https://releases.aspose.com/tasks/net/).
2. Ambiente .NET: tenha um ambiente .NET funcional configurado em sua máquina.
## Importar namespaces
Em seu projeto .NET, importe os namespaces necessários para acessar as funcionalidades do Aspose.Tasks. Adicione as seguintes linhas ao seu código:
```csharp
    using Aspose.Tasks;
    using System;
    
    using Aspose.Tasks.Saving;
    using Aspose.Tasks.Visualization;
```
## Etapa 1: definir o caminho do diretório do documento
 Antes de trabalhar com as funcionalidades do Aspose.Tasks, defina o caminho para o diretório de documentos. Substituir`"Your Document Directory"` com o caminho real.
```csharp
String DataDir = "Your Document Directory";
```
## Etapa 2: carregar o projeto
 Inicialize o Aspose.Tasks`Project` objeto carregando seu arquivo de projeto (por exemplo, TaskUsageView.mpp).
```csharp
var project = new Project(DataDir + "TaskUsageView.mpp");
```
## Etapa 3: Definir SaveOptions
 Criar uma`SaveOptions`objeto para especificar as opções de renderização. Defina a escala de tempo para ‘Dias’ e o formato de apresentação para ‘TaskUsage’.
```csharp
SaveOptions options = new PdfSaveOptions
{
    Timescale = Timescale.Days,
    PresentationFormat = PresentationFormat.TaskUsage
};
```
## Etapa 4: economize com escala de tempo de dias
Salve o projeto com as configurações de escala de tempo predefinidas de 'Dias'.
```csharp
var outputProject = "TaskUsageView_result_days_out.pdf";
project.Save(DataDir + outputProject, options);
```
## Etapa 5: economize com a escala de tempo ThirdsOfMonths
Altere as configurações de escala de tempo para 'ThirdsOfMonths' e salve o projeto.
```csharp
options.Timescale = Timescale.ThirdsOfMonths;
outputProject = "TaskUsageView_result_thirdsOfMonths_out.pdf";
project.Save(DataDir + outputProject, options);
```
## Etapa 6: economize com escala de tempo de meses
Defina a escala de tempo para 'Meses' e salve o projeto com as configurações atualizadas.
```csharp
options.Timescale = Timescale.Months;
outputProject = "TaskUsageView_result_months_out.pdf";
project.Save(DataDir + outputProject, options);
```
## Conclusão
Configurar visualizações de uso de tarefas com Aspose.Tasks for .NET é um processo simples. Ao personalizar as configurações de escala de tempo, você pode adaptar a visualização das tarefas do seu projeto de acordo com suas necessidades específicas.
 Sinta-se à vontade para explorar mais recursos e funcionalidades no[documentação](https://reference.aspose.com/tasks/net/).
## perguntas frequentes
### Posso personalizar a escala de tempo além das configurações predefinidas?
Sim, você pode definir uma escala de tempo personalizada especificando os intervalos e as unidades.
### Existem outros formatos de apresentação disponíveis?
Aspose.Tasks oferece suporte a vários formatos de apresentação, incluindo GanttChart, ResourceUsage e muito mais.
### O Aspose.Tasks é compatível com diferentes formatos de arquivo de projeto?
Sim, Aspose.Tasks oferece suporte a formatos de arquivo de projeto populares, como MPP, XML e CSV.
### Posso aplicar diferentes configurações de escala de tempo a tarefas específicas?
Com certeza, você pode personalizar as configurações de escala de tempo para tarefas individuais em seu projeto.
### Como posso obter suporte ou assistência para Aspose.Tasks?
 Visite a[Fórum Aspose.Tasks](https://forum.aspose.com/c/tasks/15) para apoio e orientação da comunidade.