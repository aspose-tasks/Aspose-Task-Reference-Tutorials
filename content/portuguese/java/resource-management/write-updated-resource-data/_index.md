---
title: Escreva dados de recursos atualizados em Aspose.Tasks
linktitle: Escreva dados de recursos atualizados em Aspose.Tasks
second_title: API Java Aspose.Tasks
description: Aprenda como atualizar facilmente dados de recursos em arquivos do MS Project usando Aspose.Tasks for Java.
type: docs
weight: 21
url: /pt/java/resource-management/write-updated-resource-data/
---
## Introdução
Neste tutorial, orientaremos você na atualização de dados de recursos do Microsoft Project usando Aspose.Tasks para Java. Aspose.Tasks é uma API Java poderosa que permite manipular arquivos do Microsoft Project sem exigir que o Microsoft Project esteja instalado em seu sistema.

## Pré-requisitos

Antes de começarmos, certifique-se de ter o seguinte:

1. Java Development Kit (JDK) instalado em seu sistema.
2.  Aspose.Tasks para biblioteca Java. Você pode baixá-lo em[aqui](https://releases.aspose.com/tasks/java/).
3. Conhecimento básico de programação Java.

## Importar pacotes

Primeiro, você precisa importar os pacotes necessários para trabalhar com Aspose.Tasks em seu código Java. Adicione as seguintes instruções de importação ao seu arquivo Java:

```java
import com.aspose.tasks.Project;
import com.aspose.tasks.Resource;
import com.aspose.tasks.Rsc;
import com.aspose.tasks.SaveFileFormat;
```

## Etapa 1: configure seu diretório de dados

Defina o diretório onde seus arquivos de dados estão localizados:

```java
String dataDir = "Your Data Directory";
```

## Etapa 2: especificar arquivos de entrada e saída

Defina os caminhos para o arquivo de entrada do MS Project e o arquivo atualizado resultante:

```java
String file = dataDir + "ResourceWithExtAttribs.xml"; // Arquivo de teste com um rsc para atualizar
String resultFile = dataDir + "OutputMPP.mpp"; // Arquivo para escrever o projeto de teste
```

## Etapa 3: carregar o projeto

 Carregue o arquivo do MS Project em um`Project` objeto:

```java
Project project = new Project(file);
```

## Etapa 4: adicionar um recurso e definir atributos

Adicione um novo recurso ao projeto e defina seus atributos como taxa padrão, taxa de horas extras e grupo:

```java
Resource rsc = project.getResources().add("Rsc");
rsc.set(Rsc.STANDARD_RATE, BigDecimal.valueOf(30));
rsc.set(Rsc.OVERTIME_RATE, BigDecimal.valueOf(45));
rsc.set(Rsc.GROUP, "Workgroup1");
```

## Etapa 5: salve o projeto

Salve o projeto atualizado com os dados do recurso modificados:

```java
project.save(resultFile, SaveFileFormat.Mpp);
```

## Conclusão

Neste tutorial, demonstramos como atualizar dados de recursos do MS Project usando Aspose.Tasks for Java. Seguindo essas etapas, você pode manipular com eficiência as informações de recursos em seus arquivos do MS Project de maneira programática.

## Perguntas frequentes

### Q1: Posso atualizar vários recursos no mesmo projeto usando Aspose.Tasks for Java?

A1: Sim, você pode atualizar vários recursos iterando por meio deles e definindo seus atributos de acordo.

### Q2: O Aspose.Tasks oferece suporte a outros formatos de arquivo além do MS Project?

A2: Sim, Aspose.Tasks oferece suporte a vários formatos de arquivo, incluindo XML, MPP e muito mais.

### Q3: O Aspose.Tasks é compatível com diferentes versões do Java?

A3: Aspose.Tasks é compatível com Java versões 6 e superiores.

### Q4: Posso realizar outras operações em arquivos do MS Project com Aspose.Tasks?

A4: Sim, você pode realizar uma ampla variedade de operações, como ler, escrever e manipular tarefas, recursos e calendários.

### P5: Onde posso encontrar ajuda ou suporte adicional para Aspose.Tasks?

 A5: Você pode visitar o[Fórum Aspose.Tasks](https://forum.aspose.com/c/tasks/15) para qualquer assistência ou dúvida.
