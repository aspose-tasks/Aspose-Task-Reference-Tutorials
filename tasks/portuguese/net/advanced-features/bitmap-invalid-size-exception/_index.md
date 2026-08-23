---
date: 2026-03-21
description: Aprenda como exportar imagens e lidar com a exceção BitmapInvalidSizeException
  ao salvar um projeto como imagem no Aspose.Tasks para .NET. Inclui etapas para salvar
  o projeto como imagem e exportar o projeto para PNG.
linktitle: Handling Invalid Size Exception for Bitmap in Aspose.Tasks
second_title: Aspose.Tasks .NET API
title: Como Exportar Imagem e Tratar Exceção de Tamanho Inválido
url: /pt/net/advanced-features/bitmap-invalid-size-exception/
weight: 22
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Como Exportar Imagem – Tratando Exceção de Tamanho Inválido para Bitmap no Aspose.Tasks

Neste tutorial você aprenderá **como exportar imagem** de um arquivo Microsoft Project usando Aspose.Tasks para .NET e, mais importante, como capturar a `BitmapInvalidSizeException` que pode ocorrer durante o processo. Exportar um projeto como imagem é uma necessidade comum para painéis de relatórios, documentação ou simplesmente compartilhar uma captura visual de um cronograma. Ao final deste guia você será capaz de **salvar projeto como imagem** de forma confiável e até **exportar projeto para PNG** sem falhas inesperadas.

## Respostas Rápidas
- **Qual exceção pode ocorrer ao exportar uma imagem?** `BitmapInvalidSizeException`  
- **Qual formato é usado no exemplo?** PNG (`SaveFileFormat.Png`)  
- **Preciso de uma licença especial?** Uma licença válida do Aspose.Tasks é necessária para uso em produção.  
- **Posso mudar a escala de tempo?** Sim – você pode definir a unidade da escala de tempo (minutos, horas, dias, etc.).  
- **O código é compatível com .NET Core?** Absolutamente – a mesma API funciona no .NET Framework e no .NET Core.

## O que é a BitmapInvalidSizeException?
`BitmapInvalidSizeException` é lançada quando as dimensões do bitmap calculadas para a imagem estão fora da faixa suportada (por exemplo, largura ou altura zero ou que excede limites internos). Isso geralmente ocorre quando a escala de tempo ou as configurações de visualização produzem uma imagem muito grande ou muito pequena.

## Por que exportar um projeto como imagem?
- **Relatórios visuais** – incorpore um diagrama de Gantt em PDFs, documentos Word ou páginas web.  
- **Compartilhamento multiplataforma** – arquivos PNG podem ser visualizados em qualquer dispositivo sem precisar do Microsoft Project.  
- **Desempenho** – imagens são leves comparadas a arquivos de projeto completos para visualizações rápidas.

## Pré-requisitos
1. Conhecimento básico de C# e desenvolvimento .NET.  
2. Aspose.Tasks para .NET instalado (pacote NuGet `Aspose.Tasks`).  
3. Um arquivo de exemplo do Microsoft Project (por exemplo, `Blank2010.mpp`).  

## Importar Namespaces
```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.Saving;
using Aspose.Tasks.Visualization;
```

## Guia Passo a Passo

### Etapa 1: Inicializar o Projeto e Escolher uma Visualização
Primeiro, crie uma instância `Project` e escolha a visualização que deseja renderizar (aqui usamos a primeira visualização de diagrama de Gantt).

```csharp
// The path to the documents directory.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "Blank2010.mpp");
GanttChartView view = (GanttChartView) project.Views.ToList()[0];
```

### Etapa 2: Configurar Opções de Salvamento de Imagem (Exportar Projeto para PNG)
Defina o formato de imagem desejado e indique ao Aspose.Tasks para usar a escala de tempo definida na visualização.

```csharp
var options = new ImageSaveOptions(SaveFileFormat.Png)
{
    Timescale = Timescale.DefinedInView
};
```

### Etapa 3: Ajustar a Unidade da Escala de Tempo (Controlar Tamanho da Imagem)
Alterar a escala de tempo influencia as dimensões do bitmap. Neste exemplo usamos **minutos** para manter o tamanho da imagem manejável.

```csharp
view.MiddleTimescaleTier.Unit = TimescaleUnit.Minutes;
view.MiddleTimescaleTier.Count = 1;
```

### Etapa 4: Tentar Salvar o Projeto como Imagem
Esta linha executa a operação real de **salvar projeto como imagem**.

```csharp
project.Save(DataDir + "SaveToStreamAndCatchException_out.mpp", options);
```

### Etapa 5: Capturar e Tratar a BitmapInvalidSizeException
Envolva a chamada de salvamento em um bloco `try / catch` para que sua aplicação possa reagir de forma elegante se o tamanho do bitmap for inválido.

```csharp
try
{
    // Attempt to save project as an image
    project.Save(DataDir + "SaveToStreamAndCatchException_out.mpp", options);
}
catch (BitmapInvalidSizeException ex)
{
    // Handle the exception – for example, log it or adjust the timescale
    Console.WriteLine(ex.Message);
}
```

## Problemas Comuns e Soluções
| Problema | Causa | Solução |
|----------|-------|----------|
| Exceção ainda lançada após ajustar a escala de tempo | A escala de tempo ainda resulta em bitmap muito grande | Reduza `view.MiddleTimescaleTier.Count` ou troque para um `TimescaleUnit` mais grosso (por exemplo, Horas). |
| Arquivo de saída está vazio | Caminho de arquivo incorreto ou permissões de gravação ausentes | Verifique se `DataDir` aponta para uma pasta gravável e se o nome do arquivo termina com `.png` caso você altere o formato. |
| Qualidade da imagem está ruim | DPI padrão pode ser baixo | Defina `options.DpiX` e `options.DpiY` para valores mais altos (por exemplo, 300). |

## Perguntas Frequentes

**Q: O que causa a BitmapInvalidSizeException no Aspose.Tasks?**  
A: Ocorre quando as dimensões calculadas do bitmap são inválidas — tipicamente porque a escala de tempo cria uma imagem muito grande ou com largura/altura zero.

**Q: Posso personalizar a escala de tempo ao exportar uma imagem?**  
A: Sim. Você pode modificar `view.MiddleTimescaleTier.Unit` e `Count` conforme suas necessidades, como mostrado no tutorial.

**Q: O Aspose.Tasks suporta outros formatos de imagem além de PNG?**  
A: Absolutamente. `SaveFileFormat` também inclui JPEG, BMP, GIF e TIFF. Basta mudar o valor do enum em `ImageSaveOptions`.

**Q: É necessária uma licença para exportar imagens em um ambiente de produção?**  
A: Sim. Embora a biblioteca funcione em modo de avaliação, uma licença comercial remove as limitações de avaliação e fornece suporte total.

**Q: Como posso melhorar a qualidade do PNG exportado?**  
A: Aumente as configurações de DPI (`options.DpiX` e `options.DpiY`) ou ajuste a escala de tempo da visualização para produzir um bitmap maior.

## Conclusão
Seguindo os passos acima, você agora sabe **como exportar imagem** de um arquivo Project, como **salvar projeto como imagem**, e como tratar elegantemente a `BitmapInvalidSizeException`. Essas técnicas tornam seus pipelines de relatório mais robustos e garantem que as exportações visuais funcionem de forma confiável em diferentes tamanhos de projeto e escalas de tempo.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Última atualização:** 2026-03-21  
**Testado com:** Aspose.Tasks 24.12 for .NET  
**Autor:** Aspose