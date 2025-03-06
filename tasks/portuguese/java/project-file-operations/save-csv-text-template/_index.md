---
title: Salvar como CSV, texto e modelo em Aspose.Tasks
linktitle: Salvar como CSV, texto e modelo em Aspose.Tasks
second_title: API Java Aspose.Tasks
description: Aprenda como salvar arquivos do Microsoft Project nos formatos CSV, Texto e Modelo usando Aspose.Tasks para Java.
weight: 16
url: /pt/java/project-file-operations/save-csv-text-template/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Salvar como CSV, texto e modelo em Aspose.Tasks

## Introdução
Neste tutorial, exploraremos como salvar arquivos de projeto em vários formatos como CSV, Texto e Modelo usando Aspose.Tasks para Java. Aspose.Tasks é uma biblioteca Java poderosa que permite aos desenvolvedores trabalhar com arquivos do Microsoft Project sem a necessidade de instalação do Microsoft Project.
## Pré-requisitos
Antes de começarmos, certifique-se de ter os seguintes pré-requisitos:
1. Java Development Kit (JDK) instalado em seu sistema.
2.  Biblioteca Aspose.Tasks para Java baixada e configurada em seu projeto Java. Você pode baixá-lo em[aqui](https://releases.aspose.com/tasks/java/).
3. Conhecimento básico da linguagem de programação Java.

## Importar pacotes
Primeiro, você precisa importar os pacotes necessários em seu arquivo Java:
```java
import java.io.IOException;
import com.aspose.tasks.*;
```
## Salvar projeto como CSV
Vamos detalhar as etapas para salvar um projeto como CSV:
### Etapa 1: carregar o projeto
```java
String projectName = "YourProject.mpp";
Project project = new Project(projectName);
```
### Etapa 2: salvar como CSV
```java
String csvFileName = "output.csv";
project.save(csvFileName, com.aspose.tasks.SaveFileFormat.CSV);
```
## Salvar projeto como texto
Veja como você pode salvar um projeto como Texto:
### Etapa 1: carregar o projeto
```java
String projectName = "YourProject.mpp";
Project project = new Project(projectName);
```
### Etapa 2: salvar como texto
```java
String textFileName = "output.txt";
project.save(textFileName, com.aspose.tasks.SaveFileFormat.TEXT);
```
## Salvar projeto como modelo
Salvar um projeto como modelo envolve as seguintes etapas:
### Etapa 1: carregar o projeto
```java
String projectName = "YourProject.mpp";
Project project = new Project(projectName);
```
### Etapa 2: definir opções de modelo
```java
SaveTemplateOptions options = new SaveTemplateOptions();
options.setRemoveActualValues(true);
options.setRemoveBaselineValues(true);
```
### Etapa 3: Salvar como modelo
```java
String templateName = "output.mpt";
project.saveAsTemplate(templateName, options);
```

## Conclusão
Neste tutorial, aprendemos como salvar arquivos do Microsoft Project como CSV, texto e modelo usando Aspose.Tasks para Java. Com essas etapas simples, você pode gerenciar com eficiência os arquivos do seu projeto em vários formatos, aumentando sua produtividade como desenvolvedor Java.
## Perguntas frequentes
### P: O Aspose.Tasks for Java pode lidar com arquivos de projeto complexos?
R: Absolutamente! Aspose.Tasks for Java pode lidar com projetos de complexidade variada com facilidade, fornecendo suporte abrangente para formatos de arquivo do Microsoft Project.
### P: Existe uma versão de teste disponível para Aspose.Tasks for Java?
 R: Sim, você pode obter uma avaliação gratuita do Aspose.Tasks for Java em[aqui](https://releases.aspose.com/).
### P: Onde posso encontrar suporte para Aspose.Tasks for Java?
 R: Você pode visitar o[Fórum Aspose.Tasks](https://forum.aspose.com/c/tasks/15) para qualquer assistência ou dúvida sobre Aspose.Tasks for Java.
### P: Posso adquirir uma licença temporária do Aspose.Tasks for Java?
 R: Sim, você pode comprar uma licença temporária de[aqui](https://purchase.aspose.com/temporary-license/), permitindo avaliar todo o potencial da biblioteca.
### P: O Aspose.Tasks for Java é compatível com diferentes sistemas operacionais?
R: Sim, Aspose.Tasks for Java é compatível com vários sistemas operacionais, incluindo Windows, macOS e Linux.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
