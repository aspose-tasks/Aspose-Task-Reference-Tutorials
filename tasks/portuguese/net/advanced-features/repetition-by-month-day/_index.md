---
title: Repetição por dia do mês em Aspose.Tasks
linktitle: Repetição por dia do mês em Aspose.Tasks
second_title: API Aspose.Tasks .NET
description: Aprenda como gerenciar tarefas recorrentes em projetos .NET com Aspose.Tasks. Guia passo a passo para lidar com a repetição por mês e dia.
type: docs
weight: 25
url: /pt/net/advanced-features/repetition-by-month-day/
---
## Introdução

No domínio do desenvolvimento .NET, Aspose.Tasks se destaca como uma ferramenta poderosa para gerenciar tarefas e cronogramas de projetos. Ele oferece uma infinidade de funcionalidades para agilizar os fluxos de trabalho de gerenciamento de projetos, incluindo o gerenciamento de tarefas recorrentes. A repetição por dia do mês é um requisito comum no agendamento de projetos, e Aspose.Tasks fornece suporte robusto para esse cenário.

## Pré-requisitos

Antes de mergulhar no tutorial, certifique-se de ter os seguintes pré-requisitos:

1. Compreensão básica de C#: É necessária familiaridade com a linguagem de programação C# para compreender os conceitos discutidos neste tutorial.
2. Instalação do Aspose.Tasks for .NET: Certifique-se de ter instalado o Aspose.Tasks for .NET. Você pode baixá-lo em[aqui](https://releases.aspose.com/tasks/net/).
3. Ambiente de Desenvolvimento Integrado (IDE): Tenha um IDE como o Visual Studio instalado em seu sistema para conveniência de codificação.

## Importar namespaces

Em seu projeto C#, importe os namespaces necessários para acessar as funcionalidades do Aspose.Tasks:

```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.Saving;

```

Vamos dividir o exemplo de código fornecido em formato de guia passo a passo:

## Etapa 1: carregar o arquivo do projeto

```csharp
// O caminho para o diretório de documentos.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "Project1.mpp");
```

 Esta linha de código inicializa uma nova instância do`Project` class, carregando o arquivo de projeto denominado "Project1.mpp".

## Etapa 2: definir parâmetros de tarefas recorrentes

```csharp
var parameters = new RecurringTaskParameters
{
    TaskName = "t1",
    Duration = project.GetDuration(1, TimeUnitType.Day),
    RecurrencePattern = new MonthlyRecurrencePattern
    {
        Repetition = new ByMonthDayRepetition { DayPosition = 1, RepetitionInterval = 2 },
        RecurrenceRange = new EndByRecurrenceRange
        {
            Start = new DateTime(2018, 7, 1, 8, 0, 0),
            Finish = new DateTime(2018, 9, 30, 17, 0, 0)
        }
    }
};
```

Esta seção define os parâmetros da tarefa recorrente, incluindo nome, duração, padrão de repetição e intervalo de recorrência.

## Etapa 3: adicionar tarefa ao projeto

```csharp
project.RootTask.Children.Add(parameters);
```

Aqui, adicionamos os parâmetros da tarefa recorrente ao projeto.

## Etapa 4: salvar o arquivo do projeto

```csharp
project.Save(DataDir + "CanAddRecurringTask_Months_EndByRecurrenceRange_Test_out.mpp", SaveFileFormat.Mpp);
```

Finalmente, o projeto modificado é salvo com a tarefa recorrente adicionada.

## Conclusão

Neste tutorial, exploramos como lidar com a repetição por dia do mês em Aspose.Tasks for .NET. Seguindo as etapas fornecidas, você pode gerenciar com eficiência tarefas recorrentes dentro dos cronogramas do seu projeto.

## Perguntas frequentes

### Q1: O Aspose.Tasks é compatível com todas as versões do .NET?

A1: Aspose.Tasks oferece suporte a várias versões do .NET framework, garantindo compatibilidade em diferentes ambientes.

### P2: Posso personalizar ainda mais o padrão de recorrência?

A2: Sim, Aspose.Tasks oferece amplas opções de personalização para definir padrões de recorrência de acordo com requisitos específicos do projeto.

### Q3: O Aspose.Tasks fornece suporte para outras funcionalidades de gerenciamento de projetos?

A3: Com certeza, Aspose.Tasks oferece uma ampla gama de recursos para gerenciamento de projetos, incluindo rastreamento de tarefas, alocação de recursos e geração de gráfico de Gantt.

### Q4: Existe uma versão de teste disponível para Aspose.Tasks?

 A4: Sim, você pode aproveitar uma avaliação gratuita em[aqui](https://releases.aspose.com/) para explorar os recursos do Aspose.Tasks antes de tomar uma decisão de compra.

### P5: Onde posso procurar assistência se encontrar problemas ou tiver dúvidas?

 A5: Você pode visitar o[Fórum Aspose.Tasks](https://forum.aspose.com/c/tasks/15) para buscar apoio da comunidade ou da equipe Aspose.