---
date: 2026-04-01
description: Aprenda como definir recorrência no Aspose.Tasks para .NET, adicionar
  tarefas recorrentes e automatizar tarefas recorrentes por mês, semana e dia.
keywords:
- how to set recurrence
- add recurring task
- automate recurring tasks
linktitle: Repetição por Mês, Semana e Dia no Aspose.Tasks
second_title: Aspose.Tasks .NET API
title: Como definir recorrência no Aspose.Tasks (Mês, Semana, Dia)
url: /pt/net/advanced-features/repetition-by-month-week-day/
weight: 26
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Como Definir Recorrência no Aspose.Tasks (Mês, Semana, Dia)

## Introdução

Se você precisa **como definir recorrência** para tarefas em um projeto, Aspose.Tasks for .NET oferece uma maneira limpa e programática de adicionar definições de tarefas recorrentes que executam por mês, semana ou dia. Neste tutorial, percorreremos um exemplo do mundo real que mostra como **adicionar tarefa recorrente**, **automatizar tarefas recorrentes** e gerenciá-las diretamente a partir do código C#. Ao final, você estará pronto para integrar esse recurso em qualquer solução de agendamento ou gerenciamento de projetos.

## Respostas Rápidas
- **O que significa “recurrence” no Aspose.Tasks?** Define um padrão (diário, semanal, mensal) que cria automaticamente instâncias de tarefas ao longo de um intervalo de datas.  
- **Qual método principal cria a recorrência?** `RecurringTaskParameters` combinado com um `RecurrencePattern` específico.  
- **Preciso de uma licença para executar este código?** Uma versão de avaliação funciona para avaliação; uma licença comercial é necessária para produção.  
- **Posso agendar tarefas semanais em vez de mensais?** Sim – troque `MonthlyRecurrencePattern` por `WeeklyRecurrencePattern`.  
- **Quais versões do .NET são suportadas?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6 e posteriores.

## O Que É Recorrência no Aspose.Tasks?

Recorrência é um conjunto de regras que indica ao Aspose.Tasks para gerar instâncias de tarefas em intervalos regulares—diariamente, semanalmente ou mensalmente—sem duplicá‑las manualmente. Esse recurso é essencial para projetos que contêm atividades rotineiras, como reuniões de status, inspeções ou trabalhos de manutenção.

## Por Que Usar Recursos de Recorrência?

- **Economize tempo:** Não é necessário copiar‑colar tarefas manualmente.  
- **Reduza erros:** A biblioteca garante datas e durações consistentes.  
- **Flexibilidade:** Combine padrões (por exemplo, “primeiro domingo de cada 2 meses”).  
- **Automação:** Perfeito para gerar cronogramas em pipelines CI ou ferramentas de relatório.

## Pré‑requisitos

Antes de começar, certifique‑se de que você tem:

1. **Compreensão Básica de C#** – você escreverá algumas linhas de código C#.  
2. **Aspose.Tasks for .NET instalado** – obtenha‑o na [download page](https://releases.aspose.com/tasks/net/).  
3. **Um arquivo de projeto .mpp** – usaremos `Project1.mpp` como arquivo fonte.

## Importar Namespaces

Para começar, importe os namespaces Aspose.Tasks necessários:

```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.Saving;
```

### Etapa 1: Carregar o Arquivo de Projeto

```csharp
// The path to th documents directory.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "Project1.mpp");
```

Criamos uma instância `Project` que aponta para um arquivo Microsoft Project existente.

### Etapa 2: Definir Parâmetros da Tarefa Recorrente

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

Aqui criamos parâmetros de **tarefa recorrente**:

- **TaskName** – o nome da tarefa gerada.  
- **Duration** – a duração de cada ocorrência.  
- **RecurrencePattern** – um padrão mensal que se repete a cada 2 meses no primeiro domingo.  
- **RecurrenceRange** – as datas de início e fim que delimitam o cronograma.

### Etapa 3: Adicionar a Tarefa Recorrente ao Projeto

```csharp
project.RootTask.Children.Add(parameters);
```

Esta linha **adiciona a tarefa recorrente** à raiz da hierarquia do projeto.

### Etapa 4: Salvar o Projeto Atualizado

```csharp
project.Save(DataDir + "CanAddRecurringTask_Months_WeekDay_EndByRecurrenceRange_Test_out.mpp", SaveFileFormat.Mpp);
```

O projeto é salvo como um novo arquivo `.mpp` que agora contém o cronograma automatizado.

## Problemas Comuns e Soluções

| Problema | Razão | Correção |
|----------|-------|----------|
| **Tarefa não aparece** | O intervalo de recorrência está fora das datas do projeto. | Verifique se os valores de `Start` e `Finish` estão dentro do calendário do projeto. |
| **Dia da semana errado** | Incompatibilidade do enum `WeekDay`. | Use `DayOfWeek.Monday` … `DayOfWeek.Sunday` conforme necessário. |
| **Exceção de licença** | Executando sem uma licença válida em produção. | Aplique uma licença temporária ou completa antes de salvar. |

## Perguntas Frequentes

### Q1: Posso personalizar o padrão de recorrência além dos exemplos fornecidos?

A1: Sim, o Aspose.Tasks for .NET oferece amplas opções de personalização para padrões de recorrência, permitindo adaptá‑los aos seus requisitos específicos.

### Q2: Existe uma versão de avaliação disponível para Aspose.Tasks for .NET?

A2: Sim, você pode obter uma avaliação gratuita do Aspose.Tasks for .NET na [releases page](https://releases.aspose.com/).

### Q3: Como posso obter suporte para Aspose.Tasks for .NET?

A3: Você pode buscar assistência e interagir com a comunidade no [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15).

### Q4: Licenças temporárias estão disponíveis para Aspose.Tasks for .NET?

A4: Sim, você pode adquirir licenças temporárias na [purchase page](https://purchase.aspose.com/temporary-license/) para fins de teste e avaliação.

### Q5: Onde posso encontrar documentação abrangente para Aspose.Tasks for .NET?

A5: Você pode consultar a detalhada [documentation](https://reference.aspose.com/tasks/net/) disponível no site da Aspose para orientação aprofundada sobre o uso da biblioteca.

---

**Última atualização:** 2026-04-01  
**Testado com:** Aspose.Tasks 24.11 for .NET  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}