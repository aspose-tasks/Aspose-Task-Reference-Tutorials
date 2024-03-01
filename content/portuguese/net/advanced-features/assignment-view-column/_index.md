---
title: Coluna de visualização de atribuição personalizada em Aspose.Tasks
linktitle: Coluna de visualização de atribuição personalizada em Aspose.Tasks
second_title: API Aspose.Tasks .NET
description: Aprenda como adicionar colunas de visualização de atribuição personalizadas em Aspose.Tasks for .NET para aprimorar os recursos de gerenciamento de projetos.
type: docs
weight: 16
url: /pt/net/advanced-features/assignment-view-column/
---
## Introdução

Neste tutorial, exploraremos como adicionar colunas personalizadas para visualizações de tarefas usando Aspose.Tasks for .NET. Colunas personalizadas fornecem flexibilidade e permitem exibir informações adicionais relevantes para suas necessidades de gerenciamento de projetos.

## Pré-requisitos

Antes de começarmos, certifique-se de ter o seguinte:

1. Conhecimento básico da linguagem de programação C#.
2.  Biblioteca Aspose.Tasks para .NET instalada. Se não, você pode baixá-lo[aqui](https://releases.aspose.com/tasks/net/).
3. Um ambiente de desenvolvimento integrado (IDE), como o Visual Studio.

## Importar namespaces

Primeiro, vamos importar os namespaces necessários para acessar as classes e métodos necessários para criar colunas de visualização de atribuição personalizadas:

```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.Saving;
using Aspose.Tasks.Visualization;

```

## Etapa 1: carregar o projeto

 Para começar, carregue seu arquivo de projeto usando o`Project` aula:

```csharp
// O caminho para o diretório de documentos.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "CreateProject2.mpp");
```

## Etapa 2: criar opções para salvar planilhas

 Em seguida, crie uma instância de`Spreadsheet2003SaveOptions` o que nos permite personalizar as colunas da visualização de tarefas:

```csharp
var options = new Spreadsheet2003SaveOptions();
```

## Etapa 3: definir coluna personalizada

 Agora, defina sua coluna personalizada criando uma instância de`AssignmentViewColumn`. Esta classe requer o nome da coluna, a largura e uma função delegada para converter os dados de atribuição em texto da coluna:

```csharp
var column = new AssignmentViewColumn("Notes", 200, delegate(ResourceAssignment assignment) { return assignment.Get(Asn.NotesText); });
```

## Etapa 4: adicionar coluna personalizada às opções

Adicione a coluna personalizada à coleção de colunas da visualização de atribuição das opções de salvamento:

```csharp
options.AssignmentView.Columns.Add(column);
```

## Etapa 5: iterar por meio de atribuições

Itere cada atribuição de recurso no projeto e exiba o texto da coluna personalizada:

```csharp
foreach (var assignment in project.ResourceAssignments)
{
    foreach (var col in options.AssignmentView.Columns)
    {
        var assnCol = (AssignmentViewColumn)col;
        Console.WriteLine("Column Field: " + assnCol.Field);
        Console.WriteLine("Column Text (converted): " + assnCol.GetColumnText(assignment));
        Console.WriteLine();
    }
}
```

## Etapa 6: salve o projeto com colunas personalizadas

Por fim, salve o projeto com as colunas de visualização de atribuição personalizada:

```csharp
project.Save(OutDir + "UsingSpreadsheet2003SaveOptions_out.xml", options);
```

## Conclusão

Neste tutorial, aprendemos como adicionar colunas de visualização de atribuição personalizadas usando Aspose.Tasks for .NET. Colunas personalizadas oferecem flexibilidade na exibição de informações adicionais adaptadas aos requisitos do seu projeto, aprimorando os recursos de gerenciamento de projetos.

## Perguntas frequentes

### P1: Posso adicionar várias colunas personalizadas à visualização da tarefa?

 A1: Sim, você pode adicionar várias colunas personalizadas criando instâncias adicionais de`AssignmentViewColumn` e adicionando-os ao`Columns` coleção.

### P2: Existem conversores predefinidos disponíveis para campos de atribuição comuns?

A2: Sim, Aspose.Tasks fornece conversores predefinidos para campos de atribuição comuns, facilitando a extração de dados para colunas personalizadas.

### P3: Posso personalizar a aparência de colunas personalizadas, como formatação de texto ou aplicação de estilos?

R3: Sim, você pode personalizar a aparência de colunas personalizadas modificando propriedades como largura, fonte e alinhamento.

### Q4: É possível remover colunas padrão da visualização de tarefas?

 A4: Sim, você pode remover colunas padrão excluindo-as do`Columns` coleção ou definindo sua largura como zero.

### P5: O Aspose.Tasks oferece suporte à exportação de projetos para outros formatos além de planilhas com colunas personalizadas?

A5: Sim, Aspose.Tasks oferece suporte à exportação de projetos para vários formatos, como PDF, HTML e XML, permitindo opções versáteis de relatórios de projetos.