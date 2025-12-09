---
date: 2025-12-02
description: Aprenda como definir o calendário, especificar os dias da semana no MS Project
  e configurar dias úteis personalizados usando Aspose.Tasks para Java. Salve o projeto
  como XML com apenas algumas linhas de código.
linktitle: How to Set Calendar and Define Weekdays in MS Project with Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Como definir calendário e dias da semana no MS Project com Aspose.Tasks
url: /pt/java/calendars/define-weekdays/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Como Definir Calendário e Dias da Semana no MS Project com Aspose.Tasks

## Introdução
Neste tutorial você descobrirá **como definir calendário** programaticamente e definir os dias da semana em um arquivo Microsoft Project usando a biblioteca Aspose.Tasks para Java. Seja para criar uma semana de trabalho padrão, adicionar dias úteis no fim de semana ou configurar um horário curto na sexta‑feira, este guia orienta você em cada passo — da criação do projeto até a gravação do arquivo como XML.

## Respostas Rápidas
- **Qual biblioteca é necessária?** Aspose.Tasks for Java  
- **Posso adicionar dias úteis no fim de semana?** Sim – basta adicionar sábado e domingo como dias úteis.  
- **Como salvo o projeto?** Use `prj.save(..., SaveFileFormat.Xml)`.  
- **Preciso de licença?** Um teste gratuito funciona para avaliação; uma licença é necessária para produção.  
- **Qual versão do Java é necessária?** Java 8 ou superior.

## O que é “como definir calendário” no contexto do MS Project?
Definir um calendário no MS Project significa especificar quais dias são dias úteis, as horas de trabalho diárias e quaisquer exceções, como feriados. Esse calendário orienta o agendamento de tarefas, a alocação de recursos e os cronogramas gerais do projeto.

## Por que usar Aspose.Tasks para manipulação de calendário?
- **Controle total** – criar, modificar ou excluir calendários programaticamente sem abrir a UI.  
- **Multiplataforma** – funciona em qualquer SO que suporte Java.  
- **Suporta todos os formatos de arquivo** – MPP, MPT e XML, para que você possa *salvar projeto como XML* para fácil integração com outros sistemas.  
- **Sem dependências COM** – ao contrário da biblioteca Microsoft Project Interop.

## Pré-requisitos
Antes de começar, certifique‑se de que você tem:

1. **Java Development Kit (JDK) 8+** – faça o download no [Oracle website](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html).  
2. **Aspose.Tasks for Java** – obtenha o JAR mais recente na [Aspose.Tasks download page](https://releases.aspose.com/tasks/java/).  
3. Uma IDE ou ferramenta de build (Maven/Gradle) para adicionar o JAR do Aspose.Tasks ao classpath do seu projeto.

## Importar Pacotes
Primeiro, importe as classes que você precisará. Essas importações dão acesso a objetos de projeto, calendário e tempo de trabalho.

```java
import com.aspose.tasks.*;
import java.util.GregorianCalendar;
```

## Guia Passo a Passo

### Passo 1: Criar uma Instância de Projeto
Crie um novo objeto `Project`. Esse objeto representa o arquivo MS Project que você editará.

```java
// The path to the documents directory.
String dataDir = "Your Data Directory";
Project prj = new Project();
```

### Passo 2: Definir um Novo Calendário
Adicione um calendário novo ao projeto. Dar a ele um nome claro ajuda quando você tem vários calendários.

```java
Calendar cal = prj.getCalendars().add("Calendar1");
```

### Passo 3: Adicionar Dias Úteis Padrão (Segunda‑Quinta)
Use o auxiliar interno `WeekDay.createDefaultWorkingDay` para definir o horário padrão das 9 h às 17 h para a semana de trabalho principal.

```java
cal.getWeekDays().add(WeekDay.createDefaultWorkingDay(DayType.Monday));
cal.getWeekDays().add(WeekDay.createDefaultWorkingDay(DayType.Tuesday));
cal.getWeekDays().add(WeekDay.createDefaultWorkingDay(DayType.Wednesday));
cal.getWeekDays().add(WeekDay.createDefaultWorkingDay(DayType.Thursday));
```

### Passo 4: Adicionar Dias Úteis no Fim de Semana
Se o seu projeto funciona nos fins de semana, basta adicionar sábado e domingo como dias úteis regulares. Isso demonstra **adicionar dias úteis no fim de semana**.

```java
cal.getWeekDays().add(new WeekDay(DayType.Saturday));
cal.getWeekDays().add(new WeekDay(DayType.Sunday));
```

### Passo 5: Definir um Dia Útil Curto Personalizado (Sexta-feira)
Aqui nós **definimos dias úteis personalizados** para sexta‑feira: um turno matutino (9 h‑12 h) e um turno vespertino (13 h‑16 h).

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

### Passo 6: Salvar o Projeto como XML
Finalmente, persista as alterações. A opção `SaveFileFormat.Xml` permite que você **salve projeto como XML**, o que é útil para integração com outras ferramentas.

```java
prj.save(dataDir + "project.xml", SaveFileFormat.Xml);
```

## Problemas Comuns & Soluções
| Problema | Solução |
|----------|---------|
| **Horários de trabalho não aplicados** | Certifique‑se de que `setDayWorking(true)` seja chamado no `WeekDay` personalizado. |
| **Arquivo não encontrado ao salvar** | Verifique se `dataDir` aponta para uma pasta existente e se sua aplicação tem permissão de gravação. |
| **Calendário não refletido nas tarefas** | Atribua o calendário recém‑criado a recursos ou tarefas usando `task.setCalendar(cal)`. |

## Perguntas Frequentes

**Q: Posso definir dias não‑úteis personalizados usando Aspose.Tasks para Java?**  
A: Sim. Defina a propriedade `DayWorking` como `false` para qualquer `WeekDay` que você queira tratar como dia não‑útil.

**Q: Como posso adicionar feriados ou exceções corporativas?**  
A: Crie objetos `CalendarException`, especifique as datas de exceção e adicione‑os a `cal.getExceptions()`.

**Q: A biblioteca é compatível com versões mais antigas do MS Project?**  
A: Absolutamente. Aspose.Tasks suporta formatos MPP, MPT e XML em várias versões do Project.

**Q: Posso modificar um calendário existente em um projeto importado?**  
A: Carregue o projeto com `new Project("existing.mpp")`, recupere o calendário desejado, faça as alterações e salve.

**Q: O Aspose.Tasks também lida com tarefas recorrentes?**  
A: Sim, você pode criar e editar tarefas recorrentes usando a classe `RecurringTask`.

## Conclusão
Agora você sabe **como definir calendário**, **definir dias da semana no MS Project**, adicionar dias úteis no fim de semana e criar um horário curto na sexta‑feira — tudo com Aspose.Tasks para Java. Salve o resultado como XML e integre a lógica de calendário em qualquer solução de gerenciamento de projetos baseada em Java.

---

**Última atualização:** 2025-12-02  
**Testado com:** Aspose.Tasks for Java 24.11  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}