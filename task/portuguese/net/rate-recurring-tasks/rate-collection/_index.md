---
title: Domine as taxas do MS Project com Aspose.Tasks
linktitle: Coleta de taxas em Aspose.Tasks
second_title: API Aspose.Tasks .NET
description: Aprenda como gerenciar taxas em arquivos do MS Project usando Aspose.Tasks for .NET. Tutorial passo a passo para gerenciamento eficaz de recursos.
type: docs
weight: 11
url: /pt/net/rate-recurring-tasks/rate-collection/
---
## Introdução
Bem-vindo ao nosso tutorial sobre gerenciamento de taxas no MS Project usando Aspose.Tasks for .NET! Neste guia, orientaremos você no processo de trabalho com taxas em seus arquivos do MS Project usando Aspose.Tasks. Quer você seja um desenvolvedor experiente ou esteja apenas começando com o desenvolvimento .NET, este tutorial fornecerá instruções passo a passo para lidar com taxas de maneira eficaz em seus projetos.
## Pré-requisitos
Antes de mergulharmos no tutorial, certifique-se de ter os seguintes pré-requisitos:
### 1. Visual Studio instalado
Certifique-se de ter o Visual Studio instalado em seu sistema. Você pode baixá-lo do site, caso ainda não o tenha feito.
### 2. Aspose.Tasks para .NET
 Baixe e instale a biblioteca Aspose.Tasks for .NET do[local na rede Internet](https://releases.aspose.com/tasks/net/).
### 3. Conhecimento básico de C# e .NET
Familiarize-se com a linguagem de programação C# e os conceitos básicos do .NET Framework para entender melhor os exemplos de código fornecidos neste tutorial.
## Importar namespaces
Em seu projeto C#, importe os namespaces necessários para usar as funcionalidades do Aspose.Tasks:
```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;

```
Agora, vamos dividir cada exemplo em várias etapas:
## Etapa 1: carregar um arquivo MS Project
```csharp
// O caminho para o diretório de documentos.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "Project1.mpp");
```
 Aqui, criamos um novo`Project` objeto carregando um arquivo MS Project existente.
## Etapa 2: adicionar um recurso e definir trabalho e taxas
```csharp
var resource = project.Resources.Add("Test Resource 1");
resource.Set(Rsc.Type, ResourceType.Work);
resource.Set(Rsc.Work, project.GetDuration(2d, TimeUnitType.Hour));
resource.Set(Rsc.StandardRate, 20m);
```
Adicionamos um novo recurso ao projeto, definimos seu tipo como trabalho, quantidade de trabalho e taxa padrão.
## Etapa 3: adicionar taxas ao recurso
```csharp
var rate1 = resource.Rates.Add(new DateTime(2019, 1, 1, 8, 0, 0));
rate1.RatesTo = new DateTime(2019, 11, 11, 17, 0, 0);
rate1.StandardRate = 5m;
rate1.StandardRateFormat = RateFormatType.Hour;
```
Adicionamos taxas ao recurso especificando as datas de início e término, a taxa padrão e o formato da taxa.
## Etapa 4: Imprimir informações sobre taxas
```csharp
Console.WriteLine("Print rates of '{0}' resource: ", resource.Rates.ParentResource.Get(Rsc.Name));
Console.WriteLine("Count of rates: {0}", resource.Rates.Count);
Console.WriteLine("Is rate collection read-only: {0}", resource.Rates.IsReadOnly);
foreach (KeyValuePair<RateType, RateByDateCollection> sortedRates in resource.Rates)
{
    foreach (KeyValuePair<DateTime, Rate> pair in sortedRates.Value)
    {
        var rate = pair.Value;
        Console.WriteLine("Rates From: " + rate.RatesFrom);
        Console.WriteLine("Rates To: " + rate.RatesTo);
        Console.WriteLine("Rate Table: " + rate.RateTable);
        Console.WriteLine();
    }
}
```
Esta etapa imprime informações sobre as taxas associadas ao recurso.
## Etapa 5: atualizar uma taxa
```csharp
var rateToUpdate = resource.Rates[RateType.B][new DateTime(2019, 11, 12, 8, 0, 0)];
rateToUpdate.RatesTo = new DateTime(2020, 12, 31, 17, 0, 0);
Console.WriteLine("Rates From: " + rateToUpdate.RatesFrom);
Console.WriteLine("Rates To: " + rateToUpdate.RatesTo);
```
Atualizamos a data de término de uma taxa específica.
## Etapa 6: remover taxas
```csharp
List<Rate> rates = resource.Rates.ToList(RateType.A);
for (var i = 0; i < rates.Count; i++)
{
    var rateToRemove = rates[i];
    resource.Rates.Remove(rateToRemove);
}
```
Esta etapa remove todas as taxas de um tipo específico.
## Etapa 7: iterar sobre as taxas restantes
```csharp
Console.WriteLine("Iterate over the rates after removing the A-typed values: ");
List<Rate> list = resource.Rates.ToList();
foreach (var rt in list)
{
    Console.WriteLine("Rates From: " + rt.RatesFrom);
    Console.WriteLine("Rates To: " + rt.RatesTo);
    Console.WriteLine("Rate Table: " + rt.RateTable);
}
```
Finalmente, iteramos sobre as taxas restantes após a remoção.
## Conclusão
Concluindo, este tutorial forneceu um guia completo sobre como gerenciar taxas em arquivos do MS Project usando Aspose.Tasks for .NET. Seguindo as instruções passo a passo descritas neste tutorial, você pode lidar com taxas de maneira eficiente em seus projetos, garantindo um gerenciamento preciso de recursos.
## Perguntas frequentes
### P: Posso usar o Aspose.Tasks for .NET com outro software de gerenciamento de projetos?
R: Sim, Aspose.Tasks for .NET oferece suporte à integração com vários softwares de gerenciamento de projetos, incluindo MS Project, Primavera e muito mais.
### P: O Aspose.Tasks for .NET é compatível com diferentes versões de arquivos do MS Project?
R: Com certeza, Aspose.Tasks for .NET suporta trabalhar com arquivos MS Project de diferentes versões, garantindo flexibilidade e compatibilidade.
### P: O Aspose.Tasks for .NET oferece documentação e suporte?
 R: Sim, você pode encontrar documentação abrangente e acesso a fóruns de suporte no Aspose.Tasks[local na rede Internet](https://reference.aspose.com/tasks/net/).
### P: Posso experimentar o Aspose.Tasks for .NET antes de comprar?
R: Sim, você pode aproveitar uma avaliação gratuita do Aspose.Tasks for .NET para avaliar seus recursos e compatibilidade com seus requisitos.
### P: Como posso adquirir uma licença do Aspose.Tasks for .NET?
 R: Você pode adquirir uma licença para Aspose.Tasks for .NET no site[local na rede Internet](https://purchase.aspose.com/temporary-license/)que oferece opções de licenciamento flexíveis para atender às suas necessidades.