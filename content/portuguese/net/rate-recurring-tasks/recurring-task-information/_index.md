---
title: Extraindo informações de tarefas recorrentes em Aspose.Tasks
linktitle: Extraindo informações de tarefas recorrentes em Aspose.Tasks
second_title: API Aspose.Tasks .NET
description: Aprenda como extrair informações de tarefas recorrentes de arquivos do MS Project usando Aspose.Tasks for .NET. Fácil integração para desenvolvedores .NET.
type: docs
weight: 13
url: /pt/net/rate-recurring-tasks/recurring-task-information/
---
## Introdução
Aspose.Tasks for .NET é uma biblioteca poderosa que permite aos desenvolvedores trabalhar com arquivos do Microsoft Project em seus aplicativos .NET. Neste tutorial, exploraremos como extrair informações de tarefas recorrentes de arquivos do MS Project usando Aspose.Tasks.
## Pré-requisitos
Antes de começarmos, certifique-se de ter os seguintes pré-requisitos:
1. Compreensão básica da linguagem de programação C#.
2. Visual Studio instalado em seu sistema.
3.  Biblioteca Aspose.Tasks para .NET instalada. Você pode baixá-lo em[aqui](https://releases.aspose.com/tasks/net/).
## Importar namespaces
Para começar, importe os namespaces necessários em seu código C#:
```csharp
    using Aspose.Tasks;
    using System;
    
```
Agora, vamos dividir o exemplo em várias etapas:
## Etapa 1: configurar o caminho do arquivo do projeto
```csharp
String DataDir = "Your Document Directory";
```
 substituir`"Your Document Directory"` com o caminho para o seu arquivo do MS Project.
## Passo 2: Carregue o arquivo MS Project
```csharp
var project = new Project(DataDir + "TestRecurringTask2016.mpp");
```
 Esta linha inicializa um novo`Project` objeto carregando o arquivo do MS Project especificado pelo caminho.
## Passo 3: Leia informações recorrentes de tarefas
```csharp
foreach (var task in project.RootTask.SelectAllChildTasks())
{
    var info = task.RecurringInfo;
    if (info == null)
    {
        continue;
    }
    // Acesse e exiba informações de tarefas recorrentes
    Console.WriteLine("Start Date: " + info.StartDate);
    Console.WriteLine("Duration: " + info.Duration);
    Console.WriteLine("End Date: " + info.EndDate);
    // Continue exibindo outras informações de tarefas recorrentes conforme necessário
}
```
Este loop percorre todas as tarefas do projeto e verifica se cada tarefa possui informações recorrentes associadas a ela. Se isso acontecer, ele recupera e exibe várias propriedades da tarefa recorrente, como data de início, duração, data de término, etc.
## Conclusão
Neste tutorial, aprendemos como extrair informações de tarefas recorrentes de arquivos do MS Project usando Aspose.Tasks for .NET. Com esse conhecimento, agora você pode integrar essa funcionalidade aos seus aplicativos .NET para trabalhar com tarefas recorrentes de maneira mais eficiente.
## Perguntas frequentes
### P: Posso modificar informações de tarefas recorrentes usando Aspose.Tasks for .NET?
R: Sim, você pode modificar informações de tarefas recorrentes de forma programática usando as APIs fornecidas.
### P: O Aspose.Tasks oferece suporte a outros formatos de arquivo de projeto além do MS Project?
R: Sim, Aspose.Tasks oferece suporte a vários formatos de arquivo de projeto, como MPP, XML e CSV.
### P: Existe uma avaliação gratuita disponível para Aspose.Tasks for .NET?
 R: Sim, você pode baixar uma avaliação gratuita em[aqui](https://releases.aspose.com/).
### P: Onde posso encontrar a documentação do Aspose.Tasks for .NET?
 R: Você pode encontrar a documentação[aqui](https://reference.aspose.com/tasks/net/).
### P: Como posso obter suporte técnico para Aspose.Tasks for .NET?
R: Você pode obter suporte técnico no fórum Aspose.Tasks.[aqui](https://forum.aspose.com/c/tasks/15).