---
title: Gerenciar critérios de grupo do MS Project com Aspose.Tasks
linktitle: Gerenciando a coleta de critérios de grupo em Aspose.Tasks
second_title: API Aspose.Tasks .NET
description: Aprenda como gerenciar a coleção Group Criterion MS Project usando Aspose.Tasks for .NET. Guia passo a passo para desenvolvedores.
weight: 28
url: /pt/net/tasks-project-management/group-criterion-collection/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Gerenciar critérios de grupo do MS Project com Aspose.Tasks

## Introdução
Aspose.Tasks for .NET é uma API poderosa que permite aos desenvolvedores trabalhar com arquivos do Microsoft Project programaticamente. Neste tutorial, exploraremos como gerenciar a coleção de critérios de grupo no MS Project usando Aspose.Tasks.

## Pré-requisitos

Antes de começarmos, certifique-se de ter o seguinte:

1.  Aspose.Tasks para .NET: certifique-se de ter a biblioteca Aspose.Tasks instalada em seu projeto .NET. Você pode baixá-lo em[aqui](https://releases.aspose.com/tasks/net/).

2. Arquivo do Microsoft Project: Tenha um arquivo do Microsoft Project (MPP) pronto para trabalhar.

## Importar namespaces

Primeiramente, você precisa importar os namespaces necessários para o seu código C#. Esta etapa é crucial para acessar as funcionalidades disponibilizadas pelo Aspose.Tasks.

```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;


```

## Etapa 1: carregar o arquivo do projeto

 Inicialize um`Project` objeto carregando o arquivo MPP. 

```csharp
string DataDir = "Your Document Directory";
var project = new Project(DataDir + "ReadGroupDefinitionData.mpp");
```

## Etapa 2: acessar os critérios do grupo

Recupere o grupo do projeto e acesse seus critérios.

```csharp
var group = project.TaskGroups.ToList()[0];
```

## Etapa 3: Iterar sobre os critérios do grupo

Percorra cada critério do grupo e exiba suas propriedades.

```csharp
foreach (var criterion in group.GroupCriteria)
{
    Console.WriteLine("Index: " + criterion.Index);
    Console.WriteLine("Field: " + criterion.Field);
    Console.WriteLine("Group On: " + criterion.GroupOn);
    Console.WriteLine();
}
```

## Etapa 4: limpar critérios de grupo

Limpe os critérios de grupo existentes se não for somente leitura.

```csharp
group.GroupCriteria.Clear();
```

## Etapa 5: adicionar novo critério

Crie um novo critério de grupo e adicione-o ao grupo.

```csharp
var criterionToAdd = new GroupCriterion
{
    Ascending = true,
    Field = Field.TaskActive
};

if (!group.GroupCriteria.Contains(criterionToAdd))
{
    group.GroupCriteria.Add(criterionToAdd);
}
```

## Etapa 6: copiar critérios para outro grupo

Copie os critérios de um grupo para outro.

```csharp
var otherGroup = project.TaskGroups.ToList()[0];

var criteria = new GroupCriterion[group.GroupCriteria.Count];
group.GroupCriteria.CopyTo(criteria, 0);
foreach (var criterion in criteria)
{
    otherGroup.GroupCriteria.Add(criterion);
}
```

### Conclusão

Neste tutorial, aprendemos como gerenciar a coleção Group Criterion MS Project usando Aspose.Tasks for .NET. Seguindo essas etapas, você pode manipular com eficiência os critérios de grupo nos arquivos do Microsoft Project de maneira programática.

## Perguntas frequentes

### Q1: O Aspose.Tasks é compatível com todas as versões do Microsoft Project?

R: Sim, Aspose.Tasks oferece suporte a arquivos do Microsoft Project de várias versões, incluindo 2003, 2007, 2010, 2013 e 2016.

### P2: Posso aplicar vários critérios a um único grupo?

R: Com certeza, você pode adicionar vários critérios a um grupo iterando cada um deles e adicionando-os de acordo.

### Q3: Existe uma versão de teste disponível para Aspose.Tasks?

 R: Sim, você pode obter uma avaliação gratuita do Aspose.Tasks em[aqui](https://releases.aspose.com/).

### Q4: Onde posso encontrar documentação para Aspose.Tasks?

 R: Você pode consultar a documentação[aqui](https://reference.aspose.com/tasks/net/).

### P5: Como posso obter suporte se encontrar algum problema?

 R: Se você tiver alguma dúvida ou enfrentar algum problema, pode buscar suporte no fórum Aspose.Tasks[aqui](https://forum.aspose.com/c/tasks/15).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
