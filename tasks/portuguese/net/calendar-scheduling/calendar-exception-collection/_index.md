---
date: 2026-04-09
description: Aprenda a definir o calendário padrão e gerenciar os feriados do projeto
  em seus projetos .NET usando o Aspose.Tasks para um agendamento preciso.
keywords:
- set standard calendar
- manage project holidays
- load project calendar
linktitle: Definir Calendário Padrão e Tratar Exceções no Aspose.Tasks
second_title: Aspose.Tasks .NET API
title: Definir Calendário Padrão e Tratar Exceções no Aspose.Tasks
url: /pt/net/calendar-scheduling/calendar-exception-collection/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Definir Calendário Padrão e Manipular Exceções no Aspose.Tasks

## Introdução

O agendamento preciso é a espinha dorsal de qualquer projeto bem-sucedido, e planos do mundo real frequentemente precisam se desviar do calendário de trabalho padrão devido a feriados, eventos especiais ou paralisações inesperadas. Aspose.Tasks para .NET facilita a configuração de **set standard calendar** e, em seguida, a sobreposição de exceções personalizadas. Neste tutorial, você aprenderá como carregar um calendário de projeto, definir um calendário padrão e gerenciar feriados do projeto através do recurso Calendar Exception Collection.

## Respostas Rápidas
- **O que faz “set standard calendar”?** Ele redefine um calendário para o horário de trabalho padrão (9 AM‑5 PM, segunda‑sexta) antes de você adicionar exceções personalizadas.  
- **Qual método limpa exceções existentes?** `Calendar.Exceptions.Clear()` remove todas as exceções definidas anteriormente.  
- **Como posso adicionar um feriado?** Crie um `CalendarException` com `DayWorking = false` e adicione-o à coleção.  
- **Preciso recarregar o projeto após as alterações?** Não, as alterações são aplicadas diretamente ao objeto `Project` em memória.  
- **Quais bibliotecas são necessárias?** Aspose.Tasks para .NET (qualquer versão .NET suportada) e namespaces `System`.

## Pré-requisitos

Antes de mergulhar no código, certifique-se de que você tem:

1. **Aspose.Tasks for .NET** – faça o download [aqui](https://releases.aspose.com/tasks/net/).  
2. Conhecimento básico de **C#** – você escreverá alguns trechos curtos.  
3. Um ambiente de desenvolvimento como **Visual Studio** ou **JetBrains Rider**.

## Importar Namespaces

Essas diretivas `using` dão acesso às classes necessárias para a manipulação de calendários.

```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;
```

## O que é uma Exceção de Calendário?

Uma *exceção de calendário* representa um período em que o horário de trabalho normal é alterado – por exemplo, um feriado em toda a empresa ou um cronograma temporário de horas extras. Ao adicionar exceções a um calendário, você pode modelar restrições do mundo real sem mudar o calendário base.

## Como Definir Calendário Padrão no Aspose.Tasks

O primeiro passo é carregar seu arquivo de projeto e recuperar o calendário com o qual deseja trabalhar.

```csharp
var project = new Project(DataDir + "project_update_test.mpp");
var calendar = project.Calendars.GetByUid(3);
```

### Etapa 1: Limpar Exceções Existentes e Redefinir para um Calendário Padrão

Antes de adicionar novas regras, é uma boa prática limpar quaisquer exceções antigas e as configurações de **set standard calendar**. Isso garante uma base limpa.

```csharp
calendar.Exceptions.Clear();
Calendar.MakeStandardCalendar(calendar);
```

### Etapa 2: Definir uma Exceção de Horário de Trabalho

Às vezes, você precisa criar um cronograma temporário (por exemplo, horas estendidas para o lançamento de um produto). O trecho a seguir define uma exceção de horário de trabalho que abrange vários dias e inclui dois períodos de trabalho diários.

```csharp
var exception = new CalendarException();
exception.FromDate = new DateTime(2020, 3, 30, 8, 0, 0);
exception.ToDate = new DateTime(2020, 4, 3, 17, 0, 0);
exception.DayWorking = true;
exception.Name = "Exception 1";

var wt1 = new WorkingTime(9, 13);
var wt2 = new WorkingTime(14, 19);

exception.WorkingTimes.Add(wt1);
exception.WorkingTimes.Add(wt2);
calendar.Exceptions.Add(exception);
```

### Etapa 3: Adicionar Exceções de Tempo Não‑Trabalhado (Feriados)

Para **manage project holidays**, crie exceções onde `DayWorking` é `false`. O exemplo abaixo adiciona um bloco de feriado de dois dias.

```csharp
var nonWorkingExceptions = new CalendarException[2];
nonWorkingExceptions[0] = new CalendarException();
nonWorkingExceptions[0].FromDate = new DateTime(2020, 4, 13, 8, 0, 0);
nonWorkingExceptions[0].ToDate = new DateTime(2020, 4, 18, 17, 0, 0);
nonWorkingExceptions[0].DayWorking = false;
nonWorkingExceptions[0].Name = "Exception 2";

// Add more exceptions if needed

calendar.Exceptions.AddRange(nonWorkingExceptions);
```

### Etapa 4: Exibir Exceções de Calendário (Verificação)

Depois de adicionar exceções, você frequentemente desejará verificar se elas foram registradas corretamente. O loop a seguir imprime os detalhes de cada exceção no console.

```csharp
Console.WriteLine("Exceptions of calendar {0}: ", calendar.Exceptions.ParentCalendar.Name);
Console.WriteLine("Exceptions count: {0}", calendar.Exceptions.Count);
Console.WriteLine();
foreach (var calendarException in calendar.Exceptions)
{
    Console.WriteLine("Name: " + calendarException.Name);
    Console.WriteLine("From Date: " + calendarException.FromDate);
    Console.WriteLine("To Date: " + calendarException.ToDate);
    Console.WriteLine("Is day working: " + calendarException.DayWorking);
    Console.WriteLine();
}
```

### Etapa 5: Remover Todas as Exceções (Limpeza)

Se precisar reverter o calendário ao seu estado original, você pode remover todas as exceções programaticamente.

```csharp
Console.WriteLine("Remove calendar exceptions...");
List<CalendarException> exceptions = calendar.Exceptions.ToList();
foreach (var calendarException in exceptions)
{
    calendar.Exceptions.Remove(calendarException);
}
```

## Problemas Comuns e Soluções

| Problema | Razão | Correção |
|----------|-------|----------|
| Exceções não aparecem após salvar | Projeto não salvo após modificações | Chame `project.Save("output.mpp")` após fazer alterações. |
| Exceções sobrepostas causam horas de trabalho inesperadas | Aspose.Tasks usa a última exceção adicionada para períodos sobrepostos | Ordene suas chamadas `Add` cuidadosamente ou ajuste as prioridades manualmente. |
| `MakeStandardCalendar` redefine horários de trabalho personalizados | Ele limpa intencionalmente os horários personalizados; adicione-os novamente após a chamada, se necessário. | Adicione seus objetos `WorkingTime` personalizados após invocar `MakeStandardCalendar`. |

## Perguntas Frequentes

**Q:** Posso adicionar várias exceções a um único calendário?  
**A:** Sim, você pode adicionar várias exceções a um calendário usando o método `AddRange`.

**Q:** Como lidar com exceções recorrentes, como feriados semanais?  
**A:** Você pode calcular programaticamente exceções recorrentes e adicioná-las ao calendário usando lógica personalizada.

**Q:** É possível importar exceções de calendário de fontes externas?  
**A:** Sim, você pode ler exceções de calendário de fontes externas como bancos de dados ou arquivos CSV e integrá-las ao seu projeto.

**Q:** O que acontece se houver exceções sobrepostas no calendário?  
**A:** Aspose.Tasks para .NET permite que você trate exceções sobrepostas definindo prioridades ou resolvendo conflitos com base nos requisitos do seu projeto.

**Q:** Posso personalizar os horários de trabalho para cada dia dentro de uma exceção?  
**A:** Sim, você pode especificar horários de trabalho personalizados para dias individuais dentro de uma exceção para atender a necessidades específicas de agendamento.

## Conclusão

Ao **setting a standard calendar** primeiro e depois sobrepor exceções personalizadas, você obtém controle total sobre o agendamento do projeto, facilitando **manage project holidays** e quaisquer outras linhas de tempo especiais. A Calendar Exception Collection no Aspose.Tasks fornece uma maneira limpa e programática de modelar calendários do mundo real diretamente em suas aplicações .NET.

---

**Última atualização:** 2026-04-09  
**Testado com:** Aspose.Tasks 24.12 for .NET  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}