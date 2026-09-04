---
date: 2026-07-05
description: Aprenda como acompanhar o orçamento do projeto e gerenciar os custos
  do projeto usando Aspose.Tasks para .NET. Defina cost accrual types para um acompanhamento
  preciso dos custos.
keywords:
- track project budget
- manage project costs
- how to set accrual
- define project cost tracking
- access resource by id
linktitle: Cost Accrual Types no Aspose.Tasks
schemas:
- author: Aspose
  dateModified: '2026-07-05'
  description: Learn how to track project budget and manage project costs using Aspose.Tasks
    for .NET. Define cost accrual types for accurate cost tracking.
  headline: Track Project Budget with Cost Accrual Types in Aspose.Tasks
  type: TechArticle
- description: Learn how to track project budget and manage project costs using Aspose.Tasks
    for .NET. Define cost accrual types for accurate cost tracking.
  name: Track Project Budget with Cost Accrual Types in Aspose.Tasks
  steps:
  - name: Import Namespaces
    text: 'Let''s start by importing the necessary namespaces to access Aspose.Tasks
      functionality in our .NET project: Now that we have the namespaces ready, we
      can move on to loading a project file.'
  - name: Load Project File
    text: The `Project` class represents a Microsoft Project file and provides access
      to its tasks, resources, and other data. First, we need to load the project
      file into our application. We create a new `Project` object and initialize it
      with the path to our project file.
  - name: Access Resource
    text: 'The `Resources` collection holds all resources defined in the project.
      The `GetById` method retrieves a resource by its unique identifier. Next, we
      access the resource to which we want to apply the cost accrual type. We use
      the `GetById` method of the `Resources` collection and pass the resource ID '
  - name: Set Cost Accrual Type
    text: The `Set` method assigns a value to a resource field. Here, we set the cost
      accrual type for the resource. In this example, we are setting it to `CostAccrualType.End`,
      which means costs will not be accrued until remaining work is zero. Choosing
      `End` is ideal when you want to **track project budget*
  - name: Continue Working with the Project
    text: After setting the cost accrual type, you can continue working with the project
      as needed, performing additional operations or calculations such as generating
      cost reports, updating assignments, or exporting the file.
  type: HowTo
- questions:
  - answer: Yes, iterate through `project.Resources` and assign the desired `CostAccrualType`
      to each resource within a `foreach` loop.
    question: Can I change the cost accrual type for multiple resources simultaneously?
  - answer: Aspose.Tasks provides `Start`, `Prorated`, and `Duration`—each aligns
      with a different billing strategy.
    question: What are the other available cost accrual types besides `End`?
  - answer: Retrieve the value via `resource.Get(TskResource.CostAccrualType)`; it
      returns the enum representing the current setting.
    question: How can I determine the current cost accrual type for a specific resource?
  - answer: Absolutely. Both tasks and resources expose a `CostAccrualType` property,
      allowing independent configuration per entity.
    question: Is it possible to apply different cost accrual types to different tasks
      in the same project?
  - answer: No, the library currently supports the four built‑in types only; custom
      logic must be implemented externally if required.
    question: Does Aspose.Tasks support custom cost accrual types?
  type: FAQPage
second_title: Aspose.Tasks .NET API
title: Acompanhe o orçamento do projeto com Cost Accrual Types no Aspose.Tasks
url: /pt/net/calendar-scheduling/cost-accrual-types/
weight: 19
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Acompanhar o Orçamento do Projeto com Tipos de Acumulação de Custos no Aspose.Tasks

## Introdução

Rastrear com precisão o **acompanhamento do orçamento do projeto** é a espinha dorsal da entrega bem‑sucedida de projetos. Quando as informações de custo são capturadas nos momentos corretos, você pode prever excessos, ajustar recursos e manter as partes interessadas informadas. Aspose.Tasks para .NET oferece aos desenvolvedores controle granular sobre a acumulação de custos, permitindo que você decida *quando* um custo é registrado — seja no início do trabalho, continuamente ou somente quando o trabalho é concluído. Este tutorial orienta você pelos conceitos, mostra como definir um tipo de acumulação e demonstra as melhores práticas para um acompanhamento confiável do orçamento.

## Respostas Rápidas
- **Qual é o objetivo principal dos tipos de acumulação de custos?** Eles determinam o ponto no ciclo de vida de uma tarefa em que o custo é reconhecido, permitindo um acompanhamento preciso do orçamento.  
- **Qual valor de enum atraso o custo até que o trabalho termine?** `CostAccrualType.End`.  
- **Preciso de uma licença para executar o código?** Sim, uma licença válida do Aspose.Tasks é necessária para uso em produção.  
- **Posso alterar os tipos de acumulação para vários recursos ao mesmo tempo?** Sim — percorra a coleção `Resources` e atribua o tipo desejado.  
- **Quais versões do .NET são suportadas?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.

## O que é Tipo de Acumulação de Custos?

Um **tipo de acumulação de custos** informa ao Aspose.Tasks quando aplicar o custo de um recurso ao orçamento do projeto. Ele é representado pela enumeração `CostAccrualType` e pode ser definido por recurso ou por tarefa. Escolher o tipo correto garante que os dados de custo estejam alinhados com as políticas de faturamento da sua organização, seja necessário registrar custos no início do trabalho, rateados ao longo da duração ou somente após a conclusão.

## Por que acompanhar o orçamento do projeto usando tipos de acumulação de custos?

Aspose.Tasks suporta **quatro** opções de acumulação — `Start`, `Prorated`, `Duration` e `End` — cobrindo toda a gama de cenários típicos de contabilidade de projetos. Selecionar a opção apropriada permite alinhar o reconhecimento de custos com ciclos de faturamento contratuais, reduzir a variância nos relatórios financeiros e gerar demonstrações de custos que se integrem perfeitamente aos sistemas ERP, tudo isso mantendo o uso de memória baixo para projetos grandes.

## Pré-requisitos

Antes de começarmos, certifique‑se de que você tem os seguintes pré‑requisitos:

### 1. Instalar Aspose.Tasks para .NET
Para começar, você precisa ter o Aspose.Tasks para .NET instalado em seu ambiente de desenvolvimento. Você pode baixar a biblioteca na [página de download](https://releases.aspose.com/tasks/net/) e seguir as instruções de instalação fornecidas.

### 2. Familiaridade com o .NET Framework
É necessário conhecimento básico do framework .NET e da linguagem de programação C# para acompanhar os exemplos neste tutorial.

## Como definir o Tipo de Acumulação de Custos para um Recurso?

Carregue o projeto, localize o recurso alvo e atribua o `CostAccrualType` desejado. O padrão de duas linhas abaixo é a abordagem padrão: criar uma instância `Project`, recuperar o recurso pelo seu ID e, em seguida, definir `CostAccrualType`. Essa sequência concisa garante que você **acompanhe o orçamento do projeto** com precisão desde o momento em que o recurso é adicionado.

### Passo 1: Importar Namespaces
Vamos começar importando os namespaces necessários para acessar a funcionalidade do Aspose.Tasks em nosso projeto .NET:

```csharp

```

### Passo 2: Carregar o Arquivo de Projeto
A classe `Project` representa um arquivo Microsoft Project e fornece acesso às suas tarefas, recursos e outros dados.

```csharp
var project = new Project("Project2.mpp");
```

### Passo 3: Acessar Recurso
A coleção `Resources` contém todos os recursos definidos no projeto. O método `GetById` recupera um recurso pelo seu identificador único.

```csharp
var resource = project.Resources.GetById(1);
```

Em seguida, acessamos o recurso ao qual queremos aplicar o tipo de acumulação de custos. Usamos o método `GetById` da coleção `Resources` e passamos o ID do recurso como argumento. Isso demonstra **acesso ao recurso por id**, um requisito comum ao automatizar atualizações de custos.

### Passo 4: Definir o Tipo de Acumulação de Custos
O método `Set` atribui um valor a um campo de recurso.

```csharp
resource.Set(Rsc.AccrueAt, CostAccrualType.End);
```

Aqui, definimos o tipo de acumulação de custos para o recurso. Neste exemplo, estamos definindo como `CostAccrualType.End`, o que significa que os custos não serão acumulados até que o trabalho restante seja zero. Escolher `End` é ideal quando você deseja **acompanhar o orçamento do projeto** somente após a tarefa estar totalmente concluída.

### Passo 5: Continuar Trabalhando com o Projeto
Após definir o tipo de acumulação de custos, você pode continuar trabalhando com o projeto conforme necessário, realizando operações ou cálculos adicionais, como gerar relatórios de custos, atualizar atribuições ou exportar o arquivo.

## Armadilhas Comuns e Dicas Profissionais
- **Dica profissional:** Sempre chame `project.Save` após modificar os tipos de acumulação para persistir as alterações.  
- **Armadilha:** Definir `CostAccrualType.Start` em um recurso que nunca inicia o trabalho inflará os relatórios de orçamento — verifique primeiro os cronogramas das tarefas.  
- **Dica profissional:** Use `project.Resources.ToList()` quando precisar atualizar em lote muitos recursos; isso evita buscas repetidas na coleção e melhora o desempenho em projetos grandes.

## Perguntas Frequentes

**Q: Posso alterar o tipo de acumulação de custos para vários recursos simultaneamente?**  
A: Sim, percorra `project.Resources` e atribua o `CostAccrualType` desejado a cada recurso dentro de um loop `foreach`.

**Q: Quais são os outros tipos de acumulação de custos disponíveis além de `End`?**  
A: Aspose.Tasks fornece `Start`, `Prorated` e `Duration` — cada um se alinha a uma estratégia de faturamento diferente.

**Q: Como posso determinar o tipo de acumulação de custos atual para um recurso específico?**  
A: Recupere o valor via `resource.Get(TskResource.CostAccrualType)`; ele retorna a enum que representa a configuração atual.

**Q: É possível aplicar diferentes tipos de acumulação de custos a diferentes tarefas no mesmo projeto?**  
A: Absolutamente. Tanto tarefas quanto recursos expõem a propriedade `CostAccrualType`, permitindo configuração independente por entidade.

**Q: O Aspose.Tasks suporta tipos de acumulação de custos personalizados?**  
A: Não, a biblioteca atualmente suporta apenas os quatro tipos incorporados; lógica personalizada deve ser implementada externamente, se necessário.

---

**Última atualização:** 2026-07-05  
**Testado com:** Aspose.Tasks 24.8 for .NET  
**Autor:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Tutoriais Relacionados

- [Calendário e Agendamento do Aspose.Tasks](/tasks/net/calendar-scheduling/)
- [Manipulando Tarifas do MS Project com Aspose.Tasks para .NET](/tasks/net/rate-recurring-tasks/handling-rates/)
- [Gerencie Recursos do MS Project com Facilidade usando Aspose.Tasks](/tasks/net/resource-risk-analysis/managing-resources/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}