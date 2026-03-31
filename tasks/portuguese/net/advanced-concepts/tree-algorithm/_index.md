---
date: 2026-03-19
description: Aprenda como adicionar recurso ao projeto e calcular a duração das tarefas
  usando o Algoritmo de Árvore do Aspose.Tasks, e atribuir recursos às tarefas em
  .NET.
linktitle: Add Resource to Project with Tree Algorithm in Aspose.Tasks
second_title: Aspose.Tasks .NET API
title: Adicionar recurso ao projeto com algoritmo de árvore no Aspose.Tasks
url: /pt/net/advanced-concepts/tree-algorithm/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Adicionar Recurso ao Projeto com Algoritmo de Árvore no Aspose.Tasks

## Introdução

Neste tutorial você descobrirá **como adicionar recurso ao projeto** aproveitando o poderoso Algoritmo de Árvore fornecido pelo Aspose.Tasks para .NET. Vamos percorrer a criação de uma hierarquia de tarefas, o cálculo da duração das tarefas e a atribuição de recursos às tarefas — tudo de forma clara, passo a passo, que você pode copiar para sua própria solução.

## Respostas Rápidas
- **O que o Algoritmo de Árvore faz?** Ele percorre uma hierarquia de tarefas para agregar valores de trabalho de forma eficiente.  
- **Qual operação principal este guia cobre?** Adicionar um recurso a um projeto e atualizar os totais de trabalho.  
- **Preciso de uma licença?** Uma licença temporária ou completa é necessária para uso em produção.  
- **Posso usar isso com .NET Core?** Sim, o Aspose.Tasks suporta .NET Framework e .NET Core.  
- **Quanto tempo leva a implementação?** Cerca de 10‑15 minutos para um arquivo de projeto básico.

## O que é “adicionar recurso ao projeto” no Aspose.Tasks?

Adicionar um recurso a um projeto significa criar um objeto `Resource`, definir seu tipo (por exemplo, trabalho) e vinculá‑lo a uma ou mais tarefas via `ResourceAssignments`. Isso permite que o agendador calcule esforço, custo e a duração total do projeto.

## Por que usar o Algoritmo de Árvore para cálculos de trabalho de recursos?

O Algoritmo de Árvore percorre a árvore de tarefas uma única vez, acumulando o trabalho das tarefas folha até suas tarefas de resumo. Essa abordagem é muito mais eficiente do que iterar sobre cada tarefa individualmente, especialmente em projetos grandes com hierarquias profundas. Também garante que os valores de trabalho resumido permaneçam sincronizados com seus filhos.

## Pré‑requisitos

