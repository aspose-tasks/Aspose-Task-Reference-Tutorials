---
title: Gerenciar valores de contorno do MS Project com Aspose.Tasks
linktitle: Coleção de valores de contorno em Aspose.Tasks
second_title: API Aspose.Tasks .NET
description: Aprenda como gerenciar valores de estrutura de tópicos em arquivos do Microsoft Project usando Aspose.Tasks for .NET. Tutorial passo a passo com exemplos de código.
type: docs
weight: 17
url: /pt/net/outline-code-page-settings/outline-value-collection/
---
## Introdução
Aspose.Tasks for .NET fornece um conjunto abrangente de recursos para interagir com arquivos do Microsoft Project. Um desses recursos é a capacidade de gerenciar valores de contorno dentro de um projeto. Neste tutorial, exploraremos como coletar e manipular valores de contorno usando Aspose.Tasks for .NET.
## Pré-requisitos
Antes de começarmos, certifique-se de ter o seguinte:
1.  Aspose.Tasks for .NET: Você pode baixar a biblioteca em[aqui](https://releases.aspose.com/tasks/net/).
2. Ambiente de desenvolvimento: certifique-se de ter um IDE adequado instalado, como o Visual Studio.
3. Conhecimento básico de C#: Familiaridade com a linguagem de programação C# será benéfica.
## Importar namespaces
Em seu arquivo de código C#, importe os namespaces necessários para acessar classes e métodos Aspose.Tasks:
```csharp
using Aspose.Tasks;
using System;

```
Vamos dividir o exemplo fornecido em várias etapas:
## Etapa 1: carregar um arquivo de projeto
 Primeiro, inicialize um`Project` objeto carregando um arquivo existente do Microsoft Project:
```csharp
string DataDir = "Your Document Directory";
var project = new Project(DataDir + "OutlineValues2010.mpp");
```
## Etapa 2: limpar valores de contorno existentes
Em seguida, limpe todos os valores de contorno existentes no projeto:
```csharp
foreach (var outlineCode in project.OutlineCodes)
{
    if (outlineCode.Values.Count <= 0)
    {
        continue;
    }
    if (!outlineCode.Values.IsReadOnly)
    {
        outlineCode.Values.Clear();
    }
}
```
## Etapa 3: definir o novo código de estrutura de tópicos
Agora, defina um novo código de estrutura com uma descrição e um valor:
```csharp
var codeDefinition = new OutlineCodeDefinition
{
    Alias = "New task outline code1",
    FieldId = ((int)ExtendedAttributeTask.OutlineCode1).ToString(),
    FieldName = "Outline Code1"
};
var value = new OutlineValue { Description = "Value description", ValueId = 1, Value = "123456", Type = OutlineValueType.Number };
codeDefinition.Values.Add(value);
project.OutlineCodes.Add(codeDefinition);
```
## Etapa 4: atualizar o valor do esboço
Atualize o valor do código de estrutura de tópicos:
```csharp
codeDefinition.Values[0].Value = "654321";
```
## Etapa 5: Iterar sobre valores de contorno
Itere pelos valores do contorno e imprima seus detalhes:
```csharp
foreach (var definitionValue in codeDefinition.Values)
{
    Console.WriteLine("Value: " + definitionValue.Value);
    Console.WriteLine("Value Id: " + definitionValue.ValueId);
    Console.WriteLine("Value Guid: " + definitionValue.ValueGuid);
    Console.WriteLine();
}
```
## Etapa 6: manipular valores de contorno
Execute operações como remover, inserir e copiar valores de contorno conforme necessário:
```csharp
if (codeDefinition.Values.Contains(value))
{
    codeDefinition.Values.Remove(value);
}
codeDefinition.Values.Insert(0, value);
Console.WriteLine("Index of inserted value: " + codeDefinition.Values.IndexOf(value));
codeDefinition.Values.RemoveAt(codeDefinition.Values.Count - 1);
var codeDefinition2 = new OutlineCodeDefinition
{
    Alias = "New outline code 2",
    FieldId = ((int)ExtendedAttributeTask.OutlineCode2).ToString(),
    FieldName = "Outline Code2"
};
var outlineValues = new OutlineValue[codeDefinition.Values.Count];
codeDefinition.Values.CopyTo(outlineValues, 0);
foreach (var outlineValue in outlineValues)
{
    codeDefinition2.Values.Add(outlineValue);
}
```
## Conclusão
Neste tutorial, aprendemos como trabalhar com valores de estrutura de tópicos em arquivos do Microsoft Project usando Aspose.Tasks for .NET. Seguindo as etapas fornecidas, você pode gerenciar com eficiência os valores de contorno em seus projetos, permitindo maior controle e flexibilidade.
## Perguntas frequentes
### P: Posso manipular vários códigos de contorno simultaneamente?
R: Sim, você pode definir e manipular vários códigos de estrutura de tópicos em um projeto usando Aspose.Tasks.
### P: O Aspose.Tasks é compatível com diferentes versões de arquivos do Microsoft Project?
R: Sim, Aspose.Tasks oferece suporte a várias versões de arquivos do Microsoft Project, incluindo formatos MPP e XML.
### P: Como posso lidar com erros ao trabalhar com valores de estrutura de tópicos?
R: Você pode implementar mecanismos de tratamento de erros, como blocos try-catch, para gerenciar exceções normalmente.
### P: Posso personalizar a aparência dos valores de contorno no meu projeto?
R: Sim, Aspose.Tasks fornece APIs abrangentes para personalizar a aparência e o comportamento dos valores de contorno de acordo com seus requisitos.
### P: Onde posso encontrar recursos adicionais e suporte para Aspose.Tasks?
 R: Você pode visitar o[Fórum Aspose.Tasks](https://forum.aspose.com/c/tasks/15) para apoio da comunidade e explorar o[documentação](https://reference.aspose.com/tasks/net/) para obter informações detalhadas sobre APIs e recursos.