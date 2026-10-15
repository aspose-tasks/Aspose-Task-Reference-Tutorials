---
date: 2026-10-15
description: Aprenda como adicionar custom property e gerenciar custom project properties
  no Aspose.Tasks para .NET, aprimorando o controle de metadados do seu projeto.
keywords:
- add custom property
- manage custom properties
- read custom properties
- add boolean property
- add string property
lastmod: 2026-10-15
linktitle: Gerenciando Custom Project Property Collection no Aspose.Tasks
og_description: Adicione custom property aos seus arquivos de projeto com Aspose.Tasks
  para .NET. Este guia mostra como gerenciar custom properties, lê-las e adicionar
  valores booleanos ou de string de forma eficiente.
og_image_alt: Guide showing how to add custom property in Aspose.Tasks .NET
og_title: Adicionar custom property usando a API Aspose.Tasks .NET para projetos
schemas:
- author: Aspose
  dateModified: '2026-10-15'
  description: Learn how to add custom property and manage custom project properties
    in Aspose.Tasks for .NET, boosting your project metadata control.
  headline: How to add custom property in Aspose.Tasks for .NET
  type: TechArticle
- description: Learn how to add custom property and manage custom project properties
    in Aspose.Tasks for .NET, boosting your project metadata control.
  name: How to add custom property in Aspose.Tasks for .NET
  steps:
  - name: initialize project
    text: '`Project` is the primary class representing a project file in Aspose.Tasks.'
  - name: check custom properties collection readiness
    text: '`CustomProperties` is the collection that holds all custom property objects
      for a project.'
  - name: add custom properties
    text: '`Add` method inserts a new custom property into the project''s collection.'
  - name: access custom properties
    text: '`CustomProperties` collection implements IEnumerable, allowing iteration
      over each `CustomProperty`.'
  - name: retrieve a custom property value
    text: '`Get` method returns the value of a custom property by its name.'
  - name: iterate over custom property names
    text: '`Names` property provides a list of all custom property names in the collection.'
  - name: remove or clear custom properties
    text: '`Remove` method deletes a specific property, while `Clear` empties the
      entire collection.'
  type: HowTo
- questions:
  - answer: Yes, you can add custom properties supporting Boolean, DateTime, Double,
      and String types.
    question: Can I add custom properties of any data type to my project using Aspose.Tasks
      for .NET?
  - answer: Absolutely, you can iterate over custom property names using the `Names`
      property.
    question: Is it possible to iterate over custom property names in Aspose.Tasks
      for .NET?
  - answer: You can remove a custom property by its name using the `Remove` method.
    question: How can I remove a specific custom property from my project?
  - answer: Yes, you can obtain a temporary license from the Aspose website for evaluation
      purposes.
    question: Does Aspose.Tasks for .NET provide support for temporary licenses?
  - answer: You can visit the Aspose.Tasks forum [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15)
      for any queries or assistance.
    question: Where can I find support or further assistance regarding Aspose.Tasks
      for .NET?
  type: FAQPage
second_title: Aspose.Tasks .NET API
tags:
- custom properties
- Aspose.Tasks
- .NET project management
- C# tasks API
title: Como adicionar custom property no Aspose.Tasks para .NET
url: /pt/net/calendar-scheduling/custom-project-property-collection/
weight: 24
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Como adicionar propriedade personalizada no Aspose.Tasks para .NET

## Introdução

O suporte a propriedades personalizadas permite armazenar metadados específicos do projeto que os campos incorporados não cobrem. Neste tutorial você aprenderá como **adicionar propriedade personalizada**, lê‑la de volta e gerenciar toda a coleção de propriedades personalizadas usando Aspose.Tasks para .NET. Ao final, você será capaz de adaptar arquivos de projeto com valores Boolean, DateTime, Double e String que atendam às regras de negócios.

## Respostas rápidas
- **Posso adicionar uma propriedade personalizada Boolean?** Sim – use `CustomPropertyType.Boolean`.
- **Quantos tipos de propriedades personalizadas são suportados?** Quatro: Boolean, DateTime, Double, String.
- **A coleção de propriedades personalizadas é somente leitura?** Pode ser somente leitura se o projeto for carregado de uma fonte somente leitura.
- **Preciso de uma licença para usar este recurso?** Uma licença temporária funciona para avaliação; uma licença completa é necessária para produção.
- **Quais versões do .NET são compatíveis?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.

## O que é uma propriedade personalizada?

Uma propriedade personalizada é um campo de metadados definido pelo usuário que você anexa a um objeto Project. Ela permite armazenar informações adicionais, como “Nível de Risco”, “ID do Cliente” ou qualquer sinalizador Boolean que não seja coberto pelos campos padrão do MS‑Project.

## Por que adicionar propriedade personalizada no Aspose.Tasks?

Aspose.Tasks suporta **mais de 50 formatos de entrada e saída** e pode lidar com projetos com **até 10.000 tarefas** sem carregar o arquivo inteiro na memória. Adicionar propriedades personalizadas permite incorporar dados críticos de negócios diretamente no arquivo do projeto, eliminando a necessidade de bancos de dados externos e garantindo que os dados viajem com o projeto.

## Pré-requisitos

