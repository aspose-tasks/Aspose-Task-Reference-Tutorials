---
title: Reduzindo a lacuna entre a lista de tarefas e o rodapé em Aspose.Tasks
linktitle: Reduzindo a lacuna entre a lista de tarefas e o rodapé em Aspose.Tasks
second_title: API Java Aspose.Tasks
description: Aprenda como reduzir a lacuna entre as listas de tarefas e rodapés do MS Project usando Aspose.Tasks for Java. Otimize o layout dos documentos do projeto sem esforço.
weight: 10
url: /pt/java/project-file-operations/reduce-gap-tasks-list-footer/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Reduzindo a lacuna entre a lista de tarefas e o rodapé em Aspose.Tasks

## Introdução
Neste tutorial, nos aprofundaremos na redução da lacuna entre a lista de tarefas e o rodapé nos arquivos do Microsoft Project usando Aspose.Tasks for Java. Seguindo estas etapas, você poderá otimizar o layout dos documentos do seu projeto sem esforço.
## Pré-requisitos
Antes de começarmos, certifique-se de ter os seguintes pré-requisitos:
1. Java Development Kit (JDK): Certifique-se de ter o JDK instalado em seu sistema.
2.  Biblioteca Aspose.Tasks para Java: Baixe e inclua a biblioteca Aspose.Tasks para Java em seu projeto. Você pode baixá-lo em[aqui](https://releases.aspose.com/tasks/java/).

## Importar pacotes
Antes de mergulhar na parte de codificação, vamos importar os pacotes necessários:
```java
import com.aspose.tasks.HtmlSaveOptions;
import com.aspose.tasks.ImageSaveOptions;
import com.aspose.tasks.PageSize;
import com.aspose.tasks.PdfSaveOptions;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.SaveOptions;
import com.aspose.tasks.Timescale;
import java.io.IOException;
```
## Etapa 1: forneça o caminho para o seu diretório de dados
```java
String dataDir = "Your Data Directory";
```
 Certifique-se de substituir`"Your Data Directory"` pelo caminho para o diretório de dados real onde está o arquivo do Microsoft Project (`HomeMovePlan.mpp` neste exemplo) está localizado.
## Etapa 2: leia o arquivo MPP
```java
Project project = new Project(dataDir + "HomeMovePlan.mpp");
```
 Esta linha de código lê o arquivo do Microsoft Project chamado`HomeMovePlan.mpp`.
## Etapa 3: definir opções de ImageSave
```java
ImageSaveOptions imageSaveOptions = new ImageSaveOptions(SaveFileFormat.Png);
imageSaveOptions.setReduceFooterGap(true);
imageSaveOptions.setRenderToSinglePage(false);
imageSaveOptions.setPageSize(PageSize.A0);
imageSaveOptions.setTimescale(Timescale.Days);
```
 Configure as opções de salvamento de imagem, definindo`ReduceFooterGap` para`true` para reduzir a lacuna entre a lista de tarefas e o rodapé.
## Etapa 4: salvar como imagem
```java
project.save(dataDir + "ReducingGapBetweenTasksListAndFooter_out.png", (SaveOptions) imageSaveOptions);
```
Salve o projeto como imagem com as opções configuradas.
## Etapa 5: definir PdfSaveOptions
```java
PdfSaveOptions pdfSaveOptions = new PdfSaveOptions();
pdfSaveOptions.setReduceFooterGap(true);
pdfSaveOptions.setSaveToSeparateFiles(true);
pdfSaveOptions.setPageSize(PageSize.A0);
pdfSaveOptions.setTimescale(Timescale.Days);
```
 Defina opções de salvamento de PDF, garantindo definir`ReduceFooterGap` para`true`.
## Etapa 6: Salvar como PDF
```java
project.save(dataDir + "ReducingGapBetweenTasksListAndFooter_out.pdf", (SaveOptions) pdfSaveOptions);
```
Salve o projeto em PDF com as opções configuradas.
## Etapa 7: definir HtmlSaveOptions
```java
HtmlSaveOptions htmlSaveOptions = new HtmlSaveOptions();
htmlSaveOptions.setReduceFooterGap(true); // definido como verdadeiro
htmlSaveOptions.setIncludeProjectNameInPageHeader(false);
htmlSaveOptions.setIncludeProjectNameInTitle(false);
htmlSaveOptions.setPageSize(PageSize.A0);
htmlSaveOptions.setTimescale(Timescale.Days);
```
 Especifique as opções de salvamento de HTML, configurando`ReduceFooterGap` para`true`.
## Etapa 8: Salvar como HTML
```java
project.save(dataDir + "ReducingGapBetweenTasksListAndFooter_out.html", htmlSaveOptions);
```
Salve o projeto como um arquivo HTML com as opções configuradas.

## Conclusão
Concluindo, reduzir a lacuna entre a lista de tarefas e o rodapé nos arquivos do Microsoft Project é um processo simples com Aspose.Tasks for Java. Seguindo as etapas descritas neste tutorial, você pode otimizar com eficiência o layout dos documentos do seu projeto.

## Perguntas frequentes

### P: O Aspose.Tasks é compatível com todas as versões do Microsoft Project?

R: Aspose.Tasks oferece suporte aos formatos Microsoft Project 2003-2019, garantindo compatibilidade entre várias versões.

### P: Posso personalizar a aparência do rodapé nos documentos do meu projeto?

R: Sim, Aspose.Tasks oferece amplas opções para personalizar a aparência dos rodapés, incluindo redução de lacunas e ajuste do posicionamento do conteúdo.

### P: O Aspose.Tasks oferece suporte para salvar projetos em formatos diferentes de PNG, PDF e HTML?

R: Sim, Aspose.Tasks oferece suporte a uma ampla variedade de formatos, incluindo XLSX, XML e MPP, entre outros.

### P: Existe uma versão de teste disponível para Aspose.Tasks?

 R: Sim, você pode baixar uma versão de avaliação gratuita do Aspose.Tasks em[aqui](https://releases.aspose.com/).

### P: Onde posso obter suporte se encontrar algum problema ao usar o Aspose.Tasks?

 R: Você pode obter assistência no fórum da comunidade Aspose.Tasks[aqui](https://forum.aspose.com/c/tasks/15).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
