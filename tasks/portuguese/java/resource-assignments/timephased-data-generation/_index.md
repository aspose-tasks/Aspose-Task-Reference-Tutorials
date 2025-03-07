---
title: Gere dados em fases em Aspose.Tasks
linktitle: Gere dados em fases para atribuições de recursos em Aspose.Tasks
second_title: API Java Aspose.Tasks
description: Aprenda como gerar dados em fases para atribuições de recursos usando Aspose.Tasks for Java. Melhore a eficiência do gerenciamento de projetos com este guia completo.
weight: 24
url: /pt/java/resource-assignments/timephased-data-generation/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Gere dados em fases em Aspose.Tasks

## Introdução
Neste tutorial, percorreremos o processo de geração de dados em fases para atribuições de recursos usando Aspose.Tasks for Java. Os dados faseados no tempo fornecem informações valiosas sobre como os recursos são alocados ao longo do tempo dentro de um projeto, ajudando os gerentes de projeto a tomar decisões informadas.
## Pré-requisitos
Antes de começarmos, certifique-se de ter os seguintes pré-requisitos:
1.  Java Development Kit (JDK): Certifique-se de ter o JDK instalado em seu sistema. Você pode baixar e instalar o JDK em[aqui](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html).
2.  Biblioteca Aspose.Tasks para Java: você precisa ter a biblioteca Aspose.Tasks para Java. Você pode baixá-lo no[local na rede Internet](https://releases.aspose.com/tasks/java/).

## Importar pacotes
Primeiro, vamos importar os pacotes necessários para trabalhar com Aspose.Tasks:
```java
import com.aspose.tasks.Asn;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.ResourceAssignment;
import com.aspose.tasks.Task;
import com.aspose.tasks.TimephasedData;
import com.aspose.tasks.WorkContourType;
```
## Etapa 1: leia o arquivo MPP de origem
```java
// O caminho para o diretório de documentos.
String dataDir = "Your Data Directory";
// Leia o arquivo MPP de origem
Project project = new Project(dataDir + "project.mpp");
```
## Etapa 2: obter atribuição de tarefas e recursos
```java
// Obtenha a primeira tarefa do Projeto
Task task = project.getRootTask().getChildren().getById(1);
// Obtenha a primeira atribuição de recursos do projeto
ResourceAssignment firstRA = project.getResourceAssignments().toList().get(0);
```
## Etapa 3: gerar dados em fases com contorno plano
```java
// Contorno plano é o contorno padrão
System.out.println("Flat contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```
## Etapa 4: alterar o contorno para tartaruga
```java
// Alterar contorno para Tartaruga
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.Turtle);
System.out.println("Turtle contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```
## Etapa 5: alterar o contorno para BackLoaded
```java
// Alterar contorno para BackLoaded
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.BackLoaded);
System.out.println("BackLoaded contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```
## Etapa 6: alterar o contorno para FrontLoaded
```java
// Alterar contorno para FrontLoaded
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.FrontLoaded);
System.out.println("FrontLoaded contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```
## Etapa 7: alterar o contorno para sino
```java
// Alterar contorno para Bell
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.Bell);
System.out.println("Bell contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```
## Etapa 8: alterar o contorno para EarlyPeak
```java
// Alterar contorno para EarlyPeak
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.EarlyPeak);
System.out.println("EarlyPeak contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```
## Etapa 9: alterar o contorno para LatePeak
```java
// Alterar contorno para LatePeak
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.LatePeak);
System.out.println("LatePeak contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```
## Etapa 10: alterar o contorno para DoublePeak
```java
// Alterar contorno para DoublePeak
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.DoublePeak);
System.out.println("DoublePeak contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```

## Conclusão
Neste tutorial, abordamos como gerar dados em fases para atribuições de recursos usando Aspose.Tasks para Java. Compreender os diferentes contornos de trabalho pode ajudar os gerentes de projeto a gerenciar com eficácia a alocação e a programação de recursos em seus projetos.
## Perguntas frequentes
### Posso usar Aspose.Tasks com outras bibliotecas Java?
Sim, Aspose.Tasks pode ser integrado com outras bibliotecas Java para aprimorar os recursos de gerenciamento de projetos.
### O Aspose.Tasks é adequado para projetos empresariais de grande escala?
Com certeza, o Aspose.Tasks foi projetado para lidar com projetos de todos os tamanhos, incluindo projetos empresariais de grande escala.
### O Aspose.Tasks oferece suporte para diferentes formatos de arquivo de projeto?
Sim, Aspose.Tasks oferece suporte a vários formatos de arquivo de projeto, incluindo MPP, XML e MPX.
### Posso personalizar os contornos do trabalho de acordo com os requisitos do meu projeto?
Sim, Aspose.Tasks permite aos usuários definir contornos de trabalho personalizados para atender às necessidades específicas do projeto.
### Existe um fórum da comunidade onde posso obter ajuda com o Aspose.Tasks?
 Sim, você pode visitar o[Fórum Aspose.Tasks](https://forum.aspose.com/c/tasks/15) para apoio e discussões.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
