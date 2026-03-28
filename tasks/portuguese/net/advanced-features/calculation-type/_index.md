---
date: 2026-03-24
description: Aprenda a configurar cálculos no Aspose.Tasks para .NET, com exemplos
  para calcular valores resumidos, definir fórmulas de cálculo e configurar o resumo
  de agregação.
linktitle: Calculation Type in Aspose.Tasks
second_title: Aspose.Tasks .NET API
title: Como definir o tipo de cálculo no Aspose.Tasks
url: /pt/net/advanced-features/calculation-type/
weight: 30
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Como Definir o Tipo de Cálculo no Aspose.Tasks

## Introdução

Se você precisa de **como definir cálculo** regras para tarefas e linhas de resumo em um arquivo Microsoft Project, este tutorial mostra exatamente isso usando Aspose.Tasks para .NET. Vamos percorrer um **exemplo de tipo de cálculo** completo, demonstrar como **calcular valores de resumo**, e explicar como **definir fórmula de cálculo** e **configurar resumo de acumulação** para atributos estendidos. Ao final, você será capaz de adicionar uma tarefa a um projeto, definir lógica de cálculo personalizada e controlar o comportamento de acumulação com confiança.

## Respostas Rápidas
- **Qual é o objetivo principal?** Controlar como os valores de tarefa e de resumo são calculados em um arquivo Project.  
- **Qual classe da API é usada?** `ExtendedAttributeDefinition` juntamente com `CalculationType` e `SummaryRowsCalculationType`.  
- **Posso usar uma fórmula?** Sim – defina `CalculationType = CalculationType.Formula` e forneça uma string de fórmula.  
- **Como faço o roll‑up dos valores de resumo?** Use `SummaryRowsCalculationType = SummaryRowsCalculationType.Rollup` e especifique um `RollupType` como `Average`.  
- **Preciso de uma licença?** Uma licença válida do Aspose.Tasks é necessária para uso em produção.

## O que é Tipo de Cálculo e como definir cálculo?

`CalculationType` informa ao Aspose.Tasks como calcular o valor de um atributo estendido. Você pode escolher um valor estático, uma fórmula ou permitir que a biblioteca faça roll‑up dos valores das tarefas filhas. Definir o cálculo corretamente é essencial quando você deseja que o projeto reflita regras de negócios personalizadas sem atualizações manuais.

## Por que usar o tipo de cálculo para calcular valores de resumo?

Quando um projeto contém tarefas de resumo, frequentemente você precisa que as linhas de resumo exibam dados agregados (por exemplo, custo total, duração média). Ao configurar **calcular valores de resumo** através de `SummaryRowsCalculationType` e `RollupType`, o Aspose.Tasks pode manter esses agregados sincronizados automaticamente à medida que você modifica tarefas individuais.

## Pré-requisitos

