---
title: Repetição por mês, dia da semana em Aspose.Tasks
linktitle: Repetição por mês, dia da semana em Aspose.Tasks
second_title: API Aspose.Tasks .NET
description: Aprenda como configurar repetições por mês, semana e dia em Aspose.Tasks for .NET para automatizar tarefas recorrentes com eficiência.
weight: 26
url: /pt/net/advanced-features/repetition-by-month-week-day/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Repetição por mês, dia da semana em Aspose.Tasks

## Introdução

No domínio do desenvolvimento de software, especialmente em aplicações de gerenciamento de projetos, a capacidade de lidar com tarefas recorrentes de forma eficiente é fundamental. Aspose.Tasks for .NET é uma biblioteca poderosa projetada para agilizar a criação e o gerenciamento de tarefas de projeto, incluindo as recorrentes. Uma dessas funcionalidades fornecidas pelo Aspose.Tasks é a capacidade de configurar repetições por mês, semana e dia, garantindo que as tarefas sejam executadas dentro do cronograma, sem intervenção manual.

## Pré-requisitos

Antes de mergulhar nos meandros da configuração de repetições por mês, semana e dia usando Aspose.Tasks for .NET, certifique-se de ter os seguintes pré-requisitos em vigor:

1. Compreensão básica de C#: Familiaridade com a linguagem de programação C# é essencial para compreender e implementar os exemplos de código fornecidos.
   
2.  Instalação do Aspose.Tasks for .NET: Certifique-se de ter baixado e instalado a biblioteca Aspose.Tasks for .NET. Você pode obter a biblioteca no[página de download](https://releases.aspose.com/tasks/net/).

3. Acesso a um arquivo de projeto .mpp: Tenha em mãos um arquivo do Microsoft Project (.mpp), pois o utilizaremos para demonstrar a implementação de repetições por mês, semana e dia.

## Importar namespaces

Para começar a utilizar Aspose.Tasks for .NET em seu aplicativo C#, você precisa importar os namespaces necessários. Veja como você pode fazer isso:

```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.Saving;

```

Vamos dividir o trecho de código fornecido em várias etapas para entender cada parte completamente.

## Etapa 1: carregar o arquivo do projeto

```csharp
// O caminho para o diretório de documentos.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "Project1.mpp");
```

 Esta etapa envolve a criação de uma nova instância do`Project` class e carregando um arquivo existente do Microsoft Project (`Project1.mpp`) do diretório especificado.

## Etapa 2: definir parâmetros de tarefas recorrentes

```csharp
var parameters = new RecurringTaskParameters
{
    TaskName = "t1",
    Duration = project.GetDuration(1, TimeUnitType.Day),
    RecurrencePattern = new MonthlyRecurrencePattern
    {
        Repetition = new ByMonthWeekDayRepetition
        {
            Position = OrdinalNumber.First,
            WeekDay = DayOfWeek.Sunday,
            RepetitionInterval = 2
        },
        RecurrenceRange = new EndByRecurrenceRange
        {
            Start = new DateTime(2018, 7, 1, 8, 0, 0),
            Finish = new DateTime(2018, 9, 2, 17, 0, 0)
        }
    }
};
```

Nesta etapa, definimos os parâmetros para uma tarefa recorrente. Especificamos o nome da tarefa, duração, padrão de repetição (mensalmente) e intervalo de recorrência (término em uma data específica).

## Etapa 3: adicionar tarefa recorrente ao projeto

```csharp
project.RootTask.Children.Add(parameters);
```

Aqui, adicionamos os parâmetros de tarefa recorrente definidos à tarefa raiz do projeto.

## Etapa 4: salvar o arquivo do projeto

```csharp
project.Save(DataDir + "CanAddRecurringTask_Months_WeekDay_EndByRecurrenceRange_Test_out.mpp", SaveFileFormat.Mpp);
```

Finalmente, salvamos o arquivo de projeto modificado com a tarefa recorrente adicionada.

## Conclusão

Concluindo, configurar repetições por mês, semana e dia no Aspose.Tasks for .NET é um processo direto que permite aos desenvolvedores automatizar o gerenciamento de tarefas recorrentes em seus projetos de forma eficiente. Seguindo as etapas descritas neste tutorial, você pode integrar perfeitamente essa funcionalidade em seus aplicativos C#, economizando tempo e esforço no gerenciamento de projetos.

## Perguntas frequentes

###Q1: Posso personalizar o padrão de recorrência além dos exemplos fornecidos?

A1: Sim, Aspose.Tasks for .NET oferece amplas opções de personalização para padrões de recorrência, permitindo adaptá-los aos seus requisitos específicos.

###Q2: Existe uma versão de teste disponível para Aspose.Tasks for .NET?

 A2: Sim, você pode obter uma avaliação gratuita do Aspose.Tasks for .NET no[página de lançamentos](https://releases.aspose.com/).

###Q3: Como posso obter suporte para Aspose.Tasks for .NET?

 A3: Você pode procurar assistência e interagir com a comunidade no[Fórum Aspose.Tasks](https://forum.aspose.com/c/tasks/15).

###Q4: As licenças temporárias estão disponíveis para Aspose.Tasks for .NET?

 A4: Sim, você pode adquirir licenças temporárias do[página de compra](https://purchase.aspose.com/temporary-license/) para fins de teste e avaliação.

###Q5: Onde posso encontrar documentação abrangente para Aspose.Tasks for .NET?

 A5: Você pode consultar o detalhado[documentação](https://reference.aspose.com/tasks/net/) disponível no site Aspose para orientação detalhada sobre a utilização da biblioteca.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
