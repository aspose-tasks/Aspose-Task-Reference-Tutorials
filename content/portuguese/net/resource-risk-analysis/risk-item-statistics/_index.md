---
title: Estatísticas para itens de risco em Aspose.Tasks
linktitle: Estatísticas para itens de risco em Aspose.Tasks
second_title: API Aspose.Tasks .NET
description: Desbloqueie o poder da análise de risco em arquivos do MS Project usando Aspose.Tasks for .NET. Obtenha insights, reduza incertezas e impulsione o sucesso do projeto sem esforço.
type: docs
weight: 21
url: /pt/net/resource-risk-analysis/risk-item-statistics/
---
## Introdução
Você está procurando aprimorar suas habilidades de gerenciamento de projetos usando Aspose.Tasks for .NET? Mergulhe no domínio da análise de risco com nosso tutorial passo a passo sobre como obter estatísticas para itens de risco em arquivos do MS Project. Ao aproveitar os poderosos recursos do Aspose.Tasks, você pode obter insights valiosos sobre as incertezas do projeto e tomar decisões informadas para mitigar os riscos de forma eficaz.
## Pré-requisitos
Antes de embarcarmos nesta jornada, certifique-se de ter os seguintes pré-requisitos em vigor:
1.  Biblioteca Aspose.Tasks for .NET: Baixe e instale a biblioteca do[Documentação Aspose.Tasks para .NET](https://reference.aspose.com/tasks/net/). Esta biblioteca fornece ferramentas robustas para manipular arquivos do MS Project programaticamente.
2. Ambiente de desenvolvimento .NET: Configure seu ambiente de desenvolvimento .NET, incluindo Visual Studio ou qualquer outro IDE de sua escolha, para facilitar a integração perfeita do Aspose.Tasks em seus projetos.

## Importar namespaces
Incorpore os namespaces necessários em seu projeto para aproveitar as funcionalidades do Aspose.Tasks:
```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.RiskAnalysis;
```

## Etapa 1: definir o diretório de dados
```csharp
String DataDir = "Your Document Directory";
```
 Certifique-se de substituir`"Your Document Directory"` com o caminho para o diretório do documento onde os arquivos do MS Project estão localizados.
## Etapa 2: definir as configurações de análise de risco
```csharp
var settings = new RiskAnalysisSettings
{
    IterationsCount = 200
};
```
 Ajusta a`IterationsCount`parâmetro com base nos requisitos do seu projeto para controlar a precisão da análise de risco.
## Etapa 3: carregar o arquivo do MS Project
```csharp
var project = new Project(DataDir + "Software Development Plan-1.mpp");
```
 Carregue o arquivo MS Project desejado no`project` objeto para análise posterior.
## Passo 4: Definir Tarefa e Inicializar Padrão de Risco
```csharp
var task = project.RootTask.Children.GetById(17);
var pattern = new RiskPattern(task)
{
    Distribution = ProbabilityDistributionType.Normal,
    Optimistic = 70,
    Pessimistic = 130,
    ConfidenceLevel = ConfidenceLevel.CL75
};
settings.Patterns.Add(pattern);
```
Especifique a tarefa para análise de risco e configure o padrão de risco com parâmetros apropriados, como tipo de distribuição, durações otimistas e pessimistas e nível de confiança.
## Passo 5: Analise os Riscos do Projeto
```csharp
var analyzer = new RiskAnalyzer(settings);
var analysisResult = analyzer.Analyze(project);
```
Inicie o processo de análise de risco usando as configurações definidas e os dados do projeto.
## Etapa 6: recuperar e exibir estatísticas
```csharp
var statistics = analysisResult.GetRiskItems(RiskItemType.EarlyFinish).Get(project.RootTask);
Console.WriteLine("Short statistic: " + statistics);
Console.WriteLine();
Console.WriteLine("Statistic details: ");
Console.WriteLine("Item Type: {0}", statistics.ItemType);
Console.WriteLine("Expected value: {0}", statistics.ExpectedValue);
Console.WriteLine("StandardDeviation: {0}", statistics.StandardDeviation);
Console.WriteLine("10% Percentile: {0}", statistics.GetPercentile(10));
Console.WriteLine("50% Percentile: {0}", statistics.GetPercentile(50));
Console.WriteLine("90% Percentile: {0}", statistics.GetPercentile(90));
Console.WriteLine("Minimum: {0}", statistics.Minimum);
Console.WriteLine("Maximum: {0}", statistics.Maximum);
```
Recupere e exiba diversas métricas estatísticas relacionadas a itens de risco no arquivo do MS Project, incluindo valor esperado, desvio padrão, percentis, valores mínimos e máximos.

## Conclusão
Concluindo, dominar a análise de risco em arquivos do MS Project usando Aspose.Tasks for .NET abre um mundo de possibilidades para gerentes de projeto e partes interessadas. Seguindo nosso tutorial abrangente, você pode navegar pelas incertezas com confiança, garantindo resultados de projeto bem-sucedidos.
## Perguntas frequentes
### Posso integrar Aspose.Tasks com outras bibliotecas .NET para funcionalidade estendida?
Absolutamente! Aspose.Tasks integra-se perfeitamente com várias bibliotecas .NET, permitindo ampliar seus recursos de acordo com os requisitos do seu projeto.
### Existe uma versão de teste disponível para Aspose.Tasks for .NET?
 Sim, você pode explorar os recursos do Aspose.Tasks acessando o[teste grátis](https://releases.aspose.com/) disponível em nosso site.
### Com que frequência são lançadas atualizações e melhorias para Aspose.Tasks?
Nós nos esforçamos para melhorar continuamente o Aspose.Tasks, lançando atualizações e melhorias periodicamente, garantindo que você sempre tenha acesso aos recursos e otimizações mais recentes.
### Posso obter suporte técnico para Aspose.Tasks?
Certamente! Nossa equipe de suporte dedicada está prontamente disponível no[Fórum Aspose.Tasks](https://forum.aspose.com/c/tasks/15) para ajudá-lo com quaisquer dúvidas ou desafios que você possa encontrar durante sua jornada de implementação.
### Vocês oferecem licenças temporárias para projetos de curto prazo?
 Sim, se você precisar do Aspose.Tasks para um projeto de curto prazo, você pode aproveitar nosso conveniente[licença temporária](https://purchase.aspose.com/temporary-license/) opção para atender às suas necessidades de licenciamento sem quaisquer compromissos de longo prazo.