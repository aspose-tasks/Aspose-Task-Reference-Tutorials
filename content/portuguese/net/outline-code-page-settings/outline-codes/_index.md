---
title: Gerenciar códigos de estrutura de tópicos do projeto em Aspose.Tasks para .NET
linktitle: Gerenciando códigos de contorno em Aspose.Tasks
second_title: API Aspose.Tasks .NET
description: Aprenda a gerenciar códigos de estrutura de tópicos do MS Project com Aspose.Tasks for .NET. Simplifique a organização do projeto sem esforço.
type: docs
weight: 10
url: /pt/net/outline-code-page-settings/outline-codes/
---
## Introdução
Neste tutorial, exploraremos como gerenciar códigos de estrutura de tópicos do Microsoft Project usando Aspose.Tasks for .NET. Os códigos de estrutura de tópicos são campos personalizados no Microsoft Project que permitem aos usuários categorizar e organizar tarefas de acordo com critérios específicos. Aspose.Tasks simplifica o processo de leitura e manipulação desses códigos de estrutura de forma programática.
## Pré-requisitos
Antes de começarmos, certifique-se de ter o seguinte:
1.  Biblioteca Aspose.Tasks for .NET: Baixe e instale a biblioteca Aspose.Tasks for .NET do[local na rede Internet](https://releases.aspose.com/tasks/net/).
2. Ambiente de Desenvolvimento: Configure um ambiente de desenvolvimento adequado para programação .NET, como Visual Studio.
3. Conhecimento básico de C#: A familiaridade com a linguagem de programação C# será benéfica para a compreensão dos exemplos de código.

## Importando Namespaces
Para começar, você precisa importar os namespaces necessários para o seu projeto C#. Isso permite acessar as classes e métodos fornecidos pela biblioteca Aspose.Tasks.
1. Abra o Visual Studio: inicie seu IDE do Visual Studio.
2. Crie um novo projeto: inicie um novo projeto C# ou abra um existente onde você pretende usar Aspose.Tasks.
3. Adicionar referência Aspose.Tasks: Clique com o botão direito em seu projeto no Solution Explorer, selecione "Gerenciar pacotes NuGet", pesquise "Aspose.Tasks" e instale a versão mais recente.
4. Importe o namespace Aspose.Tasks: na parte superior do seu arquivo C#, adicione o seguinte usando a diretiva:
```csharp
using Aspose.Tasks;
using System;

```
## Etapa 1: definir o diretório de documentos
Primeiro, defina o caminho para o diretório que contém o arquivo do MS Project.
```csharp
String DataDir = "Your Document Directory";
```
 Substituir`"Your Document Directory"` com o caminho real para o arquivo do seu projeto.
## Etapa 2: carregar o arquivo do projeto
 Instanciar um novo`Project` objeto carregando o arquivo MS Project.
```csharp
var project = new Project(DataDir + "OutlineValues2010.mpp");
```
Isso inicializa o objeto do projeto com o arquivo especificado.
## Etapa 3: leia os códigos de estrutura de tópicos
Itere todas as tarefas do projeto e recupere seus códigos de estrutura de tópicos.
```csharp
foreach (var task in project.RootTask.SelectAllChildTasks())
{
    if (task.OutlineCodes.Count <= 0)
    {
        continue;
    }
    Console.WriteLine("Print outline codes of the task: " + task.Get(Tsk.Name));
    foreach (var value in task.OutlineCodes)
    {
        Console.WriteLine("  Field Id: " + value.FieldId);
        Console.WriteLine("  Value Guid: " + value.ValueGuid);
        Console.WriteLine("  Value Id: " + value.ValueId);
    }
}
```
Este trecho de código percorre cada tarefa, verifica se ela possui códigos de estrutura e imprime detalhes como ID de campo, Guia de valor e ID de valor para cada código de estrutura associado à tarefa.

## Conclusão
Concluindo, Aspose.Tasks for .NET fornece recursos poderosos para gerenciar códigos de estrutura de tópicos do Microsoft Project programaticamente. Seguindo as etapas descritas neste tutorial, você pode ler e manipular códigos de estrutura de forma eficiente em seus arquivos do MS Project usando C#.
## Perguntas frequentes
### P: Posso modificar códigos de estrutura de tópicos usando Aspose.Tasks?
R: Sim, você pode modificar códigos de estrutura de forma programática usando Aspose.Tasks for .NET. Basta acessar os códigos gerais das tarefas e atualizar seus valores conforme necessário.
### P: O Aspose.Tasks é compatível com todas as versões do Microsoft Project?
R: Aspose.Tasks oferece suporte a uma ampla variedade de versões do Microsoft Project, incluindo 2003, 2007, 2010, 2013, 2016 e 2019.
### P: O Aspose.Tasks requer uma licença para uso comercial?
R: Sim, é necessária uma licença válida para uso comercial do Aspose.Tasks. Você pode obter uma licença no site Aspose.
### P: Posso experimentar o Aspose.Tasks antes de comprar?
R: Sim, você pode baixar uma versão de avaliação gratuita do Aspose.Tasks do site para avaliar seus recursos e capacidades.
### P: Onde posso obter suporte para Aspose.Tasks?
 R: Você pode obter suporte para Aspose.Tasks visitando o fórum em[Fórum Aspose.Tasks](https://forum.aspose.com/c/tasks/15).## Código fonte completo