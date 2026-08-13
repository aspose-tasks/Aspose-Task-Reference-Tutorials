---
date: 2026-08-13
description: Aprenda a criar um calendário padrão do MS Project em Java usando Aspose.Tasks.
  Este guia passo a passo mostra como criar um calendário padrão do MS Project, adicioná-lo
  como padrão e salvar o arquivo.
keywords:
- how to create calendar
- create ms project calendar
- aspose.tasks java calendar
- standard project calendar
lastmod: 2026-08-13
linktitle: Criar calendário padrão no Aspose.Tasks
og_description: Como criar calendário em Java com Aspose.Tasks. Aprenda a criar um
  calendário padrão do MS Project, defini-lo como padrão e salvar o arquivo do projeto
  em minutos.
og_image_alt: Developer guide showing Java code to create a standard Microsoft Project
  calendar using Aspose.Tasks
og_title: Como criar calendário – criar calendário padrão no Aspose.Tasks
schemas:
- author: Aspose
  dateModified: '2026-08-13'
  description: Learn how to create a standard MS Project calendar in Java using Aspose.Tasks.
    This step‑by‑step guide shows you how to create a standard MS Project calendar,
    add it as the default, and save the file.
  headline: How to create calendar – make standard calendar in Aspose.Tasks
  type: TechArticle
- description: Learn how to create a standard MS Project calendar in Java using Aspose.Tasks.
    This step‑by‑step guide shows you how to create a standard MS Project calendar,
    add it as the default, and save the file.
  name: How to create calendar – make standard calendar in Aspose.Tasks
  steps:
  - name: set up the data directory
    text: Define where the generated project file will be saved. Replace `"Your Data
      Directory"` with the absolute path on your machine (e.g., `C:/Projects/Output/`).
  - name: create a project instance
    text: '`Project` is Aspose.Tasks'' top‑level object that represents a single Microsoft
      Project file in memory. Instantiating it gives you a container for calendars,
      tasks, resources, and other project data.'
  - name: define and make the calendar standard
    text: '`Calendar` is the class that models a working‑time schedule. Adding a new
      calendar named **“My Cal”** and calling `makeStandardCalendar` promotes it to
      the default calendar for the entire project. > **Pro tip:** The `makeStandardCalendar`
      method automatically marks the supplied calendar as the defau'
  - name: save the project
    text: SaveFileFormat is an enumeration that specifies the file format to use when
      saving a project. Persist the project (including the new calendar) to an XML
      file. You can change the file name or format (`SaveFileFormat.Pp`) if you prefer
      a different Project version.
  - name: display completion message
    text: Give yourself a visual cue that the process finished without errors.
  type: HowTo
