---
date: 2026-07-19
description: Aprenda a adicionar tipos de campo personalizados no Aspose.Tasks para
  .NET com código passo a passo, pré‑requisitos e perguntas frequentes.
keywords:
- how to add custom field
- add custom field to project
- define extended attribute
lastmod: 2026-07-19
linktitle: Tipos de Campo Personalizados no Aspose.Tasks
og_description: Aprenda a adicionar tipos de campo personalizados no Aspose.Tasks
  para .NET. Siga este guia passo a passo para criar, definir e usar atributos estendidos
  de forma eficiente.
og_image_alt: Guide showing how to add custom field types in Aspose.Tasks using .NET
og_title: Como adicionar tipos de campo personalizados no Aspose.Tasks para .NET
schemas:
- author: Aspose
  dateModified: '2026-07-19'
  description: Learn how to add custom field types in Aspose.Tasks for .NET with step‑by‑step
    code, prerequisites, and FAQs.
  headline: How to Add Custom Field Types in Aspose.Tasks for .NET
  type: TechArticle
- description: Learn how to add custom field types in Aspose.Tasks for .NET with step‑by‑step
    code, prerequisites, and FAQs.
  name: How to Add Custom Field Types in Aspose.Tasks for .NET
  steps:
  - name: Create Project Object
    text: '`Project` is Aspose.Tasks'' top‑level object that represents a single Project
      file in memory. Instantiating it loads the file and gives you access to tasks,
      resources, and extended attributes.'
  - name: Define Custom Field
    text: '`ExtendedAttributeDefinition` describes a new column. In this example we
      create a **Text** type custom field for tasks and give it the alias “MyText”.
      The `ExtendedAttributeTask.Text1` enum value tells Aspose.Tasks where to store
      the value.'
  - name: Add Custom Field Definition to Project
    text: The project’s `ExtendedAttributes` collection holds all custom field definitions.
      Adding the definition makes it available for every task in the project.
  type: HowTo
- questions:
  - answer: Yes, Aspose.Tasks works with .NET Framework, .NET Core, and .NET 5/6/7.
    question: Can I use Aspose.Tasks with other .NET frameworks?
  - answer: Absolutely. It supports processing of projects with **up to 10,000 tasks**
      and can run in multi‑threaded server environments.
    question: Is Aspose.Tasks suitable for enterprise‑level applications?
  - answer: Yes—Aspose.Tasks reads and writes MPP, XML, HTML, and CSV formats, covering
      **all major Microsoft Project versions**.
    question: Does Aspose.Tasks support multiple project file formats?
  - answer: Yes, you can add, update, and delete resources, as well as assign custom
      fields to them.
    question: Can I manipulate resource data using Aspose.Tasks?
  - answer: Yes, you can visit the [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15)
      to interact with other users and get support from the Aspose team.
    question: Is there a community forum for Aspose.Tasks users?
  type: FAQPage
second_title: Aspose.Tasks .NET API
tags:
- custom field
- Aspose.Tasks
- .NET project management
- extended attributes
title: Como adicionar tipos de campo personalizados no Aspose.Tasks para .NET
url: /pt/net/calendar-scheduling/custom-field-types/
weight: 23
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Como Adicionar Tipos de Campo Personalizado no Aspose.Tasks

## Introdução

Neste tutorial você descobrirá **como adicionar campo personalizado** tipos a um arquivo Microsoft Project usando Aspose.Tasks para .NET. Campos personalizados permitem armazenar informações adicionais—como pontuações de risco, códigos de departamento ou notas personalizadas—diretamente em tarefas, recursos ou no próprio projeto. Percorreremos todo o processo, desde a configuração do ambiente até a definição, adição e verificação de um campo de texto personalizado.

## Respostas Rápidas
- **O que é um campo personalizado?** Uma coluna definida pelo usuário que pode conter texto, números, datas ou marcadores em tarefas/recursos.  
- **Qual classe define um campo personalizado?** `ExtendedAttributeDefinition`.  
- **Posso adicionar um campo personalizado a um projeto existente?** Sim—carregue o projeto, crie a definição e, em seguida, adicione-a à coleção.  
- **Preciso de uma licença para Aspose.Tasks?** Uma licença é necessária para produção; um teste gratuito funciona para avaliação.  
- **Versões .NET suportadas?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.

## O que é “como adicionar campo personalizado” no Aspose.Tasks?
**Como adicionar campo personalizado** refere‑se ao processo de criar um `ExtendedAttributeDefinition` e anexá‑lo à coleção `ExtendedAttributes` de um projeto. Isso permite armazenar metadados extras que não fazem parte do esquema padrão do Project. Pode ser usado para tarefas, recursos ou o próprio projeto, permitindo capturar informações como níveis de risco, códigos de departamento ou notas personalizadas que não estão disponíveis nos campos padrão.

