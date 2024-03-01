---
title: Gerenciar durações de tarefas em Aspose.Tasks
linktitle: Gerenciar durações de tarefas em Aspose.Tasks
second_title: API Java Aspose.Tasks
description: Explore Aspose.Tasks for Java e aprenda a gerenciar durações de tarefas sem esforço. Siga nosso guia passo a passo para planejar e executar projetos de forma eficaz.
type: docs
weight: 20
url: /pt/java/task-properties/manage-durations/
---
## Introdução
Aspose.Tasks for Java fornece uma solução robusta para gerenciar tarefas e durações de projetos com eficiência. Neste tutorial, exploraremos como gerenciar durações de tarefas usando Aspose.Tasks, orientando você em cada etapa. Quer você seja um desenvolvedor experiente ou iniciante, este guia o ajudará a compreender o essencial para trabalhar com durações de tarefas em seus projetos.
## Pré-requisitos
Antes de mergulhar no tutorial, certifique-se de ter os seguintes pré-requisitos em vigor:
-  Java Development Kit (JDK): Certifique-se de ter o Java instalado em sua máquina. Você pode baixá-lo[aqui](https://www.oracle.com/java/technologies/javase-downloads.html).
- Biblioteca Aspose.Tasks: Baixe e inclua a biblioteca Aspose.Tasks em seu projeto. Você pode encontrar a biblioteca[aqui](https://releases.aspose.com/tasks/java/).
## Importar pacotes
No seu projeto Java, importe os pacotes necessários para trabalhar com Aspose.Tasks:
```java
import com.aspose.tasks.Duration;
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.TimeUnitType;
import com.aspose.tasks.Tsk;
```
## Etapa 1: configure seu projeto
```java
// Crie um novo projeto
Project project = new Project();
```
## Etapa 2: adicionar uma nova tarefa
```java
// Adicione uma nova tarefa ao projeto
Task task = project.getRootTask().getChildren().add("Task");
```
## Etapa 3: obter e converter a duração da tarefa
```java
// Obtenha a duração da tarefa em dias (unidade de tempo padrão)
Duration duration = task.get(Tsk.DURATION);
System.out.println("Duration equals 1 day: " + duration.toString().equals("1 day"));
// Converter duração em unidade de tempo de horas
duration = duration.convert(TimeUnitType.Hour);
System.out.println("Duration equals 8 hrs: " + duration.toString().equals("8 hrs"));
```
## Etapa 4: atualize a duração da tarefa para 1 semana
```java
// Aumente a duração da tarefa para 1 semana
task.set(Tsk.DURATION, project.getDuration(1, TimeUnitType.Week));
System.out.println("Duration equals 1 wk: " + task.get(Tsk.DURATION).toString().equals("1 wk"));
```
## Etapa 5: diminuir a duração da tarefa
```java
// Diminuir a duração da tarefa
task.set(Tsk.DURATION, task.get(Tsk.DURATION).subtract(0.5));
System.out.println("Duration equals 0.5 wks: " + task.get(Tsk.DURATION).toString().equals("0.5 wks"));
```
Seguindo essas etapas, você gerenciou com êxito a duração das tarefas em seu projeto Aspose.Tasks for Java.
## Conclusão
Neste tutorial, cobrimos os fundamentos do gerenciamento de durações de tarefas usando Aspose.Tasks para Java. Agora, você pode incorporar essas técnicas com segurança em seus projetos para um gerenciamento eficaz da duração das tarefas.
## Perguntas frequentes
### O Aspose.Tasks é compatível com todas as versões Java?
Aspose.Tasks é compatível com Java 6 e versões posteriores.
### Posso usar Aspose.Tasks para projetos comerciais?
 Sim, você pode usar Aspose.Tasks para projetos pessoais e comerciais. Visita[aqui](https://purchase.aspose.com/buy) para detalhes de licenciamento.
### Onde posso encontrar suporte e recursos adicionais?
 Visite a[Fórum Aspose.Tasks](https://forum.aspose.com/c/tasks/15) para apoio e discussões da comunidade.
### Como posso obter uma licença temporária para fins de teste?
 Você pode obter uma licença temporária[aqui](https://purchase.aspose.com/temporary-license/) para teste e avaliação.
### Existe um teste gratuito disponível para Aspose.Tasks?
 Sim, você pode acessar o teste gratuito[aqui](https://releases.aspose.com/) para explorar Aspose.Tasks antes de fazer uma compra.