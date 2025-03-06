---
title: Trabalhando com operação NOT em Aspose.Tasks
linktitle: Trabalhando com operação NOT em Aspose.Tasks
second_title: API Aspose.Tasks .NET
description: Aprenda como usar a operação NOT em Aspose.Tasks for .NET para filtrar tarefas de forma eficaz. Aprimore seus recursos de gerenciamento de projetos agora.
type: docs
weight: 20
url: /pt/net/advanced-concepts/not-operation/
---
## Introdução

Neste tutorial, exploraremos como utilizar a operação NOT em Aspose.Tasks for .NET. A operação NOT nos permite reverter uma condição de filtro, permitindo-nos selecionar elementos que não atendem a um critério especificado.

## Pré-requisitos

Antes de começarmos, certifique-se de ter o seguinte:

1. Visual Studio: você precisa de uma instalação funcional do Visual Studio para acompanhar os exemplos de código.
2.  Aspose.Tasks for .NET: Baixe e instale a biblioteca Aspose.Tasks for .NET do[local na rede Internet](https://releases.aspose.com/tasks/net/).
3. Compreensão básica de C#: A familiaridade com a linguagem de programação C# será útil para compreender os exemplos de código.

## Importar namespaces

Primeiro, vamos importar os namespaces necessários para o nosso código:

```csharp
using Aspose.Tasks;
using Aspose.Tasks.Util;
using Aspose.Tasks.Saving;
using Aspose.Tasks.Visualization;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## Etapa 1: configurar projeto e tarefas

```csharp
var project = new Project(DataDir + "Project2.mpp");
```

 Começamos carregando um arquivo de projeto chamado "Project2.mpp" usando o`Project` classe fornecida por Aspose.Tasks. Certifique-se de que o arquivo do projeto exista no diretório especificado.

## Etapa 2: coletar tarefas do projeto

```csharp
var coll = new ChildTasksCollector();
TaskUtils.Apply(project.RootTask, coll, 0);
```

 Aqui, criamos um`ChildTasksCollector` objeto para reunir todas as tarefas dentro do projeto. Usamos então`TaskUtils.Apply` método para percorrer a hierarquia de tarefas do projeto e coletar todas as tarefas filho.

## Etapa 3: definir a condição do filtro

```csharp
var filter = new NullCondition();
```

 Definimos uma condição de filtro usando uma classe personalizada chamada`NullCondition`. Esta condição seleciona tarefas que possuem um valor nulo.

## Etapa 4: Aplicar operação NOT

```csharp
var condition = new Not<Task>(filter);
```

 Aplicamos a operação NOT à condição de filtro usando o`Not<T>`classe fornecida por Aspose.Tasks. Isso reverterá a condição do filtro, selecionando tarefas que não possuem valor nulo.

## Etapa 5: Filtrar tarefas

```csharp
List<Task> collection = Filter(coll.Tasks, condition);
```

 Filtramos as tarefas coletadas com base na condição aplicada usando um método personalizado`Filter` método. Este método usa uma coleção enumerável de tarefas e uma condição de filtro como parâmetros de entrada e retorna uma lista de tarefas que satisfazem a condição.

## Etapa 6: processar tarefas filtradas

```csharp
foreach (var task in collection)
{
    Console.WriteLine("Name: " + task.Get(Tsk.Name));

    // Trabalhe com outras propriedades...
}
```

Por fim, iteramos pelas tarefas filtradas e executamos as operações desejadas. Neste exemplo, simplesmente imprimimos os nomes das tarefas no console.

## Conclusão

Neste tutorial, aprendemos como trabalhar com a operação NOT no Aspose.Tasks for .NET. Ao reverter as condições do filtro, podemos escolher seletivamente elementos que não atendem aos critérios especificados, aumentando nossa flexibilidade na manipulação de tarefas dentro dos projetos.

## Perguntas frequentes

### Q1: Posso usar Aspose.Tasks com outras estruturas .NET?

R: Sim, Aspose.Tasks oferece suporte a vários frameworks .NET, incluindo .NET Core, .NET Standard e .NET Framework.

### Q2: Existe uma avaliação gratuita disponível para Aspose.Tasks?

 R: Sim, você pode baixar uma versão de avaliação gratuita no site[local na rede Internet](https://releases.aspose.com/).

### Q3: Como posso obter suporte para Aspose.Tasks?

 R: Você pode visitar o[Fórum Aspose.Tasks](https://forum.aspose.com/c/tasks/15) para qualquer dúvida de suporte ou assistência técnica.

### Q4: Posso comprar uma licença temporária para Aspose.Tasks?

 R: Sim, você pode adquirir uma licença temporária do[página de compra](https://purchase.aspose.com/temporary-license/).

### Q5: Onde posso encontrar documentação abrangente para Aspose.Tasks?

 R: Você pode acessar a documentação completa no site[Página de documentação do Aspose.Tasks](https://reference.aspose.com/tasks/net/).