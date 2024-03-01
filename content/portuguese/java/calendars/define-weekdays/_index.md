---
title: Defina dias da semana no calendário com Aspose.Tasks
linktitle: Defina dias da semana no calendário com Aspose.Tasks
second_title: API Java Aspose.Tasks
description: Aprenda como definir dias da semana no MS Project Calendar usando Aspose.Tasks for Java. Personalize dias e horários úteis sem esforço.
type: docs
weight: 12
url: /pt/java/calendars/define-weekdays/
---
## Introdução
Neste tutorial, percorreremos o processo de definição de dias da semana em um calendário do MS Project usando Aspose.Tasks para Java. Aspose.Tasks é uma biblioteca Java poderosa que permite aos desenvolvedores manipular arquivos do Microsoft Project programaticamente.
## Pré-requisitos
Antes de começarmos, certifique-se de ter os seguintes pré-requisitos em vigor:
1.  Java Development Kit (JDK): Certifique-se de ter o JDK instalado em seu sistema. Você pode baixá-lo no[Site da Oracle](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html) se você ainda não o fez.
2.  Biblioteca Aspose.Tasks for Java: Baixe e instale a biblioteca Aspose.Tasks for Java do[página de download](https://releases.aspose.com/tasks/java/). Siga as instruções de instalação fornecidas na documentação.

## Importar pacotes
Para começar, importe os pacotes necessários para trabalhar com Aspose.Tasks em seu projeto Java:
```java
import com.aspose.tasks.*;
import java.util.GregorianCalendar;
```
## Etapa 1: criar uma instância de projeto
Instancie um objeto Project, que representa o arquivo MS Project com o qual você trabalhará:
```java
// O caminho para o diretório de documentos.
String dataDir = "Your Data Directory";
Project prj = new Project();
```
## Etapa 2: definir calendário
Crie uma nova instância de calendário e adicione-a ao projeto:
```java
Calendar cal = prj.getCalendars().add("Calendar1");
```
## Etapa 3: adicionar dias úteis
Defina os dias úteis adicionando segunda a quinta com horários padrão:
```java
cal.getWeekDays().add(WeekDay.createDefaultWorkingDay(DayType.Monday));
cal.getWeekDays().add(WeekDay.createDefaultWorkingDay(DayType.Tuesday));
cal.getWeekDays().add(WeekDay.createDefaultWorkingDay(DayType.Wednesday));
cal.getWeekDays().add(WeekDay.createDefaultWorkingDay(DayType.Thursday));
```
## Etapa 4: definir um dia útil personalizado
Defina sábado e domingo como dias úteis:
```java
cal.getWeekDays().add(new WeekDay(DayType.Saturday));
cal.getWeekDays().add(new WeekDay(DayType.Sunday));
```
## Etapa 5: definir um dia útil curto
Defina sexta-feira como um dia útil curto com horários de trabalho personalizados:
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
## Etapa 6: salve o projeto
Salve o projeto modificado em um arquivo XML:
```java
prj.save(dataDir + "project.xml", SaveFileFormat.Xml);
```

## Conclusão
Parabéns! Você definiu com sucesso os dias da semana em um calendário do MS Project usando Aspose.Tasks para Java. Agora você pode integrar essa funcionalidade em seus aplicativos Java para manipular arquivos do MS Project programaticamente.
## Perguntas frequentes
### Q1: Posso definir dias não úteis personalizados usando Aspose.Tasks for Java?
 R: Sim, você pode definir dias não úteis personalizados definindo o`DayWorking` propriedade para`false` para o respectivo dia da semana.
### P2: Como posso adicionar feriados ao calendário?
 R: Você pode adicionar feriados criando instâncias de`CalendarExceptions` especificando as datas não úteis.
### Q3: O Aspose.Tasks é compatível com diferentes versões de arquivos do MS Project?
R: Sim, Aspose.Tasks suporta várias versões de arquivos MS Project, incluindo formatos MPP, MPT e XML.
### Q4: Posso modificar calendários existentes em um arquivo do MS Project?
R: Sim, você pode carregar um projeto existente com calendários, fazer modificações e salvar as alterações novamente no arquivo original.
### P5: O Aspose.Tasks fornece suporte para tarefas recorrentes?
R: Sim, Aspose.Tasks permite que você trabalhe com tarefas recorrentes, incluindo a definição de seus padrões e durações de recorrência.