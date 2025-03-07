---
title: Salvando arquivos do MS Project em vários formatos em Aspose.Tasks
linktitle: Salvando arquivos em vários formatos em Aspose.Tasks
second_title: API Aspose.Tasks .NET
description: Aprenda como salvar arquivos do MS Project em vários formatos usando Aspose.Tasks for .NET. Etapas fáceis para gerenciamento eficiente de projetos.
weight: 17
url: /pt/net/rate-recurring-tasks/save-file-formats/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Salvando arquivos do MS Project em vários formatos em Aspose.Tasks

## Introdução
Neste tutorial, exploraremos como salvar arquivos do Microsoft Project em vários formatos usando Aspose.Tasks for .NET. Aspose.Tasks é uma API poderosa que permite aos desenvolvedores manipular e gerenciar arquivos de projeto programaticamente.
## Pré-requisitos
Antes de começarmos, certifique-se de ter o seguinte:
1.  Aspose.Tasks for .NET: Baixe e instale Aspose.Tasks for .NET em[aqui](https://releases.aspose.com/tasks/net/).
2. Ambiente de desenvolvimento: configure um ambiente de desenvolvimento .NET, como o Visual Studio.
3. Compreensão básica de C#: A familiaridade com a linguagem de programação C# será benéfica.

## Importar namespaces
Certifique-se de importar os namespaces necessários no início do seu arquivo C#:
```csharp

using Aspose.Tasks.Saving;
```
## Etapa 1: Crie um objeto de projeto
Primeiro, crie um objeto Project e carregue seu arquivo do Microsoft Project.
```csharp
// O caminho para o diretório de documentos.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "CreateProject1.mpp");
```
## Passo 2: Salvar Projeto em Formato CSV
Agora vamos salvar o projeto no formato CSV. 
```csharp
project.Save(DataDir + "SaveProjectAsCSV_out.csv", SaveFileFormat.Csv);
```
## Etapa 3: explorar outros formatos
 Aspose.Tasks suporta vários formatos para salvar arquivos de projeto, como XML, PDF, XLSX e muito mais. Você pode explorar esses formatos simplesmente alterando o`SaveFileFormat` parâmetro no`Save` método.
```csharp
project.Save(DataDir + "SaveProjectAsXML_out.xml", SaveFileFormat.XML);
project.Save(DataDir + "SaveProjectAsPDF_out.pdf", SaveFileFormat.PDF);
project.Save(DataDir + "SaveProjectAsXLSX_out.xlsx", SaveFileFormat.XLSX);
```
Seguindo essas etapas, você pode salvar facilmente arquivos do Microsoft Project em vários formatos usando Aspose.Tasks for .NET.

## Conclusão
Neste tutorial, aprendemos como salvar arquivos do MS Project em diferentes formatos usando Aspose.Tasks for .NET. Aspose.Tasks simplifica o processo de manipulação de arquivos de projeto programaticamente, oferecendo flexibilidade e eficiência aos desenvolvedores.
## Perguntas frequentes
### P: O Aspose.Tasks é compatível com todas as versões do Microsoft Project?
R: Aspose.Tasks oferece suporte aos formatos Microsoft Project 2003 XML, Microsoft Project 2007 MPP e Microsoft Project 2010 MPP.
### P: Posso experimentar o Aspose.Tasks antes de comprar?
 R: Sim, você pode baixar uma avaliação gratuita em[aqui](https://releases.aspose.com/).
### P: Como posso obter suporte para Aspose.Tasks?
R: Você pode obter suporte no fórum da comunidade Aspose.Tasks[aqui](https://forum.aspose.com/c/tasks/15).
### P: As licenças temporárias estão disponíveis para Aspose.Tasks?
 R: Sim, licenças temporárias estão disponíveis para fins de avaliação. Você pode obter um[aqui](https://purchase.aspose.com/temporary-license/).
### P: Qual é o preço do Aspose.Tasks?
 R: As informações sobre preços podem ser encontradas na página de compra do Aspose.Tasks[aqui](https://purchase.aspose.com/buy).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