- Visual Studio (qualquer edição recente) instalado em sua estação de trabalho.  
- Aspose.Tasks for .NET – faça o download a partir do [download link](https://releases.aspose.com/tasks/net/).  
- Familiaridade básica com a sintaxe C# e a estrutura de projetos .NET.

## Importar namespaces

Os namespaces a seguir dão acesso ao modelo central do projeto e às APIs de propriedades personalizadas.

```csharp
using Aspose.Tasks;
using System;


```

## Como adicionar propriedade personalizada no Aspose.Tasks?

Para adicionar uma propriedade personalizada, primeiro carregue o projeto, depois crie um objeto `CustomProperty`, defina seu nome, tipo e valor, e finalmente adicione‑o à coleção `CustomProperties` do projeto. Esta operação incorpora os metadados diretamente no arquivo do projeto, e as alterações são salvas quando você chama `project.Save(...)`.  

`CustomProperty` representa um único campo definido pelo usuário anexado a um projeto.

```csharp
// Direct answer: Load the project, create a CustomProperty, set its Type and Value, then add it to project.CustomProperties.
```

### Etapa 1: inicializar o projeto

`Project` é a classe principal que representa um arquivo de projeto no Aspose.Tasks.

```csharp
var project = new Project(DataDir + "ReadProjectInfo.mpp");
```

### Etapa 2: verificar a prontidão da coleção de propriedades personalizadas

`CustomProperties` é a coleção que contém todos os objetos de propriedades personalizadas de um projeto.

```csharp
Console.WriteLine("Is custom properties collection read-only?: " + project.CustomProps.IsReadOnly);
```

### Etapa 3: adicionar propriedades personalizadas

O método `Add` insere uma nova propriedade personalizada na coleção do projeto.

```csharp
project.CustomProps.Add("IsEnterprise", true);
project.CustomProps.Add("Project Start Date", new DateTime(2020, 4, 16, 8, 0, 0));
project.CustomProps.Add("Precision", 10d);
project.CustomProps.Add("Custom Name", "MyProject");
```

### Etapa 4: acessar propriedades personalizadas

A coleção `CustomProperties` implementa IEnumerable, permitindo iteração sobre cada `CustomProperty`.

```csharp
foreach (var property in project.CustomProps)
{
    Console.WriteLine(property.Type);
    Console.WriteLine(property.Name);
    Console.WriteLine(property.Value);
    Console.WriteLine();
}
```

### Etapa 5: recuperar o valor de uma propriedade personalizada

O método `Get` retorna o valor de uma propriedade personalizada pelo seu nome.

```csharp
Console.WriteLine("Custom Name: " + project.CustomProps["Custom Name"]);
```

### Etapa 6: iterar sobre os nomes das propriedades personalizadas

A propriedade `Names` fornece uma lista de todos os nomes de propriedades personalizadas na coleção.

```csharp
foreach (var propName in project.CustomProps.Names)
{
    Console.WriteLine("Name: " + propName);
    Console.WriteLine();
}
```

### Etapa 7: remover ou limpar propriedades personalizadas

O método `Remove` exclui uma propriedade específica, enquanto `Clear` esvazia toda a coleção.

```csharp
if (project.CustomProps.Contains("Custom Name"))
{
    project.CustomProps.Remove("Custom Name");
}

project.CustomProps.Clear();
```

## Problemas comuns e solução de problemas

- **Coleção somente leitura** – Se `project.CustomProperties.IsReadOnly` retornar `true`, garanta que o arquivo fonte não esteja aberto com acesso exclusivo de leitura ou copie‑o para um local gravável antes de editar.  
- **Incompatibilidade de tipo** – Atribuir um valor que não corresponde ao `CustomPropertyType` declarado lança uma `ArgumentException`. Sempre defina o `Value` após especificar o `Type` correto.  
- **Salvando alterações** – Após adicionar ou remover propriedades, chame `project.Save("output.mpp")` para persistir as modificações; caso contrário, as alterações permanecem apenas na memória.

## Perguntas frequentes

**Q: Posso adicionar propriedades personalizadas de qualquer tipo de dado ao meu projeto usando Aspose.Tasks para .NET?**  
A: Sim, você pode adicionar propriedades personalizadas que suportam os tipos Boolean, DateTime, Double e String.

**Q: É possível iterar sobre os nomes das propriedades personalizadas no Aspose.Tasks para .NET?**  
A: Absolutamente, você pode iterar sobre os nomes das propriedades personalizadas usando a propriedade `Names`.

**Q: Como posso remover uma propriedade personalizada específica do meu projeto?**  
A: Você pode remover uma propriedade personalizada pelo seu nome usando o método `Remove`.

**Q: O Aspose.Tasks para .NET oferece suporte a licenças temporárias?**  
A: Sim, você pode obter uma licença temporária no site da Aspose para fins de avaliação.

**Q: Onde posso encontrar suporte ou assistência adicional sobre o Aspose.Tasks para .NET?**  
A: Você pode visitar o fórum Aspose.Tasks [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15) para quaisquer dúvidas ou assistência.

---

**Última atualização:** 2026-10-15  
**Testado com:** Aspose.Tasks 24.11 for .NET  
**Autor:** Aspose

## Tutoriais relacionados

- [Como ler propriedades de projeto incorporadas usando Aspose.Tasks para .NET](/tasks/net/advanced-features/built-in-project-property-collection/)
- [Gerenciar coleção de atributos do MS Project no Aspose.Tasks](/tasks/net/tasks-project-management/extended-attribute-collection/)
- [Tipos de campo personalizado do Aspose.Tasks – Calendário e Agendamento](/tasks/net/calendar-scheduling/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}