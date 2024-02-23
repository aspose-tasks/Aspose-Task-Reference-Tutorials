---
title: Domine o tratamento de dados em fases com Aspose.Tasks para .NET
linktitle: Tratamento de dados em fases no Aspose.Tasks
second_title: API Aspose.Tasks .NET
description: Explore o Aspose.Tasks for .NET para lidar facilmente com dados divididos em fases, aprimorar o planejamento de projetos e otimizar o gerenciamento de recursos. #Aspose #Tarefas #Projeto MS
type: docs
weight: 14
url: /pt/net/text-view-configuration/timephased-data/
---
## Introdução
No mundo do gerenciamento de projetos, o tratamento eficaz de dados faseados no tempo é crucial para a alocação de recursos, estimativa de custos e planejamento geral do projeto. Aspose.Tasks for .NET fornece uma solução poderosa para trabalhar perfeitamente com dados personalizados em fases. Este tutorial irá guiá-lo através do processo de manipulação de dados em fases usando Aspose.Tasks, permitindo otimizar o gerenciamento de recursos em seus projetos.
## Pré-requisitos
Antes de mergulhar no tutorial, certifique-se de ter os seguintes pré-requisitos em vigor:
- Uma compreensão básica dos conceitos de gerenciamento de projetos.
-  Aspose.Tasks instalado para .NET. Você pode baixá-lo[aqui](https://releases.aspose.com/tasks/net/).
- Um editor de código, como o Visual Studio, para implementar os exemplos fornecidos.
## Importar namespaces
Em seu projeto .NET, certifique-se de importar os namespaces necessários para aproveitar as funcionalidades do Aspose.Tasks. Adicione as seguintes linhas no início do seu arquivo de código:
```csharp
    using Aspose.Tasks;
    using System;
    
```
Agora, vamos dividir o exemplo fornecido em várias etapas para guiá-lo no tratamento de dados em fases usando Aspose.Tasks:
## Etapa 1: configurar o projeto
```csharp
// O caminho para o diretório de documentos.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "Project1.mpp") { CalculationMode = CalculationMode.None };
```
Aqui inicializamos um novo projeto e definimos seu modo de cálculo.
## Passo 2: Definir Recursos e Tarefas
```csharp
var workResource = project.Resources.Add("Work Resource");
workResource.Set(Rsc.Type, ResourceType.Work);
var costResource = project.Resources.Add("Cost Resource");
costResource.Set(Rsc.Type, ResourceType.Cost);
var task = project.RootTask.Children.Add("Task");
task.Set(Tsk.Start, new DateTime(2018, 1, 1, 8, 0, 0));
task.Set(Tsk.Duration, project.GetDuration(1, TimeUnitType.Day));
```
Crie recursos de trabalho e custo, bem como uma tarefa, para simular a estrutura de um projeto.
## Etapa 3: atribuir recursos à tarefa
```csharp
var workAssignment = project.ResourceAssignments.Add(task, workResource);
workAssignment.Set(Asn.WorkContour, WorkContourType.Contoured);
var costAssignment = project.ResourceAssignments.Add(task, costResource);
costAssignment.Set(Asn.WorkContour, WorkContourType.Contoured);
```
Atribua recursos de trabalho e custo à tarefa.
## Etapa 4: adicionar dados personalizados em fases
```csharp
workAssignment.TimephasedData.Clear();
var td1 = TimephasedData.CreateWorkTimephased(
    workAssignment.Get(Asn.Uid),
    new DateTime(2018, 1, 2, 8, 0, 0),
    new DateTime(2018, 1, 5, 17, 0, 0),
    TimeSpan.FromHours(40),
    TimeUnitType.Hour,
    TimephasedDataType.AssignmentRemainingWork);
workAssignment.TimephasedData.Add(td1);
// Etapas semelhantes para costAssignment
costAssignment.TimephasedData.Clear();
```
Adicione dados personalizados divididos em fases para atribuições de trabalho e custo.
## Etapa 5: exibir dados em fases
```csharp
Console.WriteLine("Print assignment timephased data:");
foreach (var assignment in project.ResourceAssignments)
{
    Console.WriteLine("Assignment UID: " + assignment.Get(Asn.Uid));
    foreach (var tds in assignment.TimephasedData)
    {
        // Exibir informações relevantes sobre cada entrada de dados faseada no tempo
    }
}
```
Por fim, exiba os dados divididos em fases para cada tarefa.
#
## Conclusão
O tratamento eficaz de dados divididos em fases no Aspose.Tasks abre novas possibilidades para planejamento detalhado de projetos e gerenciamento de recursos. Seguindo este guia passo a passo, você aprendeu como manipular dados divididos em fases para atender às necessidades específicas de seus projetos.
## perguntas frequentes
### Posso usar o Aspose.Tasks for .NET com outras ferramentas de gerenciamento de projetos?
Aspose.Tasks foi projetado principalmente para desenvolvimento .NET. Porém, suas funcionalidades podem complementar diversas ferramentas de gerenciamento de projetos.
### Existe uma avaliação gratuita disponível para Aspose.Tasks for .NET?
 Sim, você pode explorar uma avaliação gratuita[aqui](https://releases.aspose.com/).
### Como posso obter suporte para Aspose.Tasks for .NET?
 visite a[Fórum Aspose.Tasks](https://forum.aspose.com/c/tasks/15)para apoio comunitário.
### O que é uma licença temporária e como posso obtê-la?
 Saiba mais sobre licenças temporárias[aqui](https://purchase.aspose.com/temporary-license/).
### Onde posso encontrar a documentação do Aspose.Tasks for .NET?
 Consulte o abrangente[documentação](https://reference.aspose.com/tasks/net/) para obter informações detalhadas.