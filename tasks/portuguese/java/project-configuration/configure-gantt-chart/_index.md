---
title: Configurar a visualização do gráfico de Gantt em projetos Aspose.Tasks
linktitle: Configurar a visualização do gráfico de Gantt em projetos Aspose.Tasks
second_title: API Java Aspose.Tasks
description: Aprenda como configurar o Gantt MS Project Chart View em Aspose.Tasks usando Java. Personalize o projeto e visualize-os no gráfico de Gantt com passo a passo.
weight: 10
url: /pt/java/project-configuration/configure-gantt-chart/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Configurar a visualização do gráfico de Gantt em projetos Aspose.Tasks

## Introdução
Neste tutorial, você aprenderá como configurar o Gantt MS Project Chart View em projetos Aspose.Tasks usando Java. Aspose.Tasks é uma API Java poderosa que permite trabalhar com arquivos do Microsoft Project programaticamente. Seguindo essas etapas, você poderá personalizar a visualização do gráfico de Gantt de acordo com os requisitos do seu projeto.
## Pré-requisitos
Antes de começar, certifique-se de ter os seguintes pré-requisitos:
1. Java Development Kit (JDK): Certifique-se de ter o Java instalado em seu sistema.
2.  Biblioteca Aspose.Tasks: Baixe e instale a biblioteca Aspose.Tasks. Você pode baixá-lo em[aqui](https://releases.aspose.com/tasks/java/).
3. Ambiente de Desenvolvimento Integrado (IDE): Escolha um IDE de sua preferência. Este tutorial usa o IntelliJ IDEA, mas você pode usar qualquer IDE com o qual se sinta confortável.
## Importar pacotes
Primeiro, você precisa importar os pacotes necessários para trabalhar com Aspose.Tasks em seu projeto Java. Adicione as seguintes instruções de importação ao seu arquivo Java:
```java
import com.aspose.tasks.*;
```
Agora, vamos dividir o processo de configuração do Gantt MS Project Chart View em instruções passo a passo:
## Etapa 1: configurar o diretório de dados
```java
String dataDir = "Your Data Directory";
```
 Substituir`"Your Data Directory"` com o caminho para o diretório de dados do seu projeto.
## Etapa 2: carregar o arquivo do projeto
```java
Project project = new Project(dataDir + "project.mpp");
```
Carregue seu arquivo de projeto (`project.mpp` neste exemplo) usando o`Project` classe de Aspose.Tasks.
## Etapa 3: adicionar nova atividade
```java
Task task = project.getRootTask().getChildren().add("New Activity");
```
 Crie uma nova tarefa em seu projeto usando o`Task` class e adicione-a aos filhos da tarefa raiz.
## Etapa 4: definir o atributo personalizado
```java
ExtendedAttributeDefinition text1Definition = ExtendedAttributeDefinition.createTaskDefinition(ExtendedAttributeTask.Text1, null);
project.getExtendedAttributes().add(text1Definition);
```
 Defina um novo atributo personalizado usando o`ExtendedAttributeDefinition`class e adicione-a aos atributos estendidos do projeto.
## Etapa 5: adicionar um atributo personalizado à tarefa
```java
task.getExtendedAttributes().add(text1Definition.createExtendedAttribute("Activity attribute"));
```
 Adicione o atributo personalizado à tarefa criada usando o`createExtendedAttribute` método.
## Etapa 6: personalizar a tabela
```java
TableField attrField = new TableField();
attrField.setField(Field.TaskText1);
attrField.setWidth(20);
attrField.setTitle("Custom attribute");
attrField.setAlignTitle(HorizontalStringAlignment.Center);
attrField.setAlignData(HorizontalStringAlignment.Center);
Table table = project.getTables().toList().get(0);
table.getTableFields().add(3, attrField);
```
Personalize a tabela adicionando o campo de atributo de texto com largura, título e alinhamento especificados.
## Etapa 7: Salvar Projeto
```java
project.save("saved.mpp", SaveFileFormat.Mpp);
```
Salve o projeto com o Gantt MS Project Chart View configurado. O arquivo resultante pode ser aberto no Microsoft Project 2010.
## Conclusão
Parabéns! Você configurou com êxito o Gantt MS Project Chart View em projetos Aspose.Tasks usando Java. Agora você pode personalizar os atributos do projeto e visualizá-los no gráfico de Gantt de acordo com as necessidades do seu projeto.
## Perguntas frequentes
### P: Posso usar Aspose.Tasks com outras linguagens de programação?
R: Sim, Aspose.Tasks está disponível para várias linguagens de programação, incluindo .NET, Java e C++.
### P: Existe algum teste gratuito disponível para Aspose.Tasks?
 R: Sim, você pode baixar uma avaliação gratuita em[aqui](https://releases.aspose.com/).
### P: Onde posso encontrar suporte para Aspose.Tasks?
R: Você pode encontrar suporte e fazer perguntas no site[Fórum Aspose.Tasks](https://forum.aspose.com/c/tasks/15).
### P: Como posso adquirir uma licença para Aspose.Tasks?
 R: Você pode comprar uma licença de[aqui](https://purchase.aspose.com/buy).
### P: Preciso de uma licença temporária para fins de teste?
 R: Sim, você pode obter uma licença temporária em[aqui](https://purchase.aspose.com/temporary-license/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
