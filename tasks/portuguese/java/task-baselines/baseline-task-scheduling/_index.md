---
date: 2026-08-29
description: Aprenda a ler os dados da linha de base e a agendar tarefas usando Aspose.Tasks
  para Java, para que você possa comparar o progresso planejado com o real de forma
  eficiente.
keywords:
- how to read baseline
- how to set baseline
- compare planned vs actual
lastmod: 2026-08-29
linktitle: Agendamento de Tarefas de Linha de Base no Aspose.Tasks
og_description: Aprenda a ler os dados da linha de base e a agendar tarefas usando
  Aspose.Tasks para Java, permitindo comparar com precisão o progresso planejado com
  o real.
og_image_alt: Tutorial showing how to read baseline and schedule tasks with Aspose.Tasks
  Java API
og_title: Como ler a linha de base e agendar tarefas com Aspose.Tasks
schemas:
- author: Aspose
  dateModified: '2026-08-29'
  description: Learn how to read baseline data and schedule tasks using Aspose.Tasks
    for Java, so you can compare planned vs actual progress efficiently.
  headline: How to read baseline and schedule tasks with Aspose.Tasks
  type: TechArticle
- questions:
  - answer: Instantiate the `Project` class (`Project project = new Project();`).
      This creates a fresh project file ready for tasks and baselines.
    question: How do I create a new project instance in Aspose.Tasks?
  - answer: '`BaselineType.Baseline` refers to the primary baseline (Baseline 1).
      Aspose.Tasks also supports Baseline 2‑10 for additional snapshots.'
    question: What is the difference between `BaselineType.Baseline` and other baseline
      types?
  - answer: Yes, you can iterate over `TaskBaseline` objects and write the values
      to a CSV file using standard Java I/O.
    question: Can I export the baseline data to Excel or CSV?
  - answer: Setting a baseline captures the current dates but does not modify the
      task’s active schedule. You can still adjust start/finish dates after the baseline
      is set.
    question: Does setting a baseline affect existing task dates?
  - answer: Absolutely. Retrieve each baseline via `task.getBaselines().get(index)`
      and compare their `Start`, `Finish`, and `Duration` properties.
    question: Is it possible to compare multiple baselines programmatically?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- project baseline
- Aspose.Tasks
- Java project management
title: Como ler a linha de base e agendar tarefas com Aspose.Tasks
url: /pt/java/task-baselines/baseline-task-scheduling/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Como ler a linha de base e agendar tarefas com Aspose.Tasks

Neste guia você descobrirá **como ler a linha de base** de informações e agendar tarefas programaticamente usando Aspose.Tasks para Java. Ao final do tutorial, você será capaz de capturar o plano original do projeto, compará‑lo com o progresso real e gerar relatórios de variação — tudo sem precisar do Microsoft Project instalado.

## Introdução à linha de base de gerenciamento de projetos
Gerenciar uma **linha de base de gerenciamento de projetos** é um alicerce da gestão eficaz de projetos. Ela permite capturar o plano original e, posteriormente, comparar **o progresso planejado vs real** para que você possa identificar variações cedo. Neste tutorial, percorreremos como agendar linhas de base de tarefas usando Aspose.Tasks para Java, fornecendo as ferramentas para **gerenciar linhas de base de projetos** com confiança e manter seus projetos no caminho certo.

## Respostas rápidas
- **O que representa uma linha de base de gerenciamento de projetos?**  
  Ela registra o cronograma, custo e escopo aprovados no início do projeto, fornecendo uma referência para análise de variações.  
- **Qual biblioteca lida com o agendamento de linhas de base em Java?**  
  Aspose.Tasks para Java oferece uma API pure‑Java que suporta mais de 45 formatos de entrada e saída e projetos com até 100 000 tarefas.  
- **Preciso de uma licença para executar o código?**  
  Um teste gratuito funciona para testes; uma licença comercial é necessária para uso em produção.  
- **Quais são os pré‑requisitos principais?**  
  Java Development Kit (JDK) 11+ e a biblioteca Aspose.Tasks para Java.  
- **Posso visualizar as datas da linha de base após defini‑las?**  
  Sim — use o objeto `TaskBaseline` para ler os valores de início, término e duração.

## O que é uma linha de base de gerenciamento de projetos?
Uma linha de base de gerenciamento de projetos registra o cronograma, orçamento e escopo aprovados no início da execução. Ela serve como ponto de referência para medir o desempenho e identificar desvios ao longo do ciclo de vida do projeto. Inclui as datas planejadas de início e término, o custo total e os detalhes do escopo, fornecendo uma visão abrangente para comparações futuras.

## Por que usar Aspose.Tasks para agendamento de linhas de base?
Aspose.Tasks fornece uma API pure‑Java que funciona sem a necessidade do Microsoft Project instalado. Ela suporta **mais de 45 formatos de entrada e saída**, pode processar projetos com **até 100 000 tarefas** em modo de uso eficiente de memória, e oferece métodos incorporados para ler e gravar dados de linha de base — tornando a geração de relatórios automatizados e a integração simples.

