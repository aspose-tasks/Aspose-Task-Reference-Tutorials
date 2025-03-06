---
title: WBS associada à tarefa em Aspose.Tasks
linktitle: WBS associada à tarefa em Aspose.Tasks
second_title: API Java Aspose.Tasks
description: Domine WBS com Aspose.Tasks for Java - Aprenda a ler e renumerar códigos de tarefas WBS. Aumente a eficiência do gerenciamento de projetos!
weight: 36
url: /pt/java/task-properties/wbs-associated-with-task/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# WBS associada à tarefa em Aspose.Tasks

## Introdução
Bem-vindo ao mundo do gerenciamento de projetos com Aspose.Tasks for Java! Neste tutorial, nos aprofundaremos nos meandros da Estrutura Analítica do Trabalho (EAP) associada às tarefas usando Aspose.Tasks para Java. Quer você seja um desenvolvedor experiente ou esteja apenas começando, este guia o ajudará a navegar pelos fundamentos do gerenciamento eficiente de códigos WBS.
## Pré-requisitos
Antes de mergulharmos no tutorial, certifique-se de ter os seguintes pré-requisitos em vigor:
- Java Development Kit (JDK) instalado em sua máquina.
-  Biblioteca Aspose.Tasks para Java baixada e adicionada ao seu projeto. Você pode obtê-lo de[aqui](https://releases.aspose.com/tasks/java/).
## Importar pacotes
Certifique-se de importar os pacotes necessários para iniciar seu projeto:
```java
import com.aspose.tasks.ChildTasksCollector;
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.TaskUtils;
import com.aspose.tasks.Tsk;
import java.util.ArrayList;
import java.util.List;
```
## Leia os códigos WBS
Vamos começar lendo os códigos WBS associados às tarefas. Siga esses passos:
## Etapa 1: carregar o projeto
```java
Project project = new Project("Your Document Directory" + "input.mpp");
```
## Etapa 2: coletar tarefas
```java
ChildTasksCollector collector = new ChildTasksCollector();
TaskUtils.apply(project.getRootTask(), collector, 0);
```
## Etapa 3: analisar e personalizar
```java
for (Task tsk : collector.getTasks()) {
    System.out.println(tsk.get(Tsk.WBS));
    System.out.println(tsk.get(Tsk.WBS_LEVEL));
    tsk.set(Tsk.WBS, "custom wbs");
}
```
Este snippet lê e personaliza códigos WBS associados às tarefas do seu projeto.
## Renumerar códigos WBS de tarefa
Agora, vamos explorar a renumeração de códigos WBS para tarefas:
## Etapa 1: carregar o projeto
```java
Project project = new Project("Your Document Directory" + "RenumberExample.mpp");
```
## Etapa 2: selecione todas as tarefas
```java
List<Task> tasks = (List<Task>) project.getRootTask().selectAllChildTasks();
```
## Etapa 3: gerar códigos WBS iniciais
```java
System.out.println("WBS codes before: ");
for (Task task : tasks) {
    System.out.println("\"" + task.get(Tsk.WBS) + "\"" + "; ");
}
```
## Etapa 4: renumerar códigos WBS
```java
List<Integer> listIds = new ArrayList<>();
listIds.add(1);
listIds.add(2);
listIds.add(3);
project.renumberWBSCode(listIds);
```
## Etapa 5: gerar códigos WBS atualizados
```java
System.out.println("\nWBS codes after: ");
for (Task task : tasks) {
    System.out.println("\"" + task.get(Tsk.WBS) + "\"" + "; ");
}
```
Seguindo essas etapas, você renumerará efetivamente os códigos EAP para tarefas em seu projeto.
## Conclusão
Parabéns! Você aprendeu com sucesso como trabalhar com códigos WBS usando Aspose.Tasks for Java. Esse conhecimento permitirá que você gerencie e personalize com eficiência a hierarquia de tarefas do seu projeto.
## Perguntas frequentes
### P: Onde posso encontrar a documentação do Aspose.Tasks for Java?
 R: A documentação está disponível[aqui](https://reference.aspose.com/tasks/java/).
### P: Como posso baixar Aspose.Tasks para Java?
 R: Você pode baixá-lo[aqui](https://releases.aspose.com/tasks/java/).
### P: Existe uma avaliação gratuita disponível para Aspose.Tasks for Java?
 R: Sim, você pode obter um teste gratuito[aqui](https://releases.aspose.com/).
### P: Onde posso obter suporte para Aspose.Tasks for Java?
 R: Visite o[Fórum Aspose.Tasks](https://forum.aspose.com/c/tasks/15) para suporte.
### P: Posso obter uma licença temporária para Aspose.Tasks for Java?
 R: Sim, obtenha uma licença temporária[aqui](https://purchase.aspose.com/temporary-license/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
