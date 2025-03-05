---
title: Configurando parâmetros de tarefas recorrentes em Aspose.Tasks
linktitle: Configurando parâmetros de tarefas recorrentes em Aspose.Tasks
second_title: API Aspose.Tasks .NET
description: Aprenda como definir parâmetros de tarefas recorrentes no Microsoft Project usando Aspose.Tasks for .NET. Tutorial abrangente com guia passo a passo.
type: docs
weight: 14
url: /pt/net/rate-recurring-tasks/recurring-task-parameters/
---
## Introdução
Neste tutorial, iremos guiá-lo através do processo de configuração de parâmetros de tarefas recorrentes do Microsoft Project usando Aspose.Tasks for .NET.
## Pré-requisitos
Antes de começar, certifique-se de ter o seguinte:
1. Compreensão básica da linguagem de programação C#.
2. Visual Studio instalado ou qualquer outro IDE C#.
3. Biblioteca Aspose.Tasks para .NET instalada e referenciada em seu projeto.

## Importar namespaces
Primeiramente, você precisa importar os namespaces necessários em seu código C#:
```csharp
using Aspose.Tasks;
using System;

```
## Etapa 1: definir o diretório de documentos
```csharp
String DataDir = "Your Document Directory";
```
 Substituir`"Your Document Directory"` com o caminho para o diretório do seu documento.
## Etapa 2: carregar o arquivo do projeto
```csharp
var project = new Project(DataDir + "Blank2010.mpp");
```
 Esta linha de código carrega o arquivo do Microsoft Project no`project` variável.
## Etapa 3: definir parâmetros de tarefas recorrentes
```csharp
var parameters = new RecurringTaskParameters
{
    TaskName = "Recurring task",
    Duration = project.GetDuration(1, TimeUnitType.Day),
    RecurrencePattern = new WeeklyRecurrencePattern
    {
        Repetition = new WeeklyRepetition
        {
            RepetitionInterval = 2,
            WeekDays = WeekdayType.Sunday | WeekdayType.Monday | WeekdayType.Friday
        },
        RecurrenceRange = new EndByRecurrenceRange
        {
            Start = new DateTime(2018, 7, 1, 8, 0, 0),
            Finish = new DateTime(2018, 7, 20, 17, 0, 0)
        }
    },
    IgnoreResourceCalendar = false
};
```
Aqui, você define os parâmetros para a tarefa recorrente, como nome da tarefa, duração, padrão de recorrência, intervalo de recorrência e se deve ignorar o calendário de recursos.
## Etapa 4: definir calendário para tarefas recorrentes
```csharp
parameters.SetCalendar(project, "Standard");
```
Esta etapa define o calendário para a tarefa recorrente. Neste exemplo, ele define o calendário como “Padrão”.
## Etapa 5: adicionar parâmetros ao projeto
```csharp
project.RootTask.Children.Add(parameters);
```
Por fim, adicione os parâmetros à tarefa raiz do projeto.

## Conclusão
Neste tutorial, demonstramos como definir parâmetros de tarefas recorrentes do Microsoft Project usando Aspose.Tasks for .NET. Seguindo essas etapas, você pode gerenciar com eficiência tarefas recorrentes em seus projetos.
## Perguntas frequentes
### Posso personalizar ainda mais o padrão de recorrência?
Sim, Aspose.Tasks oferece vários padrões de recorrência e opções para personalizar de acordo com os requisitos do seu projeto.
### Existe uma versão de teste disponível antes de comprar?
 Sim, você pode baixar uma avaliação gratuita em Aspose.Tasks[local na rede Internet](https://purchase.aspose.com/buy) para avaliar os recursos da biblioteca.
### O Aspose.Tasks oferece suporte a outros formatos de arquivo de projeto?
Sim, Aspose.Tasks oferece suporte a vários formatos de arquivo de projeto, incluindo MPP, XML, XLSX e muito mais.
### Posso obter suporte se encontrar algum problema durante a implementação?
Sim, você pode visitar o fórum Aspose.Tasks para obter assistência da comunidade ou entrar em contato com o suporte para obter ajuda direta.
### Como posso obter uma licença temporária para Aspose.Tasks?
 Você pode obter uma licença temporária do[local na rede Internet](https://purchase.aspose.com/temporary-license/) para fins de teste.