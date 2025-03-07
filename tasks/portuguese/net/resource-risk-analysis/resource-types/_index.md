---
title: Tipos de recursos em Aspose.Tasks
linktitle: Tipos de recursos em Aspose.Tasks
second_title: API Aspose.Tasks .NET
description: Aprenda como trabalhar com diferentes tipos de recursos no Aspose.Tasks for .NET, incluindo recursos de trabalho, materiais e custos, por meio de um tutorial passo a passo.
weight: 14
url: /pt/net/resource-risk-analysis/resource-types/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Tipos de recursos em Aspose.Tasks

## Introdução
Aspose.Tasks for .NET é uma biblioteca poderosa que permite aos desenvolvedores trabalhar com arquivos do Microsoft Project programaticamente. Esteja você gerenciando tarefas, recursos ou agendas, Aspose.Tasks simplifica o processo fornecendo um conjunto abrangente de APIs. Neste tutorial, nos aprofundaremos nos diferentes tipos de recursos que você pode utilizar em seus projetos usando Aspose.Tasks for .NET.
## Pré-requisitos
Antes de começarmos, certifique-se de ter o seguinte:
1. Visual Studio: Instale o Visual Studio, um poderoso ambiente de desenvolvimento integrado (IDE) para desenvolvimento .NET.
2.  Aspose.Tasks for .NET: Baixe e instale a biblioteca Aspose.Tasks for .NET em[aqui](https://releases.aspose.com/tasks/net/).
3. Conhecimento básico de C#: Familiarize-se com C#, a linguagem de programação usada para desenvolvimento .NET.

## Importar namespaces
Primeiro, vamos importar os namespaces necessários para acessar as funcionalidades do Aspose.Tasks for .NET:
```csharp
    
```

## Etapa 1: criar uma nova instância do projeto
```csharp
var project = new Project();
```
Esta linha inicializa um novo objeto Project, que serve como contêiner para todos os dados e operações relacionados ao projeto.
## Etapa 2: adicionar um recurso de trabalho
```csharp
var work = project.Resources.Add("Work resource");
work.Set(Rsc.Type, ResourceType.Work);
```
Aqui, criamos um novo recurso de trabalho denominado "Recurso de trabalho" e especificamos seu tipo como ResourceType.Work.
## Etapa 3: adicionar um recurso material
```csharp
var material = project.Resources.Add("Material resource");
material.Set(Rsc.Type, ResourceType.Material);
material.Set(Rsc.MaterialLabel, "kg");
```
Esta etapa adiciona um recurso de material denominado "Recurso de material" com seu tipo definido como ResourceType.Material. Além disso, especificamos o rótulo do material como “kg” para indicar a unidade de medida.
## Etapa 4: adicionar um recurso de custo
```csharp
var cost = project.Resources.Add("Cost resource");
cost.Set(Rsc.Type, ResourceType.Cost);
cost.Set(Rsc.Cost, 59.99m);
```
Por fim, adicionamos um recurso de custo denominado "Recurso de custo" e definimos seu tipo como ResourceType.Cost. Adicionalmente, definimos o valor do custo em 59,99, representando o valor monetário associado a este recurso.

## Conclusão
Neste tutorial, exploramos como trabalhar com diferentes tipos de recursos no Aspose.Tasks for .NET, incluindo recursos de trabalho, materiais e custos. Seguindo o guia passo a passo, você pode gerenciar com eficácia os recursos em seus projetos de maneira programática.
## Perguntas frequentes
### P: Posso usar o Aspose.Tasks for .NET com outros formatos de software de gerenciamento de projetos?
R: Sim, Aspose.Tasks suporta vários formatos, incluindo Microsoft Project (MPP), Primavera P6 e muito mais.
### P: Existe uma avaliação gratuita disponível para Aspose.Tasks for .NET?
 R: Sim, você pode acessar o teste gratuito[aqui](https://releases.aspose.com/).
### P: Como posso obter suporte técnico para Aspose.Tasks for .NET?
 R: Você pode visitar o fórum Aspose.Tasks[aqui](https://forum.aspose.com/c/tasks/15) para assistência técnica.
### P: Posso adquirir uma licença temporária do Aspose.Tasks for .NET?
 R: Sim, você pode comprar uma licença temporária[aqui](https://purchase.aspose.com/temporary-license/).
### P: O Aspose.Tasks for .NET fornece documentação para referência?
 R: Sim, você pode encontrar a documentação[aqui](https://reference.aspose.com/tasks/net/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
