---
title: Leia as propriedades da moeda em projetos Aspose.Tasks
linktitle: Leia as propriedades da moeda em projetos Aspose.Tasks
second_title: API Java Aspose.Tasks
description: Aprenda como extrair informações monetárias de arquivos do MS Project usando Aspose.Tasks para Java. Guia passo a passo fornecido.
type: docs
weight: 10
url: /pt/java/currency-properties/read-properties/
---
## Introdução
Neste tutorial, aprenderemos como utilizar Aspose.Tasks for Java para ler propriedades de moeda de arquivos do Microsoft Project. Aspose.Tasks é uma API Java poderosa que permite aos desenvolvedores manipular documentos do Microsoft Project sem exigir a instalação do Microsoft Project. Seguindo as etapas descritas abaixo, você poderá extrair informações relacionadas à moeda sem esforço.
## Pré-requisitos
Antes de prosseguir com este tutorial, certifique-se de ter os seguintes pré-requisitos:
1. Java Development Kit (JDK): Certifique-se de ter o JDK instalado em seu sistema.
2.  Aspose.Tasks for Java JAR: Baixe a biblioteca Aspose.Tasks for Java em[aqui](https://releases.aspose.com/tasks/java/) e inclua-o em seu projeto Java.
## Importar pacotes
Comece importando os pacotes necessários para sua classe Java:
```java
import com.aspose.tasks.*;
```
## Etapa 1: configure o diretório do seu projeto
Primeiro, configure o diretório do projeto onde o arquivo do Microsoft Project está localizado. Você pode definir esse caminho de diretório da seguinte maneira:
```java
String dataDir = "Your Data Directory";
```
 Substituir`"Your Data Directory"` com o caminho real para o diretório do seu projeto.
## Etapa 2: criar uma instância do leitor de projeto
 Instanciar um`Project` objeto fornecendo o caminho para o arquivo do Microsoft Project:
```java
Project project = new Project(dataDir + "project.mpp");
```
 Certifique-se de substituir`"project.mpp"` com o nome do seu arquivo MS Project.
## Etapa 3: exibir propriedades da moeda
Recuperar e exibir propriedades de moeda do arquivo de projeto:
```java
System.out.println("Currency Code : " + project.get(Prj.CURRENCY_CODE).toString());
System.out.println("<br>Currency Digits : " + project.get(Prj.CURRENCY_DIGITS).toString());
System.out.println("<br>Currency Symbol : " + project.get(Prj.CURRENCY_SYMBOL).toString());
System.out.println("Currency Symbol Position" + project.get(Prj.CURRENCY_SYMBOL_POSITION).toString());
```
Este segmento de código busca informações como código de moeda, dígitos, símbolo e posição do símbolo do arquivo MS Project e as imprime no console.
## Etapa 4: conclusão do processo
Por último, imprima uma mensagem indicando a conclusão bem-sucedida do processo:
```java
System.out.println("Process completed Successfully");
```
## Conclusão
Neste tutorial, exploramos como ler propriedades de moeda de arquivos do Microsoft Project usando Aspose.Tasks para Java. Seguindo as etapas descritas, você pode extrair facilmente informações relacionadas à moeda de seus arquivos de projeto de forma programática, permitindo uma integração perfeita em seus aplicativos Java.
## Perguntas frequentes
### P: O Aspose.Tasks é compatível com todas as versões do Microsoft Project?
R: Aspose.Tasks oferece suporte a várias versões do Microsoft Project, incluindo arquivos MPP gerados pelo MS Project 2003-2021.
### P: Posso modificar as propriedades da moeda usando Aspose.Tasks?
R: Sim, Aspose.Tasks permite ler e modificar propriedades de moeda em arquivos do MS Project programaticamente.
### P: O Aspose.Tasks é adequado para uso comercial?
 R: Sim, Aspose.Tasks é uma biblioteca comercial projetada para uso profissional. Você pode comprar uma licença[aqui](https://purchase.aspose.com/buy).
### P: O Aspose.Tasks oferece uma avaliação gratuita?
 R: Sim, você pode aproveitar uma avaliação gratuita do Aspose.Tasks em[aqui](https://releases.aspose.com/).
### P: Onde posso procurar ajuda ou suporte para Aspose.Tasks?
 R: Você pode visitar o fórum Aspose.Tasks[aqui](https://forum.aspose.com/c/tasks/15) para qualquer assistência ou dúvida.