## Pré‑requisitos
- **Java Development Kit (JDK)** – instale o JDK 11 ou posterior. Você pode baixá‑lo no [website](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html).  
- **Aspose.Tasks for Java library** – faça o download da versão mais recente na [download page](https://releases.aspose.com/tasks/java/) e adicione o JAR ao classpath do seu projeto.

## Importar pacotes
As classes `Project`, `Task` e `TaskBaseline` estão no namespace `com.aspose.tasks`. Importe‑as no topo do seu arquivo fonte:

A classe `Project` é o objeto de nível superior do Aspose.Tasks que representa um único arquivo de projeto na memória. Ela fornece acesso a tarefas, recursos e coleções de linhas de base.

## Como ler a linha de base?
Carregue o projeto, então consulte a coleção `TaskBaseline` para cada tarefa. O objeto `TaskBaseline` devolve o início, término e duração da linha de base que foram capturados quando você chamou `setBaseline`. Essa abordagem direta permite ler os valores da linha de base sem analisar arquivos XML ou binários.

## Etapa 1: criar uma nova instância de projeto
A classe `Project` representa o arquivo completo do projeto na memória.
```java
import com.aspose.tasks.BaselineType;
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.TaskBaseline;
```

## Etapa 2: definir uma tarefa e definir a linha de base
`Task` representa um item de trabalho individual, e `setBaseline` captura seu cronograma atual como uma linha de base.
```java
Project project = new Project();
```

## Etapa 3: acessar informações da linha de base
`TaskBaseline` contém os valores salvos de início, término e duração de uma linha de base.
```java
Task task = project.getRootTask().getChildren().add("Task");
project.setBaseline(BaselineType.Baseline);
```

## Etapa 4: exibir a duração da linha de base
`Duration` representa a duração de tempo de uma tarefa ou linha de base.
```java
TaskBaseline baseline = task.getBaselines().get(0);
```

## Etapa 5: exibir a data de início da linha de base
`Start` é a data de início programada da linha de base.
```java
System.out.println(baseline.getDuration().toString());
```

## Etapa 6: exibir a data de término da linha de base
`Finish` é a data de conclusão programada da linha de base.
```java
System.out.println("Baseline Start: " + baseline.getStart());
```

## Problemas comuns e soluções
- **Linha de base não definida:** Certifique‑se de chamar `project.setBaseline(BaselineType.Baseline)` **depois** de adicionar tarefas; caso contrário, a coleção de linhas de base ficará vazia.  
- **Valores nulos:** Se `task.getBaselines()` retornar uma lista vazia, verifique se a tarefa foi adicionada à hierarquia do projeto antes de definir a linha de base.  
- **Formato de data:** Os métodos `getStart()` e `getFinish()` retornam objetos `java.util.Date`. Use `SimpleDateFormat` se precisar de um formato de exibição personalizado.

## Perguntas frequentes

**Q: Como crio uma nova instância de projeto no Aspose.Tasks?**  
**A:** Instancie a classe `Project` (`Project project = new Project();`). Isso cria um novo arquivo de projeto pronto para tarefas e linhas de base.

**Q: Qual é a diferença entre `BaselineType.Baseline` e outros tipos de linha de base?**  
**A:** `BaselineType.Baseline` refere‑se à linha de base principal (Baseline 1). Aspose.Tasks também suporta Baseline 2‑10 para snapshots adicionais.

**Q: Posso exportar os dados da linha de base para Excel ou CSV?**  
**A:** Sim, você pode iterar sobre objetos `TaskBaseline` e gravar os valores em um arquivo CSV usando I/O padrão do Java.

**Q: Definir uma linha de base afeta as datas das tarefas existentes?**  
**A:** Definir uma linha de base captura as datas atuais, mas não modifica o cronograma ativo da tarefa. Você ainda pode ajustar as datas de início/término após a linha de base ser definida.

**Q: É possível comparar várias linhas de base programaticamente?**  
**A:** Absolutamente. Recupere cada linha de base via `task.getBaselines().get(index)` e compare suas propriedades `Start`, `Finish` e `Duration`.

---

**Última atualização:** 2026-08-29  
**Testado com:** Aspose.Tasks for Java 24.12  
**Autor:** Aspose  

```java
System.out.println("Baseline Finish: " + baseline.getFinish());
```

## Tutoriais Relacionados

- [Create Task List Java – MS Project Baseline using Aspose.Tasks](/tasks/java/task-baselines/create-task-baseline/)
- [How to Set Baseline Duration in Aspose.Tasks for Java](/tasks/java/task-baselines/task-baseline-duration/)
- [Create MPP Project Java – Change Task Progress with Aspose.Tasks](/tasks/java/task-properties/change-progress/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}