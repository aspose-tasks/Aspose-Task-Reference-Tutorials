---
title: Monitore horas extras, custos restantes e trabalho em Aspose.Tasks
linktitle: Monitore horas extras, custos restantes e trabalho em Aspose.Tasks
second_title: API Java Aspose.Tasks
description: Aprenda como monitorar horas extras, custos restantes e trabalhar em projetos Java usando Aspose.Tasks. Etapas fáceis para gerenciamento de projetos eficaz.
weight: 18
url: /pt/java/resource-assignments/overtime-remaining-costs-work/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Monitore horas extras, custos restantes e trabalho em Aspose.Tasks

## Introdução
Neste tutorial, aprenderemos como usar Aspose.Tasks for Java para monitorar horas extras, custos restantes e trabalho em um projeto. Isso pode ser inestimável para gerentes de projeto e líderes de equipe, para garantir que os projetos permaneçam no caminho certo e dentro do orçamento.
## Pré-requisitos
Antes de começarmos, certifique-se de ter o seguinte:
1. Java Development Kit (JDK): Aspose.Tasks for Java requer Java SE 6 ou posterior.
2.  Aspose.Tasks for Java Library: Baixe e instale a biblioteca em[aqui](https://releases.aspose.com/tasks/java/).
3. Ambiente de Desenvolvimento Integrado (IDE): Qualquer IDE Java, como Eclipse, IntelliJ IDEA ou NetBeans.

## Importar pacotes
Comece importando os pacotes necessários em seu arquivo Java:
```java
import com.aspose.tasks.Asn;
import com.aspose.tasks.Project;
import com.aspose.tasks.ResourceAssignment;
```

## Etapa 1: configurar o diretório de dados
Defina o diretório onde seu arquivo de projeto está localizado:
```java
String dataDir = "Your Data Directory";
```
 Substituir`"Your Data Directory"` com o caminho para o arquivo do seu projeto.
## Etapa 2: carregar o projeto
 Instanciar um`Project` objeto e carregue o arquivo do projeto:
```java
Project project = new Project(dataDir + "ResourceAssignmentOvertimes.mpp");
```
 Substituir`"ResourceAssignmentOvertimes.mpp"` com o nome do arquivo do seu projeto.
## Etapa 3: iterar por meio de atribuições de recursos
Percorra cada atribuição de recurso no projeto:
```java
for (ResourceAssignment ra : project.getResourceAssignments()) {
```
## Etapa 4: imprimir custos de horas extras e trabalho
Recuperar e imprimir custos de horas extras e trabalho para cada atribuição de recurso:
```java
    System.out.println(ra.get(Asn.OVERTIME_COST));
    System.out.println(ra.get(Asn.OVERTIME_WORK).toString());
```
## Etapa 5: imprimir custos e trabalho restantes
Recupere e imprima os custos e trabalhos restantes para cada atribuição de recurso:
```java
    System.out.println(ra.get(Asn.REMAINING_COST));
    System.out.println(ra.get(Asn.REMAINING_WORK).toString());
```
## Etapa 6: Imprimir custos e trabalho restantes de horas extras
Recupere e imprima os custos de horas extras e o trabalho restantes para cada atribuição de recurso:
```java
    System.out.println(ra.get(Asn.REMAINING_OVERTIME_COST));
    System.out.println(ra.get(Asn.REMAINING_OVERTIME_WORK).toString());
}
```

## Conclusão
Monitorar horas extras, custos restantes e trabalho em um projeto é crucial para um gerenciamento de projeto bem-sucedido. Com Aspose.Tasks for Java, você pode acessar e rastrear facilmente essas informações, garantindo que seus projetos permaneçam dentro do cronograma e do orçamento.
## Perguntas frequentes
### Posso usar Aspose.Tasks for Java com outras bibliotecas Java?
Sim, Aspose.Tasks for Java é compatível com outras bibliotecas e estruturas Java.
### O Aspose.Tasks oferece suporte a diferentes formatos de arquivo de projeto?
Sim, Aspose.Tasks oferece suporte a vários formatos de arquivo de projeto, incluindo MPP, XML e muito mais.
### Existe uma versão de teste disponível?
 Sim, você pode baixar uma avaliação gratuita em[aqui](https://releases.aspose.com/).
### Onde posso encontrar suporte se encontrar problemas?
 Você pode visitar o fórum Aspose.Tasks[aqui](https://forum.aspose.com/c/tasks/15) para suporte.
### Como posso adquirir uma licença para Aspose.Tasks?
 Você pode comprar uma licença de[aqui](https://purchase.aspose.com/buy).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
