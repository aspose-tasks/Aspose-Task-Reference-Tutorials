---
title: Gerencie com eficiência as propriedades do MS Project em Aspose.Tasks
linktitle: Gerenciar propriedades padrão do projeto em Aspose.Tasks
second_title: API Java Aspose.Tasks
description: Aprenda como gerenciar propriedades padrão do MS Project usando Aspose.Tasks para Java. Simplifique seu fluxo de trabalho de gerenciamento de projetos sem esforço.
type: docs
weight: 11
url: /pt/java/project-management/default-properties/
---
## Introdução
Você está procurando agilizar seu processo de gerenciamento de projetos com Aspose.Tasks for Java? O gerenciamento de propriedades padrão em arquivos do Microsoft Project pode aumentar significativamente a eficiência. Neste tutorial, percorreremos instruções passo a passo sobre como gerenciar as propriedades padrão do MS Project usando Aspose.Tasks.
## Pré-requisitos
Antes de nos aprofundarmos no tutorial, certifique-se de ter os seguintes pré-requisitos:
### 1. Kit de Desenvolvimento Java (JDK)
   - Certifique-se de que o JDK esteja instalado em seu sistema.
   -  Você pode baixá-lo em[aqui](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html).
### 2. Aspose.Tasks para biblioteca Java
   - Baixe e inclua a biblioteca Aspose.Tasks for Java em seu projeto.
   -  Você pode baixá-lo no[local na rede Internet](https://releases.aspose.com/tasks/java/).
## Importar pacotes
Primeiramente, importe os pacotes necessários em seu arquivo Java:
```java
import com.aspose.tasks.*;
import java.util.Calendar;
```
Vamos dividir o processo em etapas gerenciáveis:
## Etapa 1: carregar o arquivo do projeto
```java
// O caminho para o diretório de documentos.
String dataDir = "Your Data Directory";
Project project = new Project(dataDir + "project.mpp");
```
## Etapa 2: exibir propriedades padrão
```java
// Exibir propriedades padrão
System.out.println("Project Version : " + project.get(Prj.SAVE_VERSION));
System.out.println("New Task Default Start: " + project.get(Prj.DEFAULT_START_TIME));
System.out.println("New Task Default Type: " + project.get(Prj.DEFAULT_TASK_TYPE));
System.out.println("Resource Default Standard Rate: " + project.get(Prj.DEFAULT_STANDARD_RATE));
System.out.println("Resource Default Overtime Rate: " + project.get(Prj.DEFAULT_OVERTIME_RATE));
System.out.println("Default Task EV Method: " + project.get(Prj.DEFAULT_TASK_EV_METHOD));
System.out.println("Default Cost Accrual: " + project.get(Prj.DEFAULT_FIXED_COST_ACCRUAL));
```
## Etapa 3: definir propriedades padrão
```java
// Definir propriedades padrão
project.set(Prj.SCHEDULE_FROM_START, new NullableBool(true));
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.set(2014, Calendar.FEBRUARY, 15, 0, 0, 0);
project.set(Prj.START_DATE, cal.getTime());
project.set(Prj.DEFAULT_START_TIME, project.get(Prj.START_DATE));
project.set(Prj.DEFAULT_TASK_TYPE, TaskType.FixedDuration);
project.set(Prj.DEFAULT_STANDARD_RATE, 15d);
project.set(Prj.DEFAULT_OVERTIME_RATE, 12d);
project.set(Prj.DEFAULT_TASK_EV_METHOD, EarnedValueMethodType.PercentComplete);
project.set(Prj.DEFAULT_FIXED_COST_ACCRUAL, CostAccrualType.Prorated);
```
## Etapa 4: Salvar o projeto no formato XML
```java
// Salve o projeto no formato XML
project.save(dataDir + "project4.xml", SaveFileFormat.Xml);
```
## Etapa 5: exibir resultado
```java
// Exibir resultado da conversão.
System.out.println("Process completed Successfully");
```
Seguindo essas etapas, você pode gerenciar com eficiência as propriedades padrão do MS Project usando Aspose.Tasks for Java.
## Conclusão
Neste tutorial, aprendemos como gerenciar propriedades padrão do MS Project usando Aspose.Tasks for Java. Ao utilizar essas técnicas, você pode otimizar o fluxo de trabalho de gerenciamento de projetos, aumentando a produtividade e a organização.
## Perguntas frequentes
### Q1: Posso usar Aspose.Tasks com outras linguagens de programação?
A1: Sim, Aspose.Tasks oferece suporte a várias linguagens de programação, como .NET, Python e Java.
### Q2: O Aspose.Tasks é adequado para uso pessoal e empresarial?
A2: Com certeza! Esteja você gerenciando pequenos projetos pessoais ou iniciativas empresariais de grande escala, o Aspose.Tasks atende a todos.
### Q3: O Aspose.Tasks oferece suporte ao cliente?
A3: Sim, você pode encontrar assistência e apoio comunitário no site[Fórum Aspose.Tasks](https://forum.aspose.com/c/tasks/15).
### Q4: Posso experimentar o Aspose.Tasks antes de comprar?
 A4: Claro! Você pode aproveitar um teste gratuito no[local na rede Internet](https://releases.aspose.com/).
### Q5: Como posso obter uma licença temporária para Aspose.Tasks?
 A5: Você pode obter uma licença temporária do[página de compra](https://purchase.aspose.com/temporary-license/) para fins de teste e avaliação.