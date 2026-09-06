---
date: 2026-08-13
description: Aprenda a ler semanas de trabalho de um calendário do MS Project usando
  Aspose.Tasks para Java. Siga o guia passo a passo com exemplos de código e dicas
  de solução de problemas.
keywords:
- how to read workweeks
- Aspose.Tasks Java
- MS Project calendar
lastmod: 2026-08-13
linktitle: Ler Semanas de Trabalho do Calendário com Aspose.Tasks
og_description: Como ler semanas de trabalho de um calendário do MS Project usando
  Aspose.Tasks para Java. Siga o tutorial conciso com etapas de configuração, trechos
  de código e dicas de solução de problemas.
og_image_alt: 'Tutorial: read workweeks from MS Project calendar using Aspose.Tasks
  Java API'
og_title: Como ler semanas de trabalho do calendário MS com Aspose.Tasks
schemas:
- author: Aspose
  dateModified: '2026-08-13'
  description: Learn how to read workweeks from an MS Project calendar using Aspose.Tasks
    for Java. Follow the step‑by‑step guide with code examples and troubleshooting
    tips.
  headline: How to read workweeks from MS calendar with Aspose.Tasks
  type: TechArticle
- description: Learn how to read workweeks from an MS Project calendar using Aspose.Tasks
    for Java. Follow the step‑by‑step guide with code examples and troubleshooting
    tips.
  name: How to read workweeks from MS calendar with Aspose.Tasks
  steps:
  - name: '**Java Development Kit (JDK)** – version 8 or later installed.'
    text: '**Java Development Kit (JDK)** – version 8 or later installed.'
  - name: '**Aspose.Tasks for Java** – download the latest JAR from the official site:
      [Aspose.Tasks for Java download](https://releases.aspose.com/tasks/java/).'
    text: '**Aspose.Tasks for Java** – download the latest JAR from the official site:
      [Aspose.Tasks for Java download](https://releases.aspose.com/tasks/java/).'
  - name: A **sample Project file** (`ReadWorkWeeksInformation.mpp`) placed in a known
      folder on your machine.
    text: A **sample Project file** (`ReadWorkWeeksInformation.mpp`) placed in a known
      folder on your machine.
  type: HowTo
- questions:
  - answer: Yes. The API provides `addWorkWeek()`, `removeWorkWeek()`, and property
      setters to change names, dates, and working times.
    question: Can I modify the work weeks information using Aspose.Tasks for Java?
  - answer: Absolutely. It supports MPP files from Project 98 up to the latest releases,
      as well as Project XML files.
    question: Is Aspose.Tasks compatible with different versions of Microsoft Project
      files?
  - answer: Yes. The library is pure Java, so you can use it alongside Spring, Jakarta
      EE, or any other framework.
    question: Can I integrate Aspose.Tasks with other Java frameworks?
  - answer: 'Yes, you can download a free 30‑day trial from the official site: [Aspose.Tasks
      trial](https://releases.aspose.com/).'
    question: Is there a trial version available for Aspose.Tasks?
  - answer: 'The Aspose community forum is the best place: [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15).'
    question: Where can I find support for Aspose.Tasks?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- read workweeks
- Aspose.Tasks
- Java project scheduling
- MS Project
- calendar API
title: Como ler semanas de trabalho do calendário MS com Aspose.Tasks
url: /pt/java/calendars/read-work-weeks/
weight: 15
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Como ler semanas de trabalho do calendário MS com Aspose.Tasks

## Introdução
Neste tutorial você **aprenderá como ler semanas de trabalho** de um calendário do Microsoft Project usando a biblioteca Aspose.Tasks para Java. Seja construindo um painel de relatórios, sincronizando cronogramas com um sistema ERP ou automatizando a extração de dados para análises, o acesso programático às definições de semanas de trabalho economiza inúmeras horas manuais. Aspose.Tasks suporta **mais de 50 formatos de entrada e saída** e pode processar arquivos de projeto com centenas de páginas sem carregar todo o arquivo na memória, oferecendo tanto flexibilidade quanto desempenho.

## Respostas rápidas
- **O que significa “ler semanas de trabalho”?** Refere‑se à extração das definições de semanas de trabalho (datas e regras diárias de horário) de um arquivo Project via código Java.  
- **Qual biblioteca é necessária?** Aspose.Tasks para Java (versão de avaliação gratuita disponível).  
- **Preciso de licença para desenvolvimento?** A avaliação funciona para testes; uma licença comercial é necessária para implantações em produção.  
- **Quais formatos de arquivo são suportados?** Tanto arquivos *.mpp* quanto arquivos Project XML são manipulados, além de mais de 50 outros formatos para importação/exportação.  
- **Quanto tempo leva a implementação?** Normalmente menos de 10 minutos após a configuração da biblioteca.

## O que é uma semana de trabalho no MS Project?
Uma semana de trabalho define as regras de calendário que determinam quando os recursos estão disponíveis durante um período específico. Ela inclui uma data de início, uma data de término e intervalos diários de horário de trabalho (por exemplo, das 9 h às 17 h). No MS Project, cada calendário pode conter várias semanas de trabalho, permitindo modelar feriados, turnos ou cronogramas sazonais.

## Como o Aspose.Tasks lê semanas de trabalho de um calendário?
Aspose.Tasks expõe a `WorkWeekCollection` de um objeto `Calendar`. Ao criar uma instância de `Project`, selecionar o calendário desejado (por UID ou nome) e iterar sobre sua `WorkWeekCollection`, você pode obter o rótulo de cada semana de trabalho, o intervalo de datas efetivo e os intervalos diários detalhados de horário. A API trata todas as conversões de data/hora e respeita automaticamente as configurações de fuso horário do projeto.

## Por que ler semanas de trabalho em Java de um calendário do Microsoft Project?
Ler semanas de trabalho programaticamente elimina a cópia e colagem manual, garante que sistemas downstream (ERP, RH, relatórios) utilizem exatamente as mesmas regras de agendamento e assegura consistência entre múltiplos projetos. A automação também reduz erros humanos e acelera pipelines de integração, especialmente quando é necessário processar dezenas de arquivos de projeto todas as noites.

## Pré-requisitos
Antes de mergulharmos no código, certifique‑se de que você tem:

1. **Java Development Kit (JDK)** – versão 8 ou superior instalada.  
2. **Aspose.Tasks para Java** – baixe o JAR mais recente no site oficial: [Aspose.Tasks for Java download](https://releases.aspose.com/tasks/java/).  
3. Um **arquivo de Projeto de exemplo** (`ReadWorkWeeksInformation.mpp`) colocado em uma pasta conhecida na sua máquina.

## Importar pacotes
Primeiro, importe as classes que precisaremos para interagir com calendários e semanas de trabalho:

`Project` representa um arquivo Microsoft Project, `Calendar` fornece seus calendários, `WorkWeek` define uma semana de trabalho e `WeekDay` representa um dia.

```java
import com.aspose.tasks.Calendar;
import com.aspose.tasks.Project;
import com.aspose.tasks.WeekDay;
import com.aspose.tasks.WeekDayCollection;
import com.aspose.tasks.WorkWeek;
import com.aspose.tasks.WorkWeekCollection;
import com.aspose.tasks.WorkingTimeCollection;
```

## Etapa 1: configurar seu diretório de dados
Defina a pasta que contém o arquivo `.mpp`. Substitua o placeholder pelo caminho real na sua máquina:

```java
String dataDir = "Your Data Directory";
```

## Etapa 2: criar uma instância de Project e acessar o calendário
A classe `Project` representa um arquivo Microsoft Project e fornece acesso às suas estruturas de dados, incluindo calendários, tarefas e recursos.  
Instancie um objeto `Project`, escolha o calendário desejado (por UID) e obtenha sua `WorkWeekCollection`:

```java
Project project = new Project(dataDir + "ReadWorkWeeksInformation.mpp");
Calendar calendar = project.getCalendars().getByUid(3);
WorkWeekCollection collection = calendar.getWorkWeeks();
```

> **Dica profissional:** Se você não tem certeza do UID do calendário, itere através de `project.getCalendars()` e imprima primeiro o nome e o UID de cada calendário.

## Etapa 3: iterar pelas semanas de trabalho
A classe `WorkWeek` encapsula a definição de uma semana de trabalho, contendo datas de início/término e configurações diárias de horário.  
Percorra cada `WorkWeek` para exibir seu nome, datas de início/término e os horários de trabalho diários:

```java
for (WorkWeek workWeek : collection) {
    // Display work week name, from and to dates
    System.out.println(workWeek.getName());
    System.out.println(workWeek.getFromDate());
    System.out.println(workWeek.getToDate());
    // Access week days and working times
    WeekDayCollection weekDays = workWeek.getWeekDays();
    for (WeekDay day : weekDays) {
        WorkingTimeCollection workingTimes = day.getWorkingTimes();
        // Further process working times if needed
    }
}
```

**O que você verá:** O console imprime o rótulo de cada semana de trabalho (por exemplo, “Standard”), seu intervalo de datas efetivo, e você pode detalhar as horas exatas de trabalho para cada dia.

## Problemas comuns e soluções
| Problema | Motivo | Solução |
|----------|--------|---------|
| `NullPointerException` ao acessar `calendar` | UID errado ou calendário não existe | Verifique o UID com `project.getCalendars().size()` e liste os calendários disponíveis primeiro. |
| Nenhuma saída para semanas de trabalho | O calendário selecionado não tem semanas de trabalho personalizadas (usa o padrão) | Use o calendário padrão (`project.getDefaultCalendar()`) ou crie uma semana de trabalho programaticamente. |
| Formato de data parece estranho | `System.out.println` usa o formato padrão de `java.util.Date` | Aplique um `SimpleDateFormat` para formatar as datas conforme necessário. |

## Perguntas frequentes
**Q: Posso modificar as informações das semanas de trabalho usando Aspose.Tasks para Java?**  
A: Sim. A API fornece `addWorkWeek()`, `removeWorkWeek()` e setters de propriedades para alterar nomes, datas e horários de trabalho.

**Q: O Aspose.Tasks é compatível com diferentes versões de arquivos Microsoft Project?**  
A: Absolutamente. Ele suporta arquivos MPP do Project 98 até as versões mais recentes, bem como arquivos Project XML.

**Q: Posso integrar o Aspose.Tasks com outros frameworks Java?**  
A: Sim. A biblioteca é pura Java, portanto pode ser usada junto com Spring, Jakarta EE ou qualquer outro framework.

**Q: Existe uma versão de avaliação disponível para o Aspose.Tasks?**  
A: Sim, você pode baixar uma avaliação gratuita de 30 dias no site oficial: [Aspose.Tasks trial](https://releases.aspose.com/).

**Q: Onde posso encontrar suporte para o Aspose.Tasks?**  
A: O fórum da comunidade Aspose é o melhor lugar: [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15).

---

**Última atualização:** 2026-08-13  
**Testado com:** Aspose.Tasks for Java 24.12 (mais recente no momento da escrita)  
**Autor:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Tutoriais Relacionados

- [Adicionar calendário ao projeto com Aspose.Tasks para Java](/tasks/java/calendars/create/)
- [Recuperar exceções de calendário com Aspose.Tasks – tutorial java asp tasks](/tasks/java/calendar-exceptions/retrieve/)
- [Como definir calendário e dias da semana no MS Project com Aspose.Tasks](/tasks/java/calendars/define-weekdays/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}