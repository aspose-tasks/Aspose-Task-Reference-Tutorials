---
date: 2026-03-21
description: Aprenda a gerenciar períodos de disponibilidade para recursos e alcançar
  uma disponibilidade eficaz de recursos de projeto com Aspose.Tasks para .NET. Este
  guia passo a passo mostra como adicionar, atualizar e remover períodos de disponibilidade.
linktitle: Collection of Availability Periods in Aspose.Tasks
second_title: Aspose.Tasks .NET API
title: Disponibilidade de Recursos do Projeto – Gerenciando Períodos de Disponibilidade
  no Aspose.Tasks
url: /pt/net/advanced-features/availability-period-collection/
weight: 18
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Disponibilidade de Recursos do Projeto: Coleção de Períodos de Disponibilidade no Aspose.Tasks

Gerenciar **a disponibilidade de recursos do projeto** é uma parte essencial do planejamento bem‑sucedido. Neste tutorial você aprenderá **como gerenciar a disponibilidade** dos recursos usando a API Aspose.Tasks para .NET, passo a passo, desde o carregamento de um projeto até a cópia de períodos entre recursos.

## Respostas Rápidas
- **Qual é a classe principal para períodos de disponibilidade?** `AvailabilityPeriod` no namespace `Aspose.Tasks`.  
- **Posso limpar os períodos existentes?** Sim, chame `resource.AvailabilityPeriods.Clear()`.  
- **Como adiciono um novo período?** Crie um objeto `AvailabilityPeriod` e use `Add` ou `Insert`.  
- **É possível copiar períodos para outro recurso?** Absolutamente – use `CopyTo` e então adicione cada item ao recurso de destino.  
- **Preciso de licença para uso em produção?** Sim, uma licença comercial do Aspose.Tasks é necessária para implantações que não sejam de avaliação.

## O que é disponibilidade de recursos do projeto?
A disponibilidade de recursos do projeto define as datas e unidades (percentual de capacidade) em que um recurso pode ser atribuído a tarefas. Ao controlar esses períodos você evita sobrecarga e melhora a precisão do cronograma.

## Por que usar Aspose.Tasks para gerenciar períodos de disponibilidade?
- **Integração total com .NET** – sem interop COM, código totalmente gerenciado.  
- **Controle granular** – defina datas de início/fim exatas e unidades fracionárias.  
- **Cópia facilitada** – mova dados de disponibilidade entre recursos sem análise manual.  
- **Desempenho otimizado** – funciona de forma eficiente com arquivos MPP grandes.

## Pré‑requisitos
1. **Visual Studio** – qualquer versão recente (2019, 2022 ou posterior).  
2. **Aspose.Tasks para .NET** – faça o download [aqui](https://releases.aspose.com/tasks/net/).  
3. **Conhecimento básico de C#** – você deve estar confortável com classes, coleções e LINQ.

## Importar Namespaces

```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;
```

Importamos o namespace principal do Aspose.Tasks junto com as coleções padrão do .NET que precisaremos mais adiante.

## Etapa 1: Inicializar o Projeto e o Recurso

```csharp
// The path to th documents directory.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "UpdateResourceData.mpp");
var resource = project.Resources.GetById(1);
```

Aqui carregamos um arquivo MPP existente e obtém‑se o recurso cuja disponibilidade será editada (ID = 1).

## Etapa 2: Limpar Períodos de Disponibilidade Existentes

```csharp
resource.AvailabilityPeriods.Clear();
```

Limpar remove quaisquer períodos previamente definidos, proporcionando uma tela limpa.

## Etapa 3: Adicionar Períodos de Disponibilidade

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

Recuperamos uma coleção de objetos `AvailabilityPeriod` (o helper `GetPeriods` presume‑se definido em outro lugar) e adicionamos cada um, verificando se a coleção é gravável.

## Etapa 4: Inserir um Novo Período de Disponibilidade

```csharp
var period2013 = new AvailabilityPeriod { AvailableFrom = new DateTime(2013, 1, 1), AvailableTo = new DateTime(2013, 12, 12), AvailableUnits = 0.81 };

if (!resource.AvailabilityPeriods.Contains(period2013))
{
    resource.AvailabilityPeriods.Insert(1, period2013);
}
```

Este cria um período personalizado para o ano 2013 e o insere na posição 1 (segundo slot) caso ainda não esteja presente.

## Etapa 5: Exibir Períodos de Disponibilidade

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

Um dump rápido no console mostra a contagem total e os detalhes de cada período – útil para depuração ou verificação.

## Etapa 6: Copiar Períodos de Disponibilidade para Outro Recurso

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

Copiamos toda a coleção para um array, limpamos os períodos do recurso de destino e, em seguida, os repovoamos. Isso demonstra como duplicar dados de disponibilidade entre recursos.

## Etapa 7: Atualizar e Remover Períodos de Disponibilidade

```csharp
// Update available units for a specific period
otherResource.AvailabilityPeriods[otherResource.AvailabilityPeriods.Count - 2].AvailableUnits = 0.90;

// Remove a specific period
otherResource.AvailabilityPeriods.Remove(period2013);
```

Aqui ajustamos o `AvailableUnits` do penúltimo período e, em seguida, removemos o período de 2013 que adicionamos anteriormente.

## Problemas Comuns e Soluções
- **Erro de coleção somente‑leitura** – Certifique‑se de que o projeto não está aberto em modo somente‑leitura ou de que você chamou `resource.AvailabilityPeriods.Clear()` antes de adicionar novos itens.  
- **Períodos sobrepostos** – Aspose.Tasks não mescla sobreposições automaticamente; pode ser necessário escrever lógica personalizada para detectá‑las e resolvê‑las.  
- **Formato de data incorreto** – Sempre use objetos `DateTime`; a análise de strings pode gerar erros dependentes de localidade.

## Perguntas Frequentes

**P: Posso adicionar campos personalizados aos períodos de disponibilidade?**  
R: Não, períodos de disponibilidade no Aspose.Tasks para .NET não suportam campos personalizados.

**P: Os períodos de disponibilidade estão vinculados a tarefas específicas?**  
R: Não, eles estão associados a recursos e definem quando o recurso está geralmente disponível para tarefas.

**P: Posso importar períodos de disponibilidade de fontes externas?**  
R: Sim, você pode importar períodos de CSV, XML ou de um banco de dados criando objetos `AvailabilityPeriod` e adicionando‑os à coleção.

**P: Como lidar com períodos de disponibilidade sobrepostos?**  
R: Sobreposições não são resolvidas automaticamente; você precisa implementar validação personalizada para mesclar ou rejeitar períodos conflitantes.

**P: Existe um limite para a quantidade de períodos de disponibilidade que um recurso pode ter?**  
R: Não há um limite codificado, mas coleções muito grandes podem afetar o desempenho; considere consolidar períodos quando possível.

## Conclusão

Neste guia abordamos tudo o que você precisa saber para gerenciar **a disponibilidade de recursos do projeto** com Aspose.Tasks para .NET — desde a inicialização de um projeto e limpeza de dados antigos, até a adição, inserção, cópia, atualização e remoção de períodos de disponibilidade. Dominar essas etapas ajuda a manter os calendários de recursos precisos e seus cronogramas de projeto realistas.

---

**Última atualização:** 2026-03-21  
**Testado com:** Aspose.Tasks para .NET (última versão)  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}