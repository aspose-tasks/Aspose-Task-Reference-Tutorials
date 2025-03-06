---
title: Gerenciamento de duração da linha de base da tarefa em Aspose.Tasks
linktitle: Gerenciamento de duração da linha de base da tarefa em Aspose.Tasks
second_title: API Java Aspose.Tasks
description: Aprenda como gerenciar com eficiência linhas de base de tarefas no MS Project usando Aspose.Tasks for Java. Este tutorial orienta você passo a passo pelo processo.
weight: 12
url: /pt/java/task-baselines/task-baseline-duration/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Gerenciamento de duração da linha de base da tarefa em Aspose.Tasks

## Introdução
Gerenciar linhas de base de tarefas no MS Project é crucial para o planejamento e rastreamento de projetos. Neste tutorial, exploraremos como gerenciar com eficácia as durações da linha de base das tarefas usando Aspose.Tasks for Java.
## Pré-requisitos
Antes de começarmos, certifique-se de ter o seguinte:
1. Ambiente de Desenvolvimento Java: Certifique-se de ter o Java Development Kit (JDK) instalado em seu sistema.
2.  Biblioteca Aspose.Tasks: Baixe e instale a biblioteca Aspose.Tasks para Java em[aqui](https://releases.aspose.com/tasks/java/).

## Importar pacotes
Primeiro, importe os pacotes necessários para o seu projeto Java:
```java
import com.aspose.tasks.BaselineType;
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.TaskBaseline;
import com.aspose.tasks.TimeUnitType;
import com.aspose.tasks.TimephasedData;
```
## Etapa 1: criar uma instância de projeto
Inicialize uma nova instância de projeto usando o seguinte código:
```java
Project project = new Project();
```
## Etapa 2: criar uma linha de base de tarefas
Crie uma nova tarefa e defina sua linha de base usando o seguinte código:
```java
Task task = project.getRootTask().getChildren().add("Task");
project.setBaseline(BaselineType.Baseline);
```
## Etapa 3: Exibir informações básicas da tarefa
Recupere e exiba informações básicas da tarefa, como duração, data de início, data de término e muito mais:
```java
TaskBaseline baseline = task.getBaselines().toList().get(0);
System.out.println("Baseline Start: " + baseline.getStart());
System.out.println("Baseline Duration: " + baseline.getDuration());
System.out.println("Baseline Duration Format: " + TimeUnitType.toString(TimeUnitType.class, baseline.getDuration().getTimeUnit()));
System.out.println("Is it an Estimated Duration?: " + baseline.getEstimatedDuration());
System.out.println("Baseline Finish: " + baseline.getFinish());
```
## Etapa 4: verificar a linha de base provisória e o custo fixo
Verifique se a linha de base é uma linha de base provisória e recupere quaisquer custos fixos associados a ela:
```java
System.out.println("Interim: " + baseline.getInterim());
System.out.println("Fixed Cost: " + baseline.getFixedCost());
```
## Etapa 5: imprimir dados em fases
Imprima dados faseados no tempo associados à linha de base da tarefa:
```java
System.out.println("Number of Timephased Items: " + baseline.getTimephasedData().size());
for (TimephasedData data : baseline.getTimephasedData()) {
    System.out.println(" UID: " + data.getUid());
    System.out.println(" Start: " + data.getStart());
    System.out.println(" Finish: " + data.getFinish());
}
```
Seguindo essas etapas, você pode gerenciar com eficácia as durações da linha de base das tarefas no MS Project usando Aspose.Tasks for Java.

## Conclusão
Gerenciar linhas de base de tarefas é essencial para o gerenciamento de projetos, permitindo rastrear desvios do cronograma planejado. Com Aspose.Tasks for Java, esse processo se torna ágil e eficiente, permitindo melhor controle e entrega do projeto.
## Perguntas frequentes
### O que é uma linha de base de tarefas no MS Project?
Uma linha de base de tarefa no MS Project é um instantâneo do cronograma inicial planejado para uma tarefa, incluindo sua data de início, data de término e duração.
### Por que o gerenciamento de linhas de base de tarefas é importante?
O gerenciamento das linhas de base das tarefas ajuda a comparar o cronograma planejado com o andamento real do projeto, facilitando um melhor acompanhamento e tomada de decisões.
### Posso modificar uma linha de base de tarefa depois de definida?
Sim, você pode modificar linhas de base de tarefas no MS Project para refletir as alterações no plano do projeto. No entanto, é essencial documentar quaisquer desvios da linha de base original.
### O Aspose.Tasks oferece suporte a outras funcionalidades de gerenciamento de projetos?
Sim, Aspose.Tasks oferece uma ampla gama de recursos para gerenciamento de projetos, incluindo agendamento de tarefas, alocação de recursos e geração de gráficos de Gantt.
### Onde posso encontrar suporte para Aspose.Tasks?
 Você pode encontrar suporte para Aspose.Tasks no[Fórum Aspose.Tasks](https://forum.aspose.com/c/tasks/15), onde você pode fazer perguntas e interagir com outros usuários.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
