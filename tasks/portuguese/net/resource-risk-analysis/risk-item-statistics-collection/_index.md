---
title: Colete estatísticas de itens de risco do MS Project em Aspose.Tasks
linktitle: Coleta de estatísticas de itens de risco em Aspose.Tasks
second_title: API Aspose.Tasks .NET
description: Aprenda como coletar estatísticas de itens de risco de arquivos do MS Project usando Aspose.Tasks for .NET. Aprimore seus recursos de gerenciamento de projetos.
type: docs
weight: 22
url: /pt/net/resource-risk-analysis/risk-item-statistics-collection/
---
## Introdução
Neste tutorial, exploraremos como coletar estatísticas de itens de risco de arquivos do MS Project usando Aspose.Tasks for .NET. Esta biblioteca fornece funcionalidades poderosas para analisar dados do projeto, incluindo avaliação de riscos e análise estatística.
## Pré-requisitos
Antes de começarmos, certifique-se de ter os seguintes pré-requisitos:
1. Aspose.Tasks para .NET: Baixe e instale a biblioteca Aspose.Tasks. Você pode obtê-lo no[página de download](https://releases.aspose.com/tasks/net/).
2. Ambiente de Desenvolvimento: Tenha um ambiente de desenvolvimento configurado para programação .NET.

## Importar namespaces
Antes de começar a codificar, certifique-se de importar os namespaces necessários em seu projeto:
```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.RiskAnalysis;

```
## Etapa 1: carregar o arquivo do projeto
Primeiro, você precisa carregar o arquivo MS Project em seu aplicativo. Veja como você pode conseguir isso:
```csharp
var project = new Project("Your_Project_File_Path.mpp");
```
## Passo 2: Definir configurações de análise de risco
Inicialize as configurações de análise de risco, incluindo o número de iterações, conforme mostrado abaixo:
```csharp
var settings = new RiskAnalysisSettings
{
    IterationsCount = 200
};
```
## Etapa 3: inicializar um padrão de risco
Configure um padrão de risco para a análise, especificando o tipo de distribuição, percentuais otimistas e pessimistas e nível de confiança:
```csharp
var pattern = new RiskPattern(task)
{
    Distribution = ProbabilityDistributionType.Normal,
    Optimistic = 70,
    Pessimistic = 130,
    ConfidenceLevel = ConfidenceLevel.CL75
};
settings.Patterns.Add(pattern);
```
## Etapa 4: realizar análise de risco
 Instancie o`RiskAnalyzer` aula e analise o projeto:
```csharp
var analyzer = new RiskAnalyzer(settings);
var analysisResult = analyzer.Analyze(project);
```
## Etapa 5: recuperar estatísticas
Recupere as estatísticas do item de risco, como o término antecipado, do resultado da análise:
```csharp
var statistics = analysisResult.GetRiskItems(RiskItemType.EarlyFinish);
```
## Etapa 6: Imprimir estatísticas
Itere sobre as estatísticas e imprima os detalhes:
```csharp
foreach (var statistic in statistics)
{
    Console.WriteLine("Short statistic: " + statistic);
    Console.WriteLine();
    Console.WriteLine("Statistic details: ");
    Console.WriteLine("Item Type: {0}", statistic.ItemType);
    Console.WriteLine("Expected value: {0}", statistic.ExpectedValue);
    Console.WriteLine("StandardDeviation: {0}", statistic.StandardDeviation);
    //Imprimir outras estatísticas relevantes...
}
```

## Conclusão
Neste tutorial, aprendemos como utilizar Aspose.Tasks for .NET para coletar estatísticas de itens de risco de arquivos do MS Project. Seguindo essas etapas, você pode analisar com eficácia os dados do projeto e avaliar os riscos potenciais, auxiliando na melhor tomada de decisões e no gerenciamento do projeto.

## Perguntas frequentes
### P: O Aspose.Tasks pode lidar com arquivos grandes do MS Project?
R: Sim, o Aspose.Tasks é capaz de lidar com grandes arquivos do MS Project com eficiência, oferecendo desempenho confiável e escalabilidade.
### P: O Aspose.Tasks oferece suporte a outros formatos de arquivo de projeto além de .mpp?
R: Sim, Aspose.Tasks oferece suporte a vários formatos de arquivo de projeto, incluindo XML e MPT.
### P: O Aspose.Tasks é adequado para aplicativos de gerenciamento de projetos de nível empresarial?
R: Com certeza, o Aspose.Tasks foi projetado para atender às demandas de aplicativos de gerenciamento de projetos de nível empresarial, fornecendo recursos robustos e documentação extensa.
### P: Posso personalizar as configurações de análise de risco no Aspose.Tasks?
R: Sim, Aspose.Tasks oferece flexibilidade na definição de configurações de análise de risco para atender aos requisitos e cenários específicos do seu projeto.
### P: O suporte técnico está disponível para usuários do Aspose.Tasks?
 R: Sim, os usuários do Aspose.Tasks podem acessar o suporte técnico através do Aspose.[fóruns](https://forum.aspose.com/c/tasks/15), onde podem fazer perguntas, relatar problemas e interagir com a comunidade.