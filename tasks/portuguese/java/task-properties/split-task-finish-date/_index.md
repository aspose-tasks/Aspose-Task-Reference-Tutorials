---
title: Dividir a data de término da tarefa em Aspose.Tasks
linktitle: Dividir a data de término da tarefa em Aspose.Tasks
second_title: API Java Aspose.Tasks
description: Aprenda como dividir datas de término de tarefas sem esforço usando Aspose.Tasks for Java. Aprimore o gerenciamento de projetos com cronogramas precisos.
weight: 28
url: /pt/java/task-properties/split-task-finish-date/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Dividir a data de término da tarefa em Aspose.Tasks

## Introdução
No gerenciamento de projetos, compreender os cronogramas das tarefas é crucial para a conclusão bem-sucedida do projeto. Aspose.Tasks for Java fornece recursos poderosos para manipular tarefas do projeto com eficiência. Neste tutorial, nos aprofundaremos na divisão de datas de término de tarefas usando Aspose.Tasks, ajudando você a gerenciar cronogramas de projetos de maneira eficaz.
## Pré-requisitos
Antes de começarmos, certifique-se de ter o seguinte:
- Conhecimento básico de programação Java.
-  Biblioteca Aspose.Tasks para Java instalada. Você pode baixá-lo[aqui](https://releases.aspose.com/tasks/java/).
- Um ambiente de desenvolvimento Java configurado.
## Importar pacotes
Comece incluindo os pacotes necessários em seu projeto Java:
```java
import com.aspose.tasks.*;
```
## Etapa 1: Encontre uma tarefa dividida
Localize a tarefa que deseja dividir no projeto:
```java
// O caminho para o diretório de documentos.
String dataDir = "Your Document Directory";
// Ler projeto
String projectName = dataDir + "SplitTask.mpp";
Project project = new Project(projectName);
Task splitTask = project.getRootTask().getChildren().getByUid(1);
```
## Etapa 2: Encontre o calendário do projeto
Recupere o calendário do projeto para cálculos de datas precisos:
```java
Calendar calendar = project.get(Prj.CALENDAR);
```
## Etapa 3: calcular a data de término da tarefa com durações diferentes
Agora, calcule a data de término da tarefa para diversas durações:
## Etapa 3.1: Duração de 8 horas
```java
System.out.println("Start Date: " + splitTask.get(Tsk.START) + "\n+ Duration 8 hours\nFinish Date: " + calendar.getTaskFinishDateFromDuration(splitTask, 8d));
```
Repita o código acima por diferentes durações, ajustando as horas de acordo.
## Conclusão
Dominar a arte de manipular as datas de término das tarefas é fundamental para um gerenciamento de projetos eficaz. Aspose.Tasks for Java simplifica esse processo, permitindo que você agilize os cronogramas do seu projeto sem esforço.
## Perguntas frequentes
### Q1: Como posso baixar Aspose.Tasks para Java?
 A1: Você pode baixá-lo[aqui](https://releases.aspose.com/tasks/java/).
### Q2: Onde posso encontrar documentação para Aspose.Tasks?
 A2: Consulte a documentação[aqui](https://reference.aspose.com/tasks/java/).
### Q3: Como obtenho uma licença temporária para Aspose.Tasks?
 A3: Obtenha uma licença temporária[aqui](https://purchase.aspose.com/temporary-license/).
### Q4: Onde posso procurar suporte para Aspose.Tasks?
 A4: Visite o fórum de suporte[aqui](https://forum.aspose.com/c/tasks/15).
### Q5: Posso comprar Aspose.Tasks?
 A5: Sim, você pode comprá-lo[aqui](https://purchase.aspose.com/buy).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
