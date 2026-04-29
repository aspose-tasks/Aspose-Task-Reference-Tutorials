---
date: 2026-01-18
description: Aprenda como criar uma lista de tarefas em Java e adicionar tarefas ao
  Microsoft Project, definindo uma linha de base sem o MS Project usando Aspose.Tasks.
linktitle: Creating a Task Baseline in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Criar Lista de Tarefas Java – Linha de Base do MS Project usando Aspose.Tasks
url: /pt/java/task-baselines/create-task-baseline/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Criar Lista de Tarefas Java – Baseline do MS Project com Aspose.Tasks

## Introdução
Neste tutorial, você **criará lista de tarefas Java** gerando um baseline de tarefas do Microsoft Project usando Aspose.Tasks para Java. Aspose.Tasks permite trabalhar com arquivos Project sem precisar do Microsoft Project instalado, então você pode **adicionar tarefa ao Microsoft Project**, manipular recursos e até **definir baseline sem MS Project**—tudo a partir de código Java puro.

## Respostas Rápidas
- **O que o Aspose.Tasks faz?** Ele fornece uma API Java para criar, ler e editar arquivos Microsoft Project sem o MS Project.  
- **Preciso ter o Microsoft Project instalado?** Não, o Aspose.Tasks funciona de forma independente.  
- **Qual versão do Java é necessária?** JDK 8 ou superior.  
- **Posso definir um baseline para uma única tarefa?** Sim, use `setBaseline` com uma lista de tarefas.  
- **É necessária licença para produção?** Sim, uma licença comercial remove as limitações de avaliação.

## O que é um Baseline de Tarefa?
Um baseline de tarefa registra os valores originais planejados de início, término e trabalho de uma tarefa. Ele serve como ponto de referência para comparar o progresso real com o plano original.

## Por que usar Aspose.Tasks para criar lista de tarefas Java?
- **Sem dependência do MS Project** – ideal para automação no servidor.  
- **Controle total** sobre tarefas, recursos e calendários via código Java.  
- **Compatibilidade entre versões** com arquivos Project 2007‑2024.

## Pré‑requisitos
1. **Java Development Kit (JDK)** – instale o JDK 8 ou mais recente.  
2. **Aspose.Tasks para Java** – faça o download da biblioteca a partir do [link de download](https://releases.aspose.com/tasks/java/).  

## Importar Pacotes
Para começar a trabalhar com Aspose.Tasks no seu projeto Java, importe os pacotes necessários:
```java
import com.aspose.tasks.BaselineType;
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import java.util.ArrayList;
import java.util.List;
```

## Etapa 1: Criar um Objeto Project
```java
Project project = new Project();
```
Aqui instanciamos um novo objeto `Project` – ele representa o arquivo MS Project que conterá nossa lista de tarefas.

## Etapa 2: Adicionar uma Tarefa ao Projeto
```java
Task task = project.getRootTask().getChildren().add("Task");
```
Usando `getRootTask()` acessamos a raiz da hierarquia do projeto e **adicionamos tarefa ao Microsoft Project**. A string `"Task"` é o nome da tarefa; você pode substituí‑la por qualquer descrição que precisar.

## Etapa 3: Definir Baseline para Tarefas Especificadas
```java
List<Task> myList = new ArrayList<Task>();
project.setBaseline(BaselineType.Baseline, (Iterable<Task>) myList);
```
Para **definir baseline sem MS Project**, crie uma lista das tarefas que deseja baseline (aqui `myList`) e passe‑a para `setBaseline`. Preencha `myList` com as tarefas que adicionou se precisar de um baseline seletivo.

## Etapa 4: Definir Baseline para Todo o Projeto
```java
project.setBaseline(BaselineType.Baseline);
```
Se preferir definir baseline para o projeto inteiro em uma única chamada, basta invocar `setBaseline` com o `BaselineType` desejado.

## Como adicionar tarefa ao Microsoft Project usando Aspose.Tasks
Além da tarefa única mostrada acima, você pode adicionar múltiplas tarefas, subtarefas e atribuir recursos. Cada chamada a `add()` retorna um objeto `Task` que pode ser configurado adicionalmente (duração, data de início, etc.).

## Como definir baseline sem MS Project
Aspose.Tasks permite a criação de baseline totalmente por código. Você pode definir diferentes tipos de baseline (Baseline, Baseline1‑Baseline10) alterando o enum `BaselineType`, permitindo rastrear várias revisões de baseline sem nunca abrir o MS Project.

## Problemas Comuns e Soluções
- **Baseline não aparece:** Certifique‑se de chamar `project.save("output.mpp")` após definir o baseline (etapa de salvamento omitida aqui por brevidade).  
- **Lista de tarefas aparece vazia:** Verifique se está adicionando tarefas ao pai correto (`getRootTask()` ou uma subtarefa).  
- **Erros de incompatibilidade de versão:** Use o JAR mais recente do Aspose.Tasks para garantir compatibilidade com formatos .mpp mais novos.

## Perguntas Frequentes

**P: Posso usar Aspose.Tasks para Java sem o Microsoft Project instalado?**  
R: Sim, o Aspose.Tasks funciona de forma independente e não requer o Microsoft Project na máquina host.

**P: O Aspose.Tasks para Java é compatível com diferentes versões do Microsoft Project?**  
R: Absolutamente. A biblioteca suporta arquivos Project de 2007 até as versões mais recentes de 2024.

**P: Posso manipular recursos do projeto usando Aspose.Tasks para Java?**  
R: Sim, você pode adicionar, atualizar e excluir recursos programaticamente, assim como as tarefas.

**P: O Aspose.Tasks para Java suporta a definição de dependências entre tarefas?**  
R: Sim, você pode definir relacionamentos predecessor‑successor usando a classe `TaskLink`.

**P: Existe suporte técnico disponível para Aspose.Tasks para Java?**  
R: Sim, você pode obter ajuda através do [forum de suporte](https://forum.aspose.com/c/tasks/15), onde a equipe da Aspose e a comunidade respondem às dúvidas.

## Conclusão
Seguindo estas etapas, você aprendeu como **criar lista de tarefas Java**, **adicionar tarefa ao Microsoft Project** e **definir baseline sem MS Project** usando Aspose.Tasks. Essa abordagem simplifica a automação de projetos, elimina a necessidade de instalações desktop do Project e oferece controle programático total sobre os dados do seu projeto.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Última atualização:** 2026-01-18  
**Testado com:** Aspose.Tasks para Java 24.12  
**Autor:** Aspose  

---