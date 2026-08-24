---
date: 2026-08-24
description: Aprenda como adicionar calendário de feriados, determinar dias úteis
  e calcular a duração da tarefa extraindo horas de trabalho dos calendários do MS
  Project usando Aspose.Tasks for Java.
keywords:
- add holidays calendar
- determine working days
- read ms project
- calculate task duration
- load mpp file
lastmod: 2026-08-24
linktitle: Como adicionar calendário de feriados e determinar dias úteis
og_description: Aprenda como adicionar calendário de feriados, determinar dias úteis
  e calcular a duração da tarefa extraindo horas de trabalho dos calendários do MS
  Project usando Aspose.Tasks for Java.
og_image_alt: Guide to add holidays calendar and calculate task duration with Aspose.Tasks
  Java
og_title: Como adicionar calendário de feriados e determinar dias úteis
schemas:
- author: Aspose
  dateModified: '2026-08-24'
  description: Learn how to add holidays calendar, determine working days and calculate
    task duration by extracting working hours from MS Project calendars using Aspose.Tasks
    for Java.
  headline: How to add holidays calendar and determine working days
  type: TechArticle
- description: Learn how to add holidays calendar, determine working days and calculate
    task duration by extracting working hours from MS Project calendars using Aspose.Tasks
    for Java.
  name: How to add holidays calendar and determine working days
  steps:
  - name: '**Java Development Kit (JDK)** – version 8 or higher.'
    text: '**Java Development Kit (JDK)** – version 8 or higher.'
  - name: '**Aspose.Tasks for Java** – download the latest JAR from [Aspose.Tasks
      for Java releases](https://releases.aspose.com/tasks/java/).'
    text: '**Aspose.Tasks for Java** – download the latest JAR from [Aspose.Tasks
      for Java releases](https://releases.aspose.com/tasks/java/).'
  - name: Basic Java programming knowledge.
    text: Basic Java programming knowledge.
  type: HowTo
- questions:
  - answer: It means identifying which calendar dates are considered work‑days for
      a given task.
    question: What does “determine working days” mean?
  - answer: Aspose.Tasks for Java provides a full‑featured API for working with MS
      Project files.
    question: Which library should I use?
  - answer: Typically 10–15 minutes for a basic extraction.
    question: How long does the implementation take?
  - answer: A free trial is available; a commercial license is required for production
      use.
    question: Do I need a license?
  - answer: Yes – you can modify calendars, add holidays, and set custom work‑time
      ranges.
    question: Can I customize working hours?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- add holidays calendar
- Aspose.Tasks
- Java project scheduling
- MS Project automation
title: Como adicionar calendário de feriados e determinar dias úteis
url: /pt/java/calendars/working-hours/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Como adicionar calendário de feriados e determinar dias úteis

Gerenciar calendários de projetos é uma parte essencial do planejamento bem‑sucedido. Neste tutorial você **adicionará calendário de feriados**, **determinará dias úteis** para qualquer tarefa e **extrairá horas de trabalho** de um calendário do MS Project usando Aspose.Tasks for Java. Ao final do guia você será capaz de **calcular a duração da tarefa**, personalizar horas de trabalho e carregar de forma confiável um **arquivo MPP** para recuperar os dados necessários — tudo sem instalar o Microsoft Project.

## Respostas rápidas
- **O que significa “determinar dias úteis”?** Significa identificar quais datas do calendário são consideradas dias úteis para uma tarefa específica.  
- **Qual biblioteca devo usar?** Aspose.Tasks for Java fornece uma API completa para trabalhar com arquivos MS Project.  
- **Quanto tempo leva a implementação?** Normalmente 10–15 minutos para uma extração básica.  
- **Preciso de licença?** Uma versão de avaliação gratuita está disponível; uma licença comercial é necessária para uso em produção.  
- **Posso personalizar horas de trabalho?** Sim – você pode modificar calendários, adicionar feriados e definir intervalos de horário de trabalho personalizados.  

## O que é “determinar dias úteis”?
**Determinar dias úteis** significa consultar um calendário de projeto para descobrir quais datas estão marcadas como dias úteis versus dias não úteis (fim de semana, feriados ou exceções personalizadas). Essa informação é essencial para **calcular a duração da tarefa** com precisão, pois somente os dias úteis contribuem para o tempo decorrido de uma tarefa.

## Por que usar Aspose.Tasks para recuperar horas de trabalho?
Aspose.Tasks permite ler arquivos MS Project sem precisar do Microsoft Project instalado, possibilitando automação em qualquer plataforma. Também oferece processamento de alto desempenho, amplo suporte a formatos e documentação detalhada.  

- **Suporte total a calendários** – calendários padrão, de recursos e de tarefas são todos acessíveis.  
- **Alto desempenho** – pode processar projetos contendo **mais de 10.000 tarefas em menos de 2 segundos** em uma CPU padrão de 2,5 GHz.  
- **Cobertura extensiva de formatos** – suporta **mais de 50 formatos de entrada e saída**, incluindo MPP, MPX, XML e Primavera.  
- **Documentação abrangente** – exemplos de código, referência de API e fóruns da comunidade estão disponíveis.

## Pré-requisitos
Antes de começar, certifique‑se de que você tem:

1. **Java Development Kit (JDK)** – versão 8 ou superior.  
2. **Aspose.Tasks for Java** – faça o download do JAR mais recente em [Aspose.Tasks for Java releases](https://releases.aspose.com/tasks/java/).  
3. Conhecimento básico de programação Java.  

## Importar pacotes
A classe `Project` é o objeto de nível superior do Aspose.Tasks que representa um único arquivo MS Project na memória. Importe o namespace necessário antes de começar:

Importar Pacotes

```java
import com.aspose.tasks.*;
```

## Como carregar um arquivo MPP com Aspose.Tasks?
A classe `Project` carrega um arquivo MS Project e fornece acesso aos seus dados. Carregue o arquivo do projeto em uma única linha de código; nenhuma interface de usuário ou interop COM é necessária. Esta etapa simples lhe dá acesso total a calendários, tarefas e recursos.

Carregando um arquivo MPP

```java
String dataDir = "Your Data Directory";
Project project = new Project(dataDir + "project.mpp");
```

## Recuperar informações de tarefa e calendário
`Task` representa uma tarefa do projeto, e `Calendar` define suas regras de horário de trabalho. Selecione a tarefa que deseja analisar e obtenha seu calendário associado. O objeto `Task` fornece os métodos `getStart()` e `getFinish()`, enquanto o objeto `Calendar` expõe as definições de horário de trabalho.

Recuperando tarefa e calendário

```java
Task task = project.getRootTask().getChildren().getById(1);
Calendar taskCalendar = task.get(Tsk.CALENDAR);
```

## Definir datas de início e fim
Objetos `Date` especificam a janela de tempo para a análise do calendário. Defina a janela de tempo para a qual você deseja **determinar dias úteis**. Usar as datas de início e fim da tarefa garante que você avalie apenas o período relevante.

Definindo datas

```java
java.util.Calendar calStartDate = java.util.Calendar.getInstance();
calStartDate.setTime(task.get(Tsk.START));
java.util.Calendar calEndDate = java.util.Calendar.getInstance();
calEndDate.setTime(task.get(Tsk.FINISH));
```

## Iterar pelas datas
Um loop `for` pode iterar por cada dia no intervalo de datas. Percorra cada data na duração da tarefa. Este loop permitirá que você **personalize horas de trabalho** posteriormente, se necessário, e é a base para calcular o tempo total de trabalho.

Iterando datas

```java
java.util.Calendar tempDate = calStartDate;
```

## Calcular duração
`Duration` agrega o tempo total de trabalho calculado a partir da iteração. Durante a iteração você verifica se cada dia é um dia útil, soma as horas de trabalho e, finalmente, calcula a duração da tarefa em minutos, horas e dias. Isso demonstra como **calcular dias úteis** e **calcular a duração da tarefa** programaticamente.

Calculando duração

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

## Como personalizar horas de trabalho e feriados
Você pode modificar os intervalos de horário de trabalho do calendário e adicionar exceções como feriados. Use `taskCalendar.addWorkingTime()` para definir novos períodos de trabalho e `taskCalendar.addException()` para inserir um feriado. Isso é útil quando o horário padrão das 9‑às‑5 não corresponde às políticas da sua organização.

## Problemas comuns e soluções
| Problema | Solução |
|----------|----------|
| **A tarefa retorna `null` para o calendário** | Certifique‑se de que a tarefa realmente tem um calendário atribuído; caso contrário, ela herda o calendário padrão do projeto. |
| **Duração incorreta devido a feriados** | Verifique se os feriados estão definidos no calendário da tarefa ou no calendário base do projeto. |
| **Incompatibilidade de fuso horário** | Use `java.util.TimeZone` para alinhar o fuso horário do calendário com o seu sistema, se necessário. |

## Perguntas frequentes
### Q: O Aspose.Tasks for Java pode lidar com estruturas de projeto complexas?
A: Sim, o Aspose.Tasks for Java oferece suporte abrangente para lidar com estruturas de projeto complexas, incluindo tarefas, recursos e calendários.

### Q: O Aspose.Tasks for Java é compatível com diferentes versões do MS Project?
A: Absolutamente, o Aspose.Tasks for Java suporta várias versões do MS Project, garantindo compatibilidade em diferentes ambientes.

### Q: Posso personalizar horas de trabalho e feriados nos calendários do projeto?
A: Sim, você pode personalizar facilmente horas de trabalho e feriados de acordo com os requisitos do seu projeto usando as APIs do Aspose.Tasks for Java.

### Q: O Aspose.Tasks for Java oferece suporte e documentação?
A: Sim, o Aspose.Tasks for Java fornece documentação extensa e fóruns de suporte dedicados para ajudar os desenvolvedores a utilizar seus recursos de forma eficaz.

### Q: Existe uma versão de avaliação disponível para o Aspose.Tasks for Java?
A: Sim, você pode acessar uma versão de avaliação gratuita do Aspose.Tasks for Java na [página de lançamentos da Aspose](https://releases.aspose.com/).

## Conclusão
Neste guia demonstramos como **adicionar calendário de feriados**, **determinar dias úteis**, **recuperar horas de trabalho** e **calcular a duração da tarefa** a partir de um calendário do MS Project usando Aspose.Tasks for Java. Seguindo os passos acima, você pode automatizar a análise de cronogramas, personalizar calendários e manter seus planos de projeto precisos e atualizados. Agora você tem as ferramentas para **ler dados do MS Project**, **carregar um arquivo MPP** e realizar cálculos precisos de duração sem a necessidade do próprio Microsoft Project.

---

**Última atualização:** 2026-08-24  
**Testado com:** Aspose.Tasks for Java 24.12 (latest at time of writing)  
**Autor:** Aspose

## Tutoriais relacionados

- [Adicionar calendário ao projeto com Aspose.Tasks for Java](/tasks/java/calendars/create/)
- [Adicionar feriados ao calendário e salvar como MPP com Aspose.Tasks](/tasks/java/calendars/update-to-mpp/)
- [Criar exceções de calendário personalizadas com Aspose.Tasks for Java](/tasks/java/calendar-exceptions/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}