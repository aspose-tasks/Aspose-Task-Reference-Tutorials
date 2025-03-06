---
title: Leia o MS Project do Primavera com Aspose.Tasks para Java
linktitle: Leia o projeto do Primavera em Aspose.Tasks
second_title: API Java Aspose.Tasks
description: Aprenda como ler arquivos MS Project do Primavera XML perfeitamente usando Aspose.Tasks for Java. Aumente a eficiência do gerenciamento de projetos.
weight: 20
url: /pt/java/project-management/read-primavera/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Leia o MS Project do Primavera com Aspose.Tasks para Java

## Introdução
No gerenciamento de projetos, a interoperabilidade entre diferentes plataformas de software é crucial para um fluxo de trabalho contínuo. Aspose.Tasks for Java fornece funcionalidade robusta para ler arquivos do Microsoft Project do Primavera XML. Este tutorial irá guiá-lo através do processo de leitura de arquivos MS Project do Primavera usando Aspose.Tasks for Java, permitindo que você examine as propriedades específicas do Primavera das tarefas de forma eficiente.
## Pré-requisitos
Antes de continuar, certifique-se de ter os seguintes pré-requisitos instalados e configurados:
1. Java Development Kit (JDK): Certifique-se de ter o JDK instalado em seu sistema.
2.  Aspose.Tasks para Java: Baixe e instale Aspose.Tasks para Java em[aqui](https://releases.aspose.com/tasks/java/).

## Importar pacotes
```java
import com.aspose.tasks.PrimaveraReadOptions;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.TimeDelta;
```
## Etapa 1: configurar o diretório de dados
```java
String dataDir = "Your Data Directory";
```
 Certifique-se de substituir`"Your Data Directory"` com o caminho real para o seu diretório de dados.
## Etapa 2: Ler o projeto do Primavera XML
```java
PrimaveraReadOptions options = new PrimaveraReadOptions();
options.setProjectUid(3883);
Project project = new Project(dataDir + "PrimaveraProject.xml", options);
```
 Certifique-se de substituir`"PrimaveraProject.xml"` pelo nome real do seu arquivo Primavera XML.
## Etapa 3: Iterar através de tarefas e recuperar propriedades específicas do Primavera
```java
for (Task task : project.enumerateAllChildTasks()) {
    System.out.println("Task '" + task.getName() + "'");
    
    if (task.isSummary()) {
        System.out.println("WBS Sequence number: " + task.getPrimaveraProperties().getSequenceNumber());
    } else {
        System.out.println("Task ActivityId: " + task.getPrimaveraProperties().getActivityId());
    }
    
    System.out.println("Activity Type: " + task.getPrimaveraProperties().getActivityType());
    System.out.println("Duration Type: " + task.getPrimaveraProperties().getDurationType());
    System.out.println("Percent Complete Type: " + task.getPrimaveraProperties().getPercentCompleteType());
    System.out.println("Original Duration: " + TimeDelta.fromMilliseconds(task.getDuration().getTimeSpan()).getTotalHours());
    System.out.println("At Complete Duration: " +
            (TimeDelta.fromMilliseconds(task.getActualDuration().getTimeSpan()).getTotalHours() + TimeDelta.fromMilliseconds(task.getRemainingDuration().getTimeSpan()).getTotalHours()));
    System.out.println("Duration % Complete: " + task.getPrimaveraProperties().getDurationPercentComplete());
    System.out.println("Physical % Complete: " + task.getPrimaveraProperties().getPhysicalPercentComplete());
    
    System.out.println("Task RemainingEarlyStart: " + task.getPrimaveraProperties().getRemainingEarlyStart());
    System.out.println("Task RemainingEarlyFinish: " + task.getPrimaveraProperties().getRemainingEarlyFinish());
    
    System.out.println("Actual costs:");
    System.out.println(task.getPrimaveraProperties().getActualExpenseCost() + ", "
                    + task.getPrimaveraProperties().getActualLaborCost() + ", "
                    + task.getPrimaveraProperties().getActualMaterialCost() + ", "
                    + task.getPrimaveraProperties().getActualNonlaborCost() + ", Total: "
                    + task.getPrimaveraProperties().getActualTotalCost());
    
    System.out.println("Labor Units:");
    System.out.println(task.getPrimaveraProperties().getActualLaborUnits() + ", " +
            task.getPrimaveraProperties().getActualNonLaborUnits() + ", " +
            task.getPrimaveraProperties().getRemainingLaborUnits() + ", " +
            task.getPrimaveraProperties().getRemainingNonLaborUnits());
    
    System.out.println("Units % Complete: " + task.getPrimaveraProperties().getUnitsPercentComplete());
}
```
Esse código itera em cada tarefa do projeto, imprimindo propriedades relevantes específicas do Primavera.

## Conclusão
Neste tutorial, você aprendeu como ler arquivos MS Project do Primavera XML usando Aspose.Tasks for Java. Essa funcionalidade permite integração e análise perfeitas de dados de projetos em diferentes plataformas, melhorando a eficiência geral do gerenciamento de projetos.
## Perguntas frequentes
### P: Posso modificar as propriedades específicas de tarefas do Primavera usando Aspose.Tasks for Java?
R: Sim, Aspose.Tasks for Java fornece APIs para modificar propriedades de tarefas específicas do Primavera conforme necessário.
### P: O Aspose.Tasks for Java oferece suporte à leitura de outros formatos de arquivo de projeto?
R: Sim, Aspose.Tasks for Java suporta a leitura de vários formatos de arquivo de projeto, incluindo MPP, XML e Primavera XML.
### P: O Aspose.Tasks for Java é adequado para aplicativos de gerenciamento de projetos de nível empresarial?
R: Com certeza, Aspose.Tasks for Java oferece recursos robustos e escalabilidade, tornando-o adequado para aplicativos de gerenciamento de projetos de nível empresarial.
### P: Posso extrair informações de recursos de projetos Primavera usando Aspose.Tasks for Java?
R: Sim, Aspose.Tasks for Java permite extrair informações de recursos junto com detalhes de tarefas de projetos Primavera.
### P: Onde posso encontrar suporte ou documentação adicional para Aspose.Tasks for Java?
 R: Você pode encontrar documentação abrangente e acesso a fóruns de suporte no[Documentação Aspose.Tasks para Java](https://reference.aspose.com/tasks/java/) página.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
