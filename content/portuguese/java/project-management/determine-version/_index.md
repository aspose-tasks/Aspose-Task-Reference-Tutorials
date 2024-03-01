---
title: Determine a versão do MS Project com Aspose.Tasks
linktitle: Determine a versão do projeto com Aspose.Tasks
second_title: API Java Aspose.Tasks
description: Aprenda como determinar a versão dos arquivos do MS Project programaticamente usando Aspose.Tasks para Java. Guia passo a passo com exemplos de código.
type: docs
weight: 12
url: /pt/java/project-management/determine-version/
---
## Introdução
Este tutorial irá guiá-lo através do uso do Aspose.Tasks for Java para determinar a versão de um arquivo do MS Project passo a passo. Aspose.Tasks é uma API Java poderosa que permite aos desenvolvedores manipular arquivos do Microsoft Project sem exigir a instalação do Microsoft Project.
## Pré-requisitos
Antes de começarmos, certifique-se de ter o seguinte:
1. Java Development Kit (JDK): Certifique-se de ter o JDK instalado em seu sistema.
2.  Arquivo JAR Aspose.Tasks for Java: Faça download da biblioteca Aspose.Tasks for Java no[local na rede Internet](https://releases.aspose.com/tasks/java/) e adicione-o ao seu projeto Java.
3. Arquivo MS Project: Prepare um arquivo MS Project (formato XML) para teste.

## Importar pacotes
Antes de mergulhar no código, vamos importar os pacotes necessários:
```java
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
```
## Etapa 1: configurar o projeto
```java
// O caminho para o diretório de documentos.
String dataDir = "Your Data Directory";
```
 Substituir`"Your Data Directory"` com o caminho para o diretório que contém o arquivo do MS Project.
## Etapa 2: carregar o projeto
```java
Project project = new Project(dataDir + "input.xml");
```
 Substituir`"input.xml"` com o nome do seu arquivo MS Project.
## Etapa 3: Determinar a Versão do Projeto
```java
//Exibir propriedade da versão do projeto
System.out.println("Project Version : " + project.get(Prj.SAVE_VERSION));
System.out.println("Last Saved : " + project.get(Prj.LAST_SAVED));
```
Este trecho de código recupera e imprime a versão e a última data salva do arquivo MS Project.
## Etapa 4: exibir resultado
```java
//Exibir resultado da conversão.
System.out.println("Process completed Successfully");
```
Esta linha indica a conclusão do processo.

## Conclusão
Neste tutorial, você aprendeu como determinar a versão de um arquivo MS Project usando Aspose.Tasks for Java. Seguindo o guia passo a passo, você pode trabalhar de forma eficiente com arquivos do MS Project em seus aplicativos Java sem complicações.

## Perguntas frequentes
### P: Posso usar Aspose.Tasks com outras linguagens de programação?
R: Sim, Aspose.Tasks oferece suporte a várias linguagens de programação, incluindo .NET, Java e C++.
### P: O Aspose.Tasks é adequado para projetos de grande escala?
R: Com certeza, o Aspose.Tasks foi projetado para lidar com projetos de qualquer tamanho com facilidade.
### P: Posso personalizar os dados do projeto usando Aspose.Tasks?
R: Sim, você pode manipular dados do projeto, modificar tarefas, recursos e muito mais usando Aspose.Tasks.
### P: O Aspose.Tasks requer a instalação do Microsoft Project?
R: Não, o Aspose.Tasks funciona de forma independente e não requer a instalação do Microsoft Project.
### P: O suporte técnico está disponível para Aspose.Tasks?
 R: Sim, você pode obter suporte técnico no fórum Aspose.Tasks em[aqui](https://forum.aspose.com/c/tasks/15).