1. **Visual Studio** – qualquer edição recente (2019, 2022 ou posterior).  
2. **Aspose.Tasks for .NET** – faça o download a partir de [aqui](https://releases.aspose.com/tasks/net/).  
3. **Conhecimento básico de C#** – você deve estar confortável com classes, objetos e LINQ simples.

## Importar Namespaces

No seu projeto C#, importe os namespaces necessários para trabalhar com as funcionalidades do Aspose.Tasks:

```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.Util;
```

Agora, vamos dividir cada exemplo em várias etapas:

## Etapa 1: Carregar Arquivo de Projeto

```csharp
var project = new Project(DataDir + "Project1.mpp");
```

Carregue o arquivo de projeto na memória usando a classe `Project`.

## Etapa 2: Definir Hierarquia de Tarefas

```csharp
var root = project.RootTask.Children.Add("Project Management");
var summary = root.Children.Add("Manage iteration");
var task = summary.Children.Add("Acquire staff");
```

Defina a hierarquia de tarefas adicionando tarefas pai e filho.

## Etapa 3: Definir Propriedades da Tarefa (incluindo **calcular duração da tarefa**)

```csharp
task.Set(Tsk.Start, new DateTime(1999, 5, 3, 9, 0, 0));
task.Set(Tsk.Duration, project.GetDuration(8 * 14, TimeUnitType.Hour));
task.Set(Tsk.Finish, project.Get(Prj.Calendar).GetFinishDateByStartAndWork(task.Get(Tsk.Start), task.Get(Tsk.Duration)));
```

Aqui nós **calculamos a duração da tarefa** convertendo horas de trabalho em um objeto `Duration` e então derivamos a data de término.

## Etapa 4: Adicionar Recurso (**atribuir recursos às tarefas**)

```csharp
var resource = project.Resources.Add("Project Manager");
resource.Set(Rsc.Type, ResourceType.Work);
project.ResourceAssignments.Add(task, resource);
```

Este trecho **adiciona um recurso ao projeto** e **atribui recursos às tarefas** para que o agendador saiba quem é responsável pelo trabalho.

## Etapa 5: Aplicar Algoritmo de Árvore

```csharp
var acc = new WorkAccumulator();
TaskUtils.Apply(summary, acc, 0);
```

Inicialize a classe `WorkAccumulator` e aplique o Algoritmo de Árvore para reunir o trabalho comum em toda a hierarquia.

## Etapa 6: Atualizar Trabalho da Tarefa

```csharp
var summaryWork = acc.Work.ToDouble();
summary.Set(Tsk.Work, project.GetWork(summaryWork));
summary.Set(Tsk.RemainingWork, project.GetWork(summaryWork));
```

Atualize os valores de trabalho das tarefas com base nas informações reunidas.

## Problemas Comuns & Dicas

- **Configurações de calendário ausentes:** Se a data de término parecer incorreta, certifique‑se de que o calendário do projeto esteja configurado corretamente antes de chamar `GetFinishDateByStartAndWork`.  
- **Incompatibilidade de tipo de recurso:** Sempre defina `Rsc.Type` como `ResourceType.Work` para recursos baseados em esforço; caso contrário, a acumulação de trabalho pode retornar zero.  
- **Dica de especialista:** Após atualizar o trabalho, chame `project.Save("UpdatedProject.mpp")` para persistir as alterações.

## Conclusão

Seguindo estas etapas, você agora sabe como **adicionar recurso ao projeto**, **calcular a duração da tarefa** e **atribuir recursos às tarefas** usando o Algoritmo de Árvore do Aspose.Tasks. Este método simplifica o gerenciamento da hierarquia e mantém os valores de trabalho resumido precisos com código mínimo.

## Perguntas Frequentes

### Q1: O que é Aspose.Tasks para .NET?

R1: Aspose.Tasks para .NET é uma API poderosa que permite aos desenvolvedores manipular arquivos Microsoft Project programaticamente usando C#.

### Q2: Posso baixar uma versão de avaliação gratuita do Aspose.Tasks para .NET?

R2: Sim, você pode baixar uma versão de avaliação gratuita do Aspose.Tasks para .NET a partir de [aqui](https://releases.aspose.com/).

### Q3: Onde posso encontrar a documentação do Aspose.Tasks para .NET?

R3: Você pode encontrar a documentação do Aspose.Tasks para .NET [aqui](https://reference.aspose.com/tasks/net/).

### Q4: Como posso obter suporte para Aspose.Tasks para .NET?

R4: Para suporte relacionado ao Aspose.Tasks para .NET, você pode visitar o [forum do Aspose.Tasks](https://forum.aspose.com/c/tasks/15).

### Q5: Existe uma licença temporária disponível para fins de teste?

R5: Sim, você pode obter uma licença temporária para fins de teste a partir de [aqui](https://purchase.aspose.com/temporary-license/).

## Perguntas Frequentes

**Q: Posso usar esta abordagem com um arquivo de projeto grande existente?**  
A: Absolutamente. O Algoritmo de Árvore funciona em qualquer instância `Project`, independentemente do tamanho.

**Q: O algoritmo também atualiza valores de custo?**  
A: O exemplo foca no trabalho, mas você pode estendê‑lo para custo acumulando `Tsk.Cost` de forma similar.

**Q: Quais versões do .NET são suportadas?**  
A: Aspose.Tasks suporta .NET Framework 4.5+, .NET Core 3.1+, .NET 5+ e .NET 6+.

**Q: Como lidar com múltiplos recursos por tarefa?**  
A: Adicione cada recurso com `project.ResourceAssignments.Add(task, resource)`; o acumulador somará automaticamente o trabalho deles.

---

**Last Updated:** 2026-03-19  
**Tested With:** Aspose.Tasks 24.11 for .NET  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}