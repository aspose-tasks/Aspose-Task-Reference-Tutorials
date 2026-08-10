---
date: 2026-04-06
description: Aprenda a adicionar um recurso ao projeto e definir períodos de disponibilidade
  do recurso usando Aspose.Tasks para .NET. Guia passo a passo para gerenciar calendários
  de recursos.
keywords:
- add resource to project
- set resource availability
- configure work schedule
linktitle: Trabalhando com Períodos de Disponibilidade no Aspose.Tasks
second_title: Aspose.Tasks .NET API
title: Adicionar recurso ao projeto e definir disponibilidade no Aspose.Tasks
url: /pt/net/advanced-features/working-with-availability-periods/
weight: 17
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Adicionar Recurso ao Projeto e Definir Disponibilidade no Aspose.Tasks

## Introdução

Neste tutorial você aprenderá **como adicionar recurso ao projeto** e, em seguida, definir seus períodos de disponibilidade usando a biblioteca Aspose.Tasks .NET. Gerenciar calendários de recursos é essencial para cronogramas de projeto realistas, e os passos abaixo orientam todo o processo — desde a criação de uma instância de projeto até a impressão dos detalhes de cada período.

## Respostas Rápidas
- **Qual é o objetivo principal?** Para adicionar um recurso a um projeto e configurar seus períodos de disponibilidade.  
- **Qual biblioteca é necessária?** Aspose.Tasks para .NET.  
- **Preciso de uma licença para produção?** Sim, é necessária uma licença comercial.  
- **Versões .NET suportadas?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6+.  
- **Tempo de implementação?** Normalmente menos de 15 minutos para cenários básicos.

## O que é “adicionar recurso ao projeto”?

Adicionar um recurso a um projeto cria um espaço reservado para uma pessoa, equipamento ou material que pode ser atribuído a tarefas. Uma vez que o recurso exista, você pode **definir a disponibilidade do recurso**, especificar seu calendário de trabalho e permitir que o agendador respeite essas restrições.

## Por que configurar cronograma de trabalho e períodos de disponibilidade?

- **Planejamento preciso:** As tarefas são agendadas somente quando o recurso está realmente livre.  
- **Controle de custos:** As unidades de disponibilidade refletem esforço em tempo parcial, ajudando a calcular corretamente os custos de mão‑de‑obra.  
- **Nivelamento de recursos:** O mecanismo pode nivelar automaticamente sobrecargas quando conhece o calendário de cada recurso.

## Pré‑requisitos

1. Visual Studio (ou qualquer IDE compatível com .NET).  
2. Aspose.Tasks para .NET – faça o download [aqui](https://releases.aspose.com/tasks/net/).  
3. Conhecimento básico de C#.

## Importar Namespaces

```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;
```

## Como adicionar recurso ao projeto?

### Etapa 1: Criar uma nova instância `Project`

```csharp
var project = new Project();
```

Este objeto representa todo o arquivo de projeto na memória.

### Etapa 2: Adicionar um recurso ao projeto

```csharp
var resource = project.Resources.Add("Work Resource");
```

A chamada cria um **recurso** chamado *Work Resource* que você pode associar posteriormente a tarefas.

### Etapa 3: Definir períodos de disponibilidade

```csharp
IEnumerable<AvailabilityPeriod> periods = this.GetPeriods();
```

`GetPeriods()` é um método auxiliar (implementação não mostrada) que devolve uma coleção de objetos `AvailabilityPeriod`. Cada período especifica uma data de início, uma data de término e as unidades (percentual de esforço em tempo integral) em que o recurso está disponível.

### Etapa 4: Adicionar os períodos ao recurso

```csharp
foreach (var period in periods)
{
    resource.AvailabilityPeriods.Add(period);
}
```

Aqui **definimos a disponibilidade do recurso** percorrendo a coleção e adicionando cada período ao calendário do recurso.

### Etapa 5: Exibir os detalhes da disponibilidade

```csharp
foreach (var period in resource.AvailabilityPeriods)
{
    Console.WriteLine("Available From: " + period.AvailableFrom);
    Console.WriteLine("Available To: " + period.AvailableTo);
    Console.WriteLine("Available Units: " + period.AvailableUnits);
    Console.WriteLine();
}
```

A saída no console permite verificar que os períodos foram armazenados corretamente.

## Armadilhas Comuns e Dicas

- **Precisão de datas:** `AvailableFrom` e `AvailableTo` são valores `DateTime`; assegure‑se de defini‑los para meia‑noite se desejar períodos de dia inteiro.  
- **Faixa de unidades:** Valores válidos são 0‑100 %; valores fora desse intervalo gerarão uma exceção.  
- **Períodos sobrepostos:** Períodos sobrepostos são mesclados automaticamente, mas é mais claro mantê‑los distintos.

## Perguntas Frequentes

### Q1: Posso usar Aspose.Tasks para .NET em projetos comerciais?
A1: Sim, Aspose.Tasks para .NET pode ser usado em projetos comerciais. Você pode adquirir uma licença [aqui](https://purchase.aspose.com/buy).

### Q2: Existe uma versão de avaliação gratuita disponível para Aspose.Tasks para .NET?
A2: Sim, você pode obter uma avaliação gratuita de Aspose.Tasks para .NET [aqui](https://releases.aspose.com/).

### Q3: Onde posso encontrar a documentação do Aspose.Tasks para .NET?
A3: Você pode encontrar a documentação [aqui](https://reference.aspose.com/tasks/net/).

### Q4: Como posso obter suporte para Aspose.Tasks para .NET?
A4: Você pode obter suporte no fórum da comunidade [aqui](https://forum.aspose.com/c/tasks/15).

### Q5: Vocês oferecem licenças temporárias para Aspose.Tasks para .NET?
A5: Sim, licenças temporárias estão disponíveis [aqui](https://purchase.aspose.com/temporary-license/).

---

**Última atualização:** 2026-04-06  
**Testado com:** Aspose.Tasks para .NET (última versão estável)  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}