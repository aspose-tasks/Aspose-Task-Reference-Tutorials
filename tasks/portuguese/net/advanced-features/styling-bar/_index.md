---
date: 2026-04-06
description: Aprenda como alterar o estilo das barras e personalizar as cores das
  barras no Aspose.Tasks para .NET para melhorar a visualização do projeto.
keywords:
- how to change bar
- customize bar colors
- Aspose.Tasks bar styling
linktitle: Barra de Estilização no Aspose.Tasks
second_title: Aspose.Tasks .NET API
title: Como Alterar o Estilo das Barras no Aspose.Tasks
url: /pt/net/advanced-features/styling-bar/
weight: 19
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Como Alterar a Estilização de Barras no Aspose.Tasks

## Introdução

Se você precisa **como alterar a barra** aparência em um arquivo Microsoft Project, Aspose.Tasks for .NET oferece controle total sobre cores de barra, formas e estilos de texto. Ao personalizar cores de barra e outros atributos visuais, você pode tornar os planos de projeto muito mais fáceis de ler e mais alinhados com a identidade visual da sua organização. Neste tutorial, percorreremos um exemplo completo, passo a passo, que mostra como alterar a estilização de barras, desde o carregamento de um projeto até a exportação com as novas regras visuais aplicadas.

## Respostas Rápidas
- **O que posso estilizar?** Barras, marcos e texto de tarefas em gráficos de Gantt.  
- **Qual formato suporta barras estilizadas?** PDF, XLSX, HTML e MPP nativo ao salvar com `PdfSaveOptions`.  
- **Preciso de uma licença?** É necessária uma licença comercial para uso em produção; uma avaliação gratuita funciona para testes.  
- **Posso aplicar múltiplos estilos?** Sim – adicione quantos objetos `BarStyle` precisar.  
- **É compatível com .NET Core?** Absolutamente – funciona com .NET Framework e .NET Core/5/6+.

## O que é Estilização de Barras no Aspose.Tasks?

A estilização de barras permite definir regras visuais que o mecanismo Aspose.Tasks aplica ao renderizar gráficos de Gantt. Cada regra (um **BarStyle**) tem como alvo um tipo específico de item — tarefas, marcos ou tarefas resumo — e permite definir cores, formas e até texto personalizado.

## Por que personalizar cores de barra?

Personalizar cores de barra ajuda as partes interessadas a identificar instantaneamente caminhos críticos, tarefas atrasadas ou marcos. Também permite combinar com esquemas de cores corporativos, fazendo com que os relatórios pareçam profissionais e alinhados à marca.

## Pré-requisitos

1. **Aspose.Tasks for .NET** – faça o download a partir da [página de download](https://releases.aspose.com/tasks/net/).  
2. Um ambiente de desenvolvimento que suporte .NET (Framework 4.6+, .NET Core 3.1+ ou superior).  
3. Familiaridade básica com C# – os exemplos utilizam código simples e autocontido.

## Importar Namespaces

First, import the namespaces that contain the classes we’ll use:

```csharp
using Aspose.Tasks;
using System.Collections.Generic;
using System.Drawing;

using Aspose.Tasks.Saving;
using Aspose.Tasks.Visualization;
```

## Etapa 1: Carregar o Projeto

Load an existing MPP file (or create a new one) so you have a project object to work with:

```csharp
// The path to th documents directory.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "Project2.mpp");
```

## Etapa 2: Configurar Opções de Salvamento

Create a `PdfSaveOptions` instance and initialise the `BarStyles` collection where we’ll store our custom styles:

```csharp
SaveOptions options = new PdfSaveOptions
{
    BarStyles = new List<BarStyle>()
};
```

## Etapa 3: Definir Estilo de Barra

Now we build a `BarStyle` object and set the properties that control how the bar looks. This is where we **customize bar colors** and shapes:

```csharp
var style = new BarStyle();
style.ItemType = BarItemType.Milestone; // Set bar item type
style.BarColor = Color.Green; // Set bar color
style.BarShape = BarShape.HalfHeight; // Set bar shape
style.StartShape = Shape.LeftBracket; // Set shape at the beginning of the bar
style.StartShapeColor = Color.Aqua; // Set color of the start shape
style.EndShape = Shape.RightBracket; // Set shape at the end of the bar
style.EndShapeColor = Color.Aquamarine; // Set color of the end shape
style.TextStyle = new TextStyle(); // Set text style
style.TextStyle.BackgroundColor = Color.Black; // Set background color for text
```

## Etapa 4: Personalizar Conversor de Texto (Opcional)

If you want to tweak the text that appears on the bar, you can assign a custom converter. The example prefixes task names that don’t already start with “T”:

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

## Etapa 5: Adicionar Estilo de Barra às Opções

Add the fully configured style to the `BarStyles` collection of the save options:

```csharp
options.BarStyles.Add(style);
```

## Etapa 6: Salvar o Projeto

Finally, export the project. The PDF (or other format) will render the Gantt chart using the bar style we defined:

```csharp
project.Save(DataDir + "WorkWithBarStyle_out.mpp", options);
```

## Problemas Comuns e Soluções

| Issue | Reason | Fix |
|-------|--------|-----|
| **Estilo de barra não aplicado** | A coleção `BarStyles` estava vazia ou não foi anexada às opções de salvamento. | Certifique-se de adicionar o `BarStyle` a `options.BarStyles` antes de chamar `Save`. |
| **Cores parecem diferentes no PDF** | A renderização de PDF pode usar um perfil de cor diferente. | Use valores padrão de `System.Drawing.Color` ou defina cores ARGB personalizadas. |
| **Conversor de texto lança referência nula** | A propriedade da tarefa `Tsk.Name` é nula para algumas tarefas. | Adicione uma verificação de nulo antes de acessar `task.Get(Tsk.Name)`. |

## Perguntas Frequentes

### Q1: Posso aplicar múltiplos estilos de barra a um único projeto?

A1: Sim, você pode definir e aplicar múltiplos estilos de barra a diferentes tipos de tarefas dentro do mesmo projeto.

### Q2: É possível alterar dinamicamente estilos de barra durante a execução?

A2: Sim, você pode modificar dinamicamente estilos de barra com base em certas condições ou preferências do usuário dentro da sua aplicação.

### Q3: O Aspose.Tasks suporta exportar projetos com barras estilizadas para diferentes formatos de arquivo?

A3: Sim, o Aspose.Tasks suporta exportar projetos com barras estilizadas para vários formatos, como PDF, XLSX e HTML.

### Q4: Existem estilos de barra predefinidos disponíveis no Aspose.Tasks?

A4: Embora o Aspose.Tasks forneça estilos de barra padrão, os desenvolvedores também podem criar estilos de barra personalizados adequados aos requisitos do seu projeto.

### Q5: Posso recuperar e modificar estilos de barra existentes dentro de um projeto usando a API?

A5: Sim, você pode recuperar e modificar estilos de barra existentes programaticamente usando a API Aspose.Tasks for .NET.

## Perguntas Frequentes

**Q: Como altero a cor da barra para tarefas regulares em vez de marcos?**  
A: Defina `style.ItemType = BarItemType.Task;` e atribua `style.BarColor` à `Color` desejada.

**Q: Posso usar esta abordagem para estilizar barras ao exportar para HTML?**  
A: Sim. Use `HtmlSaveOptions` e preencha sua coleção `BarStyles` da mesma forma.

**Q: Existe um limite para o número de estilos de barra que posso definir?**  
A: Praticamente não; você pode adicionar quantos precisar, mas mantenha o desempenho em mente para coleções muito grandes.

**Q: Preciso chamar `project.Calculate()` após alterar os estilos?**  
A: Não, os estilos são aplicados durante a operação de salvamento; o recálculo só é necessário para alterações de cronograma.

---

**Última Atualização:** 2026-04-06  
**Testado com:** Aspose.Tasks 24.11 for .NET  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}