---
date: 2026-09-25
description: Aprenda a criar cronograma de projeto em Java usando Aspose.Tasks. Este
  guia mostra como adicionar summary tasks, gerenciar project hierarchy e definir
  document directory de forma eficiente.
keywords:
- create project schedule
- java project management
- java task management
- add summary task
- manage project hierarchy
lastmod: 2026-09-25
linktitle: Criar Tasks no Aspose.Tasks
og_description: Aprenda a criar cronograma de projeto em Java usando Aspose.Tasks.
  Siga instruções passo a passo para adicionar summary tasks, gerenciar hierarchy
  e definir document directory.
og_image_alt: Tutorial image showing Aspose.Tasks Java project schedule creation
og_title: Como criar cronograma de projeto com Aspose.Tasks para Java
schemas:
- author: Aspose
  dateModified: '2026-09-25'
  description: Learn how to create project schedule in Java using Aspose.Tasks. This
    guide shows you how to add summary tasks, manage project hierarchy, and set document
    directory efficiently.
  headline: How to create project schedule with Aspose.Tasks for Java
  type: TechArticle
- description: Learn how to create project schedule in Java using Aspose.Tasks. This
    guide shows you how to add summary tasks, manage project hierarchy, and set document
    directory efficiently.
  name: How to create project schedule with Aspose.Tasks for Java
  steps:
  - name: set the document directory
    text: Define where the resulting project file will be written. Setting the directory
      early ensures all subsequent save operations use a consistent path. The `RootFolder`
      property specifies the base folder where project files are read from or written
      to.
  - name: create a new project
    text: Instantiate a fresh `Project` object that will hold your schedule. You can
      optionally pass a pre‑existing file path to load an existing schedule for modification.
      The `Project` constructor creates an empty schedule ready for task addition.
  - name: add a summary task
    text: A summary task groups related subtasks and appears as a collapsible node
      in Gantt charts. Use the `Task` class and set `IsSummary` to `true`. The `addTask`
      method creates a new task under a specified parent and returns its ID.
  - name: add a subtask
    text: Subtasks inherit start/finish dates from their parent summary task unless
      you override them. Adding a subtask is as simple as calling `addTask` again
      and specifying the parent ID. Calling `addTask` with a parent ID adds a subtask
      under that summary task. Continue adding as many tasks and subtasks as
  type: HowTo
