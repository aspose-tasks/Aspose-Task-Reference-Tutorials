---
title: MS Project com opções de planilha 2003 para Aspose.Tasks
linktitle: Opções de salvamento da planilha 2003 para Aspose.Tasks
second_title: API Aspose.Tasks .NET
description: Planilha Master 2003 Salve opções do MS Project com Aspose.Tasks para .NET. Personalize e salve perfeitamente arquivos do MS Project de forma programática.
weight: 19
url: /pt/net/saving-options/spreadsheet-2003-save-options/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# MS Project com opções de planilha 2003 para Aspose.Tasks

## Introdução
Neste tutorial, nos aprofundaremos no aproveitamento do Aspose.Tasks for .NET para utilizar as opções de salvamento do MS Project da planilha 2003. Esta ferramenta poderosa permite a manipulação e personalização perfeitas de arquivos do MS Project no ambiente .NET. Vamos analisar o processo passo a passo.
## Pré-requisitos
Antes de embarcarmos neste tutorial, certifique-se de ter os seguintes pré-requisitos:
1.  Instalação do Aspose.Tasks for .NET: Baixe e instale a biblioteca Aspose.Tasks for .NET do[Link para Download](https://releases.aspose.com/tasks/net/).
2. Familiaridade com programação C#: O conhecimento básico da linguagem de programação C# é necessário para compreender os conceitos discutidos neste tutorial.

## Importar namespaces
Comece importando os namespaces necessários para seu projeto C#:
```csharp
    
    using Aspose.Tasks.Saving;
    using Aspose.Tasks.Visualization;
```
Esses namespaces fornecem acesso às funcionalidades necessárias para salvar arquivos do MS Project no formato Planilha 2003 e personalizar as opções de visualização.
## Etapa 1: carregar o projeto
Primeiramente, carregue o arquivo MS Project usando Aspose.Tasks:
```csharp
var project = new Project(DataDir + "CreateProject2.mpp");
```
 Substituir`"Your Document Directory"`com o caminho do diretório real onde o arquivo do MS Project está localizado.
## Etapa 2: definir opções para salvar
 Defina as opções de salvamento da planilha 2003 criando uma instância de`Spreadsheet2003SaveOptions`:
```csharp
var options = new Spreadsheet2003SaveOptions();
```
## Etapa 3: personalizar colunas de visualização
Personalize as colunas de visualização do gráfico de Gantt, visualização de recursos e visualização de atribuições:
```csharp
var ganttChartColumn = new GanttChartColumn("WBS", 100, delegate(Task task) { return task.Get(Tsk.WBS); });
options.View.Columns.Add(ganttChartColumn);
var resourceViewColumn = new ResourceViewColumn("Cost center", 100, delegate(Resource resource) { return resource.Get(Rsc.CostCenter); });
options.ResourceView.Columns.Add(resourceViewColumn);
var assignmentViewColumn = new AssignmentViewColumn("Notes", 200, delegate(ResourceAssignment assignment) { return assignment.Get(Asn.NotesText); });
options.AssignmentView.Columns.Add(assignmentViewColumn);
```
Essas etapas adicionam colunas personalizadas às respectivas visualizações, aprimorando os recursos de visualização e análise do arquivo MS Project.
## Etapa 4: salve o projeto
Finalmente, salve o projeto com as opções especificadas:
```csharp
project.Save(DataDir + "UsingSpreadsheet2003SaveOptions_out.xml", options);
```
Este comando salva o projeto modificado no formato Planilha 2003 e as colunas de visualização customizadas.

## Conclusão
Utilizar o Aspose.Tasks para .NET, especificamente as opções de salvamento do MS Project do Spreadsheet 2003, permite que os desenvolvedores gerenciem e personalizem com eficiência os arquivos do MS Project de forma programática. Seguindo o guia passo a passo descrito neste tutorial, você pode integrar perfeitamente esses recursos aos seus aplicativos .NET, aumentando a produtividade e a flexibilidade.

## Perguntas frequentes
### P: O Aspose.Tasks for .NET pode ser usado em aplicativos da web e de desktop?
R: Sim, o Aspose.Tasks for .NET pode ser perfeitamente integrado em aplicativos da web e de desktop, fornecendo funcionalidade consistente em todas as plataformas.
### P: Existe uma versão de teste disponível para Aspose.Tasks for .NET?
R: Sim, você pode acessar uma avaliação gratuita do Aspose.Tasks for .NET no[local na rede Internet](https://releases.aspose.com/), permitindo que você explore seus recursos antes de fazer uma compra.
### P: Há alguma limitação para personalizar colunas de visualização usando Aspose.Tasks for .NET?
R: Aspose.Tasks for .NET oferece amplas opções de personalização para visualizar colunas, com limitações mínimas. No entanto, personalizações complexas podem exigir conhecimento avançado da biblioteca.
### P: Posso procurar assistência se encontrar problemas ao usar o Aspose.Tasks for .NET?
 R: Absolutamente! Você pode encontrar suporte e recursos abrangentes no fórum Aspose.Tasks em[https://forum.aspose.com/c/tasks/15](https://forum.aspose.com/c/tasks/15), onde especialistas e membros da comunidade estão disponíveis para ajudar a resolver quaisquer dúvidas ou desafios que você possa enfrentar.
### P: Como posso obter uma licença temporária do Aspose.Tasks for .NET?
 R: Você pode adquirir uma licença temporária para Aspose.Tasks for .NET no site[página de compra](https://purchase.aspose.com/temporary-license/), permitindo avaliar todos os recursos da biblioteca.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
