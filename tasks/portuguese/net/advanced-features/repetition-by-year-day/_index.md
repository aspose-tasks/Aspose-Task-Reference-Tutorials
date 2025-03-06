---
title: Repetição por dia do ano em Aspose.Tasks
linktitle: Repetição por dia do ano em Aspose.Tasks
second_title: API Aspose.Tasks .NET
description: Aprenda como lidar com repetições de dias do ano em Aspose.Tasks for .NET para agilizar o gerenciamento de tarefas recorrentes com eficiência.
weight: 27
url: /pt/net/advanced-features/repetition-by-year-day/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Repetição por dia do ano em Aspose.Tasks

## Introdução

No domínio do gerenciamento de projetos, o agendamento eficiente e a recorrência de tarefas desempenham papéis essenciais para garantir a execução oportuna e o fluxo de trabalho tranquilo. Aspose.Tasks for .NET oferece uma solução robusta para os desenvolvedores lidarem com tarefas recorrentes sem esforço em seus aplicativos. Neste tutorial, nos aprofundamos nas complexidades de trabalhar com repetições de dias do ano usando Aspose.Tasks, fornecendo um guia completo para a criação de tarefas recorrentes com base em padrões anuais.

## Pré-requisitos

Antes de mergulhar no tutorial, certifique-se de ter os seguintes pré-requisitos em vigor:

1.  Biblioteca Aspose.Tasks for .NET: Baixe e instale a biblioteca Aspose.Tasks for .NET do[local na rede Internet](https://releases.aspose.com/tasks/net/).
   
2. Ambiente de desenvolvimento: Configure um ambiente de desenvolvimento adequado com Visual Studio ou qualquer outro IDE preferido para desenvolvimento .NET.

3. Conhecimento básico de C#: familiarize-se com os fundamentos da linguagem de programação C# para acompanhar os exemplos de código.

4. Conceitos de gerenciamento de projetos: A compreensão dos conceitos de gerenciamento de projetos e do agendamento de tarefas ajudará na compreensão eficaz dos conceitos do tutorial.

## Importar namespaces

Antes de começarmos a codificar, vamos importar os namespaces necessários para facilitar a manipulação de nossas tarefas usando Aspose.Tasks for .NET.

```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.Saving;

```

Agora, vamos dividir o exemplo fornecido em várias etapas e elucidar cada etapa detalhadamente.

## Etapa 1: carregar o arquivo do projeto

```csharp
// O caminho para o diretório de documentos.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "Project1.mpp");
```

 Aqui, inicializamos um novo`Project` objeto e carregue um arquivo de projeto existente chamado "Project1.mpp".

## Etapa 2: definir parâmetros de tarefas recorrentes

```csharp
var parameters = new RecurringTaskParameters
{
    TaskName = "t1",
    Duration = project.GetDuration(1, TimeUnitType.Day),
    RecurrencePattern = new YearlyRecurrencePattern
    {
        Repetition = new ByYearDayRepetition { DayPosition = 1, Month = Month.July },
        RecurrenceRange = new EndByRecurrenceRange
        {
            Start = new DateTime(2018, 7, 1, 8, 0, 0),
            Finish = new DateTime(2019, 7, 1, 17, 0, 0)
        }
    }
};
```

 Nesta etapa, definimos parâmetros para nossa tarefa recorrente. Especificamos o nome da tarefa, a duração e o padrão de recorrência. Para recorrência anual, usamos o`YearlyRecurrencePattern` e defina a repetição para ocorrer no dia 1º de julho usando`ByYearDayRepetition`. Além disso, definimos o intervalo de recorrência de 1º de julho de 2018 a 1º de julho de 2019.

## Etapa 3: adicionar tarefa ao projeto

```csharp
project.RootTask.Children.Add(parameters);
```

Aqui, adicionamos os parâmetros de tarefa recorrente definidos à tarefa raiz do projeto.

## Passo 4: Salvar Projeto

```csharp
project.Save(DataDir + "CanAddRecurringTask_Years_YearDay_EndByRecurrenceRange_Test.mpp", SaveFileFormat.Mpp);
```

Finalmente, salvamos o arquivo de projeto modificado com a tarefa recorrente adicionada.

## Conclusão

Neste tutorial, exploramos o processo de trabalhar com repetições de dias do ano em Aspose.Tasks for .NET. Seguindo as etapas fornecidas, os desenvolvedores podem integrar perfeitamente a funcionalidade de tarefas recorrentes em seus aplicativos, aprimorando os recursos de gerenciamento de projetos.

## Perguntas frequentes

### Q1: O Aspose.Tasks pode lidar com padrões de recorrência complexos?

A1: Sim, Aspose.Tasks fornece suporte abrangente para vários padrões de recorrência, incluindo padrões complexos, como repetições anuais, mensais, semanais e diárias.

### Q2: O Aspose.Tasks é compatível com diferentes formatos de arquivo de projeto?

A2: Com certeza, Aspose.Tasks oferece suporte a formatos de arquivo de projeto populares, como MPP, XML e CSV, garantindo compatibilidade entre diferentes ferramentas de gerenciamento de projeto.

### Q3: O Aspose.Tasks oferece documentação e suporte para desenvolvedores?

R3: Sim, os desenvolvedores podem acessar uma extensa documentação e buscar assistência nos fóruns da comunidade Aspose.Tasks para quaisquer dúvidas ou problemas que encontrarem.

### Q4: Posso personalizar as propriedades da tarefa, como duração e data de início, usando Aspose.Tasks?

A4: Certamente, Aspose.Tasks fornece APIs robustas para manipular propriedades de tarefas dinamicamente, permitindo que os desenvolvedores personalizem durações, datas de início, dependências e muito mais.

### P5: O Aspose.Tasks é adequado para projetos de pequena escala e de nível empresarial?

A5: Na verdade, o Aspose.Tasks foi projetado para atender às necessidades dos desenvolvedores que trabalham em projetos de todas as escalas, desde tarefas individuais até projetos empresariais de grande escala.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
