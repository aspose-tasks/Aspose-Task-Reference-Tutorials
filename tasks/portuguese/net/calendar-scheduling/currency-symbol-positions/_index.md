---
date: 2026-07-19
description: Aprenda a controlar o símbolo da moeda após o valor em projetos .NET
  de forma fácil com o Aspose.Tasks.
keywords:
- currency symbol after amount
- Aspose.Tasks currency formatting
- .NET project financial reporting
lastmod: 2026-07-19
linktitle: Posições do símbolo da moeda no Aspose.Tasks
og_description: Aprenda a colocar o símbolo da moeda após o valor usando o Aspose.Tasks
  para .NET. Siga instruções passo a passo e as melhores práticas.
og_image_alt: Guide showing currency symbol after amount configuration in Aspose.Tasks
og_title: Símbolo da moeda após o valor no Aspose.Tasks — Guia rápido
schemas:
- author: Aspose
  dateModified: '2026-07-19'
  description: Learn how to control currency symbol after amount in .NET projects
    effortlessly with Aspose.Tasks.
  headline: How to Place Currency Symbol After Amount in Aspose.Tasks
  type: TechArticle
- description: Learn how to control currency symbol after amount in .NET projects
    effortlessly with Aspose.Tasks.
  name: How to Place Currency Symbol After Amount in Aspose.Tasks
  steps:
  - name: Load the Project File
    text: The `Project` class loads an existing MS‑Project file or creates a new one
      in memory.
  - name: Set Currency Symbol Position
    text: '`CurrencySymbolPosition` is an enum that lets you choose `Before` or `After`.
      Setting it to `After` places the symbol after the numeric value.'
  - name: Work with the Project
    text: After you have configured the symbol position, you can continue adding tasks,
      resources, or custom fields as needed. The setting is persisted when you save
      the project.
  type: HowTo
