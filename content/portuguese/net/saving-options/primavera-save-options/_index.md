---
title: Salvar opções do MS Project Primavera com Aspose.Tasks
linktitle: Opções de salvamento do Primavera para Aspose.Tasks
second_title: API Aspose.Tasks .NET
description: Descubra como salvar opções do MS Project para Primavera perfeitamente usando Aspose.Tasks for .NET. Siga nosso tutorial passo a passo.
type: docs
weight: 14
url: /pt/net/saving-options/primavera-save-options/
---
## Introdução
Aspose.Tasks for .NET é uma biblioteca poderosa que permite aos desenvolvedores trabalhar perfeitamente com arquivos do Microsoft Project em seus aplicativos .NET. Uma das principais funcionalidades que oferece é a capacidade de salvar opções do MS Project para o Primavera, um popular software de gerenciamento de projetos. Neste tutorial, vamos nos aprofundar em como fazer isso usando Aspose.Tasks.
## Pré-requisitos
Antes de começarmos, certifique-se de ter o seguinte:
- Compreensão básica do framework C# e .NET.
-  Aspose.Tasks for .NET instalado em seu ambiente de desenvolvimento. Se não, você pode baixá-lo[aqui](https://releases.aspose.com/tasks/net/).
- Um exemplo de arquivo do MS Project para experimentação.

## Importar namespaces
Primeiro, vamos importar os namespaces necessários para nosso código C#:
```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.Saving;
```
## Etapa 1: carregar o arquivo do MS Project
Comece carregando o arquivo MS Project com o qual você pretende trabalhar em seu aplicativo C#. Você pode fazer isso usando o`Project` classe fornecida por Aspose.Tasks.
```csharp
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "EstimatedMilestoneTasks.mpp");
```
## Etapa 2: Definir opções de salvamento do Primavera
Em seguida, crie opções de salvamento do Primavera e personalize-as de acordo com suas necessidades. Esta etapa envolve a especificação de parâmetros como prefixo, sufixo, incremento do ID de atividade e se os IDs de atividade devem ser renumerados.
```csharp
var options = new PrimaveraSaveOptions
{
    ActivityIdPrefix = "TEST",
    ActivityIdSuffix = 10000,
    ActivityIdIncrement = 5,
    RenumberActivityIds = true
};
```
## Etapa 3: Salvar opções do MS Project para Primavera
 Agora que você carregou o arquivo do projeto e definiu as opções de salvamento do Primavera, é hora de salvar as opções do Primavera. Use o`Save` método fornecido pelo`Project` class, passando o caminho do arquivo de saída desejado e as opções de salvamento do Primavera.
```csharp
project.Save(DataDir + "WorkWithPrimaveraSaveOptions_out.xer", options);
```

## Conclusão
Concluindo, aproveitar o Aspose.Tasks para .NET permite que os desenvolvedores manipulem perfeitamente os arquivos do MS Project, incluindo opções de salvamento para o Primavera. Seguindo as etapas descritas neste tutorial, você pode integrar essa funcionalidade com eficiência em seus aplicativos .NET.
## Perguntas frequentes
### P: Posso personalizar outros parâmetros além dos IDs de atividades ao salvar opções do MS Project para Primavera?
R: Sim, Aspose.Tasks oferece uma ampla gama de opções de personalização, incluindo alocação de recursos e agendamento de tarefas.
### P: O Aspose.Tasks oferece suporte a outros softwares de gerenciamento de projetos além do Primavera?
R: Sim, Aspose.Tasks oferece suporte a vários formatos compatíveis com ferramentas populares de gerenciamento de projetos, como Oracle Primavera, Microsoft Project Server e muito mais.
### P: O Aspose.Tasks é adequado para projetos de pequena escala e de nível empresarial?
R: Com certeza, o Aspose.Tasks foi projetado para atender às necessidades dos desenvolvedores que trabalham em projetos de todos os tamanhos, oferecendo escalabilidade e desempenho robusto.
### P: Posso experimentar o Aspose.Tasks gratuitamente antes de fazer uma compra?
 R: Sim, você pode baixar uma avaliação gratuita do Aspose.Tasks em[aqui](https://releases.aspose.com/) para explorar seus recursos e capacidades.
### P: Onde posso obter suporte se encontrar problemas ou dúvidas ao usar o Aspose.Tasks?
R: Você pode buscar ajuda da comunidade Aspose.Tasks e da equipe de suporte no site.[fórum](https://forum.aspose.com/c/tasks/15).