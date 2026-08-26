---
date: 2026-03-24
description: Aprenda como definir o modo de cálculo no Aspose.Tasks para .NET, abrangendo
  o modo automático, manual e nenhum, para gerenciar dependências de tarefas.
linktitle: How to Set Calculation Mode in Aspose.Tasks for .NET
second_title: Aspose.Tasks .NET API
title: Como definir o modo de cálculo no Aspose.Tasks para .NET
url: /pt/net/advanced-features/calculation-mode/
weight: 29
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Como Definir o Modo de Cálculo no Aspose.Tasks para .NET

## Introdução

Aspose.Tasks for .NET é uma API poderosa que permite trabalhar com arquivos Microsoft Project programaticamente. Uma das configurações mais importantes que você encontrará é o **modo de cálculo**, que controla como as datas das tarefas e os cronogramas do projeto são atualizados. Neste tutorial você aprenderá **como definir o cálculo**, explorará **modo de cálculo automático**, **modo de cálculo manual** e **modo de cálculo nenhum**, e verá como essas opções afetam **gerenciar dependências de tarefas**, **criar data de início do projeto** e **vincular relacionamentos de término‑início** das tarefas.

## Respostas Rápidas
- **O que é modo de cálculo?** Determina se as datas das tarefas são recalculadas automaticamente, manualmente ou não são recalculadas.  
- **Por que usar o modo de cálculo manual?** Para obter controle total sobre quando o cronograma é atualizado, útil em atualizações em massa.  
- **Qual modo é o padrão?** Modo de cálculo automático, que atualiza as datas instantaneamente após alterações.  
- **Posso mudar o modo em tempo de execução?** Sim—basta definir a propriedade `CalculationMode` no objeto `Project`.  
- **Preciso de licença?** Uma licença válida do Aspose.Tasks é necessária para uso em produção.

## O que significa “definir cálculo” no Aspose.Tasks?

Definir o modo de cálculo é tão simples quanto atribuir um valor enum ao `Project.CalculationMode`. O enum oferece três opções: `Automatic`, `Manual` e `None`. Escolher o modo correto depende do seu fluxo de trabalho—se você deseja atualizações instantâneas, processamento em lote ou controle total.

## Pré-requisitos

Antes de começar, certifique‑se de que você tem:

1. **Visual Studio** – qualquer versão recente (2019, 2022 ou posterior).  
2. **Aspose.Tasks for .NET** – faça o download e instale a biblioteca a partir de [here](https://releases.aspose.com/tasks/net/).  
3. **Conhecimento básico de C#** – você deve estar confortável em criar aplicações console e usar pacotes NuGet.

## Importar Namespaces

Antes de começarmos a trabalhar com Aspose.Tasks for .NET, vamos importar os namespaces necessários:

```csharp
using Aspose.Tasks;
using System;
```

## Como Definir o Modo de Cálculo

A seguir você encontrará exemplos passo a passo para cada modo de cálculo. Os blocos de código permanecem inalterados em relação ao tutorial original; as explicações ao redor foram ampliadas para maior clareza.

### Aplicando o Modo de Cálculo Automático

O modo automático recalcula as datas instantaneamente sempre que você modifica tarefas ou vínculos.

#### Etapa 1: Criar uma nova instância de Project

```csharp
var project = new Project
{
   CalculationMode = CalculationMode.Automatic
};
```

#### Etapa 2: Definir a data de início do projeto e adicionar tarefas

```csharp
project.Set(Prj.StartDate, new DateTime(2015, 4, 15));
var task1 = project.RootTask.Children.Add("Task 1");
var task2 = project.RootTask.Children.Add("Task 2");
```

#### Etapa 3: Vincular tarefas (fim‑para‑início)

```csharp
project.TaskLinks.Add(task1, task2, TaskLinkType.FinishToStart);
```

#### Etapa 4: Verificar datas recalculadas

```csharp
Console.WriteLine("Task1 Start + 1 Equals Task2 Start : {0} ", task1.Get(Tsk.Start).AddDays(1).Equals(task2.Get(Tsk.Start)));
// Add more verifications as needed
```

### Aplicando o Modo de Cálculo Manual

O modo manual desativa as atualizações automáticas, permitindo que você processe alterações em lote antes de forçar uma recalculação.

#### Etapa 1: Criar uma nova instância de Project

```csharp
var project = new Project
{
   CalculationMode = CalculationMode.Manual
};
```

#### Etapa 2: Definir a data de início do projeto e adicionar tarefas

```csharp
project.Set(Prj.StartDate, new DateTime(2015, 4, 15));
var task1 = project.RootTask.Children.Add("Task 1");
var task2 = project.RootTask.Children.Add("Task 2");
```

#### Etapa 3: Verificar propriedades da tarefa

```csharp
Console.WriteLine("Task1.Id Equals 1 : {0} ", task1.Get(Tsk.Id).Equals(1));
// Add more verifications as needed
```

#### Etapa 4: Vincular tarefas e verificar datas (sem recalculação automática)

```csharp
project.TaskLinks.Add(task1, task2, TaskLinkType.FinishToStart);
```

### Aplicando o Modo de Cálculo Nenhum

O modo nenhum desativa todos os cálculos internos. Use‑o quando precisar apenas ler ou exportar dados sem alterar o cronograma.

#### Etapa 1: Criar uma nova instância de Project

```csharp
var project = new Project
{
   CalculationMode = CalculationMode.None
};
```

#### Etapa 2: Adicionar uma nova tarefa

```csharp
var task = project.RootTask.Children.Add("Task");
```

#### Etapa 3: Verificar propriedades da tarefa (sem IDs automáticos)

```csharp
Console.WriteLine("Task.Id Equals 0 : {0} ", task.Get(Tsk.Id).Equals(0));
// Add more verifications as needed
```

## Problemas Comuns e Soluções

| Problema | Por que acontece | Correção |
|----------|------------------|----------|
| As datas não são atualizadas após vincular tarefas | O projeto está em modo **Manual** ou **None** | Defina `project.CalculationMode = CalculationMode.Automatic` ou chame `project.Calculate()` manualmente |
| IDs das tarefas permanecem em 0 | Usar modo **None** impede a geração de IDs | Troque para modo **Automatic** ou **Manual**, então recalcule |
| Falha ao vincular com `ArgumentException` | A data de início do predecessor é posterior à do sucessor ao usar modo **Manual** sem recalculação | Garanta datas de início corretas ou recalcule após adicionar vínculos |

## Perguntas Frequentes

**Q1: Posso mudar o modo de cálculo dinamicamente durante a execução?**  
A1: Sim, você pode modificar a propriedade `CalculationMode` a qualquer momento no seu código e então chamar `project.Calculate()` se precisar de uma atualização imediata.

**Q2: O Aspose.Tasks suporta outros formatos de arquivos de gerenciamento de projetos além do Microsoft Project?**  
A2: O Aspose.Tasks foca principalmente nos formatos do Microsoft Project, mas também oferece suporte a Primavera P6 XML, Primavera DB e Asta Powerproject XML.

**Q3: O Aspose.Tasks é adequado tanto para projetos de pequena escala quanto para projetos de nível empresarial?**  
A3: Absolutamente. A API escala de listas simples de tarefas a cronogramas complexos e multi‑fase de nível empresarial.

**Q4: Posso integrar o Aspose.Tasks com outras bibliotecas e frameworks .NET?**  
A4: Sim, você pode combinar o Aspose.Tasks com ASP.NET, WPF, Xamarin ou qualquer outra tecnologia .NET para criar soluções ricas de gerenciamento de projetos.

**Q5: Existe um fórum da comunidade ou canal de suporte disponível para usuários do Aspose.Tasks?**  
A5: Sim, você pode visitar o [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15) para suporte da comunidade e discussões.

---

**Última atualização:** 2026-03-24  
**Testado com:** Aspose.Tasks 24.11 for .NET  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}