1. Conhecimento básico de C# e da estrutura .NET.  
2. Visual Studio (qualquer versão recente) instalado na sua máquina.  
3. Biblioteca Aspose.Tasks para .NET instalada – você pode baixá‑la [aqui](https://releases.aspose.com/tasks/net/).  
4. Acesso à documentação oficial do Aspose.Tasks para .NET para referência, disponível [aqui](https://reference.aspose.com/tasks/net/).

## Importar Namespaces

Antes de mergulhar no exemplo, certifique‑se de importar os namespaces necessários:

```csharp
using Aspose.Tasks;
using System;
```

## Etapa 1: Criar um novo Project

Primeiro, criamos um objeto `Project` vazio que conterá nossas tarefas e atributos personalizados.

```csharp
var project = new Project();
```

## Etapa 2: Adicionar uma Tarefa ao Project

Agora nós **adicionamos dados de tarefa ao projeto** criando uma tarefa simples, definindo sua data de início e atribuindo uma duração de um dia.

```csharp
var task = project.RootTask.Children.Add("Task");
task.Set(Tsk.Start, new DateTime(2020, 4, 16, 8, 0, 0));
task.Set(Tsk.Duration, project.GetDuration(1, TimeUnitType.Day));
```

## Etapa 3: Definir o Tipo de Cálculo para um Atributo Estendido (Exemplo de Fórmula)

Aqui criamos uma definição de atributo estendido cujo valor é calculado a partir de uma fórmula. Isso demonstra um **exemplo de tipo de cálculo** e mostra como **definir fórmula de cálculo**.

```csharp
var calculation = ExtendedAttributeDefinition.CreateTaskDefinition(ExtendedAttributeTask.Date5, null);
calculation.CalculationType = CalculationType.Formula;
calculation.SummaryRowsCalculationType = SummaryRowsCalculationType.UseFormula;
calculation.Formula = "[stARt]";
project.ExtendedAttributes.Add(calculation);
```

## Etapa 4: Definir o Tipo de Cálculo para Linhas de Resumo (Configurar Resumo de Acumulação)

Em seguida, criamos outra definição de atributo estendido que indica ao Aspose.Tasks para **configurar resumo de acumulação** usando o tipo de acumulação *Average*. Esta é a forma típica de **calcular valores de resumo** para custo, trabalho ou campos personalizados.

```csharp
var lookup = ExtendedAttributeDefinition.CreateTaskDefinition(ExtendedAttributeTask.Cost1, null);
lookup.SummaryRowsCalculationType = SummaryRowsCalculationType.Rollup;
lookup.RollupType = RollupType.Average;
project.ExtendedAttributes.Add(lookup);
```

## Problemas Comuns & Solução de Problemas

| Sintoma | Causa Provável | Correção |
|---------|----------------|----------|
| Fórmula retorna `null` | Referência de campo incorreta na fórmula | Verifique o nome do campo entre colchetes (ex.: `[Start]` e não `[stARt]`). |
| Linhas de resumo exibem 0 | `SummaryRowsCalculationType` não definido ou `RollupType` incorreto | Garanta que `SummaryRowsCalculationType = SummaryRowsCalculationType.Rollup` e escolha um `RollupType` adequado. |
| Projeto falha ao carregar após adicionar atributos | Incompatibilidade entre a definição do atributo e o uso da tarefa | Adicione a definição do atributo **antes** de atribuí‑la a qualquer tarefa. |

## Conclusão

Neste tutorial, abordamos **como definir cálculo** nas regras do Aspose.Tasks para .NET, desde a criação de uma tarefa simples até a definição de tipos de cálculo baseados em fórmula e em roll‑up. Ao dominar essas configurações, você obtém controle detalhado sobre **calcular valores de resumo**, permitindo análises de projeto mais avançadas sem trabalho manual em planilhas.

## Perguntas Frequentes

### Q1: O que é Tipo de Cálculo no Aspose.Tasks?

A1: O Tipo de Cálculo no Aspose.Tasks determina como os valores são calculados para tarefas e tarefas de resumo dentro de um projeto, oferecendo opções como Formula e Rollup.

### Q2: Como defino o Tipo de Cálculo para um Atributo Estendido?

A2: Você pode definir o Tipo de Cálculo para um Atributo Estendido definindo sua propriedade CalculationType adequadamente.

### Q3: Posso personalizar o Tipo de Cálculo para linhas de resumo em um projeto?

A3: Sim, o Aspose.Tasks permite especificar o Tipo de Cálculo para linhas de resumo, permitindo que você ajuste os cálculos de valores de acordo com suas necessidades.

### Q4: Existem diferentes Tipos de Rollup disponíveis para cálculos de tarefas de resumo?

A4: Sim, o Aspose.Tasks oferece vários Tipos de Rollup, como Average, Sum e Count, para calcular valores de tarefas de resumo.

### Q5: Onde posso encontrar mais recursos sobre Aspose.Tasks para .NET?

A5: Você pode explorar a documentação e os fóruns de suporte da comunidade disponíveis no [Aspose.Tasks for .NET](https://reference.aspose.com/tasks/net/) para obter orientações e assistência abrangentes.

---

**Última Atualização:** 2026-03-24  
**Testado com:** Aspose.Tasks for .NET (última versão)  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}