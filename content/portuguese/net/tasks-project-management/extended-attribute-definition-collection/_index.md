---
title: Domine as definições de atributos estendidos do MS Project em Aspose.Tasks
linktitle: Coleção de definições de atributos estendidos em Aspose.Tasks
second_title: API Aspose.Tasks .NET
description: Aprenda como gerenciar definições de atributos estendidos no Microsoft Project usando Aspose.Tasks for .NET. Personalize e aprimore os dados do seu projeto sem esforço.
type: docs
weight: 14
url: /pt/net/tasks-project-management/extended-attribute-definition-collection/
---
## Introdução
Neste tutorial, exploraremos como trabalhar com definições de atributos estendidos no Microsoft Project usando Aspose.Tasks for .NET. Os atributos estendidos oferecem uma maneira flexível de personalizar e aprimorar os dados do projeto, permitindo que os usuários adicionem campos adicionais além dos campos padrão fornecidos por padrão. Com Aspose.Tasks, você pode gerenciar facilmente esses atributos estendidos para adaptar suas necessidades de gerenciamento de projetos.
## Pré-requisitos
Antes de continuar, certifique-se de ter os seguintes pré-requisitos instalados:
- [Estrutura .NET](https://dotnet.microsoft.com/download)
-  Biblioteca Aspose.Tasks para .NET. Você pode baixá-lo em[aqui](https://releases.aspose.com/tasks/net/).

## Importar namespaces
Primeiro, você precisa importar os namespaces necessários para acessar as classes e métodos Aspose.Tasks em seu projeto .NET. Siga esses passos:
## Etapa 1: abra seu projeto .NET
Abra seu projeto .NET em seu IDE preferido, como o Visual Studio.
## Etapa 2: adicionar o namespace Aspose.Tasks
Adicione a seguinte linha no início do seu arquivo de código para importar o namespace Aspose.Tasks:
```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;

```

Agora, vamos dividir os exemplos de código fornecidos em várias etapas para uma compreensão abrangente:
## Passo 1: Carregue o arquivo do projeto
```csharp
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "ReadTaskExtendedAttributes.mpp");
```
## Etapa 2: limpar definições de atributos estendidos existentes (opcional)
```csharp
if (!project.ExtendedAttributes.IsReadOnly)
{
    if (project.ExtendedAttributes.Count > 0)
    {
        project.ExtendedAttributes.Clear();
    }
}
```
## Etapa 3: Criar e incluir definição de atributo estendido para uma tarefa
```csharp
var taskDefinition = ExtendedAttributeDefinition.CreateTaskDefinition(CustomFieldType.Start, ExtendedAttributeTask.Start7, "Start 7");
project.ExtendedAttributes.Add(taskDefinition);
```
## Etapa 4: iterar sobre atributos estendidos da tarefa
```csharp
Console.WriteLine("Iterate over extended attributes of " + project.ExtendedAttributes.ParentProject.Get(Prj.Name) + " project: ");
foreach (var attribute in project.ExtendedAttributes)
{
    Console.WriteLine("Attribute Alias: " + attribute.Alias);
    Console.WriteLine("Attribute CfType: " + attribute.CfType);
    Console.WriteLine();
}
```
## Etapa 5: Criar e adicionar definição de atributo estendido para um recurso
```csharp
var resourceDefinition = ExtendedAttributeDefinition.CreateResourceDefinition(CustomFieldType.Cost, ExtendedAttributeResource.Cost5, "My cost");
if (!project.ExtendedAttributes.Contains(resourceDefinition))
{
    project.ExtendedAttributes.Add(resourceDefinition);
}
```
## Etapa 6: inserir uma definição de atributo estendido de recurso
```csharp
var resourceDefinition2 = ExtendedAttributeDefinition.CreateResourceDefinition(CustomFieldType.Number, ExtendedAttributeResource.Cost1, "My Cost 2");
if (project.ExtendedAttributes.IndexOf(resourceDefinition2) < 0)
{
    project.ExtendedAttributes.Insert(0, resourceDefinition2);
}
```
## Etapa 7: remover um atributo estendido por índice
```csharp
project.ExtendedAttributes.RemoveAt(0);
```

## Conclusão
Neste tutorial, cobrimos os fundamentos do trabalho com definições de atributos estendidos no Microsoft Project usando Aspose.Tasks for .NET. Seguindo essas etapas, você pode gerenciar e personalizar com eficiência atributos estendidos para atender aos seus requisitos de gerenciamento de projeto.
## Perguntas frequentes
### P: Posso modificar definições de atributos estendidos existentes?
R: Sim, você pode modificar definições de atributos estendidos existentes ou criar novas de acordo com suas necessidades.
### P: Os atributos estendidos são suportados em todas as versões do Microsoft Project?
R: Sim, os atributos estendidos são suportados na maioria das versões do Microsoft Project, incluindo as recentes.
### P: Posso usar atributos estendidos para calcular campos personalizados?
R: Com certeza, atributos estendidos podem ser usados para calcular campos personalizados com base em critérios específicos definidos por você.
### P: O Aspose.Tasks é compatível com outras estruturas .NET?
R: Aspose.Tasks é compatível com vários frameworks .NET, garantindo flexibilidade e facilidade de integração.
### P: Onde posso encontrar mais recursos e suporte para Aspose.Tasks?
 R: Você pode visitar o[Fórum Aspose.Tasks](https://forum.aspose.com/c/tasks/15) para obter suporte e explorar a documentação[aqui](https://reference.aspose.com/tasks/net/).