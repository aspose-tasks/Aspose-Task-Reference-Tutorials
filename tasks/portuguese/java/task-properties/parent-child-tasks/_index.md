---
title: Gerenciar tarefas pai e filho em Aspose.Tasks
linktitle: Gerenciar tarefas pai e filho em Aspose.Tasks
second_title: API Java Aspose.Tasks
description: Aumente a eficiência do gerenciamento de projetos com Aspose.Tasks for Java. Aprenda a gerenciar tarefas de pais e filhos passo a passo. Comece agora!
weight: 24
url: /pt/java/task-properties/parent-child-tasks/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Gerenciar tarefas pai e filho em Aspose.Tasks

## Introdução
No domínio do gerenciamento de projetos, a organização eficaz das tarefas é crucial. Aspose.Tasks for Java fornece uma solução robusta para gerenciar tarefas pai e filho com eficiência. Neste tutorial, orientaremos você no processo de uso do Aspose.Tasks for Java para agilizar as tarefas do seu projeto.
## Pré-requisitos
Antes de mergulhar no tutorial, certifique-se de ter os seguintes pré-requisitos em vigor:
- Compreensão básica de programação Java.
-  Biblioteca Aspose.Tasks para Java instalada. Você pode baixá-lo[aqui](https://releases.aspose.com/tasks/java/).
- Um Java Integrated Development Environment (IDE) configurado em seu sistema.
## Importar pacotes
Para começar, importe os pacotes necessários para o seu projeto Java. Esses pacotes facilitam a integração perfeita com as funcionalidades Aspose.Tasks for Java.
```java
import com.aspose.tasks.ChildTasksCollector;
import com.aspose.tasks.ConstraintType;
import com.aspose.tasks.NullableBool;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.Task;
import com.aspose.tasks.TaskUtils;
import com.aspose.tasks.TimeUnitType;
import com.aspose.tasks.Tsk;
import java.io.IOException;
import java.util.Date;
import java.util.List;
```
## Etapa 1: definir a data de início do projeto
Comece definindo a data de início do projeto e outros parâmetros relevantes.
```java
// O caminho para o diretório de documentos.
String dataDir = "Your Document Directory";
Project proj = new Project(dataDir + "Blank2010.mpp");
proj.set(Prj.NEW_TASKS_ARE_MANUAL, new NullableBool(false));
// Código adicional para importações de pacotes pode ser adicionado aqui
double oneDay = 8d * 60d * 60d * 10000000d;
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.set(2014, 9, 13, 8, 0, 0);
Date startDate = cal.getTime();
proj.set(Prj.START_DATE, startDate);
```
## Etapa 2: Adicionar tarefa pai (tarefa 1)
Crie uma tarefa pai chamada "Tarefa 1" e configure suas propriedades.
```java
Task task1 = proj.getRootTask().getChildren().add("Task 1");
cal.set(2014, 9, 13, 8, 0, 0);
task1.set(Tsk.START, cal.getTime());
task1.set(Tsk.DURATION, proj.getDuration(29, TimeUnitType.Day));
```
## Etapa 3: Adicionar tarefa pai (tarefa 2) com tarefas filhas
Agora, adicione outra tarefa pai chamada “Tarefa 2” e inclua tarefas filhas (Tarefa 3 e Tarefa 4).
```java
Task task2 = proj.getRootTask().getChildren().add("Task 2");
// Adicionar tarefas filhas à Tarefa 2
Task task3 = task2.getChildren().add("Task 3");
Task task4 = task2.getChildren().add("Task 4");
// Configuração adicional para Tarefa 3 e Tarefa 4 pode ser adicionada aqui
```
## Etapa 4: configurar tarefas secundárias
Especifique datas de início, durações e restrições para a Tarefa 3 e a Tarefa 4.
```java
// Configurar a tarefa 3
cal.set(2014, 9, 15, 8, 0, 0);
task3.set(Tsk.START, cal.getTime());
task3.set(Tsk.DURATION, proj.getDuration(3, TimeUnitType.Day));
task3.set(Tsk.CONSTRAINT_TYPE, ConstraintType.StartNoEarlierThan);
task3.set(Tsk.CONSTRAINT_DATE, task3.get(Tsk.START));
// Configurar a tarefa 4
cal.set(2014, 9, 17, 8, 0, 0);
task4.set(Tsk.START, cal.getTime());
task4.set(Tsk.DURATION, proj.getDuration(3, TimeUnitType.Day));
task4.set(Tsk.CONSTRAINT_TYPE, ConstraintType.StartNoEarlierThan);
task4.set(Tsk.CONSTRAINT_DATE, task3.get(Tsk.START));
```
## Etapa 5: atualizar a porcentagem de conclusão de tarefas
Ajuste a porcentagem de conclusão da Tarefa 3 e da Tarefa 4.
```java
task3.set(Tsk.PERCENT_COMPLETE, 50);
task4.set(Tsk.PERCENT_COMPLETE, 70);
```
## Etapa 6: salve o projeto
Por fim, salve o projeto com as alterações aplicadas.
```java
proj.save(dataDir + "ProjectJava.mpp", SaveFileFormat.Mpp);
```
Este guia passo a passo demonstra como gerenciar tarefas pai e filho de maneira eficaz usando Aspose.Tasks for Java. Experimente diferentes configurações para atender aos requisitos do seu projeto.
## Conclusão
Concluindo, Aspose.Tasks for Java capacita os desenvolvedores a lidar com tarefas de projeto com eficiência, garantindo organização e rastreamento perfeitos. Implemente as etapas descritas para aprimorar seus recursos de gerenciamento de projetos.
## Perguntas frequentes
### O Aspose.Tasks for Java é compatível com diferentes formatos de arquivo de projeto?
Sim, Aspose.Tasks for Java oferece suporte a vários formatos de arquivo de projeto, incluindo MPP e XML.
### Posso personalizar as propriedades da tarefa além do que é abordado neste tutorial?
Absolutamente! Aspose.Tasks for Java oferece amplas opções de personalização para propriedades de tarefas.
### Existe um fórum da comunidade para Aspose.Tasks onde posso buscar suporte?
 Sim, você pode visitar o[Fórum Aspose.Tasks](https://forum.aspose.com/c/tasks/15) para apoio comunitário.
### Como posso obter uma licença temporária para Aspose.Tasks for Java?
 Você pode obter uma licença temporária[aqui](https://purchase.aspose.com/temporary-license/).
### Onde posso encontrar documentação abrangente para Aspose.Tasks for Java?
 A documentação está disponível[aqui](https://reference.aspose.com/tasks/java/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
