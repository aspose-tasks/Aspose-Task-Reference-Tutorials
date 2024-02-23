---
title: Salve arquivos do MS Project como modelos com Aspose.Tasks
linktitle: Salvar opções de modelo para Aspose.Tasks
second_title: API Aspose.Tasks .NET
description: Aprenda como salvar arquivos do Microsoft Project como modelos usando Aspose.Tasks for .NET. Personalize as configurações do modelo para simplificar o gerenciamento de projetos.
type: docs
weight: 18
url: /pt/net/saving-options/save-template-options/
---
## Introdução
Neste tutorial, percorreremos o processo de salvar um modelo usando Aspose.Tasks for .NET. Os modelos são úteis para padronizar estruturas e configurações de projetos para uso futuro. Demonstraremos como salvar um projeto como modelo, ajustando suas propriedades ao longo do caminho.
## Pré-requisitos
Antes de começarmos, certifique-se de ter os seguintes pré-requisitos:
1.  Biblioteca Aspose.Tasks for .NET: Certifique-se de ter a biblioteca Aspose.Tasks for .NET instalada. Você pode baixá-lo em[aqui](https://releases.aspose.com/tasks/net/).
2. Conhecimento de programação C#: é necessário conhecimento básico de programação C# para compreender e implementar os trechos de código fornecidos.
3. Arquivo do Microsoft Project: Tenha um arquivo do Microsoft Project (formato MPP) pronto para salvar como modelo.

## Importar namespaces
```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.Saving;
```
## Etapa 1: carregar projeto
Primeiro, precisamos carregar o arquivo do Microsoft Project (.mpp) que queremos salvar como modelo.
```csharp
// O caminho para o diretório de documentos.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "EstimatedMilestoneTasks.mpp");
```
## Etapa 2: obter informações do arquivo do projeto
Recuperar informações sobre o arquivo de projeto carregado, como seu formato.
```csharp
var projectFileInfo = Project.GetProjectFileInfo(DataDir + "EstimatedMilestoneTasks.mpp");
Console.WriteLine("Project File Format: " + projectFileInfo.ProjectFileFormat);
```
## Etapa 3: configurar opções para salvar modelo
Crie opções para salvar modelos e configure suas propriedades de acordo com suas necessidades. Essas opções permitem personalizar quais dados devem ser removidos do modelo.
```csharp
var options = new SaveTemplateOptions
{
	// Remova todos os custos fixos do modelo de projeto
	RemoveFixedCosts = true,
	// Remova todos os valores reais do modelo de projeto
	RemoveActualValues = true,
	// Remover taxas de recursos do modelo de projeto
	RemoveResourceRates = true,
	// Remova todos os valores básicos do modelo de projeto
	RemoveBaselineValues = true
};
```
## Passo 4: Salvar Projeto como Modelo
Salve o projeto como modelo com as opções especificadas.
```csharp
project.SaveAsTemplate(DataDir + "SaveProjectDataAsTemplate_out.mpt", options);
```
## Etapa 5: obter informações do arquivo de modelo
Recuperar informações sobre o arquivo de modelo salvo, como seu formato.
```csharp
var templateFileInfo = Project.GetProjectFileInfo(DataDir + "SaveProjectDataAsTemplate_out.mpt");
Console.WriteLine("Project File Format: " + templateFileInfo.ProjectFileFormat);
```
Parabéns! Você salvou com sucesso um modelo usando Aspose.Tasks for .NET, personalizando suas propriedades conforme necessário.

## Conclusão
Neste tutorial, exploramos como salvar um arquivo do Microsoft Project como modelo usando Aspose.Tasks for .NET. Os modelos são valiosos para padronizar estruturas e configurações de projetos, agilizando futuras criações de projetos.
## Perguntas frequentes
### P: Posso personalizar quais dados serão removidos do modelo?
R: Sim, você pode configurar as opções Salvar modelo para remover dados específicos, como custos fixos, valores reais, taxas de recursos e valores de linha de base.
### P: O Aspose.Tasks for .NET é compatível com todas as versões do Microsoft Project?
R: Aspose.Tasks for .NET oferece ampla compatibilidade com várias versões do Microsoft Project, garantindo integração e funcionalidade perfeitas.
### P: Posso aplicar modelos a projetos existentes?
R: Sim, você pode aplicar modelos a projetos existentes carregando o arquivo de modelo e mesclando-o com seu projeto atual conforme necessário.
### P: O Aspose.Tasks for .NET oferece suporte ao desenvolvimento de plataforma cruzada?
R: Aspose.Tasks for .NET foi projetado principalmente para aplicativos de estrutura .NET executados em plataformas Windows.
### P: O suporte técnico está disponível para Aspose.Tasks for .NET?
 R: Sim, você pode buscar assistência técnica e orientação da comunidade Aspose.Tasks.[fóruns](https://forum.aspose.com/c/tasks/15) ou entre em contato diretamente com a equipe de suporte.