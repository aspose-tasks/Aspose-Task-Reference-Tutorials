---
title: Recuperar códigos de estrutura de tópicos do MS Project em Aspose.Tasks
linktitle: Recuperar códigos de contorno em Aspose.Tasks
second_title: API Java Aspose.Tasks
description: Aprenda como recuperar códigos de estrutura de tópicos do Microsoft Project programaticamente usando Aspose.Tasks para Java. Aprimore seus recursos de gerenciamento de projetos.
type: docs
weight: 15
url: /pt/java/project-file-operations/retrieve-outline-codes/
---
## Introdução
Neste tutorial, aprenderemos como recuperar códigos de estrutura de tópicos do Microsoft Project usando Aspose.Tasks para Java. Os códigos de estrutura de tópicos no MS Project fornecem uma maneira estruturada de categorizar e organizar tarefas, recursos e atribuições do projeto. Aspose.Tasks é uma poderosa biblioteca Java que permite aos desenvolvedores manipular e gerenciar arquivos do Microsoft Project programaticamente.
## Pré-requisitos
Antes de começarmos, certifique-se de ter os seguintes pré-requisitos configurados:
### 1. Ambiente de Desenvolvimento Java
Certifique-se de ter o Java Development Kit (JDK) instalado em seu sistema. Você pode baixar e instalar o JDK no site da Oracle.
### 2. Biblioteca Aspose.Tasks
 Baixe e inclua a biblioteca Aspose.Tasks em seu projeto Java. Você pode baixar a biblioteca do[Página de download do Aspose.Tasks para Java](https://releases.aspose.com/tasks/java/).
## Importar pacotes
Primeiro, importe os pacotes necessários do Aspose.Tasks em seu código Java:
```java
import com.aspose.tasks.OutlineCodeDefinition;
import com.aspose.tasks.OutlineMask;
import com.aspose.tasks.OutlineValue;
import com.aspose.tasks.Project;
```
Agora vamos dividir o código de exemplo fornecido em várias etapas:
## Etapa 1: carregar o projeto
```java
String projectName = "ProjectFile.mpp";
Project project = new Project(projectName);
```
 Nesta etapa, carregamos o arquivo do Microsoft Project em um`Project` objeto usando o nome de arquivo fornecido.
## Etapa 2: recuperar códigos de estrutura de tópicos
```java
for (OutlineCodeDefinition ocd : project.getOutlineCodes()) {
```
Iteramos cada definição de código de estrutura no projeto.
## Etapa 3: acessar as propriedades do código de estrutura de tópicos
```java
System.out.println("Alias = " + ocd.getAlias());
System.out.println("Field Id = " + ocd.getFieldId());
System.out.println("Field Name = " + ocd.getFieldName());
```
Recuperamos e imprimimos várias propriedades da definição do código de estrutura, como Alias, ID do campo e Nome do campo.
## Etapa 4: verifique o código personalizado empresarial
```java
if (ocd.getEnterprise()) {
    System.out.println("It is an enterprise custom outline code.");
} else {
    System.out.println("It is not an enterprise custom outline code.");
}
```
Verificamos se o código de contorno é um código personalizado empresarial e imprimimos o resultado de acordo.
## Etapa 5: exibir máscaras de código de contorno
```java
for (OutlineMask m1 : ocd.getMasks()) {
    System.out.println("Level of a mask = " + m1.getLevel());
    System.out.println("Mask = " + m1.toString());
}
```
Iteramos através de cada máscara associada ao código de contorno e imprimimos seu nível e valor da máscara.
## Etapa 6: exibir valores de código de estrutura de tópicos
```java
for (OutlineValue v1 : ocd.getValues()) {
    System.out.println("Description of outline value = " + v1.getDescription());
    System.out.println("Value Id = " + v1.getValueId());
    System.out.println("Value = " + v1.getValue());
    System.out.println("Type = " + v1.getType());
}
```
Iteramos cada valor do código de estrutura e imprimimos sua descrição, ID do valor, valor e tipo.
## Conclusão
Neste tutorial, aprendemos como recuperar códigos de estrutura de tópicos do MS Project usando Aspose.Tasks para Java. Seguindo as etapas fornecidas, você pode acessar e manipular efetivamente códigos de estrutura em seus aplicativos Java, habilitando recursos avançados de gerenciamento de projetos.
## Perguntas frequentes
### Q1: Posso usar Aspose.Tasks for Java para modificar códigos de estrutura de tópicos em um arquivo de projeto?
R: Sim, Aspose.Tasks for Java fornece APIs para modificar códigos de estrutura em arquivos do MS Project programaticamente.
### Q2: Existe uma versão de teste disponível para Aspose.Tasks for Java?
 R: Sim, você pode baixar uma versão de avaliação gratuita do Aspose.Tasks for Java no[Site Aspose.Tasks](https://releases.aspose.com/).
### Q3: Como posso obter suporte técnico para Aspose.Tasks for Java?
 R: Você pode obter suporte técnico visitando o[Fórum Aspose.Tasks](https://forum.aspose.com/c/tasks/15) e postando suas dúvidas lá.
### Q4: Posso adquirir uma licença temporária para Aspose.Tasks for Java?
 R: Sim, você pode adquirir uma licença temporária para Aspose.Tasks for Java no site[página de compra](https://purchase.aspose.com/temporary-license/).
### Q5: Onde posso encontrar a documentação completa do Aspose.Tasks for Java?
 R: Você pode consultar o[documentação](https://reference.aspose.com/tasks/java/) para obter informações detalhadas sobre como usar Aspose.Tasks for Java.