## Por que usar campos personalizados no gerenciamento de projetos?
Aspose.Tasks suporta **50+ built‑in extended attribute types** e permite definir **qualquer número de campos personalizados** sem impactar significativamente o tamanho do arquivo. Usando campos personalizados você pode:  
Esses campos aparecem como colunas adicionais no Microsoft Project e podem ser referenciados em fórmulas, relatórios e filtros. Eles são armazenados dentro do arquivo de projeto e viajam com ele, garantindo que quaisquer ferramentas subsequentes mantenham os dados personalizados.

## Pré-requisitos

### 1. Visual Studio Instalado
Certifique‑se de que o Visual Studio (2019 ou posterior) está instalado na sua máquina. Você pode baixá‑lo no site da Microsoft.

### 2. Aspose.Tasks para .NET
Adicione o pacote NuGet Aspose.Tasks ao seu projeto. Baixe a versão mais recente [aqui](https://releases.aspose.com/tasks/net/).

### 3. Conhecimento Básico de C#
Você deve estar confortável com a sintaxe C#, classes e a estrutura de projetos .NET.

## Importar Namespaces

O `Project`, `ExtendedAttributeDefinition` e enums relacionados vivem no namespace `Aspose.Tasks`. Importe‑o no topo do seu arquivo:

O namespace `Aspose.Tasks` fornece todos os tipos principais para manipular arquivos Microsoft Project.

```csharp

```

## Como adicionar campo personalizado a um projeto?

Carregue o projeto existente, crie uma definição de campo personalizado e adicione‑a à coleção de atributos estendidos do projeto—tudo em três etapas concisas. Esse padrão funciona para tarefas, recursos e o próprio projeto, e garante que o campo personalizado seja persistido ao salvar o arquivo.

### Etapa 1: Criar Objeto Project
`Project` é o objeto de nível superior do Aspose.Tasks que representa um único arquivo Project na memória. Instanciá‑lo carrega o arquivo e dá acesso a tarefas, recursos e atributos estendidos.

```csharp
var project = new Project(DataDir + "Project2.mpp");
```

### Etapa 2: Definir Campo Personalizado
`ExtendedAttributeDefinition` descreve uma nova coluna. Neste exemplo criamos um campo personalizado do tipo **Text** para tarefas e atribuímos o alias “MyText”. O valor do enum `ExtendedAttributeTask.Text1` indica ao Aspose.Tasks onde armazenar o valor.

```csharp
var definition = ExtendedAttributeDefinition.CreateTaskDefinition(
    CustomFieldType.Text,
    ExtendedAttributeTask.Text1,
    "MyText");
```

### Etapa 3: Adicionar Definição de Campo Personalizado ao Projeto
A coleção `ExtendedAttributes` do projeto contém todas as definições de campos personalizados. Adicionar a definição a torna disponível para cada tarefa no projeto.

```csharp
project.ExtendedAttributes.Add(definition);
```

## Problemas Comuns e Soluções
- **Campo não aparece na UI do MS Project** – Certifique‑se de definir a propriedade `Alias`; o MS Project exibe o alias como cabeçalho da coluna.  
- **Salvar gera uma exceção** – Verifique se o arquivo do projeto não está somente‑leitura e se você possui uma licença válida.  
- **Valores do campo personalizado são perdidos após recarregar** – Certifique‑se de chamar `project.Save("output.mpp")` após atribuir valores às tarefas.

## Perguntas Frequentes

**Q: Posso usar Aspose.Tasks com outras estruturas .NET?**  
A: Sim, Aspose.Tasks funciona com .NET Framework, .NET Core e .NET 5/6/7.

**Q: O Aspose.Tasks é adequado para aplicações de nível empresarial?**  
A: Absolutamente. Ele suporta o processamento de projetos com **até 10.000 tarefas** e pode ser executado em ambientes de servidor multithread.

**Q: O Aspose.Tasks suporta múltiplos formatos de arquivo de projeto?**  
A: Sim—Aspose.Tasks lê e grava formatos MPP, XML, HTML e CSV, cobrindo **todas as principais versões do Microsoft Project**.

**Q: Posso manipular dados de recursos usando Aspose.Tasks?**  
A: Sim, você pode adicionar, atualizar e excluir recursos, bem como atribuir campos personalizados a eles.

**Q: Existe um fórum da comunidade para usuários do Aspose.Tasks?**  
A: Sim, você pode visitar o [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15) para interagir com outros usuários e obter suporte da equipe Aspose.

---

**Última atualização:** 2026-07-19  
**Testado com:** Aspose.Tasks 24.12 for .NET  
**Autor:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Tutoriais Relacionados

- [Dominar Definições de Atributos Estendidos do MS Project no Aspose.Tasks](/tasks/net/tasks-project-management/extended-attribute-definition-collection/)
- [Manipular Atributos Estendidos do MS Project com Aspose.Tasks](/tasks/net/tasks-project-management/working-with-extended-attributes/)
- [Integração do Field Helper do MS Project no Aspose.Tasks](/tasks/net/tasks-project-management/field-helper/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}