- questions:
  - answer: Absolutely. The library scales from a single‑task list to enterprise‑level
      schedules with thousands of tasks.
    question: Is Aspose.Tasks suitable for small‑scale projects?
  - answer: Refer to the documentation [Aspose.Tasks Java API reference](https://reference.aspose.com/tasks/java/).
    question: Where can I find detailed documentation for Aspose.Tasks for Java?
  - answer: Visit the [temporary license request page](https://purchase.aspose.com/temporary-license/)
      for a time‑limited license that works for development and testing.
    question: How do I obtain a temporary license for Aspose.Tasks?
  - answer: Yes, you can extend tasks with custom fields, assign resources, and modify
      calendars programmatically.
    question: Can I customize task attributes using Aspose.Tasks?
  - answer: Absolutely! Join the Aspose.Tasks community on [the support forum](https://forum.aspose.com/c/tasks/15).
    question: Is there a support community for Aspose.Tasks users?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- create project schedule
- Aspose.Tasks
- Java project management
title: Como criar cronograma de projeto com Aspose.Tasks para Java
url: /pt/java/task-properties/create-tasks/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Como criar cronograma de projeto com Aspose.Tasks para Java

## Introdução
Neste tutorial você aprenderá a **criar cronograma de projeto** em uma aplicação Java usando Aspose.Tasks. Seja você quem está construindo uma lista de tarefas simples ou um planejador corporativo complexo, os passos abaixo orientam a adição de tarefas resumidas, o gerenciamento da hierarquia do projeto e a definição do diretório do documento — tudo com trechos de código claros e executáveis. Ao final, você terá um cronograma totalmente estruturado pronto para manipulação ou exportação adicional.

## Respostas rápidas
- **O que o Aspose.Tasks gerencia?** Ele lida com hierarquias de tarefas, recursos, calendários e formatos de arquivos de projeto (MS‑Project, Primavera, etc.).  
- **Preciso de licença para desenvolvimento?** Uma licença temporária gratuita funciona para avaliação; uma licença completa é necessária para produção.  
- **Qual versão do Java é suportada?** Java 8 ou superior são totalmente suportados.  
- **Posso adicionar campos personalizados às tarefas?** Sim, você pode estender tarefas com campos definidos pelo usuário via API.  
- **Existe suporte nativo para diagramas de Gantt?** Aspose.Tasks pode exportar para PDF/HTML que incluem visualizações de Gantt.

## O que é um cronograma de projeto no Aspose.Tasks?
Um cronograma de projeto é o conjunto completo de tarefas, dependências e cronologias que definem como o trabalho será realizado. Aspose.Tasks armazena essas informações em um objeto `Project` que você pode ler, modificar e salvar em vários formatos. Ele inclui datas de início e término, restrições e atribuições de recursos, permitindo planejamento e relatórios abrangentes.

## Por que usar Aspose.Tasks para gerenciamento de projetos Java?
Aspose.Tasks suporta **mais de 30 formatos de entrada e saída** e pode processar projetos com **até 10.000 tarefas** sem carregar todo o arquivo na memória, oferecendo alto desempenho para cenários de gerenciamento de projetos Java em grande escala.

## Pré‑requisitos
Antes de mergulhar no tutorial, certifique‑se de que você tem os seguintes pré‑requisitos configurados:
- **Java Development Kit (JDK)** – JDK 8 ou posterior instalado na sua máquina.  
- **Aspose.Tasks for Java library** – Baixe e instale a biblioteca a partir de [Aspose.Tasks for Java download](https://releases.aspose.com/tasks/java/).  
- **Integrated Development Environment (IDE)** – Use Eclipse, IntelliJ IDEA ou qualquer IDE compatível com Java que preferir.

## Importar pacotes
`Project`, `Task` e classes relacionadas vivem no namespace `com.aspose.tasks`. Importe‑as no topo do seu arquivo Java:

A classe `Project` representa um cronograma de projeto completo e fornece métodos para manipular tarefas e recursos.

```java
import com.aspose.tasks.*;
import java.util.Calendar;
```

A classe `Project` é o ponto de entrada para todas as operações em um arquivo de projeto.

## Como criar cronograma de projeto com Aspose.Tasks?

Carregue uma nova instância `Project`, defina o diretório do documento e comece a adicionar tarefas. Este parágrafo de resposta direta explica o fluxo principal: você cria um `Project`, configura seu `RootFolder` (o diretório do documento) e, em seguida, adiciona uma tarefa resumida seguida de subtarefas. Todas as alterações permanecem em memória até que você chame `save` para persistir o cronograma em um arquivo.

### Etapa 1: definir o diretório do documento
Defina onde o arquivo de projeto resultante será gravado. Definir o diretório antecipadamente garante que todas as operações de salvamento subsequentes usem um caminho consistente.

A propriedade `RootFolder` especifica a pasta base onde os arquivos de projeto são lidos ou gravados.

```java
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
```

### Etapa 2: criar um novo projeto
Instancie um novo objeto `Project` que armazenará seu cronograma. Opcionalmente, você pode passar o caminho de um arquivo pré‑existente para carregar um cronograma existente para modificação.

O construtor `Project` cria um cronograma vazio pronto para a adição de tarefas.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
```

### Etapa 3: adicionar uma tarefa resumida
Uma tarefa resumida agrupa subtarefas relacionadas e aparece como um nó recolhível em diagramas de Gantt. Use a classe `Task` e defina `IsSummary` como `true`.

O método `addTask` cria uma nova tarefa sob um pai especificado e retorna seu ID.

```java
// Create a new project
Project project = new Project(dataDir + "project.mpp");
```

### Etapa 4: adicionar uma subtarefa
Subtarefas herdam datas de início/término da tarefa resumida pai, a menos que você as sobrescreva. Adicionar uma subtarefa é tão simples quanto chamar `addTask` novamente e especificar o ID do pai.

Chamar `addTask` com um ID de pai adiciona uma subtarefa sob aquela tarefa resumida.

```java
// Add a summary task
Task task = project.getRootTask().getChildren().add("Summary1");
```

Continue adicionando quantas tarefas e subtarefas forem necessárias para o seu projeto. Cada etapa contribui para a construção de uma hierarquia de projeto estruturada que pode ser exportada para MS‑Project, PDF ou outros formatos suportados.

## Problemas comuns e soluções
- **Problema:** “Diretório do documento não encontrado.”  
  **Solução:** Verifique se o caminho atribuído a `RootFolder` existe no sistema de arquivos e se o processo Java tem permissões de gravação.
- **Problema:** Subtarefas não aparecem sob a tarefa resumida.  
  **Solução:** Certifique‑se de passar o ID correto da tarefa pai ao chamar `addTask`. A API requer o ID do pai como segundo argumento.
- **Problema:** Projetos grandes causam OutOfMemoryError.  
  **Solução:** Aspose.Tasks processa tarefas em modo de streaming; aumente o tamanho do heap da JVM (`-Xmx2g`) ou divida o cronograma em vários arquivos.

## Perguntas frequentes
**P: O Aspose.Tasks é adequado para projetos de pequena escala?**  
R: Absolutamente. A biblioteca escala de uma lista de tarefa única a cronogramas corporativos com milhares de tarefas.

**P: Onde posso encontrar documentação detalhada do Aspose.Tasks para Java?**  
R: Consulte a documentação [Aspose.Tasks Java API reference](https://reference.aspose.com/tasks/java/).

**P: Como obtenho uma licença temporária para o Aspose.Tasks?**  
R: Visite a [temporary license request page](https://purchase.aspose.com/temporary-license/) para uma licença de tempo limitado que funciona para desenvolvimento e testes.

**P: Posso personalizar atributos de tarefa usando Aspose.Tasks?**  
R: Sim, você pode estender tarefas com campos personalizados, atribuir recursos e modificar calendários programaticamente.

**P: Existe uma comunidade de suporte para usuários do Aspose.Tasks?**  
R: Absolutamente! Junte‑se à comunidade Aspose.Tasks no [the support forum](https://forum.aspose.com/c/tasks/15).

---

**Última atualização:** 2026-09-25  
**Testado com:** Aspose.Tasks 24.12 for Java  
**Autor:** Aspose  

```java
// Add a subtask under the summary task
Task subtask = task.getChildren().add("Subtask1");
```

## Tutoriais relacionados

- [Set Project Start Date in MS Project using Aspose.Tasks for Java](/tasks/java/project-properties/write-project-info/)
- [Create Project Management Task Dependencies in Aspose.Tasks](/tasks/java/task-links/create-task-link/)
- [How to Add Resource to Project and Create Resource Assignments in Aspose.Tasks](/tasks/java/resource-assignments/create-resource-assignments/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}