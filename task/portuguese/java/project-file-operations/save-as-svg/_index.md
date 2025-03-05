---
title: Converter MS Project para SVG em Java
linktitle: Salvar como SVG em Aspose.Tasks
second_title: API Java Aspose.Tasks
description: Aprenda como salvar arquivos do Microsoft Project como SVG em Java usando a biblioteca Aspose.Tasks. Guia passo a passo com exemplos de código.
type: docs
weight: 18
url: /pt/java/project-file-operations/save-as-svg/
---
## Introdução
Aspose.Tasks for Java é uma biblioteca poderosa para trabalhar com arquivos de gerenciamento de projetos, permitindo aos desenvolvedores manipular dados do projeto, realizar várias operações e gerar relatórios de forma eficiente. Neste tutorial, exploraremos como salvar um projeto como SVG usando Aspose.Tasks for Java. SVG (Scalable Vector Graphics) é um formato amplamente utilizado para exibição de gráficos vetoriais na web, proporcionando escalabilidade e renderização de alta qualidade.
## Pré-requisitos
Antes de começarmos, certifique-se de ter o seguinte:
### Ambiente de Desenvolvimento Java
Certifique-se de ter o Java Development Kit (JDK) instalado em seu sistema. Você pode baixar e instalar o JDK no site da Oracle.
### Aspose.Tasks para biblioteca Java
 Baixe e instale a biblioteca Aspose.Tasks for Java do site. Você pode encontrar o link para download na documentação fornecida[aqui](https://releases.aspose.com/tasks/java/).

## Importar pacotes
Primeiro, você precisa importar os pacotes necessários em seu programa Java para trabalhar com as funcionalidades do Aspose.Tasks.

```java
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.SaveOptions;
import com.aspose.tasks.SvgOptions;
import com.aspose.tasks.Timescale;
import java.io.IOException;
```

Agora vamos dividir o exemplo fornecido em várias etapas:
## Etapa 2: definir o diretório de dados
```java
String dataDir = "Your Data Directory";
```
 Substituir`"Your Data Directory"`com o caminho para o diretório onde o arquivo do projeto está localizado.
## Etapa 3: carregar o arquivo do projeto
```java
Project project = new Project(dataDir + "HomeMovePlan.mpp");
```
Esta etapa carrega o arquivo de projeto denominado "HomeMovePlan.mpp" do diretório de dados especificado.
## Etapa 4: salvar como SVG
```java
project.save(dataDir + "project5.svg", SaveFileFormat.Svg);
```
Esta etapa salva o projeto carregado no formato SVG com o nome "project5.svg" no diretório de dados especificado.

## Conclusão
Neste tutorial, aprendemos como salvar um projeto como SVG usando Aspose.Tasks for Java. Seguindo as etapas fornecidas, você pode converter arquivos de projeto com eficiência em formato SVG, permitindo integração perfeita com aplicativos baseados na web ou ferramentas de visualização.
## Perguntas frequentes
### O Aspose.Tasks for Java é compatível com todas as versões de arquivos do Microsoft Project?
Sim, Aspose.Tasks for Java oferece suporte a várias versões de arquivos do Microsoft Project, incluindo formatos MPP, MPT e XML.
### Posso personalizar a aparência da saída SVG?
Sim, você pode personalizar a aparência da saída SVG ajustando parâmetros como fontes, cores e configurações de layout.
### O Aspose.Tasks for Java requer uma licença para uso comercial?
 Sim, é necessária uma licença válida para uso comercial do Aspose.Tasks for Java. Você pode obter uma licença no site[aqui](https://purchase.aspose.com/temporary-license/).
### Posso experimentar o Aspose.Tasks for Java antes de comprar?
 Sim, você pode solicitar uma avaliação gratuita do Aspose.Tasks for Java no site[aqui](https://purchase.aspose.com/buy) para avaliar seus recursos e capacidades.
### Onde posso obter suporte para Aspose.Tasks for Java?
 Você pode obter suporte para Aspose.Tasks for Java visitando o fórum[aqui](https://forum.aspose.com/c/tasks/15), onde você pode tirar dúvidas e interagir com a comunidade.