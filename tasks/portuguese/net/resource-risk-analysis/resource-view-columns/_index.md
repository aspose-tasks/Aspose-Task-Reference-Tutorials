---
title: Personalize colunas de visualização de recursos do MS Project em Aspose.Tasks
linktitle: Personalizando colunas de visualização de recursos em Aspose.Tasks
second_title: API Aspose.Tasks .NET
description: Aprenda como personalizar colunas de visualização de recursos do MS Project de forma eficiente usando Aspose.Tasks for .NET. Crie visualizações personalizadas para melhor gerenciamento de projetos.
type: docs
weight: 17
url: /pt/net/resource-risk-analysis/resource-view-columns/
---
## Introdução
Aspose.Tasks for .NET é uma API poderosa que permite aos desenvolvedores trabalhar com arquivos do Microsoft Project programaticamente. Uma tarefa comum no gerenciamento de projetos é personalizar visualizações para exibir informações específicas. Neste tutorial, exploraremos como personalizar colunas de visualização de recursos do MS Project usando Aspose.Tasks for .NET.
## Pré-requisitos
Antes de começarmos, certifique-se de ter o seguinte:
1.  Biblioteca Aspose.Tasks for .NET: você pode baixá-lo em[aqui](https://releases.aspose.com/tasks/net/).
2. Arquivo do Microsoft Project: Tenha um arquivo de amostra do MS Project à mão para teste.
3. Ambiente de Desenvolvimento: Um ambiente de desenvolvimento configurado com o framework .NET.
## Importar namespaces
Primeiro, vamos importar os namespaces necessários para o nosso projeto:
```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;
using System.Globalization;

using Aspose.Tasks.Saving;
using Aspose.Tasks.Visualization;
```
## Etapa 1: carregar o arquivo do projeto
Carregue o arquivo MS Project usando a API Aspose.Tasks:
```csharp
var project = new Project("Your_Project_File_Path.mpp");
```
## Etapa 2: obter recursos e definir opções
Em seguida, obtenha o recurso cujas colunas de visualização você deseja personalizar e defina as opções de salvamento do PDF:
```csharp
var resource = project.Resources.GetById(1);
var options = new PdfSaveOptions();
```
## Etapa 3: definir colunas personalizadas
Agora, defina colunas personalizadas para a visualização de recursos. Você pode especificar vários campos e até usar delegados para cálculos personalizados:
```csharp
var columns = new List<ViewColumn>
{
    new ResourceViewColumn(100, Field.ResourceName),
    new ResourceViewColumn(100, Field.ResourceActualWork),
    new ResourceViewColumn(100, Field.ResourceCost),
    new ResourceViewColumn(
        "Resource Cost2", 
        80,
        delegate(Resource res)
        {
            return res.Get(Rsc.Cost).ToString(CultureInfo.InvariantCulture);
        }),
    new ResourceViewColumn(
        "Resource Cost2", 
        80,
        delegate(Resource res)
        {
            return res.Get(Rsc.Cost).ToString(CultureInfo.InvariantCulture);
        }, 
        Field.ResourceCost2)
};
```
## Etapa 4: iterar nas colunas
Itere sobre as colunas definidas e exiba suas propriedades:
```csharp
foreach (var column in columns)
{
    var col = (ResourceViewColumn)column;
    Console.WriteLine("Column Name: " + col.Name);
    Console.WriteLine("Column Field: " + col.Field);
    Console.WriteLine("Column Text: " + col.GetColumnText(resource));
    Console.WriteLine();
}
```
## Etapa 5: salve a visualização personalizada
Por fim, defina a visualização personalizada e salve-a como um arquivo PDF:
```csharp
options.View = new ProjectView(columns);
options.PresentationFormat = PresentationFormat.ResourceUsage;
project.Save("Output_PDF_File_Path.pdf", options);
```
Seguindo essas etapas, você pode personalizar com eficiência as colunas de visualização de recursos do MS Project usando Aspose.Tasks for .NET.
## Conclusão
A personalização das colunas de visualização de recursos do MS Project é essencial para exibir informações relevantes adaptadas às necessidades do seu projeto. Com Aspose.Tasks for .NET, essa tarefa se torna simples e eficiente, permitindo criar visualizações personalizadas sem esforço.
## Perguntas frequentes
### Posso personalizar visualizações para outros elementos além dos recursos?
Sim, Aspose.Tasks permite a personalização de tarefas, atribuições e também outros elementos do projeto.
### O Aspose.Tasks oferece suporte para salvar visualizações em formatos diferentes de PDF?
Sim, você pode salvar visualizações em vários formatos, como XLSX, HTML e imagens.
### É possível aplicar formatação à visualização personalizada?
Com certeza, Aspose.Tasks oferece amplas opções de formatação para aprimorar a aparência de suas visualizações personalizadas.
### Posso atualizar dinamicamente a visualização personalizada com base na alteração dos dados do projeto?
Sim, você pode atualizar e gerar novamente a visualização personalizada sempre que os dados subjacentes do projeto forem alterados.
### O Aspose.Tasks oferece suporte ao desenvolvimento multiplataforma?
Aspose.Tasks for .NET tem como alvo principal plataformas .NET, mas também existem versões disponíveis para Java e outras plataformas.