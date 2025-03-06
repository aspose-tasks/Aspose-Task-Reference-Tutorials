---
title: Escala de taxa de leitura e gravação para atribuições de recursos em Aspose.Tasks
linktitle: Escala de taxa de leitura e gravação para atribuições de recursos em Aspose.Tasks
second_title: API Java Aspose.Tasks
description: Aprenda como gerenciar a escala de taxas de atribuições de recursos de maneira eficaz em Aspose.Tasks for Java com este tutorial abrangente.
weight: 20
url: /pt/java/resource-assignments/read-write-rate-scale/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Escala de taxa de leitura e gravação para atribuições de recursos em Aspose.Tasks

## Introdução
Neste tutorial, nos aprofundaremos no gerenciamento da escala de taxas de atribuições de recursos usando Aspose.Tasks for Java, uma biblioteca robusta para trabalhar programaticamente com arquivos do Microsoft Project. Seguindo estas etapas, você poderá manipular efetivamente as configurações de escala de taxas para atribuições de recursos em seus aplicativos Java.
## Pré-requisitos
Antes de começarmos, certifique-se de ter os seguintes pré-requisitos:
1. Ambiente de Desenvolvimento Java: Certifique-se de ter o Java Development Kit (JDK) instalado em seu sistema.
2.  Biblioteca Aspose.Tasks for Java: Baixe e instale a biblioteca Aspose.Tasks for Java em[aqui](https://releases.aspose.com/tasks/java/).

## Importar pacotes
Primeiro, você precisa importar os pacotes necessários para trabalhar com as funcionalidades do Aspose.Tasks. 
```java
import com.aspose.tasks.Asn;
import com.aspose.tasks.Project;
import com.aspose.tasks.RateScaleType;
import com.aspose.tasks.Resource;
import com.aspose.tasks.ResourceAssignment;
import com.aspose.tasks.ResourceType;
import com.aspose.tasks.Rsc;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.Task;
import java.io.IOException;
```
## Etapa 1: configure seu projeto
Comece configurando seu projeto Java e inclua a biblioteca Aspose.Tasks em suas dependências.
## Etapa 2: carregar o arquivo do projeto
Carregue o arquivo de projeto com o qual deseja trabalhar em seu aplicativo Java.
```java
String dataDir = "Your Data Directory";
Project project = new Project(dataDir + "New project 2013.mpp");
```
## Etapa 3: adicionar uma tarefa
Adicione uma nova tarefa ao seu projeto.
```java
Task task = project.getRootTask().getChildren().add("t1");
```
## Etapa 4: definir recursos
Defina recursos materiais e imateriais e especifique seus tipos.
```java
Resource materialResource = project.getResources().add("materialResource");
materialResource.set(Rsc.TYPE, ResourceType.Material);
Resource nonMaterialResource = project.getResources().add("nonMaterialResource");
nonMaterialResource.set(Rsc.TYPE, ResourceType.Work);
```
## Etapa 5: atribuir recursos à tarefa
Atribua os recursos previamente definidos à tarefa juntamente com os seus tipos de escala de taxas.
```java
ResourceAssignment materialResourceAssignment = project.getResourceAssignments().add(task, materialResource);
materialResourceAssignment.set(Asn.RATE_SCALE, RateScaleType.Week);
ResourceAssignment nonMaterialResourceAssignment = project.getResourceAssignments().add(task, nonMaterialResource);
nonMaterialResourceAssignment.set(Asn.RATE_SCALE, RateScaleType.Week);
```
## Etapa 6: salve o projeto
Salve o projeto com as atribuições de recursos modificadas.
```java
project.save("output.mpp", SaveFileFormat.Mpp);
```
## Etapa 7: recuperar atribuições de recursos
Recarregue o projeto salvo e recupere atribuições de recursos para verificar as configurações da escala de taxas.
```java
Project resavedProject = new Project("output.mpp");
ResourceAssignment resavedMaterialResourceAssignment = resavedProject.getResourceAssignments().getByUid(1);
System.out.println(resavedMaterialResourceAssignment.get(Asn.RATE_SCALE));
ResourceAssignment resavedNonMaterialResourceAssignment = resavedProject.getResourceAssignments().getByUid(2);
```

## Conclusão
Gerenciar a escala de taxas de atribuições de recursos em Aspose.Tasks for Java é crucial para um gerenciamento de projetos eficaz. Seguindo este guia passo a passo, você pode manipular perfeitamente as configurações de escala de taxas para atribuições de recursos em seus aplicativos Java.
## Perguntas frequentes
### Q1: Posso usar Aspose.Tasks for Java com qualquer IDE Java?
R: Sim, Aspose.Tasks for Java é compatível com todos os principais IDEs Java, incluindo IntelliJ IDEA, Eclipse e NetBeans.
### Q2: O Aspose.Tasks oferece suporte a outros formatos de arquivo além do MPP?
R: Sim, Aspose.Tasks oferece suporte a vários formatos de arquivo, incluindo MPP, XML e HTML.
### Q3: O Aspose.Tasks é adequado para gerenciamento de projetos de nível empresarial?
R: Com certeza, o Aspose.Tasks oferece recursos abrangentes para gerenciamento de projetos de qualquer escala, tornando-o adequado para gerenciamento de projetos de nível empresarial.
### P4: Posso personalizar as atribuições de recursos além da escala de taxas?
R: Sim, o Aspose.Tasks oferece amplos recursos para personalizar atribuições de recursos, incluindo ajustes de custo, trabalho e duração.
### Q5: Existe um fórum da comunidade para suporte do Aspose.Tasks?
 R: Sim, você pode encontrar suporte e interagir com outros usuários no fórum Aspose.Tasks[aqui](https://forum.aspose.com/c/tasks/15).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
