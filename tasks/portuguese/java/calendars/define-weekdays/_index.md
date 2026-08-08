---
date: 2026-08-08
description: Aprenda a definir calendar ms project, definir horas de trabalho diárias
  e adicionar dias de trabalho nos fins de semana usando Aspose.Tasks for Java. Salve
  o projeto como XML em apenas algumas linhas de código.
keywords:
- set calendar ms project
- set daily working hours
- add weekend working days
- java create msproject file
- aspose.tasks calendar
lastmod: 2026-08-08
linktitle: Como definir calendar ms project e especificar dias úteis
og_description: Defina calendar ms project, especifique dias úteis e adicione dias
  de trabalho nos fins de semana usando Aspose.Tasks for Java. Siga este tutorial
  passo a passo e salve como XML.
og_image_alt: Screenshot of Java code configuring MS Project calendar with Aspose.Tasks
og_title: Defina calendar ms project com Aspose.Tasks – guia Java
schemas:
- author: Aspose
  dateModified: '2026-08-08'
  description: Learn how to set calendar ms project, set daily working hours, and
    add weekend working days using Aspose.Tasks for Java. Save the project as XML
    in just a few lines of code.
  headline: How to set calendar ms project and define weekdays
  type: TechArticle
- description: Learn how to set calendar ms project, set daily working hours, and
    add weekend working days using Aspose.Tasks for Java. Save the project as XML
    in just a few lines of code.
  name: How to set calendar ms project and define weekdays
  steps:
  - name: create a project instance
    text: Instantiate a `Project` object, which represents the MS Project file you
      will manipulate.
  - name: define a new calendar
    text: '`Calendar` represents a set of working times, exceptions, and holidays
      for a project.'
  - name: add standard working days (Monday‑Thursday)
    text: '`WeekDay` defines the working time for a specific day of the week.'
  - name: add weekend working days
    text: If your project runs on weekends, add Saturday and Sunday as regular working
      days. This demonstrates **add weekend working days**.
  - name: set a custom short working day (Friday)
    text: Configure Friday with a morning shift (9 am‑12 pm) and an afternoon shift
      (1 pm‑4 pm) to illustrate **set daily working hours** and a custom short workday.
  - name: save the project as XML
    text: '`SaveFileFormat` enumerates the supported file formats when saving a project,
      such as XML or MPP.'
  type: HowTo
- questions:
  - answer: Yes. Set the `DayWorking` property to `false` for any `WeekDay` you want
      to treat as a non‑working day.
    question: Can I define custom non‑working days using Aspose.Tasks for Java?
  - answer: Create `CalendarException` objects, specify the exception dates, and add
      them to `cal.getExceptions()`.
    question: How can I add holidays or company‑wide exceptions?
  - answer: Absolutely. Aspose.Tasks supports MPP, MPT, and XML formats across multiple
      Project versions.
    question: Is the library compatible with older MS Project versions?
  - answer: Load the project with `new Project("existing.mpp")`, retrieve the desired
      calendar, make changes, and save.
    question: Can I modify an existing calendar in an imported project?
  - answer: Yes, you can create and edit recurring tasks using the `RecurringTask`
      class.
    question: Does Aspose.Tasks handle recurring tasks as well?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- set calendar ms project
- aspose.tasks
- java project management
title: Como definir calendar ms project e especificar dias úteis
url: /pt/java/calendars/define-weekdays/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Como definir calendário ms project e definir dias da semana

Neste tutorial você aprenderá **como definir calendário ms project** programaticamente, definir dias da semana e configurar dias úteis personalizados usando a biblioteca Aspose.Tasks para Java. Seja construindo um motor de agendamento, integrando com sistemas ERP ou simplesmente precisando gerar um plano de projeto sem abrir o Microsoft Project, os passos abaixo mostram como criar um calendário, definir horas de trabalho diárias e adicionar dias úteis de fim de semana em poucas linhas de código.

## Respostas rápidas
- **Qual biblioteca é necessária?** Aspose.Tasks for Java.  
- **Posso adicionar dias úteis de fim de semana?** Sim – basta marcar sábado e domingo como dias úteis.  
- **Como salvo o projeto?** Chame `prj.save(..., SaveFileFormat.Xml)`.  
- **É necessária uma licença?** Uma avaliação gratuita funciona para avaliação; uma licença é necessária para uso em produção.  
- **Qual versão do Java é suportada?** Java 8 ou superior.

## O que é definir calendário ms project?
Definir o calendário no MS Project determina quais dias são considerados dias úteis, o número de horas de trabalho em cada dia e quaisquer exceções especiais, como feriados ou paralisações corporativas. Essas informações orientam o agendamento de tarefas, a alocação de recursos e os cronogramas gerais do projeto, garantindo que os cálculos respeitem os padrões reais de trabalho da organização.

## Por que usar Aspose.Tasks para manipulação de calendário?
Aspose.Tasks oferece controle programático sobre calendários sem abrir a interface do Microsoft Project. Ele funciona em qualquer sistema operacional que suporte Java, suporta mais de 50 formatos de entrada e saída e pode processar projetos com centenas de páginas sem carregar o arquivo inteiro na memória, tornando‑o ideal para automação server‑side.

