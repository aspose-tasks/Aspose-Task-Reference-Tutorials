---
title: Criar link de tarefa entre projetos em Aspose.Tasks
linktitle: Criar link de tarefa entre projetos em Aspose.Tasks
second_title: API Java Aspose.Tasks
description: Aprimore a colaboração em projetos com Aspose.Tasks for Java. Aprenda a criar links de tarefas entre projetos passo a passo. Aumente a eficiência agora!
weight: 10
url: /pt/java/task-links/create-cross-project-task-link/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Criar link de tarefa entre projetos em Aspose.Tasks

## Introdução
No mundo dinâmico do gerenciamento de projetos, eficiência e colaboração são fundamentais. Aspose.Tasks for Java fornece uma solução robusta para aprimorar seus recursos de gerenciamento de projetos. Neste tutorial, nos aprofundaremos no processo de criação de links de tarefas entre projetos usando Aspose.Tasks para Java. Este guia passo a passo irá equipá-lo com as habilidades necessárias para vincular perfeitamente tarefas em diferentes projetos, promovendo melhor coordenação e fluxos de trabalho simplificados.
## Pré-requisitos
Antes de embarcarmos neste tutorial, certifique-se de ter os seguintes pré-requisitos em vigor:
- Conhecimento prático de programação Java.
-  Aspose.Tasks para Java instalado. Você pode baixá-lo no[Página de lançamento do Aspose.Tasks para Java](https://releases.aspose.com/tasks/java/).
- Uma compreensão básica de gerenciamento de projetos e dependências de tarefas.
## Importar pacotes
Para iniciar o processo, vamos importar os pacotes necessários em seu ambiente Java. Isso garante que você tenha acesso às funcionalidades do Aspose.Tasks for Java. Use o seguinte trecho de código:
```java
import com.aspose.tasks.NullableBool;
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.TaskLink;
import com.aspose.tasks.TaskLinkType;
import com.aspose.tasks.Tsk;
```
Agora, vamos dividir o código acima em etapas compreensíveis:
## Etapa 1: configure seu ambiente
Antes de mergulhar no código, certifique-se de ter o Java instalado e de que a biblioteca Aspose.Tasks for Java esteja adicionada corretamente ao seu projeto.
## Etapa 2: criar uma instância de projeto
Inicialize um novo projeto usando a biblioteca Aspose.Tasks:
```java
Project project = new Project();
```
## Etapa 3: adicionar uma tarefa de resumo
Crie uma tarefa de resumo para organizar e gerenciar as tarefas vinculadas:
```java
Task summary = project.getRootTask().getChildren().add("Summary Task");
```
## Etapa 4: adicionar tarefa externa
Para criar um link para uma tarefa de outro projeto, adicione uma tarefa externa à tarefa de resumo:
```java
Task t2 = summary.getChildren().add("External Task");
t2.set(Tsk.EXTERNAL_TASK_PROJECT, "ExternalProject.mpp");
t2.set(Tsk.EXTERNAL_ID, 1);
t2.set(Tsk.IS_EXTERNAL_TASK, true);
t2.set(Tsk.IS_MANUAL, new NullableBool(false));
t2.set(Tsk.IS_SUMMARY, false);
```
## Etapa 5: adicionar tarefa local
Adicione uma tarefa local à tarefa de resumo. Esta será a tarefa vinculada à tarefa externa:
```java
Task t = summary.getChildren().add("Task");
```
## Etapa 6: criar link de tarefa
Estabeleça o link da tarefa entre a tarefa externa e a tarefa local:
```java
TaskLink link = project.getTaskLinks().add(t2, t);
link.setCrossProject(true);
link.setLinkType(TaskLinkType.FinishToStart);
link.setCrossProjectName("ExternalProject.mpp\\1");
```
## Etapa 7: exibir resultados
Por fim, exiba o resultado da conversão:
```java
System.out.println("Process completed Successfully");
```
## Conclusão
Parabéns! Você aprendeu com sucesso como criar links de tarefas entre projetos usando Aspose.Tasks para Java. Esta funcionalidade melhora a colaboração e a coordenação na gestão de projetos, garantindo uma integração perfeita entre tarefas em diferentes projetos.
## Perguntas frequentes
### Posso vincular tarefas de vários projetos externos na mesma tarefa de resumo?
Sim, você pode vincular tarefas de diferentes projetos externos na mesma tarefa de resumo, seguindo um processo semelhante.
### O que acontece se a tarefa externa no projeto vinculado for modificada?
Quaisquer modificações na tarefa externa serão refletidas na tarefa vinculada em seu projeto atual.
### É possível criar links entre tarefas em diferentes formatos de arquivo?
Sim, Aspose.Tasks for Java suporta vinculação de tarefas entre projetos em vários formatos de arquivo.
### Posso desvincular tarefas depois que elas estiverem vinculadas entre projetos?
Sim, você pode desvincular tarefas removendo o link da tarefa usando os métodos Aspose.Tasks apropriados.
### Há alguma limitação no número de tarefas que podem ser vinculadas entre projetos?
O número de tarefas que podem ser vinculadas está sujeito aos recursos e limitações da sua licença Aspose.Tasks.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
