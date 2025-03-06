---
title: Lidando com taxas do MS Project com Aspose.Tasks para .NET
linktitle: Tratamento de taxas em Aspose.Tasks
second_title: API Aspose.Tasks .NET
description: Domine o gerenciamento de taxas do MS Project com facilidade usando Aspose.Tasks for .NET. Automatize tarefas com eficiência para fluxos de trabalho de projeto mais tranquilos.
weight: 10
url: /pt/net/rate-recurring-tasks/handling-rates/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Lidando com taxas do MS Project com Aspose.Tasks para .NET

## Introdução
Bem-vindo ao nosso tutorial sobre como lidar com taxas do MS Project usando Aspose.Tasks for .NET! Neste guia, orientaremos você passo a passo no processo, garantindo que você possa gerenciar taxas com eficiência em seus documentos do MS Project. Aspose.Tasks for .NET fornece recursos poderosos para manipular arquivos do MS Project programaticamente, permitindo agilizar suas tarefas de gerenciamento de projetos sem esforço.
## Pré-requisitos
Antes de mergulharmos no tutorial, certifique-se de ter os seguintes pré-requisitos em vigor:
1. Visual Studio instalado: certifique-se de ter o Visual Studio instalado em seu sistema.
2.  Biblioteca Aspose.Tasks for .NET: Baixe e instale a biblioteca Aspose.Tasks for .NET. Você pode encontrar o link para download[aqui](https://releases.aspose.com/tasks/net/).
3. Compreensão básica de C#: Familiarize-se com os fundamentos da linguagem de programação C#.
## Importar namespaces
Primeiramente, você precisa importar os namespaces necessários para o seu projeto C#. Esses namespaces fornecerão acesso às classes e métodos necessários para lidar com taxas do MS Project.
## Etapa 1: importar namespace Aspose.Tasks
```csharp
using Aspose.Tasks;
using System;

```
Agora, vamos dividir o exemplo fornecido em várias etapas e entender cada etapa completamente.
## Etapa 1: carregar o arquivo do projeto
```csharp
// O caminho para o diretório de documentos.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "Project1.mpp");
```
 Nesta etapa, estamos carregando um arquivo MS Project existente chamado "Project1.mpp" usando o`Project` classe fornecida por Aspose.Tasks.
## Etapa 2: adicionar recurso e definir trabalho
```csharp
var resource = project.Resources.Add("Resource 1");
resource.Set(Rsc.Type, ResourceType.Work);
resource.Set(Rsc.Work, project.GetDuration(2d, TimeUnitType.Hour));
```
Aqui, adicionamos um novo recurso chamado “Recurso 1” ao projeto e definimos seu tipo como “Trabalho”. Também definimos a duração do trabalho para este recurso.
## Etapa 3: definir taxa padrão
```csharp
resource.Set(Rsc.StandardRate, 20m);
```
Nesta etapa, definimos a taxa padrão do recurso como US$ 20 por hora.
## Etapa 4: definir períodos de taxas
```csharp
var rate1 = resource.Rates.Add(new DateTime(2019, 1, 1, 8, 0, 0));
rate1.RateTable = RateType.A;
rate1.RatesFrom = new DateTime(2019, 1, 1, 8, 0, 0);
rate1.RatesTo = new DateTime(2019, 11, 11, 17, 0, 0);
rate1.StandardRate = 5m;
rate1.StandardRateFormat = RateFormatType.Hour;
rate1.OvertimeRate = 10m;
rate1.OvertimeRateFormat = RateFormatType.Hour;
```
Aqui definimos os períodos de taxa do recurso. A Taxa1 é definida de 1º de janeiro de 2019 a 11 de novembro de 2019, com taxas padrão e de horas extras especificadas.
## Etapa 5: adicionar outro período de taxa
```csharp
var rate2 = resource.Rates.Add(new DateTime(2019, 11, 12, 8, 0, 0));
rate2.RatesTo = new DateTime(2019, 12, 31, 17, 0, 0);
rate2.StandardRate = 10m;
rate2.StandardRateFormat = RateFormatType.Hour;
rate2.CostPerUse = 2m;
```
Nesta etapa final, adicionamos outro período tarifário a partir de 12 de novembro de 2019 a 31 de dezembro de 2019, com tarifa padrão e custo por uso diferentes definidos.
Parabéns! Você administrou com êxito as taxas do MS Project usando Aspose.Tasks for .NET.
## Conclusão
gerenciamento programático das taxas do MS Project pode melhorar significativamente o fluxo de trabalho de gerenciamento de projetos. Com Aspose.Tasks for .NET, você tem o poder de automatizar tarefas de gerenciamento de taxas com eficiência, economizando tempo e recursos.
## Perguntas frequentes
### P: O Aspose.Tasks pode lidar com estruturas de projetos complexas?
R: Sim, Aspose.Tasks fornece recursos robustos para lidar com estruturas de projetos complexos com facilidade.
### P: O Aspose.Tasks é compatível com todas as versões de arquivos do MS Project?
R: Aspose.Tasks oferece suporte a várias versões de arquivos do MS Project, garantindo compatibilidade entre diferentes plataformas.
### P: Posso modificar taxas existentes em um arquivo do MS Project usando Aspose.Tasks?
R: Absolutamente! Aspose.Tasks permite modificar taxas existentes, adicionar novas taxas e gerenciá-las dinamicamente.
### P: O Aspose.Tasks oferece suporte para cálculos de taxas personalizadas?
R: Sim, você pode implementar cálculos de taxas personalizados usando Aspose.Tasks para atender aos requisitos específicos do projeto.
### P: Existe um fórum da comunidade ou suporte disponível para usuários do Aspose.Tasks?
 R: Sim, você pode visitar o[Fórum Aspose.Tasks](https://forum.aspose.com/c/tasks/15)para buscar assistência e interagir com outros usuários.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