## Pré-requisitos
- **Java Development Kit (JDK) 8+** – download no [Oracle website](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html).  
- **Aspose.Tasks for Java** – obtenha o JAR mais recente na [Aspose.Tasks download page](https://releases.aspose.com/tasks/java/).  
- Um IDE ou ferramenta de build (Maven/Gradle) para adicionar o JAR do Aspose.Tasks ao seu classpath.

## Importar pacotes
Importe as classes que fornecem acesso a projetos, calendários e objetos de tempo de trabalho.

```java
import com.aspose.tasks.*;
import java.util.GregorianCalendar;
```

## Guia passo a passo

### Etapa 1: criar uma instância de projeto
Instancie um objeto `Project`, que representa o arquivo MS Project que você irá manipular.

```java
// The path to the documents directory.
String dataDir = "Your Data Directory";
Project prj = new Project();
```

### Etapa 2: definir um novo calendário
`Calendar` representa um conjunto de horários de trabalho, exceções e feriados para um projeto.  

```java
Calendar cal = prj.getCalendars().add("Calendar1");
```

### Etapa 3: adicionar dias úteis padrão (segunda‑quinta)
`WeekDay` define o horário de trabalho para um dia específico da semana.  

```java
cal.getWeekDays().add(WeekDay.createDefaultWorkingDay(DayType.Monday));
cal.getWeekDays().add(WeekDay.createDefaultWorkingDay(DayType.Tuesday));
cal.getWeekDays().add(WeekDay.createDefaultWorkingDay(DayType.Wednesday));
cal.getWeekDays().add(WeekDay.createDefaultWorkingDay(DayType.Thursday));
```

### Etapa 4: adicionar dias úteis de fim de semana
Se o seu projeto funciona nos fins de semana, adicione sábado e domingo como dias úteis regulares. Isso demonstra **add weekend working days**.

```java
cal.getWeekDays().add(new WeekDay(DayType.Saturday));
cal.getWeekDays().add(new WeekDay(DayType.Sunday));
```

### Etapa 5: definir um dia de trabalho curto personalizado (sexta-feira)
Configure a sexta-feira com um turno matinal (9 h‑12 h) e um turno vespertino (13 h‑16 h) para ilustrar **set daily working hours** e um dia de trabalho curto personalizado.

```java
WeekDay myWeekDay = new WeekDay(DayType.Friday);
WorkingTime wt1 = new WorkingTime(
    new GregorianCalendar(1, java.util.Calendar.JANUARY, 1, 9, 0, 0).getTime(),
    new GregorianCalendar(1, java.util.Calendar.JANUARY, 1, 12, 0, 0).getTime()
);
WorkingTime wt2 = new WorkingTime(
    new GregorianCalendar(1, java.util.Calendar.JANUARY, 1, 13, 0, 0).getTime(),
    new GregorianCalendar(1, java.util.Calendar.JANUARY, 1, 16, 0, 0).getTime()
);
myWeekDay.getWorkingTimes().add(wt1);
myWeekDay.getWorkingTimes().add(wt2);
myWeekDay.setDayWorking(true);
cal.getWeekDays().add(myWeekDay);
```

### Etapa 6: salvar o projeto como XML
`SaveFileFormat` enumera os formatos de arquivo suportados ao salvar um projeto, como XML ou MPP.  

```java
prj.save(dataDir + "project.xml", SaveFileFormat.Xml);
```

## Problemas comuns e soluções
| Problema | Solução |
|----------|---------|
| **Horários de trabalho não aplicados** | Certifique-se de que `setDayWorking(true)` seja chamado em cada `WeekDay` personalizado. |
| **Arquivo não encontrado ao salvar** | Verifique se `dataDir` aponta para uma pasta existente e se a aplicação tem permissão de gravação. |
| **Calendário não refletido nas tarefas** | Atribua o calendário recém‑criado a recursos ou tarefas usando `task.setCalendar(cal)`. |

## Perguntas frequentes

**P: Posso definir dias não úteis personalizados usando Aspose.Tasks para Java?**  
R: Sim. Defina a propriedade `DayWorking` como `false` para qualquer `WeekDay` que você deseja tratar como dia não útil.

**P: Como posso adicionar feriados ou exceções em toda a empresa?**  
R: Crie objetos `CalendarException`, especifique as datas de exceção e adicione-os a `cal.getExceptions()`.

**P: A biblioteca é compatível com versões mais antigas do MS Project?**  
R: Absolutamente. Aspose.Tasks suporta os formatos MPP, MPT e XML em várias versões do Project.

**P: Posso modificar um calendário existente em um projeto importado?**  
R: Carregue o projeto com `new Project("existing.mpp")`, recupere o calendário desejado, faça as alterações e salve.

**P: O Aspose.Tasks também lida com tarefas recorrentes?**  
R: Sim, você pode criar e editar tarefas recorrentes usando a classe `RecurringTask`.

## Conclusão
Agora você sabe **como definir calendário ms project**, definir dias da semana, adicionar dias úteis de fim de semana e configurar um horário curto de sexta-feira — tudo com Aspose.Tasks para Java. Salve o resultado como XML e integre a lógica de calendário em qualquer solução de gerenciamento de projetos baseada em Java.

---

**Last Updated:** 2026-08-08  
**Tested With:** Aspose.Tasks for Java 24.11  
**Author:** Aspose

## Tutoriais Relacionados

- [Add calendar to project with Aspose.Tasks for Java](/tasks/java/calendars/create/)
- [Determine Working Days & Working Hours with Aspose.Tasks](/tasks/java/calendars/working-hours/)
- [Add Holidays to Calendar and Save as MPP with Aspose.Tasks](/tasks/java/calendars/update-to-mpp/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< blocks/products/products-backtop-button >}}

{{< /blocks/products/pf/main-wrap-class >}}