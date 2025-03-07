---
title: Escreva o resumo do projeto MPP em Aspose.Tasks
linktitle: Escreva o resumo do projeto MPP em Aspose.Tasks
second_title: API Java Aspose.Tasks
description: Aprenda como escrever resumos de projetos MPP em Java usando Aspose.Tasks. Defina e recupere informações do projeto sem esforço.
weight: 27
url: /pt/java/project-file-operations/write-mpp-project-summary/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Escreva o resumo do projeto MPP em Aspose.Tasks

## Introdução
Neste tutorial, aprenderemos como utilizar Aspose.Tasks for Java para escrever resumos de projetos MPP. Aspose.Tasks é uma biblioteca Java poderosa para trabalhar com arquivos do Microsoft Project. Seguindo as etapas descritas abaixo, você poderá definir e recuperar várias informações resumidas sobre um projeto usando esta biblioteca.
## Pré-requisitos
Antes de começarmos, certifique-se de ter os seguintes pré-requisitos:
1. Java Development Kit (JDK): Certifique-se de ter o JDK instalado em seu sistema.
2.  Aspose.Tasks para Java: Baixe e instale a biblioteca Aspose.Tasks para Java. Você pode baixá-lo em[aqui](https://releases.aspose.com/tasks/java/).
3. Ambiente de Desenvolvimento Integrado (IDE): Escolha seu IDE preferido para desenvolvimento Java, como IntelliJ IDEA, Eclipse ou NetBeans.

## Importar pacotes
Primeiramente, importe os pacotes necessários para sua classe Java:
```java
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import java.util.Calendar;
```
## Etapa 1: configurar o projeto e definir as informações resumidas
```java
// O caminho para o diretório de documentos.
String dataDir = "Your Data Directory";
//Inicialize um novo objeto Projeto com o caminho para o arquivo do seu projeto
Project project = new Project(dataDir + "project.mpp");
// Defina informações resumidas sobre o projeto
project.set(Prj.AUTHOR, "Author");
project.set(Prj.LAST_AUTHOR, "Last Author");
project.set(Prj.REVISION, 15);
project.set(Prj.KEYWORDS, "MSP Aspose");
project.set(Prj.COMMENTS, "Comments");
// Definir data de criação do projeto
Calendar cal = Calendar.getInstance();
cal.set(2014, Calendar.FEBRUARY, 15, 0, 0, 0);
project.set(Prj.CREATION_DATE, cal.getTime());
// Defina palavras-chave para o projeto
project.set(Prj.KEYWORDS, "MPP Aspose");
// Definir a última data impressa do projeto
cal.set(2014, Calendar.MARCH, 16, 0, 0, 0);
project.set(Prj.LAST_PRINTED, cal.getTime());
```
## Etapa 2: Salvar as informações do resumo do projeto
```java
// Salve o projeto novamente no formato MPP
project.save(dataDir + "MppAspose.xml", SaveFileFormat.Xml);
// Exibir uma mensagem de sucesso
System.out.println("Process completed Successfully");
```
## Etapa 3: Leia as informações resumidas do projeto
```java
// Lendo informações resumidas do projeto
project = new Project(dataDir + "MppAspose.xml");
// Imprimir autor do projeto
System.out.println("Author: " + project.get(Prj.AUTHOR));
// Imprimir último autor do projeto
System.out.println("Last Author: " + project.get(Prj.LAST_AUTHOR));
// Imprimir o número de revisão do projeto
System.out.println("Revision: " + project.get(Prj.REVISION));
// Imprimir palavras-chave do projeto
System.out.println("Keywords: " + project.get(Prj.KEYWORDS));
// Imprimir comentários do projeto
System.out.println("Comments: " + project.get(Prj.COMMENTS));
// Imprimir data de criação do projeto
System.out.println("Creation Date: " + project.get(Prj.CREATION_DATE).toString());
// Imprimir palavras-chave do projeto (novamente)
System.out.println("Keywords: " + project.get(Prj.KEYWORDS));
// Imprimir a última data impressa do projeto
System.out.println("Last Printed: " + project.get(Prj.LAST_PRINTED).toString());
```

## Conclusão
Neste tutorial, abordamos como escrever resumos de projetos MPP usando Aspose.Tasks para Java. Seguindo essas etapas, você pode definir e recuperar com eficiência várias informações resumidas sobre os arquivos do seu projeto. Aspose.Tasks simplifica o processo de trabalho com arquivos do Microsoft Project em aplicativos Java, oferecendo funcionalidade robusta e facilidade de uso.
## Perguntas frequentes
### P: Posso usar Aspose.Tasks for Java com outras bibliotecas Java?
R: Sim, Aspose.Tasks for Java pode ser perfeitamente integrado com outras bibliotecas Java para aprimorar seus recursos de gerenciamento de projetos.
### P: Existe uma versão de teste disponível para Aspose.Tasks for Java?
 R: Sim, você pode baixar uma versão de avaliação gratuita em[aqui](https://releases.aspose.com/).
### P: Com que frequência o Aspose.Tasks for Java é atualizado?
R: Aspose.Tasks for Java é atualizado regularmente para garantir compatibilidade com as versões mais recentes dos arquivos Java e Microsoft Project.
### P: Posso personalizar ainda mais as informações do resumo do projeto?
R: Com certeza, Aspose.Tasks for Java oferece amplas opções para personalizar informações de resumo do projeto de acordo com seus requisitos específicos.
### P: Onde posso obter suporte para Aspose.Tasks for Java?
R: Você pode obter suporte no fórum da comunidade Aspose.Tasks[aqui](https://forum.aspose.com/c/tasks/15).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
