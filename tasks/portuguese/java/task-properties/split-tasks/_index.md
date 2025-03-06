---
title: Dividir tarefas em Aspose.Tasks
linktitle: Dividir tarefas em Aspose.Tasks
second_title: API Java Aspose.Tasks
description: Domine o gerenciamento de tarefas em Java com Aspose.Tasks! Aprenda como dividir tarefas de forma eficiente para otimizar cronogramas de projetos. Baixe Agora!
type: docs
weight: 29
url: /pt/java/task-properties/split-tasks/
---
## Introdução
Você está lutando com o gerenciamento de tarefas em seu projeto Java? Aspose.Tasks for Java fornece uma solução poderosa para dividir tarefas de forma eficiente, aprimorando os recursos de gerenciamento de projetos. Neste tutorial, iremos guiá-lo através do processo de divisão de tarefas usando Aspose.Tasks for Java, ajudando você a otimizar os cronogramas do seu projeto e alocações de recursos.
## Pré-requisitos
Antes de mergulhar no tutorial, certifique-se de ter os seguintes pré-requisitos em vigor:
- Java Development Kit (JDK) instalado em sua máquina.
-  Biblioteca Aspose.Tasks para Java baixada e adicionada ao seu projeto. Você pode baixá-lo no[Documentação Aspose.Tasks para Java](https://reference.aspose.com/tasks/java/).
## Importar pacotes
Comece importando os pacotes necessários para o seu projeto Java:
```java
import com.aspose.tasks.Asn;
import com.aspose.tasks.Calendar;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.ResourceAssignment;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.Task;
import com.aspose.tasks.Tsk;
import com.aspose.tasks.WorkContourType;
```
## Etapa 1: crie um novo projeto
Comece criando um novo projeto usando a biblioteca Aspose.Tasks:
```java
// Crie um novo projeto
Project splitTaskProject = new Project();
```
## Etapa 2: definir o calendário do projeto
Defina as configurações do calendário do projeto para estabelecer o cronograma:
```java
// Obtenha um calendário padrão
Calendar calendar = splitTaskProject.get(Prj.CALENDAR);
// Definir as configurações do calendário do projeto
java.util.Calendar cal = java.util.Calendar.getInstance();
// ... (continue com o exemplo)
```
## Etapa 3: adicionar uma tarefa raiz
Adicione uma tarefa raiz ao seu projeto:
```java
// Tarefa raiz
Task rootTask = splitTaskProject.getRootTask();
rootTask.set(Tsk.NAME, "Root");
```
## Etapa 4: adicionar uma nova tarefa para dividir
Adicione uma nova tarefa ao seu projeto que você deseja dividir:
```java
// Adicione uma nova tarefa
Task taskToSplit = rootTask.getChildren().add("Task1");
taskToSplit.set(Tsk.DURATION, splitTaskProject.getDuration(3));
```
## Passo 5: Criar uma Atribuição de Recursos
Crie uma nova atribuição de recursos para a tarefa:
```java
// Criar uma nova atribuição de recursos
ResourceAssignment splitResourceAssignment = splitTaskProject.getResourceAssignments().add(taskToSplit, null);
```
## Etapa 6: gerar dados em fases
Gere dados faseados no tempo da atribuição de recursos:
```java
// Gerar dados faseados no tempo de atribuição de recursos
splitResourceAssignment.timephasedDataFromTaskDuration(calendar);
```
## Etapa 7: Divida a tarefa
Divida a tarefa em várias partes:
```java
// Divida a tarefa em 3 partes
java.util.Calendar cal = java.util.Calendar.getInstance();
java.util.Calendar cal2 = java.util.Calendar.getInstance();
// ... (continue com o exemplo)
```
## Conclusão
Parabéns! Você aprendeu com sucesso como dividir tarefas usando Aspose.Tasks for Java. Esta poderosa biblioteca simplifica o gerenciamento de tarefas em projetos Java, fornecendo soluções eficientes para otimizar cronogramas de projetos e alocações de recursos.
## perguntas frequentes
### Posso dividir tarefas com durações diferentes?
Sim, você pode ajustar a duração das tarefas de acordo com os requisitos do seu projeto.
### O Aspose.Tasks for Java é compatível com todas as versões Java?
Aspose.Tasks for Java foi projetado para funcionar perfeitamente com várias versões Java, garantindo compatibilidade.
### Posso usar Aspose.Tasks for Java gratuitamente?
Aspose.Tasks for Java oferece uma avaliação gratuita, permitindo que você explore seus recursos antes de fazer uma compra.
### Como posso obter suporte para Aspose.Tasks for Java?
 Visite a[Fórum de suporte Aspose.Tasks para Java](https://forum.aspose.com/c/tasks/15) para obter assistência e se conectar com a comunidade.
### Preciso de uma licença temporária para Aspose.Tasks for Java?
 Você pode obter uma licença temporária em[esse link](https://purchase.aspose.com/temporary-license/) para fins de teste e avaliação.