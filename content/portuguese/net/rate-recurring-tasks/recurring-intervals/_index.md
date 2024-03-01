---
title: Intervalos recorrentes do MS Project sem esforço em Aspose.Tasks
linktitle: Gerenciando intervalos recorrentes em Aspose.Tasks
second_title: API Aspose.Tasks .NET
description: Descubra como gerenciar intervalos recorrentes sem esforço no MS Project usando Aspose.Tasks for .NET.
type: docs
weight: 12
url: /pt/net/rate-recurring-tasks/recurring-intervals/
---
## Introdução
Você deseja gerenciar intervalos recorrentes com eficiência em arquivos do Microsoft Project usando Aspose.Tasks for .NET? Este tutorial abrangente irá guiá-lo passo a passo pelo processo, garantindo que você possa lidar facilmente com intervalos recorrentes em seus projetos. Antes de mergulhar no tutorial, vamos examinar alguns pré-requisitos para garantir que você esteja pronto para começar.
## Pré-requisitos
Antes de prosseguir com este tutorial, certifique-se de ter o seguinte:
1. Conhecimento de programação C#: É necessário conhecimento básico da linguagem de programação C# e sua sintaxe.
2. Visual Studio instalado: certifique-se de ter o Visual Studio instalado em seu sistema para codificar e compilar os aplicativos .NET.
3. Biblioteca Aspose.Tasks for .NET: Baixe e instale a biblioteca Aspose.Tasks for .NET. Você pode obtê-lo de[aqui](https://releases.aspose.com/tasks/net/).

## Importar namespaces
Comece importando os namespaces necessários para acessar as funcionalidades fornecidas pela biblioteca Aspose.Tasks for .NET.
   
```csharp
    using Aspose.Tasks;
    using System;
    
    using Aspose.Tasks.Saving;
    using Aspose.Tasks.Visualization;
```
Agora, vamos dividir cada exemplo em várias etapas e explicá-las em detalhes.
## Etapa 1: inicializar o objeto do projeto:
```csharp
// O caminho para o diretório de documentos.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "Project2007.mpp");
```
 Aqui, inicializamos uma nova instância do`Project` class fornecendo o caminho para o arquivo do Microsoft Project.
## Etapa 2: Definir data de status:
```csharp
project.Set(Prj.StatusDate, project.Get(Prj.StartDate));
```
Esta etapa define a data de status do projeto como sua data de início.
## Etapa 3: Acesse a visualização do gráfico de Gantt:
```csharp
var view = (GanttChartView)project.Views.ToList()[1];
```
Acessamos a visualização do Gráfico de Gantt do projeto.
## Etapa 4: Leia a linha de progresso:
```csharp
var interval = view.ProgressLines.RecurringInterval;
```
Esta etapa recupera o intervalo recorrente para linhas de progresso na visualização Gráfico de Gantt.
## Etapa 5: Exibir informações de intervalo:
```csharp
Console.WriteLine("Interval: " + interval.Interval);
Console.WriteLine("Weekly Week Number: " + interval.WeeklyWeekNumber);
foreach (var day in interval.WeeklyDays)
{
    Console.WriteLine("Week day: " + day);
}
```
Aqui, exibimos informações sobre o intervalo, número da semana semanal e dias semanais.
## Etapa 6: Redefinir o intervalo recorrente:
```csharp
var newInterval = new RecurringInterval();
```
 Criamos uma nova instância de`RecurringInterval` para redefinir o intervalo recorrente.
## Etapa 7: Definir linhas de progresso mensais:
```csharp
// Defina linhas de progresso mensais por dia.
interval.MonthlyDay = true;
// Defina o número do dia das linhas de progresso mensais.
interval.MonthlyDayDayNumber = 1;
// Defina o número do mês das linhas de progresso mensais.
interval.MonthlyDayMonthNumber = 1;
// Defina linhas de progresso pelo primeiro ou último dia predefinido.
interval.MonthlyFirstLast = true;
// Defina o tipo de primeiro ou último dia das linhas de progresso mensais.
interval.MonthlyFirstLastDay = RecurringInterval.DayType.Day;
// Defina o número do mês das linhas de progresso.
interval.MonthlyFirstLastMonthNumber = 1;
```
Estas etapas configuram as linhas de progresso mensais de acordo com parâmetros especificados.
## Etapa 8: Atualizar Linhas de Progresso:
```csharp
view.ProgressLines.RecurringInterval = newInterval;
```
Atualizamos as linhas de progresso na visualização Gráfico de Gantt com o intervalo recorrente recém-definido.
## Etapa 9: Salvar projeto como PDF:
```csharp
project.Save(DataDir + "WorkWithRecurringInterval_out.pdf", SaveFileFormat.Pdf);
```
Por fim, salvamos o projeto com o intervalo recorrente atualizado como um arquivo PDF.

## Conclusão
Concluindo, o gerenciamento de intervalos recorrentes em arquivos do Microsoft Project usando Aspose.Tasks for .NET é simplificado com as funcionalidades abrangentes fornecidas pela biblioteca. Seguindo o guia passo a passo descrito neste tutorial, você pode lidar com intervalos recorrentes em seus projetos com eficiência, aumentando a produtividade e a organização.
### Perguntas frequentes
### Posso usar Aspose.Tasks for .NET com outras linguagens de programação?
Sim, Aspose.Tasks for .NET pode ser usado com qualquer linguagem compatível com .NET, como C# e VB.NET.
### Existe uma versão de teste disponível para Aspose.Tasks for .NET?
 Sim, você pode baixar uma versão de avaliação gratuita em[aqui](https://releases.aspose.com/).
### Como posso obter suporte para Aspose.Tasks for .NET?
 Você pode obter suporte no fórum Aspose.Tasks[aqui](https://forum.aspose.com/c/tasks/15).
### Posso adquirir uma licença temporária do Aspose.Tasks for .NET?
 Sim, você pode comprar uma licença temporária de[aqui](https://purchase.aspose.com/temporary-license/).
### Onde posso encontrar a documentação completa do Aspose.Tasks for .NET?
 A documentação completa pode ser encontrada[aqui](https://reference.aspose.com/tasks/net/).