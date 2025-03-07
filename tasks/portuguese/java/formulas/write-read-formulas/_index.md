---
title: Escrevendo e lendo fórmulas do MS Project em Aspose.Tasks
linktitle: Escreva e leia fórmulas em Aspose.Tasks
second_title: API Java Aspose.Tasks
description: Aprenda a escrever e ler fórmulas do MS Project de forma eficiente com Aspose.Tasks for Java. Aprimore suas habilidades de gerenciamento de projetos.
weight: 12
url: /pt/java/formulas/write-read-formulas/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Escrevendo e lendo fórmulas do MS Project em Aspose.Tasks

## Introdução
No domínio do gerenciamento de projetos, o tratamento eficaz dos dados é fundamental. Aspose.Tasks for Java é uma solução robusta que facilita a manipulação e extração de dados de arquivos do Microsoft Project. Um recurso poderoso que oferece é a capacidade de escrever e ler fórmulas do MS Project. Este tutorial irá guiá-lo através do processo de aproveitamento dessa funcionalidade para aprimorar suas tarefas de gerenciamento de projetos.
## Pré-requisitos
Antes de mergulhar neste tutorial, certifique-se de ter os seguintes pré-requisitos:
1. Kit de desenvolvimento Java (JDK): certifique-se de ter o Java instalado em seu sistema.
2.  Aspose.Tasks para Java: Baixe e instale Aspose.Tasks para Java em[aqui](https://releases.aspose.com/tasks/java/).
3. Ambiente de Desenvolvimento Integrado (IDE): Escolha seu IDE preferido para desenvolvimento Java.

## Importando Pacotes
Para começar, importe os pacotes necessários para o seu projeto Java:
```java
import com.aspose.tasks.*;
import java.io.IOException;
import java.math.BigDecimal;
import java.util.Objects;
```

## Etapa 1: configurar o diretório de dados
```java
// O caminho para o diretório de documentos.
String dataDir = "Your Data Directory";
```
Nesta etapa, defina o diretório onde seus arquivos do MS Project estão localizados.
## Etapa 2: carregar o arquivo do projeto
```java
Project project = new Project(dataDir + "project.mpp");
```
Aqui, carregue o arquivo MS Project em um`Project` objeto para manipulação.
## Etapa 3: definir fórmula personalizada
```java
project.set(Prj.NEW_TASKS_ARE_MANUAL, new NullableBool(false));
ExtendedAttributeDefinition attr = ExtendedAttributeDefinition.createTaskDefinition(CustomFieldType.Text, ExtendedAttributeTask.Text1, "Custom");
attr.setAlias("Double Costs");
attr.setFormula("[Cost]*2");
project.getExtendedAttributes().add(attr);
```
Esta etapa envolve a criação de um campo personalizado com uma fórmula que duplica o custo da tarefa.
## Etapa 4: adicionar tarefa e definir custo
```java
Task task = project.getRootTask().getChildren().add("Task");
task.set(Tsk.COST, BigDecimal.valueOf(100));
```
Aqui, uma nova tarefa é adicionada e seu custo é definido como 100.
## Etapa 5: salvar o arquivo do projeto
```java
project.save(dataDir + "saved.mpp", SaveFileFormat.Mpp);
```
Finalmente, salve o arquivo de projeto modificado.

## Conclusão
Neste tutorial, exploramos como escrever e ler fórmulas do MS Project usando Aspose.Tasks para Java. Seguindo essas etapas, você pode manipular com eficiência os dados do projeto para atender aos seus requisitos específicos.
## Perguntas frequentes
### O Aspose.Tasks é compatível com todas as versões do MS Project?
Aspose.Tasks oferece compatibilidade com diversas versões do MS Project, garantindo flexibilidade aos usuários.
### Posso integrar Aspose.Tasks em meu projeto Java existente?
Absolutamente! Aspose.Tasks fornece integração perfeita com projetos Java por meio do uso simples de API.
### Há alguma limitação nos tipos de fórmulas que posso criar?
Com Aspose.Tasks, você tem ampla flexibilidade na elaboração de fórmulas personalizadas adaptadas às necessidades do seu projeto.
### O Aspose.Tasks oferece suporte à implantação multiplataforma?
Sim, Aspose.Tasks suporta implantação em múltiplas plataformas, aumentando sua versatilidade.
### Como posso obter suporte técnico para Aspose.Tasks?
 Para assistência técnica e apoio comunitário, visite o[Fórum Aspose.Tasks](https://forum.aspose.com/c/tasks/15).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
