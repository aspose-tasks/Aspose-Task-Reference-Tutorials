---
title: Gerenciando a coleta de recursos do projeto em Aspose.Tasks
linktitle: Gerenciando a coleta de recursos em Aspose.Tasks
second_title: API Aspose.Tasks .NET
description: Aprenda como gerenciar com eficiência coleções de recursos do Microsoft Project em .NET usando a API Aspose.Tasks. Aumente a produtividade e a flexibilidade.
type: docs
weight: 13
url: /pt/net/resource-risk-analysis/managing-resource-collection/
---
## Introdução
Neste tutorial, exploraremos como gerenciar com eficácia as coleções de recursos do Microsoft Project usando Aspose.Tasks for .NET. Aspose.Tasks é uma API poderosa que permite aos desenvolvedores trabalhar com arquivos do Microsoft Project de forma programática, permitindo integração e manipulação perfeitas dos dados do projeto.
## Pré-requisitos
Antes de mergulhar neste tutorial, certifique-se de ter os seguintes pré-requisitos:
1. Conhecimento de C# e .NET Framework: Este tutorial pressupõe familiaridade com a linguagem de programação C# e o .NET Framework.
2. Instalação do Aspose.Tasks for .NET: Certifique-se de ter instalado o Aspose.Tasks for .NET. Você pode baixá-lo em[aqui](https://releases.aspose.com/tasks/net/).
3. Configuração do ambiente de desenvolvimento: configure seu ambiente de desenvolvimento com o Visual Studio ou qualquer outro IDE preferido.

## Importar namespaces
Antes de começar, importe os namespaces necessários para acessar as funcionalidades do Aspose.Tasks:
```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;


```

## Etapa 1: carregar o arquivo do projeto
Primeiramente, carregue o arquivo do Microsoft Project no objeto de projeto Aspose.Tasks:
```csharp
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "SampleProject.mpp");
```
## Etapa 2: adicionar recurso vazio
A seguir, vamos adicionar um recurso vazio ao projeto:
```csharp
var resource = project.Resources.Add();
resource.Set(Rsc.Type, ResourceType.Work);
```
## Etapa 3: adicionar recurso com um nome
Agora, adicione um recurso com um nome especificado ao projeto:
```csharp
var developer = project.Resources.Add("Developer");
developer.Set(Rsc.Type, ResourceType.Work);
```
## Etapa 4: adicionar recurso antes de outro recurso
Adicione um recurso com um nome especificado antes de outro recurso com base no seu ID:
```csharp
var manager = project.Resources.Add("Manager", developer.Get(Rsc.Id));
manager.Set(Rsc.Type, ResourceType.Work);
```
## Etapa 5: Acessando recursos por ID ou UID
Você pode acessar recursos por ID ou UID:
```csharp
var devResource = project.Resources.GetById(4);
devResource.Set(Rsc.Code, "12345");
var manResource = project.Resources.GetByUid(4);
manResource.Set(Rsc.Code, "54321");
```
## Etapa 6: Imprimir informações sobre recursos
Imprima informações sobre os recursos do projeto:
```csharp
Console.WriteLine("Print the resources of " + project.Resources.ParentProject.Get(Prj.Name) + " project.");
Console.WriteLine("Count of resources: " + project.Resources.Count);
foreach (var rsc in project.Resources)
{
    Console.WriteLine("Resource Name: " + rsc.Get(Rsc.Name));
}
```
## Etapa 7: Excluindo Recursos
Exclua recursos do projeto:
```csharp
List<Resource> list = project.Resources.ToList();
foreach (var rsc in list)
{
    rsc.Delete();
}
```

## Conclusão
O gerenciamento de coleções de recursos do Microsoft Project usando Aspose.Tasks for .NET fornece aos desenvolvedores um conjunto robusto de ferramentas para lidar com eficiência com os recursos do projeto de forma programática. Seguindo as etapas descritas neste tutorial, você pode manipular recursos de maneira transparente em seus projetos, aumentando a produtividade e a flexibilidade nas tarefas de gerenciamento de projetos.
## Perguntas frequentes
### P: O Aspose.Tasks pode lidar com arquivos de projeto em grande escala?

R: Sim, o Aspose.Tasks foi projetado para lidar com arquivos de projetos de grande escala com eficiência, oferecendo alto desempenho e confiabilidade.

### P: O Aspose.Tasks é compatível com diferentes versões do Microsoft Project?

R: Aspose.Tasks oferece suporte a várias versões do Microsoft Project, garantindo compatibilidade em diferentes ambientes.

### P: Posso personalizar as propriedades dos recursos usando Aspose.Tasks?

R: Com certeza, Aspose.Tasks oferece amplos recursos para personalizar propriedades de recursos de acordo com requisitos específicos do projeto.

### P: O Aspose.Tasks oferece suporte a multithreading para operações simultâneas?

R: Sim, Aspose.Tasks oferece suporte a multithreading, permitindo operações simultâneas em dados do projeto para melhorar o desempenho.

### P: O suporte técnico está disponível para usuários do Aspose.Tasks?

 R: Sim, os usuários do Aspose.Tasks podem acessar o suporte técnico através do fórum[aqui](https://forum.aspose.com/c/tasks/15).