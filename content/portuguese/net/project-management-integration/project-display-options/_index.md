---
title: Configurar opções de exibição do MS Project em Aspose.Tasks
linktitle: Configurar opções de exibição do projeto em Aspose.Tasks
second_title: API Aspose.Tasks .NET
description: Aprenda como configurar as opções de exibição do MS Project programaticamente usando Aspose.Tasks for .NET. Personalize a aparência do seu projeto sem esforço.
type: docs
weight: 17
url: /pt/net/project-management-integration/project-display-options/
---
## Introdução
Microsoft Project oferece uma infinidade de opções de exibição para personalizar a aparência do seu projeto. Aspose.Tasks for .NET fornece uma estrutura robusta para manipular essas opções programaticamente. Neste tutorial, exploraremos como configurar as opções de exibição do MS Project usando Aspose.Tasks.
## Pré-requisitos
Antes de mergulhar no tutorial, certifique-se de ter o seguinte:
1.  Aspose.Tasks for .NET: Baixe e instale a biblioteca de[aqui](https://releases.aspose.com/tasks/net/).
2. Arquivo Microsoft Project: Tenha um arquivo MS Project válido (.mpp) pronto para aplicar as opções de exibição.
3. Conhecimento básico de C#: É necessária familiaridade com a linguagem de programação C#.

## Importando Namespaces
Em primeiro lugar, certifique-se de importar os namespaces necessários para o seu código C#:
```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.Saving;
```
## Etapa 1: carregar o arquivo do projeto
 Carregue o arquivo do MS Project usando o`Project` classe fornecida por Aspose.Tasks:
```csharp
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "YourProjectFile.mpp");
```
## Etapa 2: configurar opções de exibição
Agora, vamos configurar diversas opções de exibição disponíveis no MS Project:
### Desativar avisos de agendamento de tarefas
Para desabilitar avisos para conflitos de agendamento com tarefas agendadas manualmente (disponível para Project 2010 e posterior):
```csharp
project.DisplayOptions.ShowTaskScheduleWarnings = false;
```
### Adicionar espaço antes do rótulo
Defina para adicionar um espaço antes do valor numérico e da abreviação da hora:
```csharp
project.DisplayOptions.AddSpaceBeforeLabel = true;
```
### Configurar exibição de rótulo para unidades de tempo
Personalize como as diferentes unidades de tempo são exibidas:
```csharp
project.DisplayOptions.MinuteLabel = MinuteLabelDisplay.Min;
project.DisplayOptions.HourLabel = HourLabelDisplay.Hr;
project.DisplayOptions.DayLabel = DayLabelDisplay.Dy;
project.DisplayOptions.WeekLabel = WeekLabelDisplay.Week;
project.DisplayOptions.MonthLabel = MonthLabelDisplay.Mon;
project.DisplayOptions.YearLabel = YearLabelDisplay.Year;
```
### Mostrar tarefa de resumo do projeto
Exiba informações resumidas sobre todo o projeto em uma única linha:
```csharp
project.DisplayOptions.ShowProjectSummaryTask = true;
```
### Habilitar sugestões de agendamento de tarefas
Permitir a exibição de sugestões para conflitos de agendamento com tarefas agendadas manualmente:
```csharp
project.DisplayOptions.ShowTaskScheduleSuggestions = true;
```
### Sublinhar hiperlinks
Defina para sublinhar hiperlinks dentro do projeto:
```csharp
project.DisplayOptions.UnderlineHyperlinks = true;
```
## Etapa 3: salve o projeto
Por fim, salve o projeto com as opções de exibição aplicadas:
```csharp
project.Save(DataDir + "ModifiedProjectFile.mpp", SaveFileFormat.Mpp);
```

## Conclusão
Neste tutorial, aprendemos como configurar as opções de exibição do MS Project usando Aspose.Tasks for .NET. Com esses recursos, você pode personalizar com eficiência a aparência dos arquivos do seu projeto de maneira programática.
## Perguntas frequentes
### P: Posso aplicar essas opções de exibição somente a tarefas específicas?
R: Sim, você pode aplicar seletivamente opções de exibição a tarefas individuais usando a API Aspose.Tasks.
### P: Essas opções de exibição afetam os dados subjacentes do projeto?
R: Não, estas opções apenas modificam a representação visual do projeto e não alteram os dados subjacentes.
### P: Essas opções de exibição são compatíveis com todas as versões do Microsoft Project?
R: Não, algumas opções podem ser específicas para determinadas versões do MS Project. Consulte a documentação para obter detalhes de compatibilidade.
### P: Posso reverter as opções de exibição para as configurações padrão?
R: Sim, você pode redefinir as opções de exibição para seus valores padrão usando a API Aspose.Tasks.
### P: Há alguma limitação para personalizar as opções de exibição de maneira programática?
R: Embora Aspose.Tasks forneça amplos recursos de personalização, certas opções de exibição podem não estar acessíveis programaticamente devido a limitações no formato de arquivo do MS Project.