---
date: 2026-04-03
description: Aprenda a usar o Aspose.Tasks para adicionar tarefas recorrentes ao projeto
  e salvar o projeto como MPP. Este guia mostra o recurso de Repetição por Ano, Semana
  e Dia passo a passo.
keywords:
- how to use aspose.tasks
- add recurring task project
- save project as mpp
linktitle: Repetição por Ano, Semana e Dia no Aspose.Tasks
second_title: Aspose.Tasks .NET API
title: Como usar o Aspose.Tasks – Repetição por Ano, Semana e Dia
url: /pt/net/advanced-features/repetition-by-year-week-day/
weight: 28
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Repetição por Ano Semana Dia no Aspose.Tasks

## Introdução

Quando você precisa **how to use Aspose.Tasks** para lidar com agendas recorrentes complexas, a biblioteca oferece controle detalhado sobre padrões anuais. Neste tutorial, vamos percorrer a criação de uma tarefa que se repete em um dia da semana específico de um determinado mês, abrangendo vários anos. Ao final, você poderá **add recurring task project** entradas e **save project as MPP** com apenas algumas linhas de C#.

## Respostas Rápidas
- **O que significa “Repetition by Year Week Day”?** Ele repete uma tarefa em um dia da semana escolhido (por exemplo, primeiro domingo) de um determinado mês a cada ano.  
- **Quais versões do .NET são suportadas?** Todas as versões modernas do .NET Framework e .NET Core/5/6.  
- **Preciso de uma licença para executar o código?** Um teste gratuito funciona para desenvolvimento; uma licença comercial é necessária para produção.  
- **Posso alterar o intervalo de recorrência?** Sim – você pode definir uma data de início, data de término ou um número fixo de ocorrências.  
- **A saída é um arquivo MPP?** Absolutamente – o projeto é salvo como um arquivo MPP pronto para o Microsoft Project.

## O que é o recurso “Repetition by Year Week Day”?

O recurso permite definir uma recorrência anual que tem como alvo um **day of the week** específico (por exemplo, Sunday) e uma **position** dentro do mês (primeiro, segundo, último, etc.). Isso é ideal para tarefas como revisões trimestrais, auditorias anuais ou qualquer evento que siga um ritmo baseado no calendário.

## Por que usar Aspose.Tasks para tarefas recorrentes?

- **Precision** – Controle total sobre meses, dias da semana e posições ordinais.  
- **Compatibility** – Gera arquivos MPP nativos que abrem perfeitamente no Microsoft Project.  
- **No COM interop** – API .NET pura, sem necessidade de instalações do Office.  
- **Scalability** – Funciona tanto para pequenos projetos quanto para cronogramas de nível empresarial.

## Pré-requisitos

Antes de mergulhar no código, certifique‑se de que você tem:

1. **Basic .NET knowledge** – Familiaridade com C# e conceitos orientados a objetos.  
2. **Aspose.Tasks for .NET** – Baixe-o a partir do [download link](https://releases.aspose.com/tasks/net/) e adicione o DLL ao seu projeto.  
3. **Access to the official docs** – A [documentation](https://reference.aspose.com/tasks/net/) contém detalhes exaustivos sobre todas as classes.  
4. **A development IDE** – Visual Studio, Rider ou qualquer editor .NET compatível.

Agora que você está pronto, vamos ver a implementação.

## Como Usar Aspose.Tasks para Tarefas Recorrentes

### Importando Namespaces Necessários

Primeiro, traga os namespaces necessários para o escopo para que você possa trabalhar com projetos, tarefas e opções de salvamento.

```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.Saving;
```

### Etapa 1: Inicializar Projeto e Parâmetros da Tarefa

Crie uma nova instância `Project`, então defina um objeto `RecurringTaskParameters` que descreve o padrão de recorrência.

```csharp
// The path to the documents directory.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "Blank2010.mpp");
var parameters = new RecurringTaskParameters
{
    TaskName = "t1",
    Duration = project.GetDuration(1, TimeUnitType.Day),
    RecurrencePattern = new YearlyRecurrencePattern
    {
        Repetition = new ByYearWeekDayRepetition
        {
            Month = Month.July, WeekDay = DayOfWeek.Sunday, Position = OrdinalNumber.First
        },
        RecurrenceRange = new EndByRecurrenceRange
        {
            Start = new DateTime(2018, 7, 1, 8, 0, 0),
            Finish = new DateTime(2019, 7, 31, 17, 0, 0)
        }
    }
};
```

> **Pro tip:** Ajuste `Month`, `WeekDay` e `Position` para corresponder ao seu cronograma real.

### Etapa 2: Adicionar Parâmetros ao Projeto

Insira a definição da tarefa recorrente na raiz do projeto.

```csharp
project.RootTask.Children.Add(parameters);
```

### Etapa 3: Salvar Projeto como MPP

Finalmente, persista o projeto em um arquivo MPP para que ele possa ser aberto no Microsoft Project ou em qualquer visualizador compatível.

```csharp
project.Save(DataDir + "CanAddRecurringTask_Years_YearWeekDay_EndByRecurrenceRange_Test.mpp", SaveFileFormat.Mpp);
```

> This demonstrates **save project as mpp** em uma única linha de código.

## Problemas Comuns e Soluções

| Sintoma | Causa Provável | Correção |
|---------|----------------|----------|
| Nenhuma tarefa aparece ao abrir o arquivo MPP | Datas do intervalo de recorrência estão fora do calendário do projeto | Verifique se as datas `Start` e `Finish` estão dentro do horário de trabalho do projeto |
| Exceção `ArgumentNullException` ao `Add` | `parameters` está nulo ou não totalmente inicializado | Garanta que todas as propriedades necessárias (TaskName, Duration, RecurrencePattern) estejam definidas |
| Dia da semana errado selecionado | Incompatibilidade de valor do enum `WeekDay` | Use `DayOfWeek.Monday` … `DayOfWeek.Sunday` conforme necessário |

## Perguntas Frequentes

**Q: Posso personalizar o padrão de recorrência além do exemplo fornecido?**  
A: Sim, Aspose.Tasks permite combinar `MonthlyRecurrencePattern`, `WeeklyRecurrencePattern` ou até objetos `RecurrenceRange` personalizados para se adequar a qualquer cronograma.

**Q: O Aspose.Tasks para .NET é compatível com outros softwares de gerenciamento de projetos?**  
A: Absolutamente – a biblioteca lê e grava formatos MPP, XML e Primavera, permitindo troca suave de dados.

**Q: Como posso lidar com exceções ou modificações em tarefas recorrentes?**  
A: Use a classe `ExceptionTask` para criar substituições para ocorrências específicas, ou edite o `RecurringTaskParameters` e salve novamente o projeto.

**Q: O Aspose.Tasks suporta soluções baseadas em nuvem?**  
A: Sim, você pode executar a API em Azure Functions, AWS Lambda ou qualquer serviço de nuvem compatível com .NET.

**Q: Existe uma versão de avaliação disponível para Aspose.Tasks para .NET?**  
A: Sim, você pode acessar uma avaliação gratuita do Aspose.Tasks para .NET a partir do [website](https://releases.aspose.com/), permitindo explorar seus recursos antes de decidir pela compra.

**Q: Como adiciono uma tarefa recorrente a um projeto existente sem sobrescrever outros dados?**  
A: Carregue o projeto existente com `new Project("Existing.mpp")`, adicione o `RecurringTaskParameters` a `RootTask.Children` e então `Save` o arquivo.

## Conclusão

Ao dominar **how to use Aspose.Tasks** para o cenário **Repetition by Year Week Day**, você ganha a capacidade de **add recurring task project** entradas que se alinham perfeitamente com calendários reais e **save project as MPP** para colaboração sem atritos. Incorpore esses trechos em suas próprias soluções para melhorar a precisão do agendamento e reduzir o esforço manual.

---

**Última atualização:** 2026-04-03  
**Testado com:** Aspose.Tasks 24.12 for .NET  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}