- questions:
  - answer: Yes, you can adjust `CurrencySymbolPosition` as many times as needed;
      just set the property and re‑save the project.
    question: Can I change the currency symbol position multiple times within the
      same project?
  - answer: Absolutely. Aspose.Tasks supports more than 50 international currencies,
      allowing you to work with any regional format.
    question: Does Aspose.Tasks support currencies other than the US Dollar?
  - answer: Yes, you can obtain a free trial of Aspose.Tasks for .NET from [here](https://releases.aspose.com/).
    question: Is there a trial version available for Aspose.Tasks for .NET?
  - answer: Certainly! You can seek support and assistance from the Aspose.Tasks community
      forum [here](https://forum.aspose.com/c/tasks/15).
    question: Can I seek assistance if I encounter any issues while using Aspose.Tasks
      for .NET?
  - answer: You can purchase a license for Aspose.Tasks for .NET from [here](https://purchase.aspose.com/buy).
    question: How can I purchase a license for Aspose.Tasks for .NET?
  type: FAQPage
second_title: Aspose.Tasks .NET API
tags:
- currency symbol
- Aspose.Tasks
- .NET financial management
title: Como colocar o símbolo da moeda após o valor no Aspose.Tasks
url: /pt/net/calendar-scheduling/currency-symbol-positions/
weight: 22
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Como colocar o símbolo da moeda após o valor no Aspose.Tasks

## Introdução

Ao gerar relatórios de custos de projetos, a posição do **currency symbol after amount** pode afetar a legibilidade e a conformidade com padrões regionais. O Aspose.Tasks para .NET permite controlar essa formatação com apenas algumas linhas de código, garantindo que cada valor financeiro apareça exatamente como seus stakeholders esperam. Neste tutorial percorreremos as etapas necessárias, explicaremos por que a configuração é importante e mostraremos como aplicá‑la em um projeto .NET do mundo real.

## Respostas rápidas
- **O que significa “currency symbol after amount”?** Exibe o símbolo (por exemplo, $) após o valor numérico, como `100 $`.
- **Qual propriedade controla a posição?** `CurrencySymbolPosition` no objeto `Project`.
- **Preciso de uma licença?** Uma versão de avaliação funciona para desenvolvimento; uma licença comercial é necessária para produção.
- **Moedas suportadas?** Mais de 50 moedas são incorporadas, cobrindo a maioria dos mercados globais.
- **Posso alterar a configuração em tempo de execução?** Sim, você pode atualizá‑la a qualquer momento antes de salvar o arquivo do projeto.

## O que é a configuração “currency symbol after amount”?
A opção **currency symbol after amount** determina se o sinal da moeda aparece antes ou depois do valor numérico em todos os campos monetários de um projeto. Ajustar essa configuração garante que os relatórios estejam em conformidade com as convenções contábeis locais sem necessidade de pós‑processamento manual. Também melhora a legibilidade para stakeholders acostumados a esse formato.

## Por que usar Aspose.Tasks para formatação de moeda?
O Aspose.Tasks oferece suporte a **mais de 50 moedas** e pode lidar com projetos com **mais de 10.000 tarefas** sem carregar todo o arquivo na memória, proporcionando desempenho rápido mesmo em hardware modesto. A API fornece controle programático, eliminando a necessidade de edições manuais em planilhas. Isso torna a geração de relatórios financeiros em larga escala eficiente e confiável.

## Pré‑requisitos

### 1. Instalação do Aspose.Tasks para .NET
Certifique‑se de que a biblioteca Aspose.Tasks esteja instalada. Você pode baixá‑la [aqui](https://releases.aspose.com/tasks/net/).

### 2. Conhecimento básico de programação .NET
É necessário ter uma compreensão fundamental de programação .NET para seguir os exemplos.

## Importar Namespaces

O namespace `Aspose.Tasks` fornece acesso à classe `Project` e aos enums relacionados.

A classe `Project` é o objeto de nível superior do Aspose.Tasks que representa um único arquivo de projeto na memória. Após importar o namespace, você pode começar a trabalhar com os dados do projeto.

```csharp

```

Agora, vamos dividir o exemplo em etapas claras e acionáveis.

## Como definir o símbolo da moeda após o valor?

`CurrencySymbolPosition` é uma enumeração que especifica se o símbolo da moeda aparece antes ou depois do valor numérico.

Carregue seu projeto, defina `CurrencySymbolPosition` como `After` e, em seguida, salve – isso é tudo que você precisa para exibir o símbolo após o valor. Essa abordagem direta funciona para qualquer moeda suportada e não requer lógica de formatação adicional. Você também pode verificar a configuração exportando um relatório de custos de exemplo para garantir que o símbolo apareça corretamente.

### Etapa 1: Carregar o arquivo do projeto
A classe `Project` carrega um arquivo MS‑Project existente ou cria um novo na memória.

```csharp
var project = new Project(DataDir + "Project2.mpp");
```

### Etapa 2: Definir a posição do símbolo da moeda
`CurrencySymbolPosition` é um enum que permite escolher `Before` ou `After`. Definir como `After` coloca o símbolo após o valor numérico.

```csharp
project.Set(Prj.CurrencySymbolPosition, CurrencySymbolPositionType.Before);
```

### Etapa 3: Trabalhar com o projeto
Depois de configurar a posição do símbolo, você pode continuar adicionando tarefas, recursos ou campos personalizados conforme necessário. A configuração é mantida ao salvar o projeto.

```csharp
// Perform other operations with the project...
```

## Problemas comuns e soluções
- **O símbolo ainda aparece antes do valor:** Certifique‑se de definir a propriedade *antes* de chamar `Save`. Alterá‑la após salvar requer salvar o arquivo novamente.
- **Moeda não suportada:** Verifique se o código da moeda que você está usando está listado na lista de suporte do Aspose.Tasks (mais de 50 moedas).
- **Desempenho reduzido em projetos grandes:** Use `ProjectReader` para transmitir arquivos grandes se você ultrapassar 10.000 tarefas.

## Perguntas frequentes

**Q: Posso mudar a posição do símbolo da moeda várias vezes dentro do mesmo projeto?**  
A: Sim, você pode ajustar `CurrencySymbolPosition` quantas vezes precisar; basta definir a propriedade e salvar o projeto novamente.

**Q: O Aspose.Tasks suporta moedas diferentes do dólar americano?**  
A: Absolutamente. O Aspose.Tasks suporta mais de 50 moedas internacionais, permitindo que você trabalhe com qualquer formato regional.

**Q: Existe uma versão de avaliação disponível para o Aspose.Tasks para .NET?**  
A: Sim, você pode obter uma avaliação gratuita do Aspose.Tasks para .NET [aqui](https://releases.aspose.com/).

**Q: Posso buscar assistência se encontrar problemas ao usar o Aspose.Tasks para .NET?**  
A: Certamente! Você pode obter suporte e assistência no fórum da comunidade Aspose.Tasks [aqui](https://forum.aspose.com/c/tasks/15).

**Q: Como posso comprar uma licença para o Aspose.Tasks para .NET?**  
A: Você pode adquirir uma licença para o Aspose.Tasks para .NET [aqui](https://purchase.aspose.com/buy).

## Conclusão

Controlar o **currency symbol after amount** é uma parte vital da geração de relatórios financeiros em softwares de gerenciamento de projetos. Com o Aspose.Tasks para .NET você pode definir essa opção programaticamente, suportando mais de 50 moedas e lidando com projetos grandes de forma eficiente. Aplique as etapas acima para garantir que os relatórios do seu projeto correspondam às expectativas de formatação de qualquer localidade.

---

**Last Updated:** 2026-07-19  
**Tested With:** Aspose.Tasks 24.11 for .NET  
**Author:** Aspose

## Tutoriais relacionados

- [Gerenciando a coleção de calendários no Aspose.Tasks](/tasks/net/calendar-scheduling/calendar-collection/)
- [Coleção de exceções de calendário no Aspose.Tasks](/tasks/net/calendar-scheduling/calendar-exception-collection/)
- [Manipulando taxas do MS Project com Aspose.Tasks para .NET](/tasks/net/rate-recurring-tasks/handling-rates/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}