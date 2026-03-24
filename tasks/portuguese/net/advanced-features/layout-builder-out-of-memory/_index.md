---
date: 2026-03-24
description: Aprenda a lidar com falta de memória e como salvar a imagem do projeto
  usando o Aspose.Tasks Layout Builder no .NET. Guia passo a passo com exemplos de
  código.
linktitle: Out of Memory Handling with Aspose.Tasks Layout Builder
second_title: Aspose.Tasks .NET API
title: Tratamento de Falta de Memória com o Aspose.Tasks Layout Builder (C#)
url: /pt/net/advanced-features/layout-builder-out-of-memory/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Manipulação de Falta de Memória com Aspose.Tasks Layout Builder

## Introdução

A manipulação de falta de memória é uma parte crítica da construção de aplicações .NET confiáveis que trabalham com arquivos de projeto grandes. Ao gerar visualizações com Aspose.Tasks Layout Builder, você pode rapidamente encontrar exceções relacionadas à memória, especialmente em diagramas de Gantt complexos. Neste tutorial, vamos guiá‑lo sobre como **tratar exceções de memória**, **personalizar a visualização do Gantt** e **salvar a imagem do projeto** com segurança, para que sua aplicação permaneça responsiva mesmo com cronogramas massivos.

## Respostas Rápidas
- **O que é manipulação de falta de memória?** Gerenciar o uso de memória e capturar erros do tipo `OutOfMemoryException` ao processar grandes volumes de dados.
- **Qual API ajuda?** Aspose.Tasks Layout Builder para .NET.
- **Cenário típico?** Renderizar um diagrama de Gantt em alta resolução para PNG.
- **Pré‑requisito chave?** .NET (Framework 4.5+ ou .NET 6) com Aspose.Tasks instalado.
- **Como capturar erros?** Use blocos `try…catch` para `ApsLayoutBuilderOutOfMemoryException` e exceções relacionadas.

## Pré‑requisitos

Antes de mergulhar no código, certifique‑se de que você tem:

1. **Noções básicas de C#** – você deve estar confortável com a sintaxe padrão de C#.
2. **Aspose.Tasks para .NET** instalado. Se ainda não o adicionou, faça o download [aqui](https://releases.aspose.com/tasks/net/).
3. **Um IDE** como Visual Studio (ou VS Code com a extensão C#) para compilar e executar o exemplo.

## Importar Namespaces

```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.Saving;
using Aspose.Tasks.Visualization;
```

## Guia Passo a Passo

### Passo 1: Carregar o Projeto

```csharp
// The path to the documents directory.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "Blank2010.mpp");
```

Esta linha carrega **Blank2010.mpp** em uma instância `Project`, preparando‑a para visualização.

### Passo 2: Personalizar a Visualização do Diagrama de Gantt

```csharp
var ganttChart = (GanttChartView)project.Views.ToList()[0];
ganttChart.MiddleTimescaleTier.Unit = TimescaleUnit.Hours;
ganttChart.BottomTimescaleTier.Unit = TimescaleUnit.Minutes;
ganttChart.BottomTimescaleTier.Count = 1;
```

Aqui nós **personalizamos a visualização do Gantt** ajustando os níveis médio e inferior da escala de tempo. Alterar esses níveis reduz a quantidade de dados renderizados de uma vez, o que pode ajudar a mitigar a pressão de memória.

### Passo 3: Configurar Opções de Salvamento de Imagem

```csharp
var options = new ImageSaveOptions(SaveFileFormat.Png);
options.Timescale = Timescale.DefinedInView;
```

`ImageSaveOptions` informa ao Aspose.Tasks como renderizar o diagrama. Escolhemos PNG como formato de saída e vinculamos a escala de tempo à visualização que acabamos de personalizar.

### Passo 4: Salvar o Projeto como Imagem

```csharp
project.Save(DataDir + "SaveToStreamWithOptionsAndCatchException_out.mpp", options);
```

A chamada `Save` **salva a imagem do projeto** usando as opções definidas acima. Se o projeto for muito grande, este é o ponto onde uma condição de falta de memória é mais provável de aparecer.

### Passo 5: Tratar Exceções

```csharp
catch (ApsLayoutBuilderOutOfMemoryException ex)
{
    Console.WriteLine(ex.Message);
}
catch (BitmapInvalidSizeException ex)
{
    Console.WriteLine(ex.Message);
}
```

Ao capturar `ApsLayoutBuilderOutOfMemoryException` você **trata a exceção de memória** de forma elegante, fornecendo uma mensagem clara em vez de travar a aplicação. O segundo `catch` lida com problemas de tamanho de bitmap que também podem surgir ao renderizar diagramas enormes.

## Problemas Comuns e Soluções

| Problema | Por que acontece | Solução |
|----------|------------------|---------|
| **OutOfMemoryException** | Renderizar uma imagem de altíssima resolução consome mais RAM do que o processo pode alocar. | Reduza as dimensões da imagem, simplifique os níveis da escala de tempo ou divida o diagrama em várias imagens. |
| **BitmapInvalidSizeException** | O tamanho de bitmap solicitado excede o máximo da plataforma. | Limite largura/altura em `ImageSaveOptions` ou renderize em segmentos. |
| **Desempenho lento** | Arquivos de projeto grandes exigem muito processamento. | Habilite `project.Set(Prj.SaveToCache, true)` antes da renderização, ou use uma thread em segundo plano. |

## Perguntas Frequentes

### Q1: O que é Aspose.Tasks para .NET?

A1: Aspose.Tasks para .NET é uma API poderosa que permite aos desenvolvedores manipular arquivos do Microsoft Project programaticamente em aplicações .NET.

### Q2: Como posso obter uma licença temporária para Aspose.Tasks?

A2: Você pode obter uma licença temporária para Aspose.Tasks visitando [este link](https://purchase.aspose.com/temporary-license/).

### Q3: O Aspose.Tasks é adequado para manipular arquivos de projeto grandes?

A3: Sim, o Aspose.Tasks oferece recursos e otimizações para lidar eficientemente com arquivos de projeto grandes, embora os desenvolvedores ainda devam considerar estratégias de gerenciamento de memória.

### Q4: Posso personalizar a aparência dos diagramas de Gantt usando Aspose.Tasks?

A4: Absolutamente! O Aspose.Tasks fornece amplas capacidades para personalizar a aparência e o layout dos diagramas de Gantt de acordo com suas necessidades.

### Q5: Onde posso encontrar mais ajuda e suporte para Aspose.Tasks?

A5: Você pode encontrar mais ajuda e suporte, além de interagir com a comunidade, no [fórum Aspose.Tasks](https://forum.aspose.com/c/tasks/15).

## Perguntas Frequentes

**P: Como posso reduzir o uso de memória ao salvar a imagem de um projeto?**  
R: Diminua a resolução da imagem, limite o intervalo da escala de tempo ou salve o diagrama em vários segmentos menores.

**P: É possível transmitir a imagem diretamente para uma resposta web?**  
R: Sim, você pode usar `project.Save(stream, options)` e escrever o stream na resposta HTTP.

**P: O Aspose.Tasks suporta .NET Core e .NET 5/6?**  
R: A biblioteca é totalmente compatível com .NET Core, .NET 5 e .NET 6.

**P: O que devo fazer se ainda encontrar um erro de falta de memória após otimizações?**  
R: Considere processar o projeto em uma máquina com mais RAM ou delegar a renderização para um serviço em segundo plano.

**P: Posso exportar o diagrama de Gantt para formatos além de PNG?**  
R: Sim, `ImageSaveOptions` suporta JPEG, BMP e TIFF além de PNG.

---

**Última atualização:** 2026-03-24  
**Testado com:** Aspose.Tasks 24.11 para .NET  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}