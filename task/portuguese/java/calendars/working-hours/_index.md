---
title: Obtenha o horário de trabalho do calendário usando Aspose.Tasks
linktitle: Obtenha o horário de trabalho do calendário usando Aspose.Tasks
second_title: API Java Aspose.Tasks
description: Extraia facilmente horas de trabalho de calendários do MS Project com Aspose.Tasks para Java. Simplifique as tarefas de gerenciamento de projetos.
type: docs
weight: 13
url: /pt/java/calendars/working-hours/
---
## Introdução
Gerenciar calendários de projetos e extrair horas de trabalho é essencial para um gerenciamento de projetos eficaz. Aspose.Tasks for Java fornece funcionalidade robusta para recuperar horas de trabalho dos calendários do MS Project sem esforço. Neste tutorial, iremos guiá-lo através do processo passo a passo.
## Pré-requisitos
Antes de mergulhar no tutorial, certifique-se de ter os seguintes pré-requisitos:
1. Java Development Kit (JDK) instalado em seu sistema.
2.  Biblioteca Aspose.Tasks para Java baixada e adicionada ao seu projeto. Você pode baixá-lo em[aqui](https://releases.aspose.com/tasks/java/).
3. Compreensão básica da linguagem de programação Java.
## Importar pacotes
Primeiro, importe os pacotes necessários para trabalhar com Aspose.Tasks for Java:
```java
import com.aspose.tasks.*;
```
## Etapa 1: carregar o arquivo do projeto
Comece carregando seu arquivo MS Project:
```java
String dataDir = "Your Data Directory";
Project project = new Project(dataDir + "project.mpp");
```
## Etapa 2: recuperar informações de tarefas e calendário
Extraia detalhes de tarefas e calendário do projeto:
```java
Task task = project.getRootTask().getChildren().getById(1);
Calendar taskCalendar = task.get(Tsk.CALENDAR);
```
## Etapa 3: definir datas de início e término
Configure as datas de início e término da tarefa:
```java
java.util.Calendar calStartDate = java.util.Calendar.getInstance();
calStartDate.setTime(task.get(Tsk.START));
java.util.Calendar calEndDate = java.util.Calendar.getInstance();
calEndDate.setTime(task.get(Tsk.FINISH));
```
## Etapa 4: iterar por meio de datas
Itere pelas datas dentro da duração da tarefa:
```java
java.util.Calendar tempDate = calStartDate;
```
## Etapa 5: calcular a duração
Calcule a duração em minutos, horas e dias:
```java
double durationInMins = 0;
double durationInHours = 0;
double durationInDays = 0;
long OneSec = 10000000;
long OneMin = 60 * OneSec;
long OneHour = 60 * OneMin;
long timeSpan;
while (tempDate.before(calEndDate)) {
    if (taskCalendar.isDayWorking(tempDate.getTime())) {
        timeSpan = (long) taskCalendar.getWorkingHours(tempDate.getTime());
        durationInMins += (double) timeSpan / OneMin;
        durationInHours += (double) timeSpan / OneHour;
        if ((timeSpan / OneHour) > 0) {
            durationInDays += ((double) timeSpan / OneHour / 8.0);
        }
    }
    tempDate.add(java.util.Calendar.DATE, 1);
}
System.out.println("Duration in Minutes = " + durationInMins);
System.out.println("Duration in Hours = " + durationInHours);
System.out.println("Duration in Days = " + durationInDays);
System.out.println();
```
## Conclusão
Neste tutorial, abordamos como recuperar horas de trabalho de um calendário do MS Project usando Aspose.Tasks para Java. Seguindo essas etapas, você pode gerenciar cronogramas de projetos com eficiência e calcular durações de tarefas com facilidade.
## Perguntas frequentes
### P: O Aspose.Tasks for Java pode lidar com estruturas de projetos complexas?
R: Sim, Aspose.Tasks for Java fornece suporte abrangente para lidar com estruturas de projetos complexas, incluindo tarefas, recursos e calendários.
### P: O Aspose.Tasks for Java é compatível com diferentes versões do MS Project?
R: Com certeza, Aspose.Tasks for Java oferece suporte a várias versões do MS Project, garantindo compatibilidade em diferentes ambientes.
### P: Posso personalizar horários de trabalho e feriados nos calendários dos projetos?
R: Sim, você pode personalizar facilmente o horário de trabalho e feriados de acordo com os requisitos do seu projeto usando APIs Aspose.Tasks para Java.
### P: O Aspose.Tasks for Java oferece suporte e documentação?
R: Sim, Aspose.Tasks for Java fornece documentação extensa e fóruns de suporte dedicados para ajudar os desenvolvedores a utilizar seus recursos de maneira eficaz.
### P: Existe uma versão de teste disponível para Aspose.Tasks for Java?
 R: Sim, você pode acessar uma versão de avaliação gratuita do Aspose.Tasks for Java em[aqui](https://releases.aspose.com/).