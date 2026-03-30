---
date: 2026-03-16
description: Aprenda a implementar o callback de salvamento de página no Aspose.Tasks
  para .NET, permitindo o tratamento personalizado de fluxos de saída de documentos
  de várias páginas.
linktitle: Implement page saving callback in Aspose.Tasks
second_title: Aspose.Tasks .NET API
title: Implementar callback de salvamento de página no Aspose.Tasks
url: /pt/net/advanced-concepts/page-saving-callback/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Implementar callback de salvamento de página no Aspose.Tasks

## Introdução

Neste tutorial, você aprenderá como **implementar callback de salvamento de página** no Aspose.Tasks para .NET. Esse recurso poderoso permite direcionar cada página de um documento de várias páginas para um stream de sua escolha, dando controle total sobre como a saída é armazenada ou processada adicionalmente.

## Respostas Rápidas
- **O que o callback de salvamento de página faz?** Ele captura cada página renderizada em um stream separado para que você possa manipulá‑las individualmente.  
- **Para qual formato posso exportar?** Qualquer formato suportado por `ImageSaveOptions`, por exemplo, PNG, JPEG, PDF.  
- **Preciso de uma licença?** Uma licença válida do Aspose.Tasks é necessária para uso em produção.  
- **Posso usar isso com .NET Core?** Sim, o Aspose.Tasks oferece suporte total ao .NET Core e .NET 5/6+.  
- **O callback é thread‑safe?** O callback é executado na mesma thread que realiza a renderização, portanto as regras normais de segurança de thread se aplicam.

## O que é **implement page saving callback**?
O padrão **implement page saving callback** permite inserir lógica personalizada no pipeline de salvamento do Aspose.Tasks. Em vez de gravar diretamente em um arquivo, você recebe um objeto `Stream` para cada página, permitindo armazená‑lo na memória, fazer upload para armazenamento em nuvem ou aplicar processamento adicional.

## Por que exportar o projeto como PNG com um callback?
Exportar um projeto como PNG fornece uma imagem raster de cada página do diagrama de Gantt, ideal para relatórios, e‑mails ou incorporação em páginas web. Usar um callback permite manter cada página em um `MemoryStream` separado sem criar arquivos temporários no disco.

## Pré‑requisitos

1. **Conhecimento em C#** – familiaridade básica com classes, interfaces e streams.  
2. **Aspose.Tasks for .NET** – faça o download e instale a partir de [here](https://releases.aspose.com/tasks/net/).  
3. **IDE** – Visual Studio, Rider ou qualquer editor compatível com .NET.

## Importar Namespaces

To start, import the required namespaces:

```csharp
using Aspose.Tasks;
using System.Collections.Generic;
using System.IO;

using Aspose.Tasks.Saving;
```

## Etapa 1: Criar um Objeto Project

Load an existing MPP file into a `Project` instance:

```csharp
var project = new Project(DataDir + "Homemoveplan.mpp");
```

## Etapa 2: Configurar Image Save Options

Set up `ImageSaveOptions` for PNG output and attach the custom callback:

```csharp
var imageSaveOptions = new ImageSaveOptions(SaveFileFormat.Png);
var callback = new CustomPageSavingCallback();
imageSaveOptions.PageSavingCallback = callback;
imageSaveOptions.RenderToSinglePage = false;
```

> **Dica profissional:** Definir `RenderToSinglePage = false` garante que cada página do diagrama de Gantt seja renderizada separadamente, o que é essencial para que o callback receba streams distintos.

## Etapa 3: Salvar o Project com Callback

Invoke the `Save` method, passing `Stream.Null` because the actual streams are supplied by the callback:

```csharp
project.Save(Stream.Null, imageSaveOptions);
```

## Etapa 4: Processar Streams de Páginas Salvas

After the save operation completes, the callback holds a collection of `MemoryStream` objects—one per page. You can now iterate over them:

```csharp
foreach (var stream in callback.PageStreams)
{
    // Process each page stream, e.g., upload to Azure Blob, write to a database, etc.
}
```

## Etapa 5: Implementar Callback Personalizado de Salvamento de Página

Create a sealed class that implements `IPageSavingCallback`. This class captures each page’s stream and stores it in a list for later use.

```csharp
private sealed class CustomPageSavingCallback : IPageSavingCallback
{
    public List<MemoryStream> PageStreams { get; } = new List<MemoryStream>();

    public void PageSaving(PageSavingArgs args)
    {
        var memoryStream = new MemoryStream();
        args.Stream = memoryStream;
        args.KeepStreamOpen = false;
        PageStreams.Add(memoryStream);
    }

    public void OnFinish()
    {
        // Perform any cleanup or finalization
    }
}
```

## Armadilhas Comuns & Solução de Problemas

| Problema | Motivo | Solução |
|----------|--------|----------|
| **Nenhuma página é retornada** | `RenderToSinglePage` deixado como `true`. | Defina `RenderToSinglePage = false` para gerar páginas separadas. |
| **Streams estão vazios** | `KeepStreamOpen` definido como `true` sem descarte posterior. | Mantenha como `false` (padrão) e deixe o callback fechar os streams automaticamente. |
| **Erros de falta de memória** | Projetos muito grandes geram muitas PNGs de alta resolução. | Processar os streams um a um ou aumentar os limites de memória da VM. |

## Perguntas Frequentes

**Q1: O que é um callback de salvamento de página no Aspose.Tasks?**  
A: Um callback de salvamento de página permite interceptar o processo de salvamento para cada página de um documento de várias páginas, fornecendo um `Stream` personalizado para essa página.

**Q2: Posso usar formatos diferentes para salvar páginas usando esse callback?**  
A: Sim. Alterando `SaveFileFormat` você pode exportar para PNG, JPEG, PDF, SVG, etc.

**Q3: O Aspose.Tasks é compatível com .NET Core?**  
A: Absolutamente. O Aspose.Tasks oferece suporte ao .NET Core, .NET 5 e .NET 6.

**Q4: Como posso lidar com erros durante o processo de salvamento de página?**  
A: Envolva a lógica do callback em blocos try/catch e registre as exceções. O método `OnFinish` é um bom local para a limpeza final.

**Q5: Onde posso encontrar mais recursos e suporte para Aspose.Tasks?**  
A: Você pode visitar o [forum Aspose.Tasks](https://forum.aspose.com/c/tasks/15) para assistência, acessar a documentação [aqui](https://reference.aspose.com/tasks/net/), ou explorar recursos adicionais e opções de licenciamento no [site Aspose.Tasks](https://purchase.aspose.com/buy).

---

**Last Updated:** 2026-03-16  
**Tested With:** Aspose.Tasks 24.12 for .NET  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}