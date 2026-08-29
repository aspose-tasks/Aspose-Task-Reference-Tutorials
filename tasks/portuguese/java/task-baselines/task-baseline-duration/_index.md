---
date: 2026-08-29
description: Aprenda como definir baseline duration e acompanhar project progress
  usando Aspose.Tasks for Java. Este guia passo a passo ajuda você a gerenciar task
  baselines de forma eficiente.
keywords:
- track project progress
- manage project baselines
- Aspose.Tasks baseline duration
- Java project scheduling
- baseline management
lastmod: 2026-08-29
linktitle: Como Definir Baseline Duration no Aspose.Tasks for Java
og_description: Aprenda como definir baseline duration e acompanhar project progress
  usando Aspose.Tasks for Java. Siga este guia detalhado para gerenciar task baselines
  de forma eficiente.
og_image_alt: Developer guide showing baseline duration setup with Aspose.Tasks for
  Java
og_title: Como definir baseline duration para acompanhar project progress
schemas:
- author: Aspose
  dateModified: '2026-08-29'
  description: Learn how to set baseline duration and track project progress using
    Aspose.Tasks for Java. This step‑by‑step guide helps you manage task baselines
    efficiently.
  headline: How to set baseline duration to track project progress
  type: TechArticle
- description: Learn how to set baseline duration and track project progress using
    Aspose.Tasks for Java. This step‑by‑step guide helps you manage task baselines
    efficiently.
  name: How to set baseline duration to track project progress
  steps:
  - name: '**Java Development Environment** – JDK 8+ installed and configured.'
    text: '**Java Development Environment** – JDK 8+ installed and configured.'
  - name: '**Aspose.Tasks for Java** – download the library from the [Aspose.Tasks
      for Java download page](https://releases.aspose.com/tasks/java/).'
    text: '**Aspose.Tasks for Java** – download the library from the [Aspose.Tasks
      for Java download page](https://releases.aspose.com/tasks/java/).'
  - name: '**IDE or build tool** – Maven, Gradle, or any IDE you prefer.'
    text: '**IDE or build tool** – Maven, Gradle, or any IDE you prefer.'
  type: HowTo
- questions:
  - answer: No. Calling `project.setBaseline(BaselineType.Baseline)` records the baseline
      for all tasks in the project at once.
    question: Do I need to call `setBaseline` for each task individually?
  - answer: Use `project.setBaseline(BaselineType.Baseline1)` (or Baseline2‑Baseline10)
      after updating the task’s schedule.
    question: How can I set an interim baseline for a specific task?
  - answer: Yes. Iterate over `task.getBaselines()` and write the desired fields to
      a CSV file using standard Java I/O.
    question: Is it possible to export the baseline data to CSV?
  - answer: Absolutely. Load the file with `new Project("myproject.mpp")` and then
      access each task’s baselines as shown above.
    question: Can I read an existing .mpp file that already contains baselines?
  - answer: Aspose.Tasks works with single‑project .mpp files. For multi‑project scenarios,
      combine the projects programmatically.
    question: Does Aspose.Tasks handle multi‑project files?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- baseline duration
- Aspose.Tasks
- Java project management
- task baselines
title: Como definir baseline duration para acompanhar project progress
url: /pt/java/task-baselines/task-baseline-duration/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Como definir a duração da linha de base para acompanhar o progresso do projeto

## Introdução
Acompanhar o progresso do projeto começa com uma linha de base sólida. Neste tutorial você descobrirá **como definir a duração da linha de base** para tarefas em arquivos Microsoft Project usando a biblioteca Aspose.Tasks para Java, e entenderá por que estabelecer uma linha de base cedo ajuda a monitorar desvios de cronograma, variações de custo e superalocação de recursos ao longo da vida do projeto.

## Respostas rápidas
- **O que significa “definir linha de base”?** Registra o início, término e duração originais de uma tarefa para que você possa comparar mudanças futuras.  
- **Qual classe do Aspose.Tasks cria um projeto?** A classe `Project` – você também aprenderá como **criar uma instância de projeto** corretamente.  
- **Preciso de uma licença para executar o código?** Uma licença de avaliação gratuita funciona para testes; uma licença comercial é necessária para produção.  
- **Posso recuperar linhas de base intermediárias?** Sim, o Aspose.Tasks permite consultar linhas de base intermediárias e seus custos fixos.  
- **Qual versão do Java é necessária?** Java 8 ou superior é recomendada.  
- **Como isso me ajuda a acompanhar o progresso do projeto?** Uma vez que a linha de base está definida, você pode comparar instantaneamente as datas reais com o plano original usando recursos de relatório integrados.

## O que é uma linha de base de tarefa e por que defini‑la?
Uma linha de base de tarefa captura o cronograma planejado (data de início, data de término e duração) em um ponto específico no tempo. Ao definir uma linha de base você cria um ponto de referência que facilita identificar desvios de cronograma, estouros de custo e superalocação de recursos à medida que o projeto evolui.

## Por que usar Aspose.Tasks para gerenciamento de linhas de base?
Aspose.Tasks fornece **compatibilidade total com .mpp** – você pode ler e gravar arquivos nativos do Microsoft Project sem precisar do Microsoft Office instalado. A API oferece acesso programático a **mais de 50 formatos de entrada e saída**, suporta **linhas de base intermediárias 1‑10** e pode lidar com **projetos de centenas de páginas** sem carregar todo o arquivo na memória, o que é essencial para processamento em lote de alto desempenho.

## Pré‑requisitos
1. **Ambiente de Desenvolvimento Java** – JDK 8+ instalado e configurado.  
2. **Aspose.Tasks for Java** – baixe a biblioteca na [página de download do Aspose.Tasks for Java](https://releases.aspose.com/tasks/java/).  
3. **IDE ou ferramenta de build** – Maven, Gradle ou qualquer IDE de sua preferência.

## Importar pacotes
As importações a seguir trazem as classes principais do Aspose.Tasks necessárias para trabalhar com projetos, tarefas, linhas de base e dados faseados no tempo.

```java
import com.aspose.tasks.BaselineType;
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.TaskBaseline;
import com.aspose.tasks.TimeUnitType;
import com.aspose.tasks.TimephasedData;
```

## Etapa 1: criar uma instância de projeto
A classe `Project` representa um arquivo Microsoft Project na memória e é o ponto de entrada para todas as operações.

```java
Project project = new Project();
```

## Etapa 2: criar uma linha de base de tarefa
Um `TaskBaseline` armazena o início, término e duração planejados para uma tarefa específica.

```java
Task task = project.getRootTask().getChildren().add("Task");
project.setBaseline(BaselineType.Baseline);
```

## Etapa 3: exibir informações da linha de base da tarefa
O método `getBaselines()` retorna a coleção de linhas de base associadas a uma tarefa.

```java
TaskBaseline baseline = task.getBaselines().toList().get(0);
System.out.println("Baseline Start: " + baseline.getStart());
System.out.println("Baseline Duration: " + baseline.getDuration());
System.out.println("Baseline Duration Format: " + TimeUnitType.toString(TimeUnitType.class, baseline.getDuration().getTimeUnit()));
System.out.println("Is it an Estimated Duration?: " + baseline.getEstimatedDuration());
System.out.println("Baseline Finish: " + baseline.getFinish());
```

## Etapa 4: verificar linha de base intermediária e custo fixo
`BaselineType` enumera as linhas de base primárias e intermediárias (Baseline, Baseline1‑Baseline10).

```java
System.out.println("Interim: " + baseline.getInterim());
System.out.println("Fixed Cost: " + baseline.getFixedCost());
```

## Etapa 5: imprimir dados faseados no tempo
`TimephasedData` representa uma peça de informação de cronograma para um intervalo de tempo específico.

```java
System.out.println("Number of Timephased Items: " + baseline.getTimephasedData().size());
for (TimephasedData data : baseline.getTimephasedData()) {
    System.out.println(" UID: " + data.getUid());
    System.out.println(" Start: " + data.getStart());
    System.out.println(" Finish: " + data.getFinish());
}
```

Seguindo estas etapas, você pode **definir a duração da linha de base** para qualquer tarefa e recuperar informações detalhadas da linha de base usando o Aspose.Tasks para Java, proporcionando uma maneira confiável de **acompanhar o progresso do projeto** ao longo do ciclo de vida do projeto.

## Problemas comuns e soluções
- **Linha de base não aparece no MS Project:** Certifique-se de que chamou `project.setBaseline(BaselineType.Baseline)` **depois** de adicionar a tarefa.  
- **NullPointerException em `getBaselines()`:** Verifique se a tarefa foi adicionada ao projeto antes de definir a linha de base.  
- **Incompatibilidade de unidade de tempo:** Use `TimeUnitType` para formatar a duração corretamente, especialmente ao trabalhar com calendários personalizados.

## Perguntas Frequentes
### O que é uma linha de base de tarefa no MS Project?
Uma linha de base de tarefa no MS Project é uma captura do cronograma planejado inicial de uma tarefa, incluindo sua data de início, data de término e duração.

### Por que gerenciar linhas de base de tarefa é importante?
Gerenciar linhas de base de tarefa ajuda a comparar o cronograma planejado com o progresso real do projeto, facilitando um melhor acompanhamento e tomada de decisão.

### Posso modificar uma linha de base de tarefa depois de definida?
Sim, você pode modificar linhas de base de tarefa no MS Project para refletir mudanças no plano do projeto. No entanto, é essencial documentar quaisquer desvios da linha de base original.

### O Aspose.Tasks suporta outras funcionalidades de gerenciamento de projetos?
Sim, o Aspose.Tasks oferece uma ampla gama de recursos para gerenciamento de projetos, incluindo agendamento de tarefas, alocação de recursos e geração de diagramas de Gantt.

### Onde posso encontrar suporte para o Aspose.Tasks?
Você pode encontrar suporte para o Aspose.Tasks no [fórum do Aspose.Tasks](https://forum.aspose.com/c/tasks/15), onde pode fazer perguntas e interagir com outros usuários.

## Perguntas frequentes adicionais
**Q: Preciso chamar `setBaseline` para cada tarefa individualmente?**  
A: Não. Chamar `project.setBaseline(BaselineType.Baseline)` registra a linha de base para todas as tarefas do projeto de uma só vez.

**Q: Como posso definir uma linha de base intermediária para uma tarefa específica?**  
A: Use `project.setBaseline(BaselineType.Baseline1)` (ou Baseline2‑Baseline10) após atualizar o cronograma da tarefa.

**Q: É possível exportar os dados da linha de base para CSV?**  
A: Sim. Itere sobre `task.getBaselines()` e escreva os campos desejados em um arquivo CSV usando I/O padrão do Java.

**Q: Posso ler um arquivo .mpp existente que já contém linhas de base?**  
A: Absolutamente. Carregue o arquivo com `new Project("myproject.mpp")` e então acesse as linhas de base de cada tarefa conforme mostrado acima.

**Q: O Aspose.Tasks lida com arquivos multi‑projeto?**  
A: O Aspose.Tasks funciona com arquivos .mpp de projeto único. Para cenários multi‑projeto, combine os projetos programaticamente.

---

**Última atualização:** 2026-08-29  
**Testado com:** Aspose.Tasks for Java 24.12  
**Autor:** Aspose

## Tutoriais Relacionados

- [Criar lista de tarefas Java – Linha de base do MS Project usando Aspose.Tasks](/tasks/java/task-baselines/create-task-baseline/)
- [Criar projeto MPP Java – Alterar progresso da tarefa com Aspose.Tasks](/tasks/java/task-properties/change-progress/)
- [Linha de base de gerenciamento de projetos – Agendamento de tarefas com Aspose.Tasks](/tasks/java/task-baselines/baseline-task-scheduling/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}