- questions:
  - answer: Yes, Aspose.Tasks supports a wide range of Microsoft Project versions,
      from 2000 up to the latest releases.
    question: Is Aspose.Tasks compatible with all versions of Microsoft Project?
  - answer: Absolutely! You can modify working days, add exceptions, and define specific
      working times using the `WeekDay` and `WorkingTime` classes.
    question: Can I customize the calendar settings further?
  - answer: Certainly. The library is designed for high‑performance, scalable environments
      and offers comprehensive support for large Project files.
    question: Is Aspose.Tasks suitable for enterprise‑level applications?
  - answer: Yes, Aspose provides dedicated forums, ticket‑based support, and extensive
      documentation to help you resolve any issues quickly.
    question: Does Aspose.Tasks offer technical support for developers?
  - answer: Yes, you can explore a free trial version available on the [website](https://purchase.aspose.com/buy),
      allowing you to evaluate all features before committing.
    question: Can I try Aspose.Tasks before making a purchase?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- calendar creation
- aspose.tasks
- java project management
title: Como criar calendário – criar calendário padrão no Aspose.Tasks
url: /pt/java/calendars/make-standard/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Como criar calendário – criar calendário padrão no Aspose.Tasks

## Introdução
Neste tutorial você aprenderá **como criar calendário** objetos para arquivos Microsoft Project usando a biblioteca Aspose.Tasks para Java. Vamos percorrer a criação de um calendário padrão do MS Project, torná‑lo o calendário padrão (standard) e salvar o arquivo do projeto. Ao final do guia, você poderá integrar a criação de calendários em qualquer solução de gerenciamento de projetos baseada em Java.

## Respostas rápidas
- **O que significa “calendário padrão”?** É a definição de horário de trabalho padrão aplicada às tarefas que não têm um calendário personalizado atribuído.  
- **Qual biblioteca é necessária?** Aspose.Tasks para Java – uma API pura em Java que funciona sem o Microsoft Project instalado.  
- **Preciso de uma licença?** Uma avaliação gratuita funciona para desenvolvimento; uma licença comercial é necessária para implantações em produção.  
- **Qual formato de arquivo é gerado?** Um arquivo Microsoft Project baseado em XML (`.xml`).  
- **Quanto tempo leva a implementação?** Cerca de 5‑10 minutos para uma configuração básica de calendário.

## O que é um calendário padrão no Microsoft Project?
Um calendário padrão define os dias e horas de trabalho padrão para um projeto, tipicamente de segunda a sexta, das 8 h às 17 h. Quando você adiciona um calendário padrão, qualquer tarefa que não tenha um calendário personalizado atribuído herda esses horários de trabalho, garantindo agendamento consistente ao longo do projeto.

## Por que usar Aspose.Tasks para criar um calendário?
Aspose.Tasks para Java suporta **mais de 50 formatos de entrada e saída** e pode processar projetos com até **10.000 tarefas** sem carregar todo o arquivo na memória. Esta biblioteca pura em Java permite automatizar a criação de arquivos Project em servidores, pipelines CI ou qualquer aplicação Java, eliminando a necessidade de uma instalação licenciada do Microsoft Project.

## Pré-requisitos
Antes de começar, certifique‑se de que o seguinte esteja configurado:

### Instalação do Java Development Kit (JDK)
Instale a versão mais recente do JDK no site da Oracle ou em uma distribuição OpenJDK.

### Biblioteca Aspose.Tasks para Java
Faça o download da biblioteca na [página de download](https://releases.aspose.com/tasks/java/). Adicione o JAR ao classpath do seu projeto.

## Importar pacotes
Precisamos apenas de uma importação para este tutorial:

```java
import com.aspose.tasks.*;
```

## Guia passo a passo

### Etapa 1: configurar o diretório de dados
Defina onde o arquivo de projeto gerado será salvo.

```java
String dataDir = "Your Data Directory";
```

Substitua `"Your Data Directory"` pelo caminho absoluto na sua máquina (por exemplo, `C:/Projects/Output/`).

### Etapa 2: criar uma instância de projeto
`Project` é o objeto de nível superior do Aspose.Tasks que representa um único arquivo Microsoft Project na memória. Instanciá‑lo fornece um contêiner para calendários, tarefas, recursos e outros dados do projeto.

```java
Project project = new Project();
```

### Etapa 3: definir e tornar o calendário padrão
`Calendar` é a classe que modela um cronograma de horário de trabalho. Adicionar um novo calendário chamado **“My Cal”** e chamar `makeStandardCalendar` promove‑o ao calendário padrão para todo o projeto.

```java
Calendar cal1 = project.getCalendars().add("My Cal");
Calendar.makeStandardCalendar(cal1);
```

> **Dica profissional:** O método `makeStandardCalendar` marca automaticamente o calendário fornecido como padrão para o projeto, que é exatamente o que você precisa quando deseja **adicionar funcionalidade de calendário padrão**.

### Etapa 4: salvar o projeto
`SaveFileFormat` é uma enumeração que especifica o formato de arquivo a ser usado ao salvar um projeto.  
Persista o projeto (incluindo o novo calendário) em um arquivo XML.

```java
project.save(dataDir + "project.xml", SaveFileFormat.Xml);
```

Você pode alterar o nome do arquivo ou o formato (`SaveFileFormat.Pp`) se preferir uma versão diferente do Project.

### Etapa 5: exibir mensagem de conclusão
Forneça a si mesmo um indicativo visual de que o processo terminou sem erros.

```java
System.out.println("Process completed Successfully");
```

## Problemas comuns & soluções
| Problema | Causa | Solução |
|----------|-------|---------|
| **Arquivo não encontrado** | `dataDir` aponta para uma pasta inexistente | Crie a pasta ou use um caminho absoluto |
| **Exceção de licença** | Executando sem uma licença válida do Aspose.Tasks em produção | Aplique um arquivo de licença via `License license = new License(); license.setLicense("Aspose.Tasks.lic");` |
| **Calendário vazio** | Esquecer de adicionar definições de horário de trabalho | Use `cal1.getWeekDays().add(WeekDay.DayType.Monday)` etc., se precisar de horas personalizadas |

## Perguntas frequentes

**P: O Aspose.Tasks é compatível com todas as versões do Microsoft Project?**  
R: Sim, o Aspose.Tasks suporta uma ampla gama de versões do Microsoft Project, desde 2000 até as versões mais recentes.

**P: Posso personalizar ainda mais as configurações do calendário?**  
R: Absolutamente! Você pode modificar os dias de trabalho, adicionar exceções e definir horários de trabalho específicos usando as classes `WeekDay` e `WorkingTime`.

**P: O Aspose.Tasks é adequado para aplicações de nível empresarial?**  
R: Certamente. A biblioteca foi projetada para ambientes de alto desempenho e escaláveis, oferecendo suporte abrangente para arquivos Project grandes.

**P: O Aspose.Tasks oferece suporte técnico para desenvolvedores?**  
R: Sim, a Aspose fornece fóruns dedicados, suporte baseado em tickets e documentação extensa para ajudá‑lo a resolver quaisquer problemas rapidamente.

**P: Posso experimentar o Aspose.Tasks antes de comprar?**  
R: Sim, você pode explorar uma versão de avaliação gratuita disponível no [site](https://purchase.aspose.com/buy), permitindo avaliar todos os recursos antes de se comprometer.

---

**Última atualização:** 2026-08-13  
**Testado com:** Aspose.Tasks for Java 24.12  
**Autor:** Aspose

## Tutoriais Relacionados

- [Adicionar calendário ao projeto com Aspose.Tasks para Java](/tasks/java/calendars/create/)
- [Como definir o calendário do projeto Java com Aspose.Tasks](/tasks/java/calendars/properties/)
- [Criar exceções de calendário personalizadas com Aspose.Tasks para Java](/tasks/java/calendar-exceptions/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}