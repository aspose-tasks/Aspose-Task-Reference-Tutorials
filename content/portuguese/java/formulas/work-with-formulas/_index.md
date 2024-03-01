---
title: Fórmulas do MS Project com Aspose.Tasks para Java
linktitle: Trabalhe com fórmulas em Aspose.Tasks
second_title: API Java Aspose.Tasks
description: Aprenda como manipular arquivos do MS Project em Java usando a biblioteca Aspose.Tasks. Crie, modifique e calcule atributos com facilidade.
type: docs
weight: 11
url: /pt/java/formulas/work-with-formulas/
---
## Introdução
Neste tutorial, nos aprofundaremos no trabalho com fórmulas do MS Project usando Aspose.Tasks para Java. Aspose.Tasks é uma biblioteca poderosa que permite aos desenvolvedores manipular arquivos do Microsoft Project programaticamente. Com seus amplos recursos, você pode criar, ler, modificar e converter facilmente arquivos de projeto em aplicativos Java.
## Pré-requisitos
Antes de começarmos, certifique-se de ter os seguintes pré-requisitos configurados:
### Ambiente de Desenvolvimento Java
Certifique-se de ter um Java Development Kit (JDK) instalado em seu sistema. Você pode baixar e instalar o JDK mais recente no site da Oracle.
### Biblioteca Aspose.Tasks
Você precisa ter a biblioteca Aspose.Tasks adicionada ao seu projeto Java. Você pode baixar a biblioteca do[Página de download do Aspose.Tasks para Java](https://releases.aspose.com/tasks/java/) e inclua-o nas dependências do seu projeto.

## Importar pacotes
Antes de mergulhar nos exemplos, importe os pacotes necessários para o seu código Java:
```java
import com.aspose.tasks.*;
import java.util.Calendar;
```

Vamos dividir o exemplo fornecido em várias etapas:
## Etapa 1: Crie um projeto de teste com campo personalizado
```java
Project project = CreateTestProjectWithCustomField();
```
 Primeiro, crie um projeto de teste com um campo personalizado usando o`CreateTestProjectWithCustomField()` método. Este método retornará um objeto Project representando o projeto recém-criado.
## Etapa 2: Definir uma definição de atributo estendido
```java
ExtendedAttributeDefinition attr = project.getExtendedAttributes().get(0);
attr.setAlias("Days from finish to deadline");
attr.setFormula("[Deadline] - [Finish]");
```
Recupere a definição de atributo estendida do projeto e configure seu alias e fórmula. Neste exemplo, estamos definindo um atributo para calcular o número de dias desde a data de término até o prazo final.
## Etapa 3: definir o prazo para uma tarefa
```java
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.set(2015, Calendar.MARCH, 26, 8, 0, 0);
Task task = project.getRootTask().getChildren().getById(1);
task.set(Tsk.DEADLINE, cal.getTime());
```
Crie um objeto Calendário e defina a data limite. Em seguida, recupere uma tarefa do projeto e defina seu prazo usando o objeto Calendário.
## Etapa 4: salve o projeto
```java
project.save("SaveFile.mpp", SaveFileFormat.Mpp);
```
Por fim, salve o projeto em um arquivo com o nome e formato especificados. Neste caso, estamos salvando-o como um arquivo MPP.

## Conclusão
Neste tutorial, aprendemos como trabalhar com fórmulas do MS Project usando Aspose.Tasks for Java. Seguindo essas etapas, você pode manipular efetivamente os arquivos do projeto de forma programática, adicionando campos personalizados e calculando atributos com base em fórmulas.

## Perguntas frequentes
### P: Posso usar Aspose.Tasks com outras linguagens de programação?
R: Sim, Aspose.Tasks oferece suporte a várias linguagens de programação, incluindo Java, .NET e muito mais.
### P: Existe uma avaliação gratuita disponível para Aspose.Tasks?
 R: Sim, você pode baixar uma avaliação gratuita do Aspose.Tasks em[aqui](https://releases.aspose.com/).
### P: Onde posso encontrar documentação para Aspose.Tasks?
 R: Você pode encontrar a documentação do Aspose.Tasks[aqui](https://reference.aspose.com/tasks/java/).
### P: Como posso obter suporte para Aspose.Tasks?
 R: Para obter suporte, você pode visitar o[Fórum Aspose.Tasks](https://forum.aspose.com/c/tasks/15).
### P: Preciso de uma licença temporária para usar o Aspose.Tasks?
R: Se precisar de recursos adicionais, você pode obter uma licença temporária em[aqui](https://purchase.aspose.com/temporary-license/).