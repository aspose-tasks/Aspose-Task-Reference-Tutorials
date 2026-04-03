---
date: 2026-04-03
description: Aprenda a agendar tarefas de gerenciamento de projetos e como adicionar
  tarefas recorrentes usando Aspose.Tasks para .NET, incluindo salvar o projeto como
  MPP.
keywords:
- project management task scheduling
- how to add recurring task
- save project as mpp
linktitle: Repetição por dia do ano no Aspose.Tasks
second_title: Aspose.Tasks .NET API
title: Agendamento de Tarefas de Gerenciamento de Projetos com Repetição por Dia do
  Ano no Aspose.Tasks
url: /pt/net/advanced-features/repetition-by-year-day/
weight: 27
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Agendamento de Tarefas de Gerenciamento de Projetos com Repetição por Dia do Ano no Aspose.Tasks

## Introdução

Um **agendamento de tarefas de gerenciamento de projetos** eficaz é a espinha dorsal de qualquer projeto bem‑sucedido. Quando as tarefas se repetem anualmente — como auditorias anuais, janelas de manutenção ou revisões sazonais — lidar com essas recorrências manualmente pode se tornar propenso a erros e consumir tempo. Aspose.Tasks para .NET simplifica isso permitindo que você defina programaticamente padrões de dia‑do‑ano, para que possa se concentrar no que realmente importa: entregar valor. Neste tutorial, você aprenderá **como adicionar lógica de tarefa recorrente** baseada em um dia específico do ano e verá exatamente **como salvar o projeto como MPP** para integração perfeita com o Microsoft Project.

## Respostas Rápidas
- **O que significa “repetição por dia do ano”?** Ele agenda uma tarefa em um dia específico de um mês específico a cada ano.  
- **Qual classe da API cria a recorrência?** `YearlyRecurrencePattern` combinada com `ByYearDayRepetition`.  
- **Posso definir uma data de início e fim?** Sim, usando `EndByRecurrenceRange`.  
- **Qual formato de arquivo é produzido?** O projeto é salvo como um arquivo MPP (`SaveFileFormat.Mpp`).  
- **Preciso de uma licença para produção?** É necessária uma licença comercial para uso não‑avaliativo.

## Pré‑requisitos

Antes de mergulhar no tutorial, certifique‑se de que você tem os seguintes pré‑requisitos em vigor:

1. Biblioteca Aspose.Tasks para .NET: Baixe e instale a biblioteca Aspose.Tasks para .NET a partir do [site](https://releases.aspose.com/tasks/net/).  
2. Ambiente de Desenvolvimento: Configure um ambiente de desenvolvimento adequado com o Visual Studio ou qualquer outra IDE de sua preferência para desenvolvimento .NET.  
3. Conhecimento Básico de C#: Familiarize‑se com os fundamentos da linguagem de programação C# para acompanhar os exemplos de código.  
4. Conceitos de Gerenciamento de Projetos: Compreender os conceitos de gerenciamento de projetos e agendamento de tarefas ajudará a entender os conceitos do tutorial de forma eficaz.

## Importar Namespaces

Antes de começarmos a codificar, vamos importar os namespaces necessários para facilitar a manipulação de tarefas usando Aspose.Tasks para .NET.

```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.Saving;
```

Agora, vamos dividir o exemplo fornecido em várias etapas e elucidar cada etapa em detalhe.

## Como Adicionar Tarefa Recorrente com Padrão de Dia do Ano

### Passo 1: Carregar Arquivo de Projeto

```csharp
// The path to th documents directory.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "Project1.mpp");
```

Aqui, inicializamos um novo objeto `Project` e carregamos um arquivo de projeto existente chamado **Project1.mpp**.

### Passo 2: Definir Parâmetros da Tarefa Recorrente

```csharp
var parameters = new RecurringTaskParameters
{
    TaskName = "t1",
    Duration = project.GetDuration(1, TimeUnitType.Day),
    RecurrencePattern = new YearlyRecurrencePattern
    {
        Repetition = new ByYearDayRepetition { DayPosition = 1, Month = Month.July },
        RecurrenceRange = new EndByRecurrenceRange
        {
            Start = new DateTime(2018, 7, 1, 8, 0, 0),
            Finish = new DateTime(2019, 7, 1, 17, 0, 0)
        }
    }
};
```

Nesta etapa, definimos os parâmetros para nossa tarefa recorrente. Especificamos o nome da tarefa, a duração e o padrão de recorrência. Para recorrência anual, usamos o `YearlyRecurrencePattern` e definimos a repetição para ocorrer no **1º dia de julho** usando `ByYearDayRepetition`. Além disso, definimos o intervalo de recorrência de 1 de julho de 2018 a 1 de julho de 2019.

### Passo 3: Adicionar Tarefa ao Projeto

```csharp
project.RootTask.Children.Add(parameters);
```

Aqui, adicionamos os parâmetros da tarefa recorrente definidos à tarefa raiz do projeto.

### Passo 4: Salvar Projeto como MPP

```csharp
project.Save(DataDir + "CanAddRecurringTask_Years_YearDay_EndByRecurrenceRange_Test.mpp", SaveFileFormat.Mpp);
```

Finalmente, nós **salvamos o projeto como um arquivo MPP**, tornando‑o pronto para ser aberto no Microsoft Project ou em qualquer visualizador compatível.

## Por Que Isso Importa

- **Automação** – Elimina a inserção manual de tarefas anuais, reduzindo erros humanos.  
- **Consistência** – Garante que o mesmo padrão dia‑mês seja aplicado ao longo de vários anos.  
- **Integração** – O arquivo MPP resultante pode ser compartilhado com as partes interessadas que dependem do Microsoft Project.  

## Armadilhas Comuns & Dicas

- **Precisão do DateTime** – Certifique‑se de que a hora de início esteja alinhada ao calendário do seu projeto; caso contrário, a tarefa pode aparecer deslocada.  
- **Fusos horários** – A API trabalha com objetos `DateTime`; considere a conversão para UTC se sua aplicação abranger várias regiões.  
- **Aplicação de licença** – No modo de avaliação, o MPP salvo pode conter uma marca d'água; use uma licença válida para produção.

## Perguntas Frequentes

**Q: O Aspose.Tasks pode lidar com padrões de recorrência complexos?**  
A: Sim, o Aspose.Tasks fornece suporte abrangente para vários padrões de recorrência, incluindo repetições anuais, mensais, semanais e diárias.

**Q: O Aspose.Tasks é compatível com diferentes formatos de arquivo de projeto?**  
A: Absolutamente, o Aspose.Tasks suporta formatos de arquivo de projeto populares como MPP, XML e CSV, garantindo compatibilidade entre diferentes ferramentas de gerenciamento de projetos.

**Q: O Aspose.Tasks oferece documentação e suporte para desenvolvedores?**  
A: Sim, os desenvolvedores podem acessar documentação extensa e buscar assistência nos fóruns da comunidade Aspose.Tasks para quaisquer dúvidas ou problemas que encontrarem.

**Q: Posso personalizar propriedades da tarefa, como duração e data de início, usando o Aspose.Tasks?**  
A: Certamente, o Aspose.Tasks fornece APIs robustas para manipular propriedades de tarefas dinamicamente, permitindo que os desenvolvedores personalizem durações, datas de início, dependências e muito mais.

**Q: O Aspose.Tasks é adequado tanto para projetos de pequena escala quanto para projetos de nível empresarial?**  
A: De fato, o Aspose.Tasks foi projetado para atender às necessidades de desenvolvedores que trabalham em projetos de todas as escalas, desde tarefas individuais até projetos empresariais de grande porte.

---

**Última Atualização:** 2026-04-03  
**Testado com:** Aspose.Tasks 24.12 for .NET  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}