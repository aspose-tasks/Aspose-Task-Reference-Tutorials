---
title: Recuperar exceções de calendário com Aspose.Tasks
linktitle: Recuperar exceções de calendário com Aspose.Tasks
second_title: API Java Aspose.Tasks
description: Aprenda como recuperar exceções de calendário do MS Project usando Aspose.Tasks for Java. Tutorial passo a passo para integração perfeita.
type: docs
weight: 13
url: /pt/java/calendar-exceptions/retrieve/
---
## Introdução
Neste tutorial, exploraremos como recuperar exceções de calendário do MS Project usando a biblioteca Aspose.Tasks para Java. Aspose.Tasks é uma ferramenta poderosa que permite aos desenvolvedores manipular arquivos do Microsoft Project programaticamente. Iremos guiá-lo passo a passo pelo processo, dividindo cada exemplo em várias etapas para facilitar o entendimento.
## Pré-requisitos
Antes de começarmos, certifique-se de ter os seguintes pré-requisitos:
1. Kit de desenvolvimento Java (JDK): certifique-se de ter o JDK instalado em seu sistema.
2.  Aspose.Tasks para Java: Baixe e instale Aspose.Tasks para Java em[aqui](https://releases.aspose.com/tasks/java/).
3. Ambiente de Desenvolvimento Integrado (IDE): Você pode usar qualquer IDE de sua escolha, como IntelliJ IDEA ou Eclipse.

## Importar pacotes
Primeiro, você precisa importar os pacotes necessários para trabalhar com Aspose.Tasks:
```java
import com.aspose.tasks.*;
```
## Etapa 1: configure seu diretório de dados
```java
// O caminho para o diretório de documentos.
String dataDir = "Your Data Directory";
```
 Certifique-se de substituir`"Your Data Directory"` com o caminho para o diretório que contém o arquivo do MS Project.
## Etapa 2: carregar o arquivo do MS Project
```java
Project project = new Project(dataDir + "project.mpp");
```
 Esta linha inicializa um novo`Project` objeto carregando o arquivo do MS Project especificado pelo caminho.
## Etapa 3: recuperar exceções de calendário
```java
for (Calendar cal : project.getCalendars()) {
    for (CalendarException calExc : cal.getExceptions()) {
        System.out.println("From: " + calExc.getFromDate().toString());
        System.out.println("To: " + calExc.getToDate().toString());
    }
}
```
Aqui, iteramos em cada calendário do projeto e, em seguida, em cada exceção de calendário desse calendário. Imprimimos as datas de início e término de cada exceção.

## Conclusão
Neste tutorial, aprendemos como recuperar exceções de calendário do MS Project usando Aspose.Tasks for Java. Seguindo estas etapas simples, você pode integrar perfeitamente essa funcionalidade em seus aplicativos Java.
## perguntas frequentes
### O Aspose.Tasks pode lidar com diferentes versões de arquivos do MS Project?
Sim, Aspose.Tasks suporta várias versões de arquivos MS Project, incluindo formatos MPP, MPT e XML.
### Existe um teste gratuito disponível para Aspose.Tasks?
 Sim, você pode baixar uma avaliação gratuita do Aspose.Tasks em[aqui](https://releases.aspose.com/).
### Onde posso encontrar documentação para Aspose.Tasks for Java?
 Você pode consultar a documentação[aqui](https://reference.aspose.com/tasks/java/).
### Como posso obter suporte para Aspose.Tasks?
 Você pode obter suporte no fórum da comunidade[aqui](https://forum.aspose.com/c/tasks/15).
### Existe uma opção para licenças temporárias para Aspose.Tasks?
 Sim, você pode obter licenças temporárias de[aqui](https://purchase.aspose.com/temporary-license/).