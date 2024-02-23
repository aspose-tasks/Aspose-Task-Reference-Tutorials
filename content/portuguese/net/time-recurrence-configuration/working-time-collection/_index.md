---
title: Dominando os tempos de trabalho em Aspose.Tasks
linktitle: Coleção de tempos de trabalho em Aspose.Tasks
second_title: API Aspose.Tasks .NET
description: Explore o poder do Aspose.Tasks for .NET no gerenciamento eficiente de cronogramas de projetos. Personalize calendários, defina horários de trabalho e simplifique seus projetos com facilidade.
type: docs
weight: 14
url: /pt/net/time-recurrence-configuration/working-time-collection/
---
## Introdução
Você deseja dominar a arte de gerenciar horários de trabalho no Aspose.Tasks for .NET? Não procure mais! Neste guia passo a passo, nos aprofundaremos nos meandros da coleta de tempo de trabalho usando Aspose.Tasks, capacitando você a lidar com calendários personalizados com eficiência e agilizar os cronogramas de seu projeto.
## Pré-requisitos
Antes de embarcarmos nesta jornada, certifique-se de ter os seguintes pré-requisitos em vigor:
-  Biblioteca Aspose.Tasks for .NET: Baixe e instale a biblioteca Aspose.Tasks for .NET do[Página de lançamento do Aspose.Tasks](https://releases.aspose.com/tasks/net/).
- Ambiente de Trabalho: Configure um ambiente de desenvolvimento adequado, de preferência usando um IDE compatível com .NET.
## Importar namespaces
Em seu projeto, importe os namespaces necessários para acessar as funcionalidades do Aspose.Tasks:
```csharp
    using Aspose.Tasks;
    using System;
    using System.Collections.Generic;
    
```
Agora, vamos dividir o tutorial em várias etapas, garantindo uma experiência de aprendizado tranquila.
## Etapa 1: crie um calendário personalizado
Comece criando um novo projeto e adicionando um calendário personalizado a ele:
```csharp
var project = new Project();
var calendar = project.Calendars.Add("Custom Calendar");
```
## Passo 2: Definir Dias Úteis
Configure dias úteis padrão de segunda a sexta:
```csharp
foreach (var dayType in Enum.GetValues(typeof(DayType)).Cast<DayType>())
{
    if (dayType != DayType.Saturday && dayType != DayType.Sunday)
    {
        calendar.WeekDays.Add(WeekDay.CreateDefaultWorkingDay(dayType));
    }
}
```
## Etapa 3: configurar horários de trabalho aos sábados
Especifique o horário de trabalho aos sábados:
```csharp
var saturdayWorkingTimes = new List<WorkingTime>
{
    new WorkingTime(8, 12),
    new WorkingTime(13, 15)
};
var saturday = new WeekDay(DayType.Saturday, saturdayWorkingTimes);
```
## Etapa 4: imprimir os períodos de trabalho aos sábados
Imprima os horários de trabalho configurados para sábado:
```csharp
Console.WriteLine("Saturday working period number: " + saturday.WorkingTimes.Count);
foreach (var time in saturday.WorkingTimes)
{
    Console.WriteLine("From Time: " + time.From);
    Console.WriteLine("To Time: " + time.To);
}
```
## Etapa 5: configurar horários de trabalho aos domingos
Defina horários de trabalho para domingos:
```csharp
var sundayWorkingTimes = new List<WorkingTime>
{
    new WorkingTime(10, 15)
};
var sunday = new WeekDay(DayType.Sunday, sundayWorkingTimes);
```
## Etapa 6: imprimir os períodos de trabalho de domingo
Imprima os horários de trabalho configurados para domingo:
```csharp
List<WorkingTime> workingTimes = sunday.WorkingTimes.ToList();
Console.WriteLine("Sunday working period number: " + workingTimes.Count);
for (var index = 0; index < workingTimes.Count; index++)
{
    var time = workingTimes[index];
    Console.WriteLine("From Time: " + time.From);
    Console.WriteLine("To Time: " + time.To);
}
```
## Etapa 7: adicionar dias personalizados ao calendário
Incluir o sábado e domingo configurados no calendário:
```csharp
calendar.WeekDays.Add(saturday);
calendar.WeekDays.Add(sunday);
```
## Etapa 8: percorrer os horários de trabalho
Percorra os horários de trabalho e exiba-os para cada dia no calendário:
```csharp
foreach (var day in calendar.WeekDays)
{
    Console.WriteLine(day.DayType + ": ");
    foreach (var workingTime in day.WorkingTimes)
    {
        Console.WriteLine("From: " + workingTime.From);
        Console.WriteLine("To: " + workingTime.To);
    }
    Console.WriteLine();
}
```
Agora que navegou com sucesso pelas etapas, você está equipado para aproveitar o poder do Aspose.Tasks for .NET no gerenciamento eficaz dos horários de trabalho.
## Conclusão
Dominar a coleta de horários de trabalho no Aspose.Tasks permite que você personalize calendários de projetos, garantindo agendamento preciso e utilização eficiente de recursos. Mergulhe em seus projetos com confiança, munido do conhecimento adquirido neste guia completo.
## perguntas frequentes
### O Aspose.Tasks é adequado para gerenciamento de projetos em grande escala?
Sim, o Aspose.Tasks foi projetado para lidar com projetos de diversos tamanhos, fornecendo recursos robustos para um gerenciamento eficiente de projetos.
### Posso integrar Aspose.Tasks com outras bibliotecas .NET?
Certamente! Aspose.Tasks integra-se perfeitamente com outras bibliotecas .NET, aumentando sua versatilidade e compatibilidade.
### Com que frequência o Aspose.Tasks é atualizado?
 Aspose.Tasks é atualizado regularmente para incorporar novos recursos, aprimoramentos e melhorias de compatibilidade. Verifica a[página de lançamento](https://releases.aspose.com/tasks/net/) para obter as atualizações mais recentes.
### Existe um teste gratuito disponível para Aspose.Tasks?
 Sim, você pode explorar o Aspose.Tasks com uma avaliação gratuita visitando[esse link](https://releases.aspose.com/).
### Onde posso procurar suporte para Aspose.Tasks?
 Para qualquer dúvida ou assistência, visite o[Fórum de suporte Aspose.Tasks](https://forum.aspose.com/c/tasks/15).