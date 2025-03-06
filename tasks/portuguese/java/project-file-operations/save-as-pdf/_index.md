---
title: Salvar como PDF em Aspose.Tasks
linktitle: Salvar como PDF em Aspose.Tasks
second_title: API Java Aspose.Tasks
description: Aprenda como converter arquivos de projeto em PDF usando Aspose.Tasks for Java. Passos simples para uma conversão eficiente.
weight: 17
url: /pt/java/project-file-operations/save-as-pdf/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Salvar como PDF em Aspose.Tasks

## Introdução
Neste tutorial, orientaremos você no processo de salvar um projeto como PDF usando Aspose.Tasks for Java. Com Aspose.Tasks, você pode converter com eficiência os arquivos do seu projeto em formato PDF, garantindo compatibilidade e facilidade de compartilhamento. Vamos mergulhar nas etapas:
## Pré-requisitos
Antes de começar, certifique-se de ter o seguinte:
1. Kit de desenvolvimento Java (JDK): certifique-se de ter o JDK instalado em seu sistema.
2.  Biblioteca Aspose.Tasks para Java: Baixe e instale a biblioteca Aspose.Tasks. Você pode encontrar o link para download[aqui](https://releases.aspose.com/tasks/java/).
3. Um arquivo de projeto: Tenha um arquivo de projeto (por exemplo, HomeMovePlan.mpp) pronto para ser convertido em PDF.

## Importar pacotes
```java
import com.aspose.tasks.PdfSaveOptions;
import com.aspose.tasks.PresentationFormat;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.SaveOptions;
import com.aspose.tasks.Timescale;
```
## Etapa 1: leia o arquivo do projeto de entrada
```java
String dataDir = "Your Data Directory";
Project project = new Project(dataDir + "HomeMovePlan.mpp");
```
 Certifique-se de substituir`"Your Data Directory"` pelo caminho para o diretório de dados que contém o arquivo do projeto.
## Passo 2: Salve o Projeto como PDF
```java
project.save(dataDir + "Project5.pdf", SaveFileFormat.Pdf);
```
Este trecho de código salva o projeto como um arquivo PDF com o nome "Project5.pdf".
## Etapa 3: Ajustar o conteúdo ao tamanho da célula
```java
Project project1 = new Project(dataDir + "project6.mpp");
SaveOptions o = new PdfSaveOptions();
o.setFitContent(true);
o.setTimescale(Timescale.Months);
o.setPresentationFormat(PresentationFormat.TaskUsage);
```
Aqui, definimos opções para salvar o PDF, incluindo ajuste de conteúdo, escala de tempo e formato de apresentação.
## Etapa 4: ocultar legendas
```java
o.setLegendOnEachPage(false);
```
Esta etapa oculta as legendas em cada página do PDF.
## Passo 5: Salve o Projeto com Opções Aplicadas
```java
project1.save(dataDir + "result_months_WithoutLegend.pdf", o);
```
Por fim, este código salva o projeto com as opções aplicadas em um arquivo PDF.

## Conclusão
Neste tutorial, aprendemos como usar Aspose.Tasks for Java para salvar um projeto como PDF. Seguindo estas etapas simples, você pode converter com eficiência os arquivos do seu projeto para fácil compartilhamento e distribuição.
## Perguntas frequentes
### P: O Aspose.Tasks é compatível com todas as versões do Java?
R: Sim, Aspose.Tasks oferece suporte a versões Java a partir do JDK 6 e superior.
### P: Posso personalizar a aparência da saída PDF?
R: Absolutamente! Aspose.Tasks oferece várias opções para personalizar a saída do PDF de acordo com suas necessidades.
### P: O Aspose.Tasks oferece suporte a outros formatos de arquivo para conversão?
R: Sim, Aspose.Tasks oferece suporte a uma ampla variedade de formatos de arquivo, incluindo MPP, XML, XLSX e muito mais.
### P: Existe uma versão de teste disponível para Aspose.Tasks?
 R: Sim, você pode obter uma avaliação gratuita do Aspose.Tasks em[aqui](https://releases.aspose.com/).
### P: Onde posso obter suporte para Aspose.Tasks?
 R: Para suporte e assistência, você pode visitar o[Fórum Aspose.Tasks](https://forum.aspose.com/c/tasks/15).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
