---
date: 2026-02-26
description: Aprenda como dividir tarefas com Aspose.Tasks para Java – o guia definitivo
  sobre como dividir tarefas, definir o calendário do projeto e criar atribuição de
  recursos.
linktitle: Split Tasks in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Como dividir tarefas no Aspose.Tasks
url: /pt/java/task-properties/split-tasks/
weight: 29
---

26" keep same.

"**Tested With:** Aspose.Tasks for Java 24.11" keep.

"**Author:** Aspose" keep.

Then closing shortcodes.

Then backtop button shortcode.

Make sure to keep all markdown formatting.

Now produce final content.{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Como Dividir Tarefas no Aspose.Tasks

## Introdução
Se você está procurando **como dividir tarefas** em um projeto baseado em Java, chegou ao lugar certo. Aspose.Tasks for Java oferece uma maneira limpa e programática de dividir uma tarefa de longa duração em partes menores e gerenciáveis, o que ajuda no nivelamento de recursos, relatórios precisos e cronogramas de projeto mais apertados. Neste tutorial, percorreremos todo o processo — desde a configuração do calendário do projeto até a criação de uma atribuição de recurso e, finalmente, a divisão da tarefa em múltiplos segmentos.

## Respostas Rápidas
- **O que é divisão de tarefas?** Dividir uma única tarefa em vários intervalos menores, preservando sua duração total.  
- **Por que dividir tarefas em Java?** Permite alocação precisa de recursos e melhor acompanhamento do progresso.  
- **Qual biblioteca ajuda?** Aspose.Tasks for Java fornece métodos incorporados para divisão e faseamento temporal.  
- **Preciso de licença?** Um teste gratuito funciona para desenvolvimento; uma licença é necessária para produção.  
- **Qual versão do Java é suportada?** A biblioteca funciona com Java 8 e versões mais recentes.

## Pré-requisitos
Antes de mergulhar no tutorial, certifique‑se de que você tem os seguintes pré‑requisitos em vigor:
- Java Development Kit (JDK) instalado na sua máquina.  
- Biblioteca Aspose.Tasks for Java baixada e adicionada ao seu projeto. Você pode baixá‑la na [documentação do Aspose.Tasks for Java](https://reference.aspose.com/tasks/java/).

## Importar Pacotes
Comece importando os pacotes necessários para o seu projeto Java:

```java
import com.aspose.tasks.Asn;
import com.aspose.tasks.Calendar;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.ResourceAssignment;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.Task;
import com.aspose.tasks.Tsk;
import com.aspose.tasks.WorkContourType;
```

## Etapa 1: Criar um Novo Projeto
Inicie criando um novo projeto usando a biblioteca Aspose.Tasks:

```java
// Create a new project
Project splitTaskProject = new Project();
```

## Etapa 2: Definir o Calendário do Projeto
Definir o **calendário do projeto** estabelece dias úteis, feriados e a linha do tempo geral para o seu cronograma. Esta etapa é essencial para cálculos precisos de faseamento temporal.

```java
// Get a standard calendar
Calendar calendar = splitTaskProject.get(Prj.CALENDAR);
// Set project's calendar settings
java.util.Calendar cal = java.util.Calendar.getInstance();
// ... (continue with the example)
```

## Etapa 3: Adicionar uma Tarefa Raiz
Todo projeto precisa de um contêiner raiz. Adicionar uma tarefa raiz fornece um local para anexar todas as tarefas subsequentes.

```java
// Root task
Task rootTask = splitTaskProject.getRootTask();
rootTask.set(Tsk.NAME, "Root");
```

## Etapa 4: Adicionar uma Nova Tarefa para Dividir
Crie a tarefa que você pretende dividir. Aqui definimos uma duração de três dias como exemplo.

```java
// Add a new task
Task taskToSplit = rootTask.getChildren().add("Task1");
taskToSplit.set(Tsk.DURATION, splitTaskProject.getDuration(3));
```

## Etapa 5: Criar uma Atribuição de Recurso
Uma **atribuição de recurso** vincula um recurso (ou um placeholder) à tarefa. Isso é necessário antes de gerar dados de faseamento temporal.

```java
// Create a new resource assignment
ResourceAssignment splitResourceAssignment = splitTaskProject.getResourceAssignments().add(taskToSplit, null);
```

## Etapa 6: Gerar Dados de Faseamento Temporal
Dados de faseamento temporal representam como o trabalho é distribuído ao longo da duração da tarefa. Gerá‑los prepara a tarefa para a divisão.

```java
// Generate resource assignment timephased data
splitResourceAssignment.timephasedDataFromTaskDuration(calendar);
```

## Etapa 7: Dividir a Tarefa
Agora nós **dividimos a tarefa em partes**. Neste exemplo dividimos a tarefa de três dias em três segmentos de um dia cada.

```java
// Split the task into 3 parts
java.util.Calendar cal = java.util.Calendar.getInstance();
java.util.Calendar cal2 = java.util.Calendar.getInstance();
// ... (continue with the example)
```

## Por que Dividir Tarefas?
Dividir tarefas oferece controle mais granular sobre:
- **Nivelamento de recursos:** Atribuir recursos diferentes a cada segmento.
- **Acompanhamento de progresso:** Atualizar o status por segmento.
- **Relatórios:** Gerar gráficos de Gantt e relatórios mais detalhados.

## Problemas Comuns e Soluções
- **Dados de calendário ausentes:** Certifique‑se de chamar `timephasedDataFromTaskDuration` antes de dividir.  
- **Segmentos de duração zero:** Verifique se cada intervalo dividido tem duração diferente de zero; caso contrário, a biblioteca o ignorará.  
- **Exceções de licença:** Executar sem uma licença válida pode adicionar uma marca d'água aos arquivos exportados.

## Perguntas Frequentes
### Posso dividir tarefas com durações diferentes?
Sim, você pode ajustar a duração de cada parte para atender aos requisitos do seu projeto.

### O Aspose.Tasks for Java é compatível com todas as versões do Java?
Aspose.Tasks for Java foi projetado para funcionar perfeitamente com Java 8 e versões mais recentes, garantindo ampla compatibilidade.

### Posso usar o Aspose.Tasks for Java gratuitamente?
Aspose.Tasks for Java oferece um teste gratuito, permitindo que você explore seus recursos antes de efetuar a compra.

### Como posso obter suporte para o Aspose.Tasks for Java?
Visite o [forum de suporte do Aspose.Tasks for Java](https://forum.aspose.com/c/tasks/15) para obter assistência e conectar‑se com a comunidade.

### Preciso de uma licença temporária para o Aspose.Tasks for Java?
Você pode obter uma licença temporária neste [link](https://purchase.aspose.com/temporary-license/) para fins de teste e avaliação.

---

**Last Updated:** 2026-02-26  
**Tested With:** Aspose.Tasks for Java 24.11  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}