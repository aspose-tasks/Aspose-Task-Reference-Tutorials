---
title: Configuração passo a passo do código WBS em Aspose.Tasks .NET
linktitle: Configurar máscaras de código WBS em Aspose.Tasks
second_title: API Aspose.Tasks .NET
description: Explore passo a passo a configuração de máscaras de código WBS em projetos .NET usando Aspose.Tasks. Aprimore os recursos de gerenciamento de projetos sem esforço.
type: docs
weight: 14
url: /pt/net/view-wbs-code-configuration/wbs-code-masks/
---
## Introdução
Aspose.Tasks for .NET é uma biblioteca poderosa que capacita os desenvolvedores a manipular com eficiência dados de gerenciamento de projetos em aplicativos .NET. Neste tutorial, exploraremos o processo de configuração de máscaras de código da estrutura analítica do trabalho (WBS) usando Aspose.Tasks.
## Pré-requisitos
Antes de mergulhar no tutorial, certifique-se de ter os seguintes pré-requisitos em vigor:
-  Aspose.Tasks for .NET Library: Baixe e instale a biblioteca de[Documentação Aspose.Tasks para .NET](https://reference.aspose.com/tasks/net/).
- Ambiente de desenvolvimento: certifique-se de ter um ambiente de desenvolvimento .NET funcional configurado.
- Diretório de documentos: Escolha um diretório em seu sistema para armazenar os arquivos do projeto.
## Importar namespaces
Em seu projeto .NET, inclua os namespaces necessários para trabalhar com Aspose.Tasks:
```csharp
    using Aspose.Tasks;
    using System;
    
    using Aspose.Tasks.Saving;
```
## Etapa 1: criar uma instância de projeto
Comece criando uma nova instância de projeto:
```csharp
String DataDir = "Your Document Directory";
var project = new Project();
```
## Etapa 2: Definir a definição do código WBS
Configure a definição do código WBS para o seu projeto:
```csharp
project.WBSCodeDefinition = new WBSCodeDefinition();
project.WBSCodeDefinition.GenerateWBSCode = true;
project.WBSCodeDefinition.VerifyUniqueness = true;
project.WBSCodeDefinition.CodePrefix = "CRS-";
```
## Etapa 3: adicionar máscaras de código WBS
Defina máscaras de código WBS e adicione-as ao projeto:
```csharp
var mask = new WBSCodeMask();
mask.Length = 2;
mask.Separator = "-";
mask.Sequence = WBSSequence.OrderedNumbers;
project.WBSCodeDefinition.CodeMaskCollection.Add(mask);
mask = new WBSCodeMask();
mask.Length = 1;
mask.Separator = "-";
mask.Sequence = WBSSequence.OrderedUppercaseLetters;
project.WBSCodeDefinition.CodeMaskCollection.Add(mask);
```
## Etapa 4: criar tarefas
Adicione tarefas ao projeto:
```csharp
var task = project.RootTask.Children.Add("Task 1");
task.Children.Add("Task 2");
```
## Etapa 5: recalcular
Recalcule o projeto para garantir que os códigos EAP sejam aplicados corretamente:
```csharp
project.Recalculate();
```
## Etapa 6: exibir informações da máscara WBS
Envie informações sobre máscaras WBS para o console:
```csharp
Console.WriteLine("Number of WBS masks: " + project.WBSCodeDefinition.CodeMaskCollection.Count);
var i = 0;
foreach (var cm in project.WBSCodeDefinition.CodeMaskCollection)
{
    Console.WriteLine("WBS Mask #{0}: Level->{1}", ++i, cm.Level);
}
```
## Passo 7: Salve o Projeto
Salve o projeto com os códigos WBS adicionados:
```csharp
project.Save(DataDir + @"AddWBSCodes_out.xml", SaveFileFormat.Xml);
```
Parabéns! Você configurou com sucesso máscaras de código WBS em seu projeto Aspose.Tasks.
## Conclusão
Neste tutorial, exploramos o processo passo a passo de configuração de máscaras de código WBS usando Aspose.Tasks for .NET. Essa poderosa biblioteca oferece aos desenvolvedores uma maneira perfeita de aprimorar os recursos de gerenciamento de projetos em seus aplicativos .NET.

## Perguntas frequentes
### Posso usar o Aspose.Tasks gratuitamente?
 Aspose.Tasks oferece um teste gratuito, que você pode baixar[aqui](https://releases.aspose.com/).
### Onde posso encontrar suporte adicional?
 visite a[Fórum Aspose.Tasks](https://forum.aspose.com/c/tasks/15)para apoio comunitário.
### Como posso obter uma licença temporária?
 Você pode obter uma licença temporária[aqui](https://purchase.aspose.com/temporary-license/).
### Existe documentação detalhada disponível?
 Sim, a documentação abrangente está disponível[aqui](https://reference.aspose.com/tasks/net/).
### Onde posso comprar o Aspose.Tasks?
 Compre Aspose.Tasks[aqui](https://purchase.aspose.com/buy).