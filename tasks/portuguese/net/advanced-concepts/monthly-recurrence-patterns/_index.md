---
date: 2026-03-08
description: Aprenda a criar uma tarefa recorrente mensal no Aspose.Tasks para .NET
  com este tutorial passo a passo.
linktitle: How to Create Monthly Recurring Task in Aspose.Tasks
second_title: Aspose.Tasks .NET API
title: Como criar tarefa recorrente mensal no Aspose.Tasks
url: /pt/net/advanced-concepts/monthly-recurrence-patterns/
weight: 18
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Criar Tarefa Recorrente Mensal Usando Aspose.Tasks

## Introdução

Aspose.Tasks for .NET permite que você manipule programaticamente arquivos do Microsoft Project, e uma das necessidades reais mais comuns é **criar cronogramas de tarefa recorrente mensal**. Seja construindo uma ferramenta de acompanhamento de projetos, automatizando a alocação de recursos ou gerando itens de trabalho de manutenção recorrentes, este tutorial orienta você passo a passo a adicionar um padrão de recorrência mensal a uma tarefa.

Nas próximas seções, você verá como configurar o projeto, definir os parâmetros de recorrência e, finalmente, salvar o arquivo atualizado — tudo com explicações claras e dicas práticas.

## Respostas Rápidas
- **O que significa “tarefa recorrente mensal”?** Uma tarefa que se repete em um padrão de dia ou semana definido a cada mês.  
- **Qual classe da API lida com recorrência?** `RecurringTaskParameters` junto com `MonthlyRecurrencePattern`.  
- **Preciso de uma licença para executar o exemplo?** Uma avaliação gratuita funciona para avaliação; uma licença é necessária para produção.  
- **Posso alterar o intervalo?** Sim – defina `RepetitionInterval` para o número de meses entre as ocorrências.  
- **Quais formatos de arquivo são suportados?** Tanto arquivos de Projeto `.mpp` quanto `.xml` podem ser carregados e salvos.

## O que é um Padrão de Recorrência Mensal?

Um padrão de recorrência mensal informa ao Microsoft Project (e ao Aspose.Tasks) com que frequência uma tarefa deve se repetir a cada mês. Você pode especificar um dia fixo do mês (por exemplo, o 1º) ou uma posição relativa (por exemplo, a última sexta‑feira). A API traduz essas regras na estrutura subjacente do arquivo de Projeto.

## Por que usar Aspose.Tasks para isso?

- **Controle total** – Sem limitações de interface; você define todos os aspectos do padrão no código.  
- **Multiplataforma** – Funciona no .NET Framework, .NET Core e .NET 5/6+.  
- **Sem necessidade do Microsoft Project** – Gere ou modifique arquivos em um servidor ou pipeline de CI.  

## Pré‑requisitos

Antes de começar, certifique‑se de que você tem:

- .NET 6 (ou .NET 5/Framework 4.7+) instalado.  
- Pacote NuGet Aspose.Tasks for .NET adicionado ao seu projeto.  
- Um arquivo de Projeto de exemplo (`Project1.mpp`) colocado em uma pasta conhecida (`DataDir`).  

## Importar Namespaces

Primeiro, importe os namespaces necessários para trabalhar com tarefas e salvar projetos:

```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.Saving;
```

## Etapa 1: Inicializar o Projeto

Crie uma instância `Project` que aponte para o seu arquivo `.mpp` existente. Isso carrega o arquivo na memória para que você possa modificá‑lo.

```csharp
var project = new Project(DataDir + "Project1.mpp");
```

> **Dica profissional:** Se o arquivo não existir, o Aspose.Tasks criará automaticamente um novo projeto em branco.

## Etapa 2: Definir Parâmetros da Tarefa Recorrente

Defina os detalhes da tarefa recorrente, incluindo seu nome, duração e o padrão mensal que você deseja aplicar.

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

- `DayPosition = 1` significa que a tarefa ocorre no **primeiro dia** do mês.  
- `RepetitionInterval = 2` faz a tarefa repetir **a cada dois meses**.  
- `Start` e `Finish` definem a janela geral durante a qual a recorrência está ativa.

