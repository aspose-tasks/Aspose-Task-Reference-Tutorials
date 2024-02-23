---
title: Barra de estilo em Aspose.Tasks
linktitle: Barra de estilo em Aspose.Tasks
second_title: API Aspose.Tasks .NET
description: Aprenda como estilizar barras no Aspose.Tasks for .NET para aprimorar a visualização do projeto.
type: docs
weight: 19
url: /pt/net/advanced-features/styling-bar/
---
## Introdução

Estilizar barras no Aspose.Tasks é um aspecto essencial na criação de planos de projeto visualmente atraentes. Com a flexibilidade oferecida pela API Aspose.Tasks, os desenvolvedores podem personalizar vários aspectos das barras, como cor, forma e estilo de texto, para aprimorar a visualização do projeto. Neste tutorial, exploraremos como estilizar barras usando Aspose.Tasks for .NET, dividindo cada exemplo em etapas gerenciáveis.

## Pré-requisitos

Antes de começarmos, certifique-se de ter os seguintes pré-requisitos em vigor:

1.  Biblioteca Aspose.Tasks for .NET: Baixe e instale a biblioteca Aspose.Tasks for .NET do[página de download](https://releases.aspose.com/tasks/net/).
2. Ambiente de desenvolvimento: Configure um ambiente de desenvolvimento com suporte ao framework .NET.
3. Compreensão básica de C#: A familiaridade com a linguagem de programação C# será benéfica.

## Importar namespaces

Primeiramente, vamos importar os namespaces necessários para acessar as classes e métodos Aspose.Tasks:

```csharp
using Aspose.Tasks;
using System.Collections.Generic;
using System.Drawing;

using Aspose.Tasks.Saving;
using Aspose.Tasks.Visualization;

```

## Etapa 1: carregar o projeto

Para começar, carregue o arquivo do projeto usando a API Aspose.Tasks:

```csharp
// O caminho para o diretório de documentos.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "Project2.mpp");
```

## Etapa 2: configurar opções de salvamento

Defina as opções de salvamento, especificando os estilos de barra a serem aplicados:

```csharp
SaveOptions options = new PdfSaveOptions
{
    BarStyles = new List<BarStyle>()
};
```

## Etapa 3: definir o estilo da barra

Crie um novo estilo de barra e personalize suas propriedades:

```csharp
var style = new BarStyle();
style.ItemType = BarItemType.Milestone; // Definir tipo de item da barra
style.BarColor = Color.Green; // Definir cor da barra
style.BarShape = BarShape.HalfHeight; //Definir formato da barra
style.StartShape = Shape.LeftBracket; // Defina a forma no início da barra
style.StartShapeColor = Color.Aqua; // Definir a cor da forma inicial
style.EndShape = Shape.RightBracket; // Defina a forma no final da barra
style.EndShapeColor = Color.Aquamarine; // Defina a cor da forma final
style.TextStyle = new TextStyle(); // Definir estilo de texto
style.TextStyle.BackgroundColor = Color.Black; // Defina a cor de fundo do texto
```

## Etapa 4: personalizar o conversor de texto

Opcionalmente, personalize o conversor de texto para modificar a renderização do texto:

```csharp
style.LeftBarTextConverter = task =>
{
    if (!task.Get(Tsk.Name).StartsWith("T"))
    {
        task.Set(Tsk.Name, "T" + task.Get(Tsk.Name));
    }
    return task.Get(Tsk.Name);
};
```

## Etapa 5: adicionar estilo de barra às opções

Adicione o estilo de barra configurado às opções de salvamento:

```csharp
options.BarStyles.Add(style);
```

## Etapa 6: salve o projeto

Por fim, salve o projeto com os estilos de barra aplicados:

```csharp
project.Save(DataDir + "WorkWithBarStyle_out.mpp", options);
```

## Conclusão

A personalização de estilos de barra no Aspose.Tasks for .NET fornece aos desenvolvedores a capacidade de criar planos de projeto visualmente atraentes. Seguindo as etapas descritas neste tutorial, você pode estilizar barras com eficiência para atender aos requisitos específicos de visualização do projeto.

## Perguntas frequentes

### Q1: Posso aplicar vários estilos de barra a um único projeto?

A1: Sim, você pode definir e aplicar vários estilos de barra a diferentes tipos de tarefas no mesmo projeto.
   
### Q2: É possível alterar dinamicamente os estilos das barras durante o tempo de execução?

R2: Sim, você pode modificar dinamicamente os estilos de barra com base em determinadas condições ou preferências do usuário em seu aplicativo.
   
### Q3: O Aspose.Tasks oferece suporte à exportação de projetos com barras estilizadas para diferentes formatos de arquivo?

A3: Sim, Aspose.Tasks suporta a exportação de projetos com barras estilizadas para vários formatos, como PDF, XLSX e HTML.
   
### Q4: Existem estilos de barra predefinidos disponíveis no Aspose.Tasks?

A4: Embora Aspose.Tasks forneça estilos de barra padrão, os desenvolvedores também podem criar estilos de barra personalizados adaptados aos requisitos do projeto.
   
### P5: Posso recuperar e modificar estilos de barra existentes em um projeto usando a API?

A5: Sim, você pode recuperar e modificar estilos de barra existentes programaticamente usando Aspose.Tasks for .NET API.