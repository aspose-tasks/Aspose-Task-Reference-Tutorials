---
title: Crie uma linha de base de tarefas do MS Project em Aspose.Tasks
linktitle: Criando uma linha de base de tarefa em Aspose.Tasks
second_title: API Java Aspose.Tasks
description: Aprenda como criar uma linha de base de tarefas do Microsoft Project em Java usando Aspose.Tasks, uma biblioteca poderosa para gerenciar dados de projetos sem esforço.
weight: 11
url: /pt/java/task-baselines/create-task-baseline/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Crie uma linha de base de tarefas do MS Project em Aspose.Tasks

## Introdução
Neste tutorial, nos aprofundaremos no processo de criação de uma linha de base de tarefas do Microsoft Project usando Aspose.Tasks para Java. Aspose.Tasks é uma biblioteca Java poderosa que permite aos desenvolvedores trabalhar com arquivos do Microsoft Project sem exigir a instalação do Microsoft Project. Com Aspose.Tasks, você pode manipular facilmente os dados do projeto, incluindo tarefas, recursos e calendários, para agilizar as tarefas de gerenciamento de projetos.
## Pré-requisitos
Antes de começarmos, certifique-se de ter os seguintes pré-requisitos:
1. Kit de desenvolvimento Java (JDK): Aspose.Tasks for Java requer JDK instalado em seu sistema. Você pode baixar e instalar o JDK no site da Oracle.
2.  Biblioteca Aspose.Tasks para Java: Baixe a biblioteca Aspose.Tasks para Java no[Link para Download](https://releases.aspose.com/tasks/java/) oferecido.

## Importar pacotes
Para começar a trabalhar com Aspose.Tasks em seu projeto Java, importe os pacotes necessários:
```java
import com.aspose.tasks.BaselineType;
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import java.util.ArrayList;
import java.util.List;
```

## Etapa 1: Crie um objeto de projeto
```java
Project project = new Project();
```
 Primeiro, crie um novo`Project` objeto. Este objeto representa o arquivo do Microsoft Project com o qual você trabalhará.
## Etapa 2: adicionar uma tarefa ao projeto
```java
Task task = project.getRootTask().getChildren().add("Task");
```
 Usando o`getRootTask()` método, acesse a tarefa raiz do projeto e adicione uma nova tarefa a ela usando o`add()` método. Forneça um nome para a tarefa entre parênteses.
## Etapa 3: definir linha de base para tarefas específicas
```java
List<Task> myList = new ArrayList<Task>();
project.setBaseline(BaselineType.Baseline, (Iterable<Task>) myList);
```
Para definir uma linha de base para tarefas específicas, crie uma lista de tarefas (`myList` neste caso) e preencha-o com as tarefas para as quais deseja definir a linha de base. Então, use o`setBaseline()` método, especificando o tipo de linha de base e a lista de tarefas.
## Etapa 4: definir a linha de base para todo o projeto
```java
project.setBaseline(BaselineType.Baseline);
```
 Alternativamente, você pode definir uma linha de base para todo o projeto simplesmente chamando o método`setBaseline()` método com o tipo de linha de base especificado.

## Conclusão
Neste tutorial, exploramos como criar uma linha de base de tarefas do Microsoft Project usando Aspose.Tasks para Java. Seguindo as etapas descritas acima, você pode gerenciar com eficiência os dados do projeto e agilizar as tarefas de gerenciamento de projetos com facilidade.
## Perguntas frequentes
### Posso usar Aspose.Tasks for Java sem o Microsoft Project instalado?
Sim, Aspose.Tasks for Java permite que você trabalhe com arquivos do Microsoft Project sem exigir que o Microsoft Project esteja instalado em seu sistema.
### O Aspose.Tasks for Java é compatível com diferentes versões do Microsoft Project?
Sim, Aspose.Tasks for Java oferece suporte a várias versões do Microsoft Project, garantindo compatibilidade em diferentes ambientes.
### Posso manipular recursos do projeto usando Aspose.Tasks for Java?
Com certeza, Aspose.Tasks for Java fornece recursos robustos para manipular recursos do projeto, incluindo adição, atualização e remoção de recursos conforme necessário.
### O Aspose.Tasks for Java oferece suporte à configuração de dependências de tarefas?
Sim, você pode definir dependências de tarefas sem esforço usando Aspose.Tasks for Java, permitindo estabelecer a sequência de tarefas em seu projeto.
### O suporte técnico está disponível para Aspose.Tasks for Java?
 Sim, você pode acessar o suporte técnico para Aspose.Tasks for Java através do[Fórum de suporte](https://forum.aspose.com/c/tasks/15), onde você pode fazer perguntas e buscar ajuda da comunidade e da equipe de suporte do Aspose.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