## Etapa 3: Adicionar Parâmetros ao Projeto

Anexe o objeto `RecurringTaskParameters` à coleção de filhos da tarefa raiz. Isso cria efetivamente a tarefa recorrente na hierarquia do projeto.

```csharp
project.RootTask.Children.Add(parameters);
```

## Etapa 4: Salvar o Projeto

Persista as alterações salvando o projeto em um novo arquivo. Você pode escolher qualquer formato suportado; aqui usamos o formato nativo `.mpp`.

```csharp
project.Save(OutDir + "CanAddRecurringTask_Months_EndByRecurrenceRange_Test_out.mpp", SaveFileFormat.Mpp);
```

Depois de executar o código, abra o arquivo resultante no Microsoft Project para ver a tarefa recorrente mensal que você acabou de criar.

## Problemas Comuns e Soluções

| Problema | Causa | Solução |
|----------|-------|---------|
| A tarefa não aparece após salvar | Projeto não atualizado na interface | Reabra o arquivo ou chame `project.UpdateTaskLinks()` antes de salvar. |
| Data de início incorreta | `Start` definido para um fim de semana | Use um `DateTime` que caia em um dia útil ou ajuste o calendário. |
| Intervalo de recorrência ignorado | Usando `ByMonthDayRepetition` com `DayPosition` = 0 | Garanta que `DayPosition` esteja entre 1‑31. |

## Conclusão

Seguindo estas etapas, você agora sabe como **criar cronogramas de tarefa recorrente mensal** com Aspose.Tasks para .NET. A API oferece controle granular sobre intervalos de recorrência, intervalos de início/fim e o padrão de dia específico, permitindo automatizar cenários complexos de planejamento de projetos.

## Perguntas Frequentes

### Q1: O Aspose.Tasks é compatível com todas as versões de arquivos do Microsoft Project?

A1: O Aspose.Tasks suporta várias versões de arquivos do Microsoft Project, incluindo MPP, MPT, XML e MPX.

### Q2: Posso personalizar ainda mais o padrão de recorrência?

A2: Sim, o Aspose.Tasks oferece opções extensas para personalizar padrões de recorrência, incluindo diário, semanal, mensal e anual.

### Q3: Existe uma avaliação gratuita disponível para Aspose.Tasks?

A3: Sim, você pode obter uma avaliação gratuita do Aspose.Tasks no site [here](https://releases.aspose.com/).

### Q4: Como posso obter suporte para Aspose.Tasks?

A4: Você pode buscar assistência e participar de discussões no [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15).

### Q5: Onde posso comprar uma licença para Aspose.Tasks?

A5: Você pode comprar uma licença para Aspose.Tasks no site [here](https://purchase.aspose.com/buy)

## Perguntas Frequentes

**Q: Posso usar este código em uma aplicação .NET Core?**  
A: Absolutamente. Aspose.Tasks for .NET suporta totalmente .NET Core 3.1 e versões posteriores.

**Q: Como altero a recorrência para “último dia útil do mês”?**  
A: Use `ByMonthDayRepetition` com `DayPosition = -1` (valores negativos contam a partir do final do mês) e defina `WeekDay` adequadamente.

**Q: O que acontece se o intervalo de recorrência exceder o calendário do projeto?**  
A: A API respeita o calendário do projeto; ocorrências que caem em dias não úteis são ignoradas ou movidas conforme as configurações do calendário.

**Q: É possível excluir uma ocorrência específica de uma tarefa recorrente?**  
A: Sim. Após adicionar a tarefa recorrente, você pode recuperar ocorrências individuais via `Task.GetOccurrences()` e excluir as que não precisar.

**Q: O Aspose.Tasks lida com diferenças de fuso horário automaticamente?**  
A: A biblioteca armazena datas em UTC; você pode converter para horário local usando os métodos padrão de .NET `DateTime`, se necessário.

---

**Última atualização:** 2026-03-08  
**Testado com:** Aspose.Tasks 24.11 for .NET  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}