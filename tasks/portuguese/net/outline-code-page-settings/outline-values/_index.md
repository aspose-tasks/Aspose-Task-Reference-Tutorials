---
title: Dominando os valores do MS Project Outline com Aspose.Tasks
linktitle: Gerenciando valores de contorno em Aspose.Tasks
second_title: API Aspose.Tasks .NET
description: Aprenda como gerenciar valores de contorno do MS Project com eficiência usando Aspose.Tasks for .NET. Personalize os contornos do projeto com facilidade.
weight: 16
url: /pt/net/outline-code-page-settings/outline-values/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Dominando os valores do MS Project Outline com Aspose.Tasks

## Introdução
Neste tutorial, exploraremos como gerenciar valores de estrutura de tópicos do Microsoft Project usando a biblioteca Aspose.Tasks para .NET. Com Aspose.Tasks, você pode manipular facilmente códigos de estrutura de tópicos, criar novos valores de estrutura de tópicos e personalizar contornos de projetos de acordo com seus requisitos.
## Pré-requisitos
Antes de começar, certifique-se de ter o seguinte:
1.  Instalação do Aspose.Tasks for .NET: Baixe e instale a biblioteca Aspose.Tasks for .NET em[aqui](https://releases.aspose.com/tasks/net/).
2. Ambiente de desenvolvimento: certifique-se de ter um ambiente de desenvolvimento configurado, como o Visual Studio, com compatibilidade com o .NET framework.
3. Compreensão básica da programação C#: Familiarize-se com os fundamentos da linguagem de programação C#, pois usaremos C# para trabalhar com a biblioteca Aspose.Tasks.

## Importar namespaces
Comece importando os namespaces necessários para seu código C#:
```csharp
    using Aspose.Tasks;
    using System;
    
```
## Etapa 1: carregar o arquivo do projeto
```csharp
// O caminho para o diretório de documentos.
string DataDir = "Your Document Directory";
var project = new Project(DataDir + "OutlineValues2010.mpp");
```
Esta etapa inicializa um novo objeto Project e carrega o arquivo do Microsoft Project do diretório especificado.
## Etapa 2: definir definições de código de estrutura de tópicos
```csharp
var outline = new OutlineCodeDefinition();
outline.FieldId = ExtendedAttributeTask.OutlineCode7.ToString("D");
outline.Alias = "My Outline Code";
var outline2 = new OutlineCodeDefinition();
outline2.FieldId = ExtendedAttributeTask.OutlineCode7.ToString("D");
outline2.Alias = "My Outline Code 2";
project.OutlineCodes.Add(outline);
```
Aqui, definimos dois objetos OutlineCodeDefinition e os adicionamos à coleção OutlineCodes do projeto.
## Passo 3: Definir Máscara de Contorno
```csharp
var mask = new OutlineMask();
mask.Type = MaskType.Characters;
outline.Masks.Add(mask);
```
Esta etapa configura um OutlineMask para a definição do código de estrutura de tópicos.
## Etapa 4: criar valores de contorno
```csharp
var value = new OutlineValue();
value.Value = "Text value 1";
value.ValueId = 1;
value.Type = OutlineValueType.Text;
value.Description = "Text value descr 1";
value.IsCollapsed = false;
outline.Values.Add(value);
var value2 = new OutlineValue();
value2.DurationValue = project.GetDuration(1, TimeUnitType.Hour);
value2.ValueId = 2;
outline2.Values.Add(value2);
```
Nesta etapa, criamos dois objetos OutlineValue e definimos suas propriedades como valor, ID do valor, tipo, descrição e status de recolhimento.

## Conclusão
Gerenciar valores de contorno do MS Project usando Aspose.Tasks for .NET é simples com as funcionalidades fornecidas. Seguindo as etapas descritas neste tutorial, você pode manipular com eficiência códigos e valores de estrutura de tópicos para personalizar os contornos do projeto de acordo com suas necessidades.
## Perguntas frequentes
### P: Posso usar Aspose.Tasks com outras estruturas .NET?
R: Sim, Aspose.Tasks é compatível com vários frameworks .NET, garantindo flexibilidade em seu ambiente de desenvolvimento.
### P: Existe uma versão de teste disponível para Aspose.Tasks?
 R: Sim, você pode acessar uma versão de avaliação gratuita do Aspose.Tasks em[aqui](https://releases.aspose.com/).
### P: Como posso obter suporte para Aspose.Tasks?
 R: Para suporte e assistência, você pode visitar o fórum Aspose.Tasks[aqui](https://forum.aspose.com/c/tasks/15).
### P: Posso comprar uma licença temporária para Aspose.Tasks?
R: Sim, você pode adquirir uma licença temporária para Aspose.Tasks em[aqui](https://purchase.aspose.com/temporary-license/).
### P: Onde posso encontrar documentação detalhada para Aspose.Tasks?
 R: Você pode consultar a documentação abrangente disponível[aqui](https://reference.aspose.com/tasks/net/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
