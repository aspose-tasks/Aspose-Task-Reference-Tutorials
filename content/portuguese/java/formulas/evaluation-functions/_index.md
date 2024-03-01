---
title: Funções de avaliação de suporte em fórmulas Aspose.Tasks
linktitle: Funções de avaliação de suporte em fórmulas Aspose.Tasks
second_title: API Java Aspose.Tasks
description: Aprenda como oferecer suporte à avaliação de funções do MS Project em fórmulas Aspose.Tasks usando Java. Aumente sua produtividade com Aspose.Tasks.
type: docs
weight: 10
url: /pt/java/formulas/evaluation-functions/
---

## Introdução
Aspose.Tasks for Java é uma biblioteca poderosa que permite aos desenvolvedores manipular arquivos do Microsoft Project programaticamente. Um de seus principais recursos é a capacidade de oferecer suporte à avaliação de funções do MS Project nas fórmulas Aspose.Tasks. Esse recurso permite que os usuários executem cálculos e análises complexos diretamente em seus aplicativos Java.
## Pré-requisitos
Antes de começar a integrar funções do MS Project nas fórmulas Aspose.Tasks, certifique-se de ter o seguinte:
1. Ambiente de desenvolvimento Java: certifique-se de ter o Java instalado em seu sistema junto com um IDE compatível para desenvolvimento Java, como IntelliJ IDEA ou Eclipse.
2.  Biblioteca Aspose.Tasks para Java: Baixe e inclua a biblioteca Aspose.Tasks para Java em seu projeto Java. Você pode baixá-lo no[Página de download do Aspose.Tasks para Java](https://releases.aspose.com/tasks/java/).
## Importar pacotes
Para começar, importe os pacotes necessários em sua classe Java para utilizar as funcionalidades do Aspose.Tasks:
```java
import com.aspose.tasks.*;
```

## Etapa 1: Crie um novo objeto de projeto
 Primeiro, crie um novo`Project`objeto para trabalhar:
```java
Project project = new Project();
```
Isso inicializa um novo projeto vazio.
## Etapa 2: definir um atributo estendido para tarefas
A seguir, defina um atributo estendido para tarefas. Este atributo conterá dados personalizados associados às tarefas:
```java
ExtendedAttributeDefinition attr = ExtendedAttributeDefinition.createTaskDefinition(CustomFieldType.Number, ExtendedAttributeTask.Number1, "Sine");
```
 Aqui, criamos um atributo estendido do tipo`Number` com o nome "Sine" para tarefas.
## Etapa 3: adicionar o atributo estendido ao projeto
Adicione a definição de atributo estendido à lista de atributos estendidos do projeto:
```java
project.getExtendedAttributes().add(attr);
```
Isso adiciona o atributo personalizado ao projeto.
## Etapa 4: crie uma nova tarefa
Agora, vamos criar uma nova tarefa dentro do projeto:
```java
Task task = project.getRootTask().getChildren().add("Task");
```
Isso adiciona uma nova tarefa chamada "Tarefa" ao projeto.
## Etapa 5: associar o atributo estendido à tarefa
Associe o atributo estendido criado anteriormente à tarefa:
```java
ExtendedAttribute a = attr.createExtendedAttribute();
task.getExtendedAttributes().add(a);
```
Isso associa o atributo estendido "Sine" à tarefa.

## Conclusão
Concluindo, a integração das funções do MS Project nas fórmulas Aspose.Tasks em Java é um processo simples. Seguindo as etapas fornecidas, você pode utilizar com eficácia os poderosos recursos do Aspose.Tasks for Java para manipular e analisar arquivos do Microsoft Project programaticamente.
## Perguntas frequentes
### P: O Aspose.Tasks for Java pode lidar com fórmulas complexas do MS Project?
R: Sim, Aspose.Tasks for Java oferece suporte à avaliação de uma ampla variedade de funções do MS Project, permitindo cálculos complexos em aplicativos Java.
### P: O Aspose.Tasks for Java é compatível com diferentes versões de arquivos do Microsoft Project?
R: Sim, Aspose.Tasks for Java oferece suporte a várias versões de arquivos do Microsoft Project, incluindo formatos MPP, MPT e XML.
### P: Posso experimentar o Aspose.Tasks for Java antes de comprar?
 R: Sim, você pode baixar uma versão de avaliação gratuita do Aspose.Tasks for Java no site[aqui](https://purchase.aspose.com/buy).
### P: Como posso obter suporte para Aspose.Tasks for Java?
R: Você pode obter suporte no fórum da comunidade Aspose.Tasks[aqui](https://forum.aspose.com/c/tasks/15).
### P: Existe uma licença temporária disponível para Aspose.Tasks for Java?
 R: Sim, você pode obter uma licença temporária para fins de teste no site Aspose[aqui](https://purchase.aspose.com/temporary-license/).