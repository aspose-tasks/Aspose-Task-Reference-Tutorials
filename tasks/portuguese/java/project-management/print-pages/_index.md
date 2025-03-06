---
title: Imprimir páginas para separar imagens em Aspose.Tasks
linktitle: Imprimir páginas para separar imagens em Aspose.Tasks
second_title: API Java Aspose.Tasks
description: Aprenda como imprimir páginas para separar imagens em Aspose.Tasks for Java. Melhore a visualização do projeto com este guia passo a passo.
weight: 22
url: /pt/java/project-management/print-pages/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Imprimir páginas para separar imagens em Aspose.Tasks

## Introdução
Neste tutorial, orientaremos você no processo de impressão de páginas para imagens separadas usando Aspose.Tasks for Java. Esta funcionalidade pode ser particularmente útil quando você precisa visualizar layouts de projetos ou tarefas críticas separadamente.
## Pré-requisitos
Antes de começarmos, certifique-se de ter os seguintes pré-requisitos:
1.  Kit de desenvolvimento Java (JDK): certifique-se de ter o JDK instalado em seu sistema. Você pode baixá-lo em[aqui](https://www.oracle.com/java/technologies/javase-jdk15-downloads.html).
   
2.  Biblioteca Aspose.Tasks para Java: Baixe e inclua a biblioteca Aspose.Tasks para Java em seu projeto. Você pode obtê-lo de[aqui](https://releases.aspose.com/tasks/java/).

## Importar pacotes
Certifique-se de importar os pacotes necessários no início do seu arquivo Java:
```java
import com.aspose.tasks.Gridline;
import com.aspose.tasks.GridlineType;
import com.aspose.tasks.ImageSaveOptions;
import com.aspose.tasks.LinePattern;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import java.awt.*;
import java.util.ArrayList;
```
## Etapa 1: carregar dados do projeto
Primeiro, carregue os dados do projeto do seu arquivo MPP:
```java
String dataDir = "Your Data Directory";
Project project = new Project(dataDir + "CustomerFeedback.mpp");
```
## Etapa 2: definir opções para salvar imagens
Defina as opções para salvar a imagem, incluindo data de início, data de término, tarefas críticas, legenda e linhas de grade:
```java
ImageSaveOptions saveOptions = new ImageSaveOptions(SaveFileFormat.Png);
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.setTime(project.get(Prj.START_DATE));
cal.add(java.util.Calendar.DATE, -3);
saveOptions.setStartDate(cal.getTime());
saveOptions.setEndDate(project.get(Prj.FINISH_DATE));
saveOptions.setMarkCriticalTasks(true);
saveOptions.setLegendOnEachPage(false);
```
## Etapa 3: personalizar linhas de grade
Personalize as linhas de grade da imagem, especificando tipo, cor e padrão:
```java
saveOptions.setGridlines(new ArrayList<Gridline>());
Gridline gridline = new Gridline();
gridline.setGridlineType(GridlineType.GanttRow);
gridline.setColor(Color.BLUE);
gridline.setPattern(LinePattern.Dashed);
saveOptions.getGridlines().add(gridline);
```
## Etapa 4: salvar imagens
Salve o layout do projeto como imagens, tanto como um arquivo único quanto como arquivos separados:
```java
project.save(dataDir + "CustomerFeedback.png", saveOptions);
saveOptions.setRenderToSinglePage(false);
project.save(dataDir + "CustomerFeedback_.png", saveOptions);
```

## Conclusão
Neste tutorial, demonstramos como imprimir páginas em imagens separadas usando Aspose.Tasks para Java. Seguindo as etapas descritas acima, você pode visualizar com eficiência os layouts do projeto e as tarefas críticas de acordo com suas necessidades.
## Perguntas frequentes
### P: Posso personalizar o formato da imagem ao salvar layouts de projetos?
 R: Sim, Aspose.Tasks for Java suporta vários formatos de imagem, como PNG, JPEG, BMP, etc.`ImageSaveOptions` aula.
### P: O Aspose.Tasks for Java é compatível com diferentes ambientes de desenvolvimento Java?
R: Sim, Aspose.Tasks for Java é compatível com a maioria dos ambientes de desenvolvimento Java, incluindo Eclipse, IntelliJ IDEA e NetBeans.
### P: Posso integrar Aspose.Tasks for Java em meu projeto Maven ou Gradle?
R: Sim, você pode integrar facilmente Aspose.Tasks for Java em seu projeto Maven ou Gradle adicionando a dependência apropriada em seu`pom.xml` ou`build.gradle` arquivo.
### P: O Aspose.Tasks for Java oferece suporte à exportação de dados do projeto para outros formatos além de imagens?
R: Sim, Aspose.Tasks for Java oferece suporte à exportação de dados do projeto para vários formatos, como PDF, HTML, XLSX, etc., proporcionando flexibilidade na visualização de dados e relatórios.
### P: Existe algum suporte da comunidade disponível para Aspose.Tasks for Java?
 R: Sim, você pode encontrar suporte da comunidade, fazer perguntas e interagir com outros usuários no site.[Fórum Aspose.Tasks](https://forum.aspose.com/c/tasks/15).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
