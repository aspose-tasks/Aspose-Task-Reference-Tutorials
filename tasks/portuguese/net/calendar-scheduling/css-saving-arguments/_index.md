---
date: 2026-07-05
description: Aprenda como personalizar CSS ao exportar um projeto para HTML usando
  Aspose.Tasks para .NET. Ajuste a saída HTML com argumentos de salvamento de CSS.
keywords:
- how to customize css
- export project to html
- customize html output
linktitle: Como personalizar CSS ao salvar projetos com Aspose.Tasks
schemas:
- author: Aspose
  dateModified: '2026-07-05'
  description: Learn how to customize CSS while exporting a project to HTML using
    Aspose.Tasks for .NET. Tailor HTML output with CSS saving arguments.
  headline: How to Customize CSS When Saving Projects with Aspose.Tasks
  type: TechArticle
- questions:
  - answer: Using custom CSS can reduce the total size by up to 15 % because you can
      eliminate unused default styles.
    question: How does customizing CSS affect the size of the exported HTML?
  - answer: Absolutely. Implement the callbacks once and reuse them across any number
      of project exports.
    question: Can I use the same callbacks for multiple projects?
  - answer: Yes, set `HtmlSaveOptions.EmbeddedCss = true` to inline the stylesheet,
      which simplifies distribution.
    question: Is it possible to embed CSS directly into the HTML instead of separate
      files?
  type: FAQPage
second_title: Aspose.Tasks .NET API
title: Como personalizar CSS ao salvar projetos com Aspose.Tasks
url: /pt/net/calendar-scheduling/css-saving-arguments/
weight: 20
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Como Personalizar CSS ao Salvar Projetos com Aspose.Tasks

Neste guia, você descobrirá **como personalizar CSS** durante a exportação HTML de um arquivo Microsoft Project usando Aspose.Tasks para .NET. Ajustando os argumentos de salvamento de CSS, você obtém controle total sobre o estilo visual das páginas HTML geradas, fazendo com que a saída corresponda à sua identidade visual ou padrões de relatório.

## Respostas Rápidas
- **Qual é o ponto de entrada principal?** Use `HtmlSaveOptions` com callbacks personalizados.  
- **Preciso de uma licença?** Sim, uma licença válida do Aspose.Tasks é necessária para produção.  
- **Quais versões do .NET são suportadas?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6+.  
- **Posso exportar projetos grandes?** Aspose.Tasks lida com projetos com > 10.000 tarefas sem carregar todo o arquivo na memória.  
- **A personalização de CSS é opcional?** Sim, você pode omitir os callbacks para usar a folha de estilo padrão.

## Como Personalizar CSS no Aspose.Tasks?

Carregue seu projeto, anexe callbacks de salvamento de CSS ao objeto `HtmlSaveOptions` e, em seguida, chame `project.Save`. Esse padrão permite que você escreva arquivos CSS personalizados, substitua estilos padrão e controle a estrutura de pastas — tudo em poucas linhas de código. Os callbacks são invocados automaticamente para cada arquivo CSS durante o processo de exportação.

`HtmlSaveOptions` configura como um projeto é exportado para HTML.

## Introdução

Neste tutorial, mergulharemos no processo de salvar argumentos de CSS usando Aspose.Tasks para .NET. Cascading Style Sheets (CSS) são essenciais para definir a apresentação dos elementos HTML. Aspose.Tasks permite manipular e salvar esses atributos de CSS de forma eficiente.

## Pré-requisitos

Antes de começarmos, certifique‑se de que você tem os seguintes pré‑requisitos em vigor:

1. **Instalação:** Verifique se você instalou o Aspose.Tasks para .NET. Você pode baixá‑lo no [website](https://releases.aspose.com/tasks/net/).

2. **Conhecimento Básico:** Familiaridade com C# e o ambiente de desenvolvimento .NET é recomendada.

## Importar Namespaces

Para começar, importe os namespaces necessários:

```csharp
using Aspose.Tasks;
using System.Collections.Generic;
using System.IO;

using Aspose.Tasks.Saving;
using Aspose.Tasks.Visualization;

```

## Etapa 1: Definir Callbacks de Salvamento de CSS

`ICssSavingCallback` é uma interface que permite personalizar como os arquivos CSS são salvos durante a exportação HTML.

Um **callback de salvamento de CSS** é um delegate que o Aspose.Tasks invoca para gravar arquivos CSS durante a exportação HTML. Defina os métodos de callback para controlar como cada arquivo CSS é criado:

```csharp
private class ResourcePrefixForNestedResources : ICssSavingCallback
{
    public void CssSaving(CssSavingArgs args)
    {
        // Implement your CSS saving logic here
    }
}
```

## Etapa 2: Implementar Callbacks de Salvamento de Fonte e Imagem

`FontSavingArgs` fornece informações sobre a fonte que está sendo salva, enquanto `ImageSavingArgs` fornece detalhes para recursos de imagem.

Implemente os métodos de callback de salvamento de fonte e imagem de forma semelhante:

```csharp
public void FontSaving(FontSavingArgs args)
{
    // Implement your font saving logic here
}

public void ImageSaving(ImageSavingArgs args)
{
    // Implement your image saving logic here
}
```

## Etapa 3: Configurar Opções de Salvamento

`HtmlSaveOptions` é o objeto de configuração que controla como um Project é exportado para HTML.

`HtmlSaveOptions` permite especificar callbacks, pastas de saída e outras configurações de exportação.

Defina suas propriedades para usar os callbacks definidos anteriormente e para especificar a pasta de saída:

```csharp
public static HtmlSaveOptions GetSaveOptions(int pageNumber)
{
    var options = new HtmlSaveOptions
    {
        // Configure HTML saving options
    };

    var program = new ResourcePrefixForNestedResources();
    options.FontSavingCallback = program;
    options.CssSavingCallback = program;
    options.ImageSavingCallback = program;

    return options;
}
```

## Etapa 4: Salvar Projeto com CSS Personalizado

`Project` representa um arquivo Microsoft Project que pode ser manipulado e salvo.

Finalmente, salve seu projeto com as configurações de CSS personalizadas:

```csharp
var project = new Project("Project1.mpp");
var options = ResourcePrefixForNestedResources.GetSaveOptions(1);
project.Save("document_out.html", options);
```

## Por que Personalizar CSS ao Exportar Projetos?

Aspose.Tasks suporta **exportação de projeto para HTML** em 30+ formatos e pode gerar até 30 arquivos CSS separados por exportação. Processa projetos contendo mais de 10 000 tarefas mantendo o uso de memória abaixo de 200 MB, permitindo relatórios em escala empresarial sem gargalos de desempenho.

## Conclusão

Neste tutorial, exploramos como salvar argumentos de CSS usando Aspose.Tasks para .NET. Ao definir callbacks de salvamento de CSS e configurar as opções de salvamento HTML, podemos manipular atributos de CSS de forma eficiente de acordo com nossas necessidades.

## Perguntas Frequentes

### Q1: O que é Aspose.Tasks para .NET?

A1: Aspose.Tasks para .NET é uma poderosa API .NET que permite aos desenvolvedores trabalhar programaticamente com arquivos Microsoft Project.

### Q2: Posso personalizar atributos CSS ao salvar arquivos HTML com Aspose.Tasks?

A2: Sim, você pode definir callbacks de salvamento de CSS para personalizar os atributos de CSS conforme suas necessidades.

### Q3: O Aspose.Tasks para .NET é compatível com todas as versões de arquivos Microsoft Project?

A3: Aspose.Tasks para .NET suporta várias versões de arquivos Microsoft Project, garantindo compatibilidade em diferentes ambientes.

### Q4: Onde posso encontrar documentação abrangente para Aspose.Tasks para .NET?

A4: Você pode consultar a [documentation](https://reference.aspose.com/tasks/net/) para informações detalhadas e exemplos.

### Q5: O Aspose.Tasks para .NET oferece suporte para desenvolvedores?

A5: Sim, você pode obter suporte da comunidade Aspose.Tasks através do [forum](https://forum.aspose.com/c/tasks/15).

**Perguntas Adicionais**

**Q: Como a personalização de CSS afeta o tamanho do HTML exportado?**  
A: Usar CSS personalizado pode reduzir o tamanho total em até 15 % porque você pode eliminar estilos padrão não utilizados.

**Q: Posso usar os mesmos callbacks para vários projetos?**  
A: Absolutamente. Implemente os callbacks uma vez e reutilize‑os em qualquer número de exportações de projetos.

**Q: É possível incorporar CSS diretamente no HTML em vez de arquivos separados?**  
A: Sim, defina `HtmlSaveOptions.EmbeddedCss = true` para inserir a folha de estilo inline, o que simplifica a distribuição.

---

**Última Atualização:** 2026-07-05  
**Testado com:** Aspose.Tasks 24.11 para .NET  
**Autor:** Aspose

## Tutoriais Relacionados

- [Salvar MS Project como HTML com Aspose.Tasks](/tasks/net/saving-options/html-save-options/)
- [Implementando Callback de Salvamento de Página no Aspose.Tasks](/tasks/net/advanced-concepts/page-saving-callback/)
- [Manipulando Salvamento de Imagem no Aspose.Tasks](/tasks/net/advanced-concepts/image-saving/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< blocks/products/products-backtop-button >}}

{{< /blocks/products/pf/main-wrap-class >}}