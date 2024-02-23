---
title: Dominando a coleta de dados em fases no Aspose.Tasks
linktitle: Coleta de dados em fases em Aspose.Tasks
second_title: API Aspose.Tasks .NET
description: Explore a coleta de dados em fases no Aspose.Tasks for .NET. Guia passo a passo, perguntas frequentes e muito mais. Aprimore seus recursos de gerenciamento de projetos hoje mesmo!
type: docs
weight: 15
url: /pt/net/text-view-configuration/timephased-data-collection/
---
## Introdução
Você está procurando aproveitar o poder dos dados em fases em seus aplicativos .NET usando Aspose.Tasks? Não procure mais! Este guia abrangente irá orientá-lo no processo de coleta de dados em fases com Aspose.Tasks for .NET, garantindo que você aproveite ao máximo esta poderosa biblioteca.
## Pré-requisitos
Antes de mergulhar no tutorial, certifique-se de ter os seguintes pré-requisitos em vigor:
1.  Aspose.Tasks for .NET Library: Baixe e instale a biblioteca de[Documentação Aspose.Tasks .NET](https://reference.aspose.com/tasks/net/).
2. Ambiente de desenvolvimento .NET: certifique-se de ter um ambiente de desenvolvimento .NET funcional configurado.
3. Seu diretório de documentos: substitua o espaço reservado "Seu diretório de documentos" nos trechos de código pelo caminho para o diretório de documentos.
## Importar namespaces
Em seu projeto .NET, comece importando os namespaces necessários para aproveitar as funcionalidades do Aspose.Tasks:
```csharp
    using Aspose.Tasks;
    using System;
    using System.Collections.Generic;
    
```
## 1. Crie um projeto e recursos
```csharp
var project = new Project(DataDir + "Project1.mpp");
var resource = project.Resources.Add("Resource 1");
resource.Set(Rsc.Type, ResourceType.Work);
var resource2 = project.Resources.Add("Resource 2");
resource2.Set(Rsc.Type, ResourceType.Work);
```
## 2. Adicione tarefas ao projeto
```csharp
var task = project.RootTask.Children.Add("Task 1");
// Definir propriedades da tarefa...
var task2 = project.RootTask.Children.Add("Task 2");
// Definir propriedades da tarefa2...
```
## 3. Atribuir recursos às tarefas
```csharp
var assignment = project.ResourceAssignments.Add(task, resource);
// Definir propriedades de atribuição...
var assignment2 = project.ResourceAssignments.Add(task2, resource2);
// Definir propriedades de atribuição2...
```
## 4. Trabalhe com dados faseados no tempo
```csharp
// Definir contorno de trabalho contornado
assignment.Set(Asn.WorkContour, WorkContourType.Contoured);
// Verifique se a coleta de dados em fases é somente leitura
Console.WriteLine("Is timephased data collection read-only?: " + assignment.TimephasedData.IsReadOnly);
// Limpar dados gerados em fases
assignment.TimephasedData.Clear();
// Criar e adicionar dados divididos em fases
var td = new TimephasedData
{
    // Definir propriedades de dados em fases...
};
assignment.TimephasedData.Add(td);
// Adicione uma lista de dados divididos em fases
var list = new List<TimephasedData>();
// Adicione mais itens de dados em fases à lista...
assignment.TimephasedData.AddRange(list);
// Filtrar dados faseados no tempo por tipo e intervalo de datas
Console.WriteLine("Print filtered timephased data:");
IList<TimephasedData> filteredTds = assignment.TimephasedData.SelectBetweenStartAndFinish(
    TimephasedDataType.AssignmentRemainingWork,
    new DateTime(2019, 11, 11, 0, 0, 0),
    new DateTime(2019, 11, 13));
// Imprimir dados filtrados em fases...
```
## 5. Manipule dados em fases
```csharp
//Adicione um item de dados com faseamento temporal incorreto e exclua-o
var td4 = new TimephasedData
{
    // Definir propriedades de dados em fases incorretas...
};
assignment.TimephasedData.Add(td4);
// Exclua o item de dados em fases incorreto
if (assignment.TimephasedData.Contains(td4))
{
    assignment.TimephasedData.Remove(td4);
}
// Iterar sobre todos os itens divididos em fases
Console.WriteLine("Print all timephased items:");
foreach (var item in assignment.TimephasedData)
{
    // Imprimir detalhes do item em fases...
}
```
## 6. Copie dados em fases para outra tarefa
```csharp
// Copiar dados divididos em fases para outra tarefa
var timephasedDatas = new TimephasedData[assignment.TimephasedData.Count];
assignment.TimephasedData.CopyTo(timephasedDatas, 0);
assignment2.TimephasedData.Clear();
foreach (var data in timephasedDatas)
{
    assignment2.TimephasedData.Add(data);
}
// Converta a coleção em uma lista simples
List<TimephasedData> tds = assignment.TimephasedData.ToList();
// Remova itens de dados divididos em fases, um por um
foreach (var timephasedData in tds)
{
    assignment.TimephasedData.Remove(timephasedData);
}
```
## Conclusão
Concluindo, este tutorial forneceu um passo a passo detalhado da coleta de dados em fases usando Aspose.Tasks for .NET. Seguindo essas etapas, você pode integrar perfeitamente essa funcionalidade em seus projetos, permitindo controle de tempo e gerenciamento de recursos eficazes.
## perguntas frequentes
### Posso usar o Aspose.Tasks for .NET com outras ferramentas de gerenciamento de projetos?
Sim, o Aspose.Tasks for .NET foi projetado para funcionar com ferramentas populares de gerenciamento de projetos e oferece suporte a vários formatos de arquivo.
### Existe um limite para o número de recursos e tarefas que posso gerenciar com Aspose.Tasks?
Aspose.Tasks lida com projetos de tamanhos variados e não há limite estrito no número de recursos e tarefas.
### Como posso obter suporte para quaisquer problemas ou dúvidas relacionadas ao Aspose.Tasks for .NET?
 Para suporte, visite o[Fórum Aspose.Tasks](https://forum.aspose.com/c/tasks/15) para se conectar com a comunidade e obter assistência.
### Posso experimentar o Aspose.Tasks for .NET antes de comprá-lo?
 Sim, você pode explorar os recursos do Aspose.Tasks for .NET acessando o[teste grátis](https://releases.aspose.com/).
### Onde posso comprar uma licença para Aspose.Tasks for .NET?
 Você pode comprar uma licença para Aspose.Tasks for .NET[aqui](https://purchase.aspose.com/buy).