---
title: Leia dados em fases para recursos em Aspose.Tasks
linktitle: Leia dados em fases para recursos em Aspose.Tasks
second_title: API Java Aspose.Tasks
description: Aprenda como extrair dados em fases de recursos do MS Project usando Aspose.Tasks para Java. Tutorial passo a passo.
type: docs
weight: 15
url: /pt/java/resource-management/read-timephased-data/
---
## Introdução
Neste tutorial, orientaremos você através do processo de leitura de dados em fases para recursos do MS Project usando Aspose.Tasks para Java. Esta biblioteca fornece funcionalidades poderosas para gerenciar arquivos do Microsoft Project de forma programática.
## Pré-requisitos
Antes de começarmos, certifique-se de ter os seguintes pré-requisitos:
1.  Java Development Kit (JDK): Certifique-se de ter o JDK instalado em seu sistema. Você pode baixá-lo no[local na rede Internet](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html) e siga as instruções de instalação.
2.  Biblioteca Aspose.Tasks para Java: Baixe a biblioteca Aspose.Tasks para Java no[página de download](https://releases.aspose.com/tasks/java/) e siga as instruções de instalação fornecidas na documentação.

## Importar pacotes
```java
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.Resource;
import com.aspose.tasks.TimephasedData;
import com.aspose.tasks.TimephasedDataType;
```
## Etapa 1: configurar o diretório de dados
Primeiro, defina o diretório onde o arquivo do MS Project está localizado.
```java
String dataDir = "Your Data Directory";
```
## Etapa 2: Leia o arquivo de modelo do MS Project
Especifique o nome do seu arquivo de modelo do MS Project.
```java
String fileName = "ResourceTimephasedData.mpp";
```
## Etapa 3: ler o arquivo de entrada como projeto
Leia o arquivo de entrada usando Aspose.Tasks e carregue-o como um objeto Project.
```java
Project project = new Project(dataDir + fileName);
```
## Etapa 4: obter recursos por ID
Recupere o recurso desejado do projeto por seu identificador exclusivo (ID).
```java
Resource resource = project.getResources().getByUid(1);
```
## Etapa 5: Imprimir dados faseados no tempo para trabalho de recursos
Imprima os dados faseados no tempo para o trabalho dos recursos.
```java
System.out.println("Timephased data of ResourceWork");
for (TimephasedData td : resource.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println("Start: " + td.getStart().toString());
    System.out.println(" Work: " + td.getValue());
}
```
## Etapa 6: Imprimir dados faseados no tempo para custo de recursos
Imprima os dados faseados no tempo para o custo dos recursos.
```java
System.out.println("Timephased data of ResourceCost");
for (TimephasedData td : resource.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE), TimephasedDataType.ResourceCost)) {
    System.out.println("Start: " + td.getStart().toString());
    System.out.println(" Cost: " + td.getValue());
}
```

## Conclusão
Neste tutorial, aprendemos como ler dados em fases para recursos do MS Project usando Aspose.Tasks para Java. Seguindo essas etapas, você pode extrair com eficiência informações valiosas dos arquivos do seu projeto de forma programática.
## Perguntas frequentes
### O Aspose.Tasks pode lidar com outros tipos de arquivos de projeto além do Microsoft Project?
Sim, Aspose.Tasks oferece suporte a vários formatos de arquivo, incluindo MPP, XML e CSV.
### O Aspose.Tasks é compatível com diferentes ambientes de desenvolvimento Java?
Sim, Aspose.Tasks é compatível com todos os principais IDEs e frameworks Java.
### Posso manipular dados do projeto usando Aspose.Tasks?
Com certeza, Aspose.Tasks fornece APIs abrangentes para criar, modificar e analisar dados de projetos.
### Aspose.Tasks é adequado para projetos de nível empresarial?
Sim, Aspose.Tasks é amplamente utilizado em ambientes corporativos devido à sua confiabilidade e escalabilidade.
### Onde posso encontrar suporte se encontrar problemas ao usar o Aspose.Tasks?
 Você pode visitar o[Fórum Aspose.Tasks](https://forum.aspose.com/c/tasks/15) pela assistência da comunidade e da equipe de apoio.