---
date: 2026-06-25
description: Aprenda como adicionar tarefa e atualizar arquivos MPP usando Aspose.Tasks
  for Java, uma biblioteca de gerenciamento de projetos Java que permite criar arquivos
  de tarefa do Microsoft Project e salvar o projeto como MPP.
keywords:
- how to add task
- create task microsoft project
- java project management library
- save project as mpp
linktitle: Como adicionar tarefa e atualizar arquivo MPP no Aspose.Tasks
schemas:
- author: Aspose
  dateModified: '2026-06-25'
  description: Learn how to add task and update MPP files using Aspose.Tasks for Java,
    a java project management library that lets you create task Microsoft Project
    files and save project as MPP.
  headline: How to Add Task and Update MPP File in Aspose.Tasks
  type: TechArticle
- description: Learn how to add task and update MPP files using Aspose.Tasks for Java,
    a java project management library that lets you create task Microsoft Project
    files and save project as MPP.
  name: How to Add Task and Update MPP File in Aspose.Tasks
  steps:
  - name: '**Java Development Environment** – JDK 8+ installed and configured.'
    text: '**Java Development Environment** – JDK 8+ installed and configured.'
  - name: '**Aspose.Tasks for Java** – Download from the [download page](https://releases.aspose.com/tasks/java/).'
    text: '**Aspose.Tasks for Java** – Download from the [download page](https://releases.aspose.com/tasks/java/).'
  - name: '**Basic Java knowledge** – Familiarity with classes, objects, and date
      handling.'
    text: '**Basic Java knowledge** – Familiarity with classes, objects, and date
      handling.'
  type: HowTo
- questions:
  - answer: Loop over a collection of task names and repeat the “create task” block
      inside the loop.
    question: How do I add multiple tasks at once?
  - answer: Yes—use `task.set(Tsk.CUSTOM_FIELD_x, value)` where *x* is the field index.
    question: Can I set custom fields for the new task?
  - answer: Clone the source task (`Task cloned = sourceTask.clone();`) and then add
      it to the desired parent.
    question: Is it possible to copy an existing task as a template?
  - answer: Retrieve the task by ID (`Task existing = project.getRootTask().getChildren().getById(id);`)
      and modify its properties.
    question: What if I need to update an existing task instead of adding a new one?
  - answer: Yes—use `project.save("output.pdf", SaveFileFormat.Pdf);` or `SaveFileFormat.Png`
      for visual representations.
    question: Does Aspose.Tasks support saving to other formats like PDF or PNG?
  type: FAQPage
second_title: Aspose.Tasks Java API
title: Como adicionar tarefa e atualizar arquivo MPP no Aspose.Tasks
url: /pt/java/project-management/update-mpp/
weight: 19
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Como Adicionar Tarefa e Atualizar Arquivo MPP no Aspose.Tasks

## Introdução
Neste tutorial você aprenderá **como adicionar tarefa** a um arquivo Microsoft Project (MPP) existente e, em seguida, salvar o cronograma atualizado usando Aspose.Tasks for Java, uma biblioteca **java de gerenciamento de projetos** líder. Seja você quem esteja construindo um agendador personalizado, automatizando atualizações em massa ou integrando dados de projeto a um sistema maior, o guia passo a passo abaixo mostra exatamente como carregar um projeto, inserir uma nova tarefa, definir suas datas e persistir o resultado como um novo documento MPP.

## Respostas Rápidas
- **O que significa “how to add task” neste contexto?** Significa criar programaticamente um novo item de trabalho dentro de um arquivo MPP existente.  
- **Qual biblioteca realiza a operação?** Aspose.Tasks for Java, uma robusta biblioteca java de gerenciamento de projetos.  
- **Preciso de uma licença?** Um teste gratuito funciona para desenvolvimento; uma licença comercial é necessária para produção.  
- **Posso salvar o resultado como MPP?** Sim—use `project.save(..., SaveFileFormat.Mpp)` para **salvar o projeto como mpp**.  
- **Qual versão do Java é necessária?** Java 8 ou superior.

## O que é “how to add task” em um arquivo MPP?
Adicionar uma tarefa significa inserir um novo item de trabalho na hierarquia do projeto, definir suas datas de início/fim e persistir a alteração de volta ao arquivo MPP. Aspose.Tasks abstrai os detalhes de baixo nível do formato de arquivo, permitindo que você se concentre na lógica de negócios enquanto lida automaticamente com atribuições de recursos, calendários e cálculos de dependência. Ele também atualiza quaisquer atribuições relacionadas e recalcula o cronograma do projeto para manter a consistência entre tarefas dependentes.

## Por que usar Aspose.Tasks para Java?
- **Compatibilidade total**: Suporta 100% dos recursos do Microsoft Project 2007‑2021 (mais de 150 tipos de tarefa e 200 campos de recurso).  
- **Zero dependência**: Não requer COM, Office ou bibliotecas nativas—API Java pura funciona onde o JRE funciona.  
- **Conjunto rico de recursos**: Inclui vinculação de tarefas, alocação de recursos, campos personalizados e relatórios integrados.  
- **Alto desempenho**: Processa projetos com até 10.000 tarefas usando menos de 200 MB de RAM, tornando‑o ideal para automação no lado do servidor.

## Pré-requisitos
1. **Ambiente de Desenvolvimento Java** – JDK 8+ instalado e configurado.  
2. **Aspose.Tasks for Java** – Baixe da [página de download](https://releases.aspose.com/tasks/java/).  
3. **Conhecimento básico de Java** – Familiaridade com classes, objetos e manipulação de datas.  

## Importar Pacotes
Primeiro, importe as classes que você precisará. Isso lhe dá acesso à manipulação de projetos, propriedades de tarefas e tratamento de datas.

```java
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.Task;
import com.aspose.tasks.Tsk;
import java.util.Calendar;
```
```java
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.Task;
import com.aspose.tasks.Tsk;
import java.util.Calendar;
```  
`Project` representa um arquivo Microsoft Project carregado na memória. `SaveFileFormat` enumera os formatos nos quais você pode salvar, como MPP ou PDF. `Task` modela um item de trabalho individual dentro da hierarquia do projeto. `Tsk` fornece constantes para campos de tarefa usados ao definir ou recuperar valores. `Calendar` oferece utilitários de data‑hora para definir cronogramas.

## Etapa 1: Definir Diretório de Dados
```java
String dataDir = "Your Data Directory";
```  
Substitua `"Your Data Directory"` pelo caminho absoluto onde seu arquivo MPP de origem está localizado.

## Etapa 2: Ler Projeto Existente
A classe `Project` é o objeto central do Aspose.Tasks que representa um arquivo Microsoft Project na memória.  
```java
Project project = new Project(dataDir + "SampleMSP2010.mpp");
```  
O construtor carrega **SampleMSP2010.mpp**, fornecendo um modelo de objeto totalmente manipulável.

## Etapa 3: Criar uma Nova Tarefa (how to add task)
A classe `Task` representa um item de trabalho individual dentro da hierarquia do projeto.  
```java
Task task = project.getRootTask().getChildren().add("Task1");
```  
Esta linha **cria tarefa no mpp** adicionando um filho chamado *Task1* à tarefa raiz.

## Etapa 4: Definir Datas de Início e Término
A classe `Calendar` fornece utilitários de data‑hora; os meses são baseados em zero (por exemplo, `Calendar.JULY`).  
```java
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.set(2012, Calendar.JULY, 1, 8, 0, 0);
task.set(Tsk.START, cal.getTime());
cal.set(2012, Calendar.JULY, 1, 17, 0, 0);
task.set(Tsk.FINISH, cal.getTime());
```  
Aqui definimos o cronograma para a tarefa recém‑adicionada. Ajuste as datas para corresponder ao cronograma do seu projeto.

## Etapa 5: Salvar o Projeto (save project as mpp)
`SaveFileFormat.Mpp` indica ao Aspose.Tasks que escreva o arquivo novamente no formato nativo do Microsoft Project.  
```java
project.save(dataDir + "AfterLinking.mpp", SaveFileFormat.Mpp);
```  
O projeto atualizado, agora contendo a nova tarefa, é persistido como **AfterLinking.mpp**.

## Problemas Comuns e Soluções
| Problema | Solução |
|----------|----------|
| **Arquivo não encontrado** | Verifique se `dataDir` termina com um separador de caminho (`/` ou `\\`) e se o nome do arquivo está correto. |
| **Datas incorretas** | Lembre‑se de que os meses do `Calendar` são baseados em zero; `Calendar.JULY` corresponde a julho. |
| **Exceção de licença** | Instale uma licença válida do Aspose.Tasks antes de chamar qualquer API para evitar marcas d'água de avaliação. |

## Perguntas Frequentes
**Q: Como adiciono várias tarefas de uma vez?**  
A: Percorra uma coleção de nomes de tarefas e repita o bloco “create task” dentro do loop.

**Q: Posso definir campos personalizados para a nova tarefa?**  
A: Sim—use `task.set(Tsk.CUSTOM_FIELD_x, value)` onde *x* é o índice do campo.

**Q: É possível copiar uma tarefa existente como modelo?**  
A: Clone a tarefa fonte (`Task cloned = sourceTask.clone();`) e então adicione‑a ao pai desejado.

**Q: E se eu precisar atualizar uma tarefa existente em vez de adicionar uma nova?**  
A: Recupere a tarefa por ID (`Task existing = project.getRootTask().getChildren().getById(id);`) e modifique suas propriedades.

**Q: O Aspose.Tasks suporta salvar em outros formatos como PDF ou PNG?**  
A: Sim—use `project.save("output.pdf", SaveFileFormat.Pdf);` ou `SaveFileFormat.Png` para representações visuais.

---

**Última atualização:** 2026-06-25  
**Testado com:** Aspose.Tasks for Java 24.12  
**Autor:** Aspose

## Tutoriais Relacionados

- [Como Criar Arquivo MPP – Criar & Salvar Projeto Vazio em Formato MPP com Aspose.Tasks](/tasks/java/project-configuration/create-save-mpp/)
- [Como Criar Projeto – Definir Novos Atributos de Tarefa com Aspose.Tasks](/tasks/java/project-file-operations/set-attributes-new-tasks/)
- [Criar Lista de Tarefas Java – Linha de Base do MS Project usando Aspose.Tasks](/tasks/java/task-baselines/create-task-baseline/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< blocks/products/products-backtop-button >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}