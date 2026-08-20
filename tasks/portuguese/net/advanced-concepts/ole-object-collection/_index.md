---
date: 2026-03-14
description: Aprenda como extrair arquivos incorporados e carregar o arquivo de projeto
  usando Aspose.Tasks para .NET. Este tutorial mostra a extração passo a passo de
  objetos OLE.
linktitle: Collection of OLE Objects in Aspose.Tasks
second_title: Aspose.Tasks .NET API
title: Extrair arquivos incorporados de objetos OLE no Aspose.Tasks
url: /pt/net/advanced-concepts/ole-object-collection/
weight: 23
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Extrair Arquivos Incorporados de Objetos OLE em Aspose.Tasks

## Introdução

Neste tutorial você **extrairá arquivos incorporados** que são armazenados como objetos OLE dentro de um arquivo Microsoft Project usando Aspose.Tasks para .NET. Seja para extrair documentos Word vinculados, planilhas Excel ou arquivos rich‑text, os passos abaixo mostram como **carregar o arquivo de projeto**, descobrir cada entrada OLE e gravar o conteúdo binário de volta ao disco. Ao final, você estará confortável com um fluxo de trabalho completo de **c# extract ole** que pode reutilizar em suas próprias aplicações.

## Respostas Rápidas
- **O que significa “extrair arquivos incorporados”?** Significa ler a carga binária dos objetos OLE e salvá‑los como arquivos separados no disco.  
- **Qual método da API carrega o projeto?** `new Project(filePath)` do namespace Aspose.Tasks.  
- **Posso exportar objetos OLE de qualquer tipo?** Apenas formatos que o Aspose.Tasks reconheça (por exemplo, RTF, Word, Excel) são suportados.  
- **Preciso de licença para isso?** Uma avaliação gratuita funciona para testes; uma licença comercial é necessária para produção.  
- **Quais versões do .NET são suportadas?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.

## O que significa “extrair arquivos incorporados” no contexto de objetos OLE?

OLE (Object Linking and Embedding) permite que um arquivo Project contenha cópias completas de documentos externos. Extrair esses arquivos incorporados fornece acesso direto ao conteúdo original sem abrir o arquivo Project no Microsoft Project.

## Por que extrair arquivos incorporados de objetos OLE?

- **Preservar dados originais:** Mantenha um backup de cada documento anexado.  
- **Automatizar relatórios:** Extraia relatórios Word ou Excel de vários projetos em um único lote.  
- **Integrar com outros sistemas:** Alimente os arquivos extraídos em pipelines de gerenciamento de documentos ou análise de dados.  

## Pré‑requisitos

Antes de começar, certifique‑se de que você tem:

1. **Visual Studio** – qualquer versão recente (2019, 2022 ou posterior).  
2. **Aspose.Tasks for .NET** – faça o download e instale a partir de [aqui](https://releases.aspose.com/tasks/net/).  
3. **Conhecimento básico de C#** – você deve estar confortável com loops, coleções e I/O de arquivos.  

## Importar Namespaces

Para começar, importe os namespaces necessários ao seu projeto:

```csharp
using Aspose.Tasks;
using System.Collections.Generic;
using System.IO;
```

## Etapa 1: Carregar o Arquivo de Projeto

Primeiro, carregue o arquivo Project que contém os objetos OLE que você deseja extrair:

```csharp
var project = new Project(DataDir + "Embedded.mpp");
```

> **Dica:** `DataDir` deve apontar para a pasta onde seu arquivo `.mpp` está localizado. Esta etapa satisfaz o requisito de **load project file**.

## Etapa 2: Definir Extensões de Arquivo

Crie uma tabela de consulta que mapeia os identificadores `FileFormat` do OLE para os nomes de arquivo de saída desejados. Isso facilita **export ole objects** com as extensões corretas:

```csharp
IDictionary<string, string> extensions = new Dictionary<string, string>
{
    { "RTF", "_rtfFile_out.rtf" },
    { "MSWordDoc", "_wordFile_out.docx" },
    { "ExcelML12", "_excelFile_out.xlsx" }
};
```

## Etapa 3: Percorrer Objetos OLE e Extrair Arquivos Incorporados

Agora percorra cada objeto OLE no projeto, verifique se seu formato é um dos suportados e grave o conteúdo binário em um novo arquivo:

```csharp
foreach (var oleObject in project.OleObjects)
{
    if (string.IsNullOrEmpty(oleObject.FileFormat) || !extensions.ContainsKey(oleObject.FileFormat))
    {
        continue;
    }

    var path = OutDir + "EmbeddedContent_" + extensions[oleObject.FileFormat];
    using (var stream = new FileStream(path, FileMode.Create))
    {
        stream.Write(oleObject.Content, 0, oleObject.Content.Length);
    }
}
```

> **Pro dica:** `OutDir` deve ser um diretório gravável. O código acima criará arquivos como `EmbeddedContent__wordFile_out.docx`, efetivamente **extract ole objects** do projeto.

## Problemas Comuns e Soluções

| Problema | Motivo | Solução |
|----------|--------|---------|
| Nenhum arquivo é criado | `OutDir` não existe ou não tem permissão de gravação | Certifique‑se de que o diretório exista e que a aplicação tenha acesso de escrita. |
| Formato de arquivo inesperado | `FileFormat` do objeto OLE não está no dicionário | Adicione o formato ausente ao dicionário `extensions`. |
| Objetos OLE grandes causam pressão de memória | Carregamento de muitos objetos grandes de uma vez | Processar os objetos um‑por‑um como mostrado, ou transmiti‑los diretamente para o disco. |

## Perguntas Frequentes

**P: O que é um objeto OLE?**  
R: Um objeto OLE (Object Linking and Embedding) é uma tecnologia que permite incorporar ou vincular arquivos de outros aplicativos dentro de um documento.

**P: Como instalo o Aspose.Tasks para .NET?**  
R: Você pode baixar o Aspose.Tasks para .NET a partir de [aqui](https://releases.aspose.com/tasks/net/) e seguir as instruções de instalação fornecidas.

**P: Posso trabalhar com objetos OLE no Aspose.Tasks sem conhecimento prévio de C#?**  
R: Embora seja recomendável ter noções básicas de C#, o Aspose.Tasks oferece documentação abrangente e tutoriais para ajudar usuários a começar, independentemente de sua experiência em programação.

**P: Existe uma avaliação gratuita disponível para o Aspose.Tasks?**  
R: Sim, você pode obter uma avaliação gratuita do Aspose.Tasks a partir de [aqui](https://releases.aspose.com/).

**P: Onde posso encontrar suporte para o Aspose.Tasks?**  
R: Você pode buscar suporte e fazer perguntas no fórum do Aspose.Tasks [aqui](https://forum.aspose.com/c/tasks/15).

---

**Última atualização:** 2026-03-14  
**Testado com:** Aspose.Tasks 24.11 for .NET  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}