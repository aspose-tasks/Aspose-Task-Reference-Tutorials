---
date: 2026-08-13
description: Aprenda como adicionar feriados a um calendário, atribuir o calendário
  a um projeto e salvar o arquivo MS Project como MPP usando Aspose.Tasks para Java.
keywords:
- add holidays to calendar
- assign calendar to project
- create ms project calendar
- automate schedule generation
- convert project to mpp
lastmod: 2026-08-13
linktitle: Atualizar calendário para formato MPP no Aspose.Tasks
og_description: Adicione feriados ao calendário, atribua-o a um projeto e converta
  o cronograma para MPP usando Aspose.Tasks para Java. Aprenda a automação passo a
  passo.
og_image_alt: Guide showing Java code that adds holidays to a calendar and saves as
  MPP with Aspose.Tasks
og_title: Adicionar feriados ao calendário e salvar como MPP com Aspose.Tasks
schemas:
- author: Aspose
  dateModified: '2026-08-13'
  description: Learn how to add holidays to a calendar, assign the calendar to a project,
    and save the MS Project file as MPP using Aspose.Tasks for Java.
  headline: Add holidays to calendar and save as MPP with Aspose.Tasks
  type: TechArticle
- description: Learn how to add holidays to a calendar, assign the calendar to a project,
    and save the MS Project file as MPP using Aspose.Tasks for Java.
  name: Add holidays to calendar and save as MPP with Aspose.Tasks
  steps:
  - name: import required packages
    text: First, bring the Aspose.Tasks classes and Java utilities into scope.
  - name: set up the data directory
    text: Define where your input template and output files will live. Replace the
      placeholder with the actual path on your machine.
  - name: define input and output file names
    text: We’ll load an existing MPP file (or a blank project) and write the result
      to a new file.
  - name: load the project and add a new calendar
    text: '`Project` class represents an MS Project file in memory and provides access
      to its calendars, tasks, and resources. Create a `Project` instance from the
      source file and add a calendar named **“Calendar 1”**.'
  - name: customize the calendar (optional)
    text: '`Calendar` object defines working days, hours, and exceptions for a project
      schedule. If you need specific working times, holidays, or exceptions, call
      your own helper method. The sample uses `GetTestCalendar` as a placeholder.
      > **Pro tip:** You can directly manipulate `cal1.getWeekDays()` to set w'
  - name: assign the calendar to the project
    text: Tell the project to use the newly created calendar for all its scheduling
      calculations.
  - name: save the project as MPP
    text: '`SaveFileFormat` enumeration specifies the output format, with `Mpp` indicating
      native Microsoft Project format. Now **convert project to MPP** by saving it
      with the `SaveFileFormat.Mpp` option.'
  - name: confirm successful completion
    text: A simple console message lets you know the process finished without errors.
  type: HowTo
- questions:
  - answer: Yes, Aspose.Tasks supports all Microsoft Project file formats from Project
      2007 through Project 2024, covering more than 10 versions.
    question: Is Aspose.Tasks for Java compatible with different versions of MS Project?
  - answer: Absolutely. You can define working days, set custom work weeks, add holidays,
      and even create multiple calendars within a single project file.
    question: Can I customize calendars according to specific project requirements?
  - answer: Yes, you can get help from the Aspose.Tasks community forum [Aspose.Tasks
      community forum](https://forum.aspose.com/c/tasks/15).
    question: Does Aspose.Tasks for Java offer support for troubleshooting and assistance?
  - answer: Yes, a fully functional free trial is available [Aspose.Tasks free trial](https://releases.aspose.com/).
    question: Is there a free trial available for Aspose.Tasks for Java?
  - answer: Temporary licenses can be requested via the Aspose website [Aspose temporary
      license request](https://purchase.aspose.com/temporary-license/).
    question: How can I obtain a temporary license for Aspose.Tasks for Java?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- add holidays
- Aspose.Tasks
- Java project scheduling
title: Adicionar feriados ao calendário e salvar como MPP com Aspose.Tasks
url: /pt/java/calendars/update-to-mpp/
weight: 16
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Adicionar feriados ao calendário e salvar como MPP com Aspose.Tasks

## Introdução

Na gestão moderna de projetos, você frequentemente precisa **adicionar feriados ao calendário** de arquivos, criar um **calendário MS Project** e, em seguida, compartilhar o cronograma no formato nativo MPP. Seja consolidando cronogramas de múltiplas fontes ou migrando dados legados, gerar um calendário programaticamente elimina erros manuais e acelera a entrega. Este tutorial orienta você por todo o processo de criação de um calendário no MS Project, personalizando-o com feriados, **atribuir calendário ao projeto**, e finalmente **converter projeto para MPP** usando a API Aspose.Tasks Java.

## Respostas Rápidas
- **O que este tutorial cobre?** Adicionar feriados a um calendário, atribuí‑lo a um projeto e salvar o resultado como um arquivo MPP com Aspose.Tasks para Java.  
- **Preciso de uma licença?** Um teste gratuito funciona para desenvolvimento; uma licença comercial é necessária para produção.  
- **Qual versão do Java é necessária?** Java 8 ou superior (JDK 8+).  
- **Posso personalizar o calendário?** Sim – você pode adicionar horários de trabalho, exceções e feriados.  
- **Quanto tempo leva a implementação?** Cerca de 10‑15 minutos para um calendário básico.  

## O que é “criar calendário MS Project”?

Criar um calendário MS Project significa definir os dias úteis, horas e exceções que orientam o agendamento de tarefas dentro de um arquivo Microsoft Project. Usando Aspose.Tasks, você pode construir esse calendário programaticamente, definir feriados e incorporá‑lo a um projeto sem abrir a interface do MS Project.

## Por que usar Aspose.Tasks para esta tarefa?

Você deve usar Aspose.Tasks porque ele oferece compatibilidade total com Java, não requer Microsoft Office e permite gerar e salvar arquivos MPP nativos diretamente a partir do código. A biblioteca suporta todos os recursos de calendário, funciona em qualquer ambiente de servidor e processa projetos com até 10 000 tarefas em menos de um segundo.

## Pré-requisitos

1. **Java Development Kit (JDK) 8+** – certifique‑se de que `java -version` exiba 1.8 ou superior.  
2. **Aspose.Tasks for Java** – faça o download do JAR mais recente no [site da Aspose](https://releases.aspose.com/tasks/java/).  
3. **IDE** – IntelliJ IDEA, Eclipse ou qualquer editor de sua preferência.  
4. **Conhecimento básico de Java** – familiaridade com classes, métodos e I/O de arquivos.

## Como adicionar feriados ao calendário

Para adicionar feriados, você cria um novo objeto `Calendar`, obtém sua coleção `Exceptions` e adiciona entradas `DateException` para cada data de feriado. `DateException` representa uma data ou intervalo não‑útil em um calendário. O Aspose.Tasks então trata essas datas como dias não‑úteis, garantindo que as tarefas sejam agendadas ao redor dos feriados definidos.

### Etapa 1: importar pacotes necessários

Primeiro, traga as classes Aspose.Tasks e as utilidades Java para o escopo.

```java
import com.aspose.tasks.*;

import java.util.Date;
import java.util.GregorianCalendar;
```

### Etapa 2: configurar o diretório de dados

Defina onde seus arquivos de modelo de entrada e saída ficarão. Substitua o placeholder pelo caminho real na sua máquina.

```java
String dataDir = "Your Data Directory";
```

### Etapa 3: definir nomes de arquivos de entrada e saída

Carregaremos um arquivo MPP existente (ou um projeto em branco) e gravaremos o resultado em um novo arquivo.

```java
String resultFile = "OutputMpp.mpp";
String newFile = "SampleMpp.mpp";
```

### Etapa 4: carregar o projeto e adicionar um novo calendário

A classe `Project` representa um arquivo MS Project na memória e fornece acesso aos seus calendários, tarefas e recursos.

Crie uma instância `Project` a partir do arquivo fonte e adicione um calendário chamado **“Calendar 1”**.

```java
Project project = new Project(dataDir + newFile);
Calendar cal1 = project.getCalendars().add("Calendar 1");
```

### Etapa 5: personalizar o calendário (opcional)

O objeto `Calendar` define dias úteis, horas e exceções para o cronograma de um projeto.

Se precisar de horários de trabalho específicos, feriados ou exceções, chame seu próprio método auxiliar. O exemplo usa `GetTestCalendar` como placeholder.

```java
GetTestCalendar(cal1); // Additional method for customizing calendar if required
```

> **Dica profissional:** Você pode manipular diretamente `cal1.getWeekDays()` para definir horas de trabalho para cada dia da semana, ou usar `cal1.getExceptions()` para **adicionar feriados ao calendário**.

### Etapa 6: atribuir o calendário ao projeto

Informe ao projeto para usar o calendário recém‑criado em todos os seus cálculos de agendamento.

```java
project.set(Prj.CALENDAR, cal1);
```

### Etapa 7: salvar o projeto como MPP

A enumeração `SaveFileFormat` especifica o formato de saída, sendo `Mpp` o formato nativo do Microsoft Project.

Agora **converta o projeto para MPP** salvando-o com a opção `SaveFileFormat.Mpp`.

```java
project.save(dataDir + resultFile, SaveFileFormat.Mpp);
```

### Etapa 8: confirmar a conclusão bem‑sucedida

Uma mensagem simples no console indica que o processo terminou sem erros.

```java
System.out.println("Process completed Successfully");
```

## Casos de uso comuns

- **Geração automatizada de cronogramas** para projetos recorrentes (por exemplo, sprints semanais).  
- **Migração de calendários legados CSV ou Excel** para um arquivo MS Project totalmente funcional.  
- **Relatórios do lado do servidor** onde um serviço web devolve um arquivo MPP sob demanda.  

## Solução de problemas e armadilhas comuns

| Problema | Causa | Correção |
|----------|-------|----------|
| `NullPointerException` ao `project.save` | `dataDir` aponta para uma pasta inexistente | Certifique‑se de que o diretório exista ou crie‑o programaticamente. |
| Calendário não aplicado às tarefas | As tarefas ainda referenciam o calendário padrão | Após definir `Prj.CALENDAR`, também atualize `Task.CALENDAR` de cada tarefa se elas foram sobrescritas anteriormente. |
| Arquivo de saída tem 0 KB | Permissões de gravação ausentes | Execute a JVM com permissões de sistema de arquivos adequadas ou escolha um caminho gravável. |

## Perguntas frequentes

**Q: O Aspose.Tasks para Java é compatível com diferentes versões do MS Project?**  
A: Sim, o Aspose.Tasks suporta todos os formatos de arquivo do Microsoft Project desde o Project 2007 até o Project 2024, abrangendo mais de 10 versões.

**Q: Posso personalizar calendários de acordo com requisitos específicos do projeto?**  
A: Absolutamente. Você pode definir dias úteis, definir semanas de trabalho personalizadas, adicionar feriados e até criar múltiplos calendários dentro de um único arquivo de projeto.

**Q: O Aspose.Tasks para Java oferece suporte para solução de problemas e assistência?**  
A: Sim, você pode obter ajuda no fórum da comunidade Aspose.Tasks [fórum da comunidade Aspose.Tasks](https://forum.aspose.com/c/tasks/15).

**Q: Existe um teste gratuito disponível para Aspose.Tasks para Java?**  
A: Sim, um teste gratuito totalmente funcional está disponível [teste gratuito do Aspose.Tasks](https://releases.aspose.com/).

**Q: Como posso obter uma licença temporária para Aspose.Tasks para Java?**  
A: Licenças temporárias podem ser solicitadas através do site da Aspose [solicitação de licença temporária da Aspose](https://purchase.aspose.com/temporary-license/).

**Última atualização:** 2026-08-13  
**Testado com:** Aspose.Tasks for Java 24.12  
**Autor:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Tutoriais Relacionados

- [Adicionar calendário ao projeto com Aspose.Tasks para Java](/tasks/java/calendars/create/)
- [Como definir dias da semana em calendários do MS Project – Aspose.Tasks Java](/tasks/java/calendars/)
- [Criar exceções de calendário personalizadas com Aspose.Tasks para Java](/tasks/java/calendar-exceptions/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}