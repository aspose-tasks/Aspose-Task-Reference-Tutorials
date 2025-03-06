---
title: Tipo de cálculo em Aspose.Tasks
linktitle: Tipo de cálculo em Aspose.Tasks
second_title: API Aspose.Tasks .NET
description: Aprenda como personalizar cálculos de valor em projetos .NET com Tipo de Cálculo na biblioteca Aspose.Tasks.
type: docs
weight: 30
url: /pt/net/advanced-features/calculation-type/
---
## Introdução

Neste tutorial, exploraremos o recurso Tipo de cálculo em Aspose.Tasks for .NET. Aspose.Tasks é uma biblioteca poderosa que permite aos desenvolvedores .NET trabalhar com arquivos do Microsoft Project sem a necessidade do Microsoft Project instalado em seus sistemas. O Tipo de Cálculo nos permite definir como os valores são calculados para tarefas e tarefas de resumo dentro de um projeto.

## Pré-requisitos

Antes de começarmos, certifique-se de ter os seguintes pré-requisitos:

1. Conhecimento básico de C# e .NET framework.
2. Visual Studio instalado em seu sistema.
3.  Biblioteca Aspose.Tasks para .NET instalada. Você pode baixá-lo em[aqui](https://releases.aspose.com/tasks/net/).
4.  Acesso à documentação do Aspose.Tasks for .NET para referência, disponível[aqui](https://reference.aspose.com/tasks/net/).

## Importar namespaces

Antes de mergulhar no exemplo, importe os namespaces necessários:

```csharp
using Aspose.Tasks;
using System;


```

## Passo 1: Crie um novo projeto

Primeiro, vamos criar um novo objeto de projeto:

```csharp
var project = new Project();
```

## Etapa 2: adicionar uma tarefa

Agora, vamos adicionar uma tarefa ao nosso projeto:

```csharp
var task = project.RootTask.Children.Add("Task");
task.Set(Tsk.Start, new DateTime(2020, 4, 16, 8, 0, 0));
task.Set(Tsk.Duration, project.GetDuration(1, TimeUnitType.Day));
```

## Etapa 3: Definir o tipo de cálculo para um atributo estendido

Criaremos uma definição de atributo estendida com o Tipo de Cálculo definido como Fórmula:

```csharp
var calculation = ExtendedAttributeDefinition.CreateTaskDefinition(ExtendedAttributeTask.Date5, null);
calculation.CalculationType = CalculationType.Formula;
calculation.SummaryRowsCalculationType = SummaryRowsCalculationType.UseFormula;
calculation.Formula = "[stARt]";
project.ExtendedAttributes.Add(calculation);
```

## Etapa 4: definir o tipo de cálculo para linhas de resumo

A seguir, criaremos outra definição de atributo estendida onde os valores para tarefas de resumo são calculados usando o tipo de rollup Average:

```csharp
var lookup = ExtendedAttributeDefinition.CreateTaskDefinition(ExtendedAttributeTask.Cost1, null);
lookup.SummaryRowsCalculationType = SummaryRowsCalculationType.Rollup;
lookup.RollupType = RollupType.Average;
project.ExtendedAttributes.Add(lookup);
```

## Conclusão

Neste tutorial, exploramos como trabalhar com o tipo de cálculo no Aspose.Tasks for .NET. Ao definir Tipos de Cálculo para atributos estendidos, podemos personalizar como os valores são calculados para tarefas e tarefas de resumo dentro de um projeto, proporcionando maior flexibilidade e controle.

## Perguntas frequentes

### Q1: Qual é o tipo de cálculo em Aspose.Tasks?

A1: O tipo de cálculo em Aspose.Tasks determina como os valores são calculados para tarefas e tarefas de resumo dentro de um projeto, oferecendo opções como Fórmula e Rollup.

### P2: Como defino o tipo de cálculo para um atributo estendido?

A2: Você pode definir o tipo de cálculo para um atributo estendido definindo sua propriedade CalculationType adequadamente.

### P3: Posso personalizar o tipo de cálculo para linhas de resumo em um projeto?

A3: Sim, Aspose.Tasks permite especificar o tipo de cálculo para linhas de resumo, permitindo personalizar cálculos de valor com base em seus requisitos.

### P4: Existem diferentes tipos de rollup disponíveis para cálculos de tarefas de resumo?

A4: Sim, Aspose.Tasks fornece vários tipos de rollup, como Média, Soma e Contagem para calcular valores de tarefas de resumo.

### P5: Onde posso encontrar mais recursos no Aspose.Tasks for .NET?

 R5: Você pode explorar a documentação e os fóruns de suporte da comunidade disponíveis no[Aspose.Tasks para .NET](https://reference.aspose.com/tasks/net/) para orientação e assistência abrangentes.