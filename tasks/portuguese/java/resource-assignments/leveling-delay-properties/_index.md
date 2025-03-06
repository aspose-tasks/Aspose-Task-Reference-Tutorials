---
title: Lidar com propriedades de atraso de nivelamento em Aspose.Tasks
linktitle: Lidar com propriedades de atraso de nivelamento para atribuições de recursos em Aspose.Tasks
second_title: API Java Aspose.Tasks
description: Aprenda como lidar com propriedades de atraso de nivelamento para atribuições de recursos em Aspose.Tasks for Java com este tutorial abrangente.
weight: 17
url: /pt/java/resource-assignments/leveling-delay-properties/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Lidar com propriedades de atraso de nivelamento em Aspose.Tasks

## Introdução
Neste tutorial, percorreremos o processo de manipulação de propriedades de atraso de nivelamento para atribuições de recursos em Aspose.Tasks for Java. Aspose.Tasks é uma poderosa biblioteca Java que permite trabalhar com arquivos do Microsoft Project sem exigir que o Microsoft Project esteja instalado em seu sistema.
## Pré-requisitos
Antes de começarmos, certifique-se de ter os seguintes pré-requisitos:
1.  Java Development Kit (JDK): Certifique-se de ter o Java JDK instalado em seu sistema. Você pode baixá-lo e instalá-lo no[local na rede Internet](https://www.oracle.com/java/technologies/javase-jdk15-downloads.html).
   
2.  Biblioteca Aspose.Tasks para Java: Baixe a biblioteca Aspose.Tasks para Java no[página de download](https://releases.aspose.com/tasks/java/).

## Importar pacotes
Primeiro, importe os pacotes necessários para o seu projeto Java para usar as funcionalidades do Aspose.Tasks:
```java
import com.aspose.tasks.Asn;
import com.aspose.tasks.Project;
import com.aspose.tasks.Resource;
import com.aspose.tasks.ResourceAssignment;
import com.aspose.tasks.Task;
import com.aspose.tasks.TimeUnitType;
import com.aspose.tasks.Tsk;
import java.util.Calendar;
```

## Etapa 1: Crie um objeto de projeto
 Instanciar um`Project` objeto:
```java
Project prj = new Project();
```
## Etapa 2: crie uma tarefa
Adicione uma tarefa ao projeto:
```java
Task task = prj.getRootTask().getChildren().add("Task 1");
```
## Etapa 3: definir a data e duração de início da tarefa
Defina a data de início e a duração da tarefa:
```java
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.set(2000, Calendar.JANUARY, 3, 8, 0, 0);
task.set(Tsk.START, cal.getTime());
task.set(Tsk.DURATION, prj.getDuration(8));
```
## Etapa 4: adicionar um recurso
Adicione um recurso ao projeto:
```java
Resource resource = prj.getResources().add("Resource 1");
```
## Passo 5: Criar uma Atribuição de Recursos
Crie uma atribuição de recursos para a tarefa e o recurso:
```java
ResourceAssignment assignment = prj.getResourceAssignments().add(task, resource);
```
## Etapa 6: definir o atraso de nivelamento
Defina o atraso de nivelamento para a tarefa:
```java
assignment.set(Asn.DELAY, prj.getDuration(0, TimeUnitType.Day));
```
## Etapa 7: exibir resultados
Imprima o atraso de nivelamento e outras informações relevantes:
```java
System.out.println("Delay: " + assignment.get(Asn.DELAY));
System.out.println("Leveling Delay: " + assignment.get(Asn.LEVELING_DELAY));
System.out.println("Process completed Successfully");
```

## Conclusão
Neste tutorial, aprendemos como lidar com propriedades de atraso de nivelamento para atribuições de recursos em Aspose.Tasks for Java. Seguindo estas etapas, você pode gerenciar com eficiência atribuições de recursos em seus projetos Java.
## Perguntas frequentes
### P: Posso usar Aspose.Tasks com outras bibliotecas Java?

R: Sim, Aspose.Tasks pode ser integrado a outras bibliotecas Java para aprimorar os recursos de gerenciamento de projetos.

### P: O Aspose.Tasks é compatível com diferentes versões de arquivos do Microsoft Project?

R: Sim, Aspose.Tasks oferece suporte a várias versões de arquivos do Microsoft Project, garantindo compatibilidade em diferentes ambientes.

### P: Onde posso encontrar suporte adicional para Aspose.Tasks?

 R: Você pode encontrar suporte e recursos no site[Fórum Aspose.Tasks](https://forum.aspose.com/c/tasks/15).

### P: Posso experimentar o Aspose.Tasks antes de comprar?

 R: Sim, você pode obter uma avaliação gratuita do Aspose.Tasks no[página de lançamentos](https://releases.aspose.com/).

### P: Como posso obter uma licença temporária para Aspose.Tasks?

 R: Você pode solicitar uma licença temporária do[página de licença temporária](https://purchase.aspose.com/temporary-license/) para fins de avaliação.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
