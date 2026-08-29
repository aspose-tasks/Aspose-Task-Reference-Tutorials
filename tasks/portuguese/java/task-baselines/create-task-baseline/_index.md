---
date: 2026-08-29
description: Aprenda como adicionar task a project em Java, criar uma task list e
  definir uma baseline sem Microsoft Project usando Aspose.Tasks.
keywords:
- add task to project
- how to set baseline
- how to create baseline
- how to add task
- java create ms project
lastmod: 2026-08-29
linktitle: Criando uma Task Baseline em Aspose.Tasks
og_description: Aprenda como adicionar task a project em Java e definir uma baseline
  usando Aspose.Tasks. Este guia mostra código passo a passo sem precisar de Microsoft
  Project.
og_image_alt: 'Tutorial: add task to project and set baseline with Aspose.Tasks Java'
og_title: Como adicionar task a project em Java e definir uma baseline
schemas:
- author: Aspose
  dateModified: '2026-08-29'
  description: Learn how to add task to project in Java, create a task list, and set
    a baseline without Microsoft Project using Aspose.Tasks.
  headline: How to add task to project in Java and set a baseline
  type: TechArticle
- questions:
  - answer: Yes, Aspose.Tasks works independently and does not require Microsoft Project
      on the host machine.
    question: Can I use Aspose.Tasks for Java without Microsoft Project installed?
  - answer: Absolutely. The library supports Project files from 2007 through the latest
      2024 releases.
    question: Is Aspose.Tasks for Java compatible with different versions of Microsoft
      Project?
  - answer: Yes, you can add, update, and delete resources programmatically, just
      like tasks.
    question: Can I manipulate project resources using Aspose.Tasks for Java?
  - answer: Yes, you can define predecessor‑successor relationships using the `TaskLink`
      class.
    question: Does Aspose.Tasks for Java support setting task dependencies?
  - answer: Yes, you can get help via the [support forum](https://forum.aspose.com/c/tasks/15),
      where Aspose staff and the community respond to queries.
    question: Is technical support available for Aspose.Tasks for Java?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- add task to project
- Aspose.Tasks
- Java project automation
title: Como adicionar task a project em Java e definir uma baseline
url: /pt/java/task-baselines/create-task-baseline/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Como adicionar tarefa ao projeto em Java e definir uma linha de base

## Introdução
Neste tutorial você **adicionará tarefa ao projeto** programaticamente, gerará uma linha de base de tarefa do Microsoft Project e salvará o arquivo — tudo sem nunca abrir o Microsoft Project. Aspose.Tasks for Java oferece uma API pura‑Java que funciona em qualquer plataforma, tornando‑a perfeita para pipelines de build automatizados, serviços de relatório ou qualquer solução server‑side que precise manipular arquivos .mpp.

## Respostas rápidas
- **O que o Aspose.Tasks faz?** Ele fornece uma API Java para criar, ler e editar arquivos Microsoft Project sem exigir o Microsoft Project.  
- **Preciso ter o Microsoft Project instalado?** Não, a biblioteca funciona completamente de forma independente.  
- **Qual versão do Java é necessária?** JDK 8 ou superior.  
- **Posso definir uma linha de base para uma única tarefa?** Sim – chame `setBaseline` em uma lista que contenha apenas as tarefas desejadas.  
- **É necessária licença para produção?** Sim, uma licença comercial remove limites de avaliação e desbloqueia todos os recursos.

## O que é uma linha de base de tarefa?
Uma linha de base de tarefa captura a data de início planejada originalmente, a data de término e o esforço de trabalho de uma tarefa no momento em que o cronograma é salvo pela primeira vez. Essa captura funciona como um ponto de referência, permitindo que gerentes de projeto comparem o progresso e os custos reais com o plano inicial e calculem variações para análise de desempenho.

## Por que usar Aspose.Tasks para adicionar tarefa ao projeto em Java?
Você pode criar, modificar e definir linhas de base de tarefas sem qualquer instalação de desktop, o que habilita fluxos de trabalho totalmente automatizados. Aspose.Tasks suporta **mais de 50 formatos de entrada e saída** e pode lidar com projetos com **centenas de tarefas** mantendo o uso de memória abaixo de 200 MB, tornando‑a ideal para serviços em nuvem e pipelines CI/CD.

## Pré‑requisitos
1. **Java Development Kit (JDK)** – instale o JDK 8 ou mais recente.  
2. **Aspose.Tasks for Java** – faça o download da biblioteca a partir do [download link](https://releases.aspose.com/tasks/java/).  

## Importar pacotes
Para começar a trabalhar com Aspose.Tasks no seu projeto Java, importe os pacotes necessários:
```java
import com.aspose.tasks.BaselineType;
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import java.util.ArrayList;
import java.util.List;
```

## Etapa 1: criar um objeto de projeto
A classe `Project` é o objeto de nível superior do Aspose.Tasks que representa um arquivo Microsoft Project na memória. Instanciá‑la fornece um projeto em branco que você pode preencher com tarefas, recursos e calendários.

```java
Project project = new Project();
```
Aqui instanciamos um novo objeto `Project` – ele representa o arquivo MS Project que conterá nossa lista de tarefas.

## Etapa 2: adicionar uma tarefa ao projeto
A classe `Task` representa um item de trabalho individual em um cronograma de projeto. Cada `Task` pode ter sua própria duração, data de início e atribuições de recursos.

```java
Task task = project.getRootTask().getChildren().add("Task");
```
Usando `getRootTask()` acessamos a raiz da hierarquia do projeto e **adicionamos tarefa ao Microsoft Project**. A string `"Task"` é o nome da tarefa; você pode substituí‑la por qualquer descrição que precisar.

## Etapa 3: definir linha de base para tarefas especificadas
`BaselineType` é uma enumeração que define qual slot de linha de base (Baseline, Baseline1 … Baseline10) você deseja gravar. Ao passar uma lista de tarefas, você pode definir linha de base apenas nos itens selecionados.

```java
List<Task> myList = new ArrayList<Task>();
project.setBaseline(BaselineType.Baseline, (Iterable<Task>) myList);
```
Para **definir linha de base sem o MS Project**, crie uma lista das tarefas que deseja incluir na linha de base (aqui `myList`) e passe‑a para `setBaseline`. Preencha `myList` com as tarefas que adicionou caso precise de uma linha de base seletiva.

## Etapa 4: definir linha de base para todo o projeto
`setBaseline` grava os valores de linha de base selecionados em cada tarefa do projeto.  
Se preferir definir linha de base para todo o projeto em uma única chamada, basta invocar `setBaseline` com o `BaselineType` desejado.

```java
project.setBaseline(BaselineType.Baseline);
```
Esta chamada grava os valores de linha de base escolhidos para **todas as tarefas** do projeto, garantindo uma captura completa do cronograma original.

## Como adicionar tarefa ao Microsoft Project usando Aspose.Tasks
`add()` cria uma nova tarefa filha sob a tarefa pai especificada e retorna o objeto `Task` recém‑criado.  
Você adiciona uma tarefa chamando `add()` em um objeto `Task` pai (geralmente a tarefa raiz). O método devolve uma nova instância de `Task` que pode ser configurada adicionalmente — duração, data de início, recursos ou campos personalizados — antes de salvar o arquivo do projeto.

## Como definir linha de base sem o MS Project
Aspose.Tasks permite a criação de linhas de base totalmente por código. Escolha um `BaselineType` (por exemplo, `BaselineType.Baseline`) e invoque `setBaseline`. Você pode repetir isso com `Baseline1`‑`Baseline10` para manter múltiplas linhas de base de **revisão**, tudo **sem** abrir o Microsoft Project.

## Problemas comuns e soluções
- **Linha de base não aparece:** Certifique‑se de chamar `project.save("output.mpp")` após **definir a linha de base** (etapa de salvamento omitida aqui por brevidade).  
- **Lista de tarefas aparece vazia:** Verifique se está adicionando tarefas ao pai correto (`getRootTask()` ou uma subtarefa).  
- **Erros de incompatibilidade de versão:** Use o JAR mais recente do Aspose.Tasks para garantir compatibilidade com formatos .mpp mais novos.

## Perguntas frequentes

**P: Posso usar Aspose.Tasks for Java sem o Microsoft Project instalado?**  
R: Sim, o Aspose.Tasks funciona de forma independente e não requer o Microsoft Project na máquina host.

**P: O Aspose.Tasks for Java é compatível com diferentes versões do Microsoft Project?**  
R: Absolutamente. A biblioteca suporta arquivos de projeto de 2007 até as versões mais recentes de 2024.

**P: Posso manipular recursos do projeto usando Aspose.Tasks for Java?**  
R: Sim, você pode adicionar, atualizar e excluir recursos programaticamente, assim como as tarefas.

**P: O Aspose.Tasks for Java suporta a definição de dependências entre tarefas?**  
R: Sim, você pode definir relacionamentos predecessor‑successor usando a classe `TaskLink`.

**P: Existe suporte técnico disponível para Aspose.Tasks for Java?**  
R: Sim, você pode obter ajuda através do [support forum](https://forum.aspose.com/c/tasks/15), onde a equipe da Aspose e a comunidade respondem às dúvidas.

## Conclusão
Seguindo estas etapas, você aprendeu a **adicionar tarefa ao projeto** em Java, criar uma lista de tarefas e **definir linha de base sem o MS Project** usando Aspose.Tasks. Essa abordagem simplifica a automação de projetos, elimina a necessidade de instalações desktop do Project e oferece controle programático total sobre todos os aspectos do seu cronograma.

---

**Última atualização:** 2026-08-29  
**Testado com:** Aspose.Tasks for Java 24.12  
**Autor:** Aspose

## Tutoriais relacionados

- [How to Create Project aspose.tasks – Set New Task Attributes](/tasks/java/project-file-operations/set-attributes-new-tasks/)
- [How to Set Baseline Duration in Aspose.Tasks for Java](/tasks/java/task-baselines/task-baseline-duration/)
- [Create Tasks Aspose Java – Task Properties](/tasks/java/task-properties/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}