---
title: Adicionar atributos estendidos a tarefas em Aspose.Tasks
linktitle: Adicionar atributos estendidos a tarefas em Aspose.Tasks
second_title: API Java Aspose.Tasks
description: Explore o poder do Aspose.Tasks Java na personalização de arquivos do Microsoft Project com atributos estendidos. Aprimore seus recursos de gerenciamento de projetos sem esforço.
weight: 11
url: /pt/java/task-properties/add-extended-attributes/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Adicionar atributos estendidos a tarefas em Aspose.Tasks

## Introdução
Aprimorar seus recursos de gerenciamento de projetos é crucial para um rastreamento eficiente de tarefas e gerenciamento de recursos. Aspose.Tasks for Java fornece uma solução poderosa para desenvolvedores Java manipularem arquivos do Microsoft Project perfeitamente. Neste tutorial, exploraremos como adicionar atributos estendidos a tarefas usando Aspose.Tasks for Java, permitindo que você personalize e organize os dados do seu projeto de acordo com seus requisitos específicos.
## Pré-requisitos
Antes de mergulhar no tutorial, certifique-se de ter os seguintes pré-requisitos:
- Conhecimento básico de programação Java.
-  Biblioteca Aspose.Tasks para Java instalada. Você pode baixá-lo no[local na rede Internet](https://releases.aspose.com/tasks/java/).
- Um Java Integrated Development Environment (IDE) instalado em seu sistema.
## Importar pacotes
Em seu projeto Java, importe os pacotes necessários para acessar as funcionalidades do Aspose.Tasks:
```java
import java.io.IOException;
import com.aspose.tasks.*;
```
Agora, vamos dividir cada exemplo em várias etapas:
## 1. Adicionando Atributo de Texto Simples
1. Defina o caminho do diretório do documento:
```java
String dataDir = "Your Document Directory";
```
2. Crie um novo projeto:
```java
Project project = new Project(dataDir + "project.mpp");
```
3. Crie uma definição de atributo estendida do tipo Text1:
```java
ExtendedAttributeDefinition taskExtendedAttributeText1Definition = ExtendedAttributeDefinition.createTaskDefinition(CustomFieldType.Text, ExtendedAttributeTask.Text1, "Task City Name");
```
4. Adicione a definição à coleção Extended Attributes do projeto:
```java
project.getExtendedAttributes().add(taskExtendedAttributeText1Definition);
```
5. Adicione uma tarefa ao projeto:
```java
Task task = project.getRootTask().getChildren().add("Task 1");
```
6. Crie um atributo estendido a partir da definição de atributo:
```java
ExtendedAttribute taskExtendedAttributeText1 = taskExtendedAttributeText1Definition.createExtendedAttribute();
```
7. Atribua um valor ao Atributo Estendido gerado:
```java
taskExtendedAttributeText1.setTextValue("London");
```
8. Adicione o atributo estendido à tarefa:
```java
task.getExtendedAttributes().add(taskExtendedAttributeText1);
```
9. Salve o projeto:
```java
project.save(dataDir + "PlainTextExtendedAttribute_out.mpp", SaveFileFormat.Mpp);
```
## 2. Adicionando atributo de texto com opção de pesquisa
Siga as mesmas etapas acima, substituindo Text1 por Text2 e personalizando os valores de pesquisa.
## 3. Adicionando atributo de duração com opção de pesquisa
Siga as mesmas etapas acima, substituindo Text1 por Duration2 e personalizando os valores de pesquisa.
## Conclusão
Seguindo este guia passo a passo, você aprendeu como aproveitar o Aspose.Tasks for Java para adicionar atributos estendidos a tarefas em seus arquivos do Microsoft Project. Essa personalização permite adaptar sua abordagem de gerenciamento de projetos, aumentando a flexibilidade e a eficiência.
## perguntas frequentes
### P: Posso usar Aspose.Tasks for Java com outras bibliotecas Java?
R: Sim, Aspose.Tasks for Java pode ser perfeitamente integrado aos seus projetos Java e funciona bem com outras bibliotecas Java.
### P: O Aspose.Tasks for Java é adequado para aplicativos de gerenciamento de projetos em grande escala?
R: Com certeza, o Aspose.Tasks for Java foi projetado para lidar com projetos de tamanhos variados, incluindo aplicativos de grande escala.
### P: Há alguma consideração de licenciamento para usar Aspose.Tasks for Java em um projeto comercial?
 R: Sim, certifique-se de revisar as informações de licenciamento fornecidas no[Site Aspose.Tasks](https://purchase.aspose.com/buy).
### P: Como posso obter suporte ou assistência com Aspose.Tasks for Java?
 R: Visite o[Fórum Aspose.Tasks](https://forum.aspose.com/c/tasks/15) para apoio e discussões da comunidade.
### P: Posso experimentar o Aspose.Tasks for Java antes de comprar?
 R: Sim, você pode acessar uma versão de avaliação gratuita[aqui](https://releases.aspose.com/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
