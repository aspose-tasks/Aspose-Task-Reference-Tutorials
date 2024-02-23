---
title: Personalize as configurações de visualização de página do MS Project em Aspose.Tasks
linktitle: Definir configurações de visualização de página em Aspose.Tasks
second_title: API Aspose.Tasks .NET
description: Aprenda como definir as configurações de visualização de página em Aspose.Tasks for .NET para personalizar o formato de impressão de seus documentos do Microsoft Project.
type: docs
weight: 21
url: /pt/net/outline-code-page-settings/page-view-settings/
---
## Introdução
O Microsoft Project é uma ferramenta poderosa para gerenciamento de projetos, mas às vezes você precisa personalizar a forma como seu projeto é visualizado e impresso. Com Aspose.Tasks for .NET, você pode definir facilmente as configurações de visualização de página para atender aos seus requisitos específicos. Neste tutorial, guiaremos você pelo processo passo a passo.
## Pré-requisitos
Antes de começarmos, certifique-se de ter o seguinte:
1.  Aspose.Tasks for .NET: Certifique-se de ter baixado e instalado a biblioteca Aspose.Tasks for .NET. Você pode baixá-lo em[aqui](https://releases.aspose.com/tasks/net/).
2. Arquivo do Microsoft Project: tenha em mãos um arquivo do Microsoft Project para o qual deseja definir as configurações de visualização de página.

## Importar namespaces
Primeiro, você precisa importar os namespaces necessários para trabalhar com Aspose.Tasks em seu projeto .NET.
```csharp
    
    using Aspose.Tasks.Saving;
```
## Etapa 1: carregar o arquivo do projeto
 Comece carregando seu arquivo do Microsoft Project em uma instância do`Project` aula.
```csharp
// O caminho para o diretório de documentos.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "Input.mpp");
```
## Etapa 2: definir a contagem das primeiras colunas
Especifique o número das primeiras colunas a serem impressas em todas as páginas.
```csharp
project.DefaultView.PageInfo.PageViewSettings.FirstColumnsCount = 2;
```
## Etapa 3: imprimir notas
Escolha se deseja imprimir notas junto com o projeto.
```csharp
project.DefaultView.PageInfo.PageViewSettings.PrintNotes = true;
```
## Etapa 4: ajustar a escala de tempo ao final da página
Decida se deseja ajustar a escala de tempo ao final de uma página durante a impressão.
```csharp
project.DefaultView.PageInfo.PageViewSettings.FitTimescaleToEndOfPage = true;
```
## Etapa 5: imprimir todas as colunas da planilha
Especifique se deseja imprimir todas as colunas da planilha de uma visualização.
```csharp
project.DefaultView.PageInfo.PageViewSettings.PrintAllSheetColumns = true;
```
## Etapa 6: imprimir páginas em branco
Escolha se deseja imprimir páginas em branco de uma visualização.
```csharp
project.DefaultView.PageInfo.PageViewSettings.PrintBlankPages = false;
```
## Etapa 7: imprimir as primeiras colunas em todas as páginas
Defina se deseja imprimir um número especificado de primeiras colunas em todas as páginas.
```csharp
project.DefaultView.PageInfo.PageViewSettings.PrintFirstColumnsCountOnAllPages = true;
```
## Etapa 8: salve o projeto com as configurações definidas
Por fim, salve o projeto com as configurações de visualização de página definidas, especificando o formato de saída, como PDF.
```csharp
project.Save(DataDir + "ProjectWithComments_out.pdf", SaveFileFormat.Pdf);
```

## Conclusão
Definir as configurações de visualização de página do Microsoft Project em Aspose.Tasks for .NET é simples e permite adaptar o formato de impressão às suas necessidades exatas. Seguindo as etapas descritas neste tutorial, você pode garantir que os documentos do seu projeto sejam apresentados exatamente conforme necessário.
## Perguntas frequentes
### P: Posso definir as configurações de visualização de página para outros formatos de arquivo além de PDF?
R: Sim, Aspose.Tasks oferece suporte a vários formatos de arquivo para salvar projetos, incluindo XLSX, MPP e HTML.
### P: Há alguma limitação quanto ao número de colunas que posso imprimir?
R: Aspose.Tasks permite que você personalize o número de colunas a serem impressas com base em seus requisitos.
### P: Posso aplicar configurações de visualização de página diferentes para projetos diferentes?
R: Sim, você pode ajustar as configurações de visualização de página de forma independente para cada arquivo de projeto com o qual trabalha.
### P: O Aspose.Tasks é compatível com todas as versões do Microsoft Project?
R: Aspose.Tasks oferece compatibilidade com o Microsoft Project 2003 e versões posteriores.
### P: Onde posso encontrar mais assistência ou suporte para Aspose.Tasks?
 R: Você pode visitar o[Fórum Aspose.Tasks](https://forum.aspose.com/c/tasks/15)para quaisquer dúvidas ou problemas que você encontrar durante o uso.