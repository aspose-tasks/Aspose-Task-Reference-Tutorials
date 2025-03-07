---
title: Coleção de períodos de disponibilidade em Aspose.Tasks
linktitle: Coleção de períodos de disponibilidade em Aspose.Tasks
second_title: API Aspose.Tasks .NET
description: Aprenda como gerenciar períodos de disponibilidade de recursos em Aspose.Tasks for .NET. Este tutorial passo a passo orienta você na adição, atualização e remoção de períodos de disponibilidade, garantindo um planejamento eficaz dos recursos do projeto.
weight: 18
url: /pt/net/advanced-features/availability-period-collection/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Coleção de períodos de disponibilidade em Aspose.Tasks

## Introdução

Neste tutorial, exploraremos como trabalhar com a coleta do período de disponibilidade de um recurso no Aspose.Tasks for .NET. Gerenciar os períodos de disponibilidade é crucial para o gerenciamento de projetos, permitindo-nos definir quando os recursos estão disponíveis para as tarefas de um projeto.

## Pré-requisitos

Antes de começarmos, certifique-se de ter o seguinte:

1. Visual Studio: certifique-se de ter o Visual Studio instalado em seu sistema.
2.  Aspose.Tasks for .NET: Baixe e instale a biblioteca Aspose.Tasks for .NET em[aqui](https://releases.aspose.com/tasks/net/).
3. Compreensão Básica: Familiaridade com C# e .NET framework.

## Importar namespaces

Primeiro, precisamos importar os namespaces necessários para o nosso projeto:

```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;


```

Vamos dividir o código de exemplo em várias etapas e entender cada parte:

## Etapa 1: inicializar o projeto e o recurso

```csharp
// O caminho para o diretório de documentos.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "UpdateResourceData.mpp");
var resource = project.Resources.GetById(1);
```

Aqui estamos carregando um arquivo de projeto e obtendo um recurso específico por seu ID.

## Etapa 2: limpar os períodos de disponibilidade existentes

```csharp
resource.AvailabilityPeriods.Clear();
```

Limpamos todos os períodos de disponibilidade existentes associados ao recurso.

## Etapa 3: adicionar períodos de disponibilidade

```csharp
IEnumerable<AvailabilityPeriod> periods = this.GetPeriods();
foreach (var period in periods)
{
    if (!resource.AvailabilityPeriods.IsReadOnly)
    {
        resource.AvailabilityPeriods.Add(period);
    }
}
```

Iteramos uma coleção de períodos de disponibilidade e os adicionamos ao recurso.

## Etapa 4: insira um novo período de disponibilidade

```csharp
var period2013 = new AvailabilityPeriod { AvailableFrom = new DateTime(2013, 1, 1), AvailableTo = new DateTime(2013, 12, 12), AvailableUnits = 0.81 };

if (!resource.AvailabilityPeriods.Contains(period2013))
{
    resource.AvailabilityPeriods.Insert(1, period2013);
}
```

Criamos um novo período de disponibilidade para o ano de 2013 e inserimos na coleção.

## Etapa 5: Exibir períodos de disponibilidade

```csharp
Console.WriteLine("Count of availability periods: " + resource.AvailabilityPeriods.Count);
foreach (var period in resource.AvailabilityPeriods)
{
    Console.WriteLine("Available From: " + period.AvailableFrom);
    Console.WriteLine("Available To: " + period.AvailableTo);
    Console.WriteLine("Available Units: " + period.AvailableUnits);
    Console.WriteLine();
}
```

Imprimimos a contagem e detalhes de cada período de disponibilidade associado ao recurso.

## Etapa 6: copiar períodos de disponibilidade para outro recurso

```csharp
var periodsToCopy = new AvailabilityPeriod[resource.AvailabilityPeriods.Count];
resource.AvailabilityPeriods.CopyTo(periodsToCopy, 0);

var otherResource = project.Resources.GetById(2);
otherResource.AvailabilityPeriods.Clear();
foreach (var period in periodsToCopy)
{
    otherResource.AvailabilityPeriods.Add(period);
}
```

Copiamos os períodos de disponibilidade de um recurso para outro.

## Etapa 7: atualizar e remover períodos de disponibilidade

```csharp
// Atualizar unidades disponíveis para um período específico
otherResource.AvailabilityPeriods[otherResource.AvailabilityPeriods.Count - 2].AvailableUnits = 0.90;

// Remover um período específico
otherResource.AvailabilityPeriods.Remove(period2013);
```

Atualizamos as unidades disponíveis por um período e retiramos períodos específicos da coleção.

## Conclusão

Neste tutorial, aprendemos como trabalhar com coleções de períodos de disponibilidade em Aspose.Tasks for .NET. Gerenciar a disponibilidade de recursos é essencial para o planejamento e execução eficazes do projeto.

## Perguntas frequentes

### Q1: Posso adicionar campos personalizados aos períodos de disponibilidade?

A1: Não, os períodos de disponibilidade no Aspose.Tasks for .NET não oferecem suporte a campos personalizados.

### P2: Os períodos de disponibilidade estão vinculados a tarefas específicas?

A2: Não, os períodos de disponibilidade estão associados aos recursos e definem quando estes estão disponíveis para tarefas em geral.

### P3: Posso importar períodos de disponibilidade de fontes externas?

A3: Sim, você pode importar períodos de disponibilidade de várias fontes de dados usando Aspose.Tasks para APIs .NET.

### P4: Como lidar com períodos de disponibilidade sobrepostos?

A4: Aspose.Tasks for .NET não fornece mecanismos integrados para lidar com períodos sobrepostos. Talvez seja necessário implementar uma lógica personalizada para gerenciar esses cenários.

### P5: Existe um limite para o número de períodos de disponibilidade que um recurso pode ter?

R5: Não há limite predefinido para o número de períodos de disponibilidade que um recurso pode ter, mas o desempenho pode ser prejudicado com um grande número de períodos.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
