---
date: 2026-08-03
description: Aprenda como criar um calendário do ms project, adicionar o calendário
  a um projeto e salvar o projeto como XML usando Aspose.Tasks para Java.
keywords:
- create ms project calendar
- Aspose.Tasks Java
- project calendar automation
lastmod: 2026-08-03
linktitle: Adicionar calendário ao projeto usando Aspose.Tasks
og_description: Crie calendário do ms project programaticamente usando Aspose.Tasks
  para Java. Adicione calendários, personalize cronogramas e exporte para XML em minutos.
og_image_alt: Guide to creating MS Project calendar with Aspose.Tasks Java API
og_title: Criar calendário do ms project com Aspose.Tasks para Java
schemas:
- author: Aspose
  dateModified: '2026-08-03'
  description: Learn how to create ms project calendar, add calendar to a project,
    and save the project as XML using Aspose.Tasks for Java.
  headline: Create ms project calendar with Aspose.Tasks for Java
  type: TechArticle
- description: Learn how to create ms project calendar, add calendar to a project,
    and save the project as XML using Aspose.Tasks for Java.
  name: Create ms project calendar with Aspose.Tasks for Java
  steps:
  - name: import the required Aspose.Tasks package
    text: First, bring the Aspose.Tasks classes into scope so you can work with projects
      and calendars.
  - name: set the data directory path
    text: Define where the generated project file will be written. Replace the placeholder
      with an absolute or relative path on your machine.
  - name: create a new Project instance
    text: '`Project` is the core class that represents a Microsoft Project file in
      memory.'
  - name: define the calendars you want to add
    text: '`Calendar` defines a schedule with working days, exceptions, and working
      times for a project. > **Pro tip:** After adding a calendar, you can customize
      its working days with `cal1.getWeekDays().add(...)` and set daily work hours
      using `cal1.getBaseCalendar().setWorkingTime(...)`.'
  - name: save the project (save project as XML)
    text: '`SaveFileFormat.Xml` tells Aspose.Tasks to write the project in XML format.'
  - name: display a completion message
    text: Let the user know the operation finished successfully. By following these
      six concise steps, you have successfully **added a calendar to a project** and
      saved the result as an XML file.
  type: HowTo
- questions:
  - answer: Yes – after adding a calendar you can define exceptions, working hours,
      and non‑working days using the `WeekDay` and `Exception` classes.
    question: Can Aspose.Tasks handle complex calendars with multiple exceptions?
  - answer: Absolutely. Retrieve a task via `prj.getRootTask().getChildren().add("Task
      Name")` and set `task.set(Tsk.CALENDAR, cal3);`.
    question: Is it possible to assign the new calendar to specific tasks?
  - answer: Yes. Replace `SaveFileFormat.Xml` with `SaveFileFormat.Mpp` or `SaveFileFormat.P6`
      as needed; Aspose.Tasks supports **12** output formats.
    question: Does the library support saving in other formats like MPP?
  - answer: A temporary evaluation license is sufficient for testing; a full license
      is required for production deployments.
    question: Do I need a license for development builds?
  - answer: 'The Aspose.Tasks community forum is an excellent resource: [Aspose.Tasks
      forum](https://forum.aspose.com/c/tasks/15).'
    question: Where can I get help if I run into issues?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- create ms project calendar
- Aspose.Tasks
- Java project management
title: Criar calendário do ms project com Aspose.Tasks para Java
url: /pt/java/calendars/create/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Criar calendário do ms project com Aspose.Tasks para Java

## Introdução
Nos fluxos de trabalho modernos de gerenciamento de projetos, a capacidade de **criar calendário do ms project** programaticamente pode economizar horas de edição manual. Aspose.Tasks para Java oferece uma API limpa e tipada para manipular arquivos do Microsoft Project sem nunca abrir o cliente de desktop. Neste tutorial você aprenderá como adicionar um calendário, como criar um calendário do MS Project e como salvar o projeto como XML — tudo com apenas algumas linhas de código Java.

## Respostas rápidas
- **O que significa “criar calendário do ms project”?**  
  Significa inserir uma nova definição de horário de trabalho (calendário) em um arquivo do Microsoft Project via código.  
- **Qual biblioteca lida com isso?**  
  Aspose.Tasks para Java fornece a classe `Calendar` e o contêiner `Project` para gerenciar calendários.  
- **Preciso de licença?**  
  Uma licença de avaliação temporária funciona para testes; uma licença completa é necessária para uso em produção.  
- **Posso salvar o arquivo como XML?**  
  Sim — use `SaveFileFormat.Xml` para exportar o projeto como um arquivo XML.  
- **Quais são os pré‑requisitos?**  
  Java JDK 8+ e o JAR do Aspose.Tasks para Java no seu classpath.

## O que é criar calendário do ms project?
Criar um calendário do MS Project significa adicionar programaticamente uma nova definição de calendário a um arquivo de Projeto, especificando dias úteis, exceções e horas de trabalho diárias, e então atribuir esse calendário a tarefas, recursos ou ao projeto inteiro para que os cálculos de cronograma respeitem o horário de trabalho definido.

## Por que usar Aspose.Tasks para Java para adicionar calendário ao projeto?
Você deve usar Aspose.Tasks para Java porque ele fornece uma API totalmente tipada que funciona sem o Microsoft Project instalado, suporta todas as principais versões do Project (2007‑2021, cobrindo mais de 5 lançamentos) e pode exportar para XML, MPP e **mais de 10** outros formatos, permitindo a criação automatizada em massa de calendários em qualquer servidor.

## Pré‑requisitos
- **Java Development Kit (JDK) 8 ou mais recente** instalado e configurado.  
- Biblioteca **Aspose.Tasks para Java** – faça o download no [site oficial](https://releases.aspose.com/tasks/java/) e adicione o JAR ao classpath do seu projeto.  
- Uma IDE ou ferramenta de build (Maven/Gradle) de sua escolha.

## Guia passo a passo

### Etapa 1: importar o pacote Aspose.Tasks necessário
Primeiro, traga as classes do Aspose.Tasks para o escopo para que você possa trabalhar com projetos e calendários.

```java
import com.aspose.tasks.*;
```

### Etapa 2: definir o caminho do diretório de dados
Defina onde o arquivo de projeto gerado será gravado. Substitua o placeholder por um caminho absoluto ou relativo na sua máquina.

```java
String dataDir = "Your Data Directory";
```

### Etapa 3: criar uma nova instância de Project
`Project` é a classe central que representa um arquivo do Microsoft Project na memória.

```java
Project prj = new Project();
```

### Etapa 4: definir os calendários que você deseja adicionar
`Calendar` define um cronograma com dias úteis, exceções e horários de trabalho para um projeto.

```java
Calendar cal1 = prj.getCalendars().add("no info");
Calendar cal2 = prj.getCalendars().add("no name");
Calendar cal3 = prj.getCalendars().add("cal3");
```

> **Dica profissional:** Depois de adicionar um calendário, você pode personalizar seus dias úteis com `cal1.getWeekDays().add(...)` e definir as horas de trabalho diárias usando `cal1.getBaseCalendar().setWorkingTime(...)`.

### Etapa 5: salvar o projeto (salvar projeto como XML)
`SaveFileFormat.Xml` indica ao Aspose.Tasks que escreva o projeto no formato XML.

```java
prj.save(dataDir + "project.xml", SaveFileFormat.Xml);
```

### Etapa 6: exibir uma mensagem de conclusão
Informe ao usuário que a operação foi concluída com sucesso.

```java
System.out.println("Process completed Successfully");
```

Seguindo estas seis etapas concisas, você adicionou com sucesso **um calendário a um projeto** e salvou o resultado como um arquivo XML.

## Problemas comuns e soluções
| Problema | Motivo | Solução |
|----------|--------|---------|
| **`NullPointerException` em `prj.getCalendars()`** | Objeto Project não inicializado corretamente. | Garanta que `new Project()` seja chamado antes de acessar os calendários. |
| **Arquivo não encontrado ao salvar** | `dataDir` aponta para uma pasta inexistente. | Crie o diretório primeiro ou use um caminho absoluto. |
| **Nome do calendário aparece como “no info”** | Nomes de placeholder foram usados no exemplo. | Substitua por nomes significativos que reflitam o cronograma (ex.: “Calendário de Feriados dos EUA”). |
| **XML salvo não pode ser aberto no MS Project** | Versão desatualizada do Aspose.Tasks. | Atualize para a versão mais recente do Aspose.Tasks para Java. |

## Perguntas frequentes

**P: O Aspose.Tasks pode lidar com calendários complexos com múltiplas exceções?**  
R: Sim – após adicionar um calendário você pode definir exceções, horários de trabalho e dias não úteis usando as classes `WeekDay` e `Exception`.

**P: É possível atribuir o novo calendário a tarefas específicas?**  
R: Absolutamente. Recupere uma tarefa via `prj.getRootTask().getChildren().add("Task Name")` e defina `task.set(Tsk.CALENDAR, cal3);`.

**P: A biblioteca suporta salvar em outros formatos como MPP?**  
R: Sim. Substitua `SaveFileFormat.Xml` por `SaveFileFormat.Mpp` ou `SaveFileFormat.P6` conforme necessário; o Aspose.Tasks suporta **12** formatos de saída.

**P: Preciso de licença para builds de desenvolvimento?**  
R: Uma licença de avaliação temporária é suficiente para testes; uma licença completa é necessária para implantações em produção.

**P: Onde posso obter ajuda se encontrar problemas?**  
R: O fórum da comunidade Aspose.Tasks é um excelente recurso: [Fórum Aspose.Tasks](https://forum.aspose.com/c/tasks/15).

---

**Última atualização:** 2026-08-03  
**Testado com:** Aspose.Tasks para Java 24.12 (mais recente no momento da escrita)  
**Autor:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Tutoriais relacionados

- [Como definir dias da semana em calendários do MS Project – Aspose.Tasks Java](/tasks/java/calendars/)
- [Como definir o calendário do projeto Java com Aspose.Tasks](/tasks/java/calendars/properties/)
- [Criar exceções de calendário personalizadas com Aspose.Tasks para Java](/tasks/java/calendar-exceptions/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}