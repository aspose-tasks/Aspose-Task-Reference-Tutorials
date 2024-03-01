---
title: Salve dados do MS Project no Excel em Aspose.Tasks
linktitle: Salvar dados no Excel em Aspose.Tasks
second_title: API Java Aspose.Tasks
description: Aprenda como salvar dados do Microsoft Project em arquivos Excel usando Aspose.Tasks para Java. Fácil integração para desenvolvedores Java.
type: docs
weight: 19
url: /pt/java/project-file-operations/save-data-to-excel/
---
## Introdução
Aspose.Tasks for Java é uma biblioteca poderosa que permite aos desenvolvedores trabalhar com arquivos do Microsoft Project programaticamente. Neste tutorial, iremos guiá-lo passo a passo pelo processo de salvar dados de um arquivo de projeto em um arquivo Excel.
## Pré-requisitos
Antes de começarmos, certifique-se de ter os seguintes pré-requisitos:
1. Java Development Kit (JDK): Certifique-se de ter o Java instalado em seu sistema. Você pode baixar e instalar a versão mais recente do JDK no site da Oracle.
2.  Biblioteca Aspose.Tasks para Java: Baixe a biblioteca Aspose.Tasks para Java no[Link para Download](https://releases.aspose.com/tasks/java/) e inclua-o em seu projeto Java.

## Importar pacotes
Primeiro, você precisa importar os pacotes necessários em seu código Java para trabalhar com Aspose.Tasks.
```java
import java.io.IOException;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
```

Vamos dividir o exemplo fornecido em várias etapas:
## Etapa 1: definir o caminho do diretório de dados
```java
String dataDir = "Your Data Directory";
```
 Substituir`"Your Data Directory"`pelo caminho para o diretório de dados onde o arquivo do projeto está localizado.
## Etapa 2: carregar o arquivo do projeto
```java
Project project = new Project(dataDir + "project5.mpp");
```
Esta linha de código carrega o arquivo de projeto denominado "project5.mpp" do diretório de dados especificado.
## Etapa 3: salve o projeto como XLSX
```java
project.save(dataDir + "project1.xlsx", SaveFileFormat.Xlsx);
```
 Aqui o`save` O método é usado para salvar o arquivo de projeto carregado como um arquivo Excel com o nome "project1.xlsx" no mesmo diretório de dados. Nós especificamos o`SaveFileFormat.Xlsx` parâmetro para salvá-lo no formato XLSX.

## Conclusão
Neste tutorial, aprendemos como salvar dados de um arquivo do Microsoft Project em um arquivo Excel usando Aspose.Tasks for Java. Seguindo as etapas fornecidas, você pode integrar perfeitamente essa funcionalidade em seus aplicativos Java.
## Perguntas frequentes
### Posso usar Aspose.Tasks for Java para manipular dados do projeto programaticamente?
Sim, Aspose.Tasks for Java oferece recursos abrangentes para manipular dados do projeto, incluindo leitura, gravação e modificação de arquivos do projeto.
### Existe um teste gratuito disponível para Aspose.Tasks for Java?
 Sim, você pode baixar uma versão de avaliação gratuita do Aspose.Tasks for Java em[aqui](https://releases.aspose.com/).
### Onde posso encontrar documentação para Aspose.Tasks for Java?
Você pode encontrar a documentação para Aspose.Tasks for Java[aqui](https://reference.aspose.com/tasks/java/).
### Como posso obter suporte para quaisquer problemas ou dúvidas relacionadas ao Aspose.Tasks for Java?
 Você pode obter suporte visitando o fórum Aspose.Tasks[aqui](https://forum.aspose.com/c/tasks/15).
### Posso comprar uma licença temporária para Aspose.Tasks for Java?
 Sim, você pode comprar uma licença temporária de[aqui](https://purchase.aspose.com/temporary-license/).