---
date: 2026-03-05
description: Aprenda como salvar imagens, gerar HTML com imagens e personalizar a
  exportação de imagens usando Aspose.Tasks para .NET. Guia passo a passo para salvar
  o projeto como HTML.
linktitle: How to Save Images with Aspose.Tasks for .NET
second_title: Aspose.Tasks .NET API
title: Como salvar imagens com Aspose.Tasks para .NET
url: /pt/net/advanced-concepts/image-saving/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Como Salvar Imagens com Aspose.Tasks para .NET

## Introdução

Neste tutorial você descobrirá **como salvar imagens** de arquivos Microsoft Project usando a API Aspose.Tasks para .NET. Seja para incorporar gráficos em relatórios, gerar páginas HTML que contenham recursos visuais do projeto ou simplesmente exportar recursos diagramáticos, os passos abaixo o guiarão por todo o processo — desde a configuração do objeto do projeto até a personalização dos callbacks de exportação de imagens.

## Respostas Rápidas
- **O que significa “como salvar imagens” no Aspose.Tasks?**  
  Refere‑se ao uso da interface `IImageSavingCallback` para controlar onde e como os recursos visuais são gravados no disco.
- **Posso salvar um projeto como HTML com imagens incorporadas?**  
  Sim, usando `HtmlSaveOptions` junto com callbacks de salvamento de imagens você pode **salvar o projeto como HTML** que inclui todas as imagens geradas.
- **Preciso de uma licença para exportação de imagens?**  
  Uma licença de avaliação temporária funciona para testes; uma licença completa é necessária para uso em produção.
- **Quais versões do .NET são suportadas?**  
  Aspose.Tasks para .NET suporta .NET Framework 4.5+, .NET Core 3.1+, e .NET 5/6+.
- **É possível personalizar a exportação de imagens (formato, pasta, nomeação)?**  
  Absolutamente – o callback oferece controle total sobre o nome do arquivo, formato e destino.

## O que é “como salvar imagens” no contexto do Aspose.Tasks?
Salvar imagens significa extrair elementos visuais (gráficos, barras de Gantt, gráficos de recursos) de um arquivo Project e gravá‑los em arquivos de imagem (PNG, JPEG, etc.). O Aspose.Tasks fornece um mecanismo flexível de callbacks que permite decidir a localização exata, convenção de nomenclatura e até o formato da imagem.

## Por que usar o Aspose.Tasks para salvar imagens?
- **Controle programático total** – nenhuma interação manual de UI necessária.  
- **Multiplataforma** – funciona no Windows, Linux e macOS via .NET Core.  
- **Renderização de alta fidelidade** – as imagens mantêm a mesma qualidade da visualização original do Project.  
- **Geração fácil de HTML** – combine `HtmlSaveOptions` com callbacks de imagem para **gerar HTML com imagens** automaticamente.

## Pré‑requisitos

Antes de começar, certifique‑se de que você tem o seguinte:

1. Visual Studio instalado na sua máquina de desenvolvimento.  
2. Aspose.Tasks para .NET baixado de [aqui](https://releases.aspose.com/tasks/net/).  
3. Familiaridade básica com C# e a estrutura de projetos .NET.

## Importar Namespaces

Primeiro, traga os namespaces necessários para o seu arquivo fonte:

```csharp
using Aspose.Tasks;
using System.Collections.Generic;
using System.IO;

using Aspose.Tasks.Saving;
using Aspose.Tasks.Visualization;
```

## Passo 1: Criar um Objeto Project

Carregue o arquivo Microsoft Project com o qual deseja trabalhar:

```csharp
var project = new Project("Project1.mpp");
```

## Passo 2: Definir Opções de Salvamento

Crie as opções de salvamento HTML que também conterão nossos callbacks de salvamento de imagens:

```csharp
var options = GetSaveOptions(1);
```

## Passo 3: Salvar o Projeto como HTML (save project as html)

Agora exporte o projeto para um arquivo HTML. As imagens referenciadas no HTML serão geradas pelo callback que definiremos a seguir:

```csharp
project.Save("document_out.html", options);
```

## Passo 4: Implementar Callback de Salvamento de Imagem (customize image export)

Implemente a interface `IImageSavingCallback`. É aqui que você **personaliza o comportamento da exportação de imagens**:

```csharp
private class ResourcePrefixForNestedResources : IImageSavingCallback
{
    public void ImageSaving(ImageSavingArgs args)
    {
        // Image saving logic goes here
    }
}
```

## Passo 5: Salvar Imagens no Diretório Especificado

Dentro do método `ImageSaving`, decida onde cada imagem deve ser armazenada. O exemplo abaixo diferencia recursos PNG de outros formatos:

```csharp
if (args.FileName.EndsWith("png"))
{
    // Save nested resources
}
else
{
    // Save regular resources
}
```

## Passo 6: Especificar Opções de Salvamento (including callbacks)

Configure os callbacks para fontes, CSS e imagens. Isso garante que cada elemento visual seja tratado de forma consistente:

```csharp
public static HtmlSaveOptions GetSaveOptions(int pageNumber)
{
    var options = new HtmlSaveOptions
    {
        // Specify save options here
    };

    var program = new ResourcePrefixForNestedResources();
    options.FontSavingCallback = program;
    options.CssSavingCallback = program;
    options.ImageSavingCallback = program;

    return options;
}
```

## Problemas Comuns e Soluções

| Problema | Causa | Correção |
|----------|-------|----------|
| Imagens não aparecem no HTML gerado | Callback não atribui um caminho de arquivo válido | Certifique‑se de que `args.Path` aponta para uma pasta gravável e defina `args.ImageStream` corretamente. |
| Arquivos PNG são salvos com extensão errada | A lógica condicional verifica apenas o sufixo “png” | Use `Path.GetExtension(args.FileName).Equals(".png", StringComparison.OrdinalIgnoreCase)` para detecção robusta. |
| Referências HTML quebradas após mover arquivos | Caminhos relativos mudaram após mover a pasta de saída | Mantenha as pastas HTML e de imagens juntas ou atualize `options.ImageFolder` adequadamente. |

## Conclusão

Seguindo estes passos, você agora sabe **como salvar imagens** de um arquivo Project, **salvar o projeto como HTML** e **personalizar a exportação de imagens** para se adequar à estrutura de pastas da sua aplicação. Essa abordagem permite **gerar HTML com imagens** que podem ser incorporadas em relatórios, portais de documentação ou painéis web de forma fluida.

## Perguntas Frequentes

**Q1: Posso usar o Aspose.Tasks para manipular arquivos de projeto em outros formatos além de HTML?**  
A1: Sim, o Aspose.Tasks suporta vários formatos como PDF, XLSX e MPP.

**Q2: O Aspose.Tasks oferece suporte à integração com armazenamento em nuvem?**  
A2: Sim, o Aspose.Tasks oferece APIs para trabalhar com serviços de armazenamento em nuvem populares como Amazon S3 e Google Drive.

**Q3: O Aspose.Tasks é compatível com .NET Core?**  
A3: Sim, o Aspose.Tasks é compatível com .NET Core, permitindo o desenvolvimento de aplicações multiplataforma.

**Q4: Posso personalizar a aparência das imagens salvas?**  
A4: Sim, você pode personalizar a aparência das imagens modificando a lógica de salvamento dentro dos métodos de callback.

**Q5: O Aspose.Tasks oferece versões de avaliação para fins de teste?**  
A5: Sim, você pode obter uma avaliação gratuita do Aspose.Tasks de [aqui](https://releases.aspose.com/).

---

**Última atualização:** 2026-03-05  
**Testado com:** Aspose.Tasks 24.11 para .NET  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}