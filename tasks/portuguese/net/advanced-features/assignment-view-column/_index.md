---
date: 2026-03-19
description: Aprenda a adicionar várias colunas personalizadas e formatar a largura
  das colunas personalizadas ao exportar um projeto para XML usando o Aspose.Tasks
  para .NET.
linktitle: Add Multiple Custom Columns to Assignment View in Aspose.Tasks
second_title: Aspose.Tasks .NET API
title: Adicionar várias colunas personalizadas à visualização de atribuições no Aspose.Tasks
url: /pt/net/advanced-features/assignment-view-column/
weight: 16
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Adicionar Múltiplas Colunas Personalizadas à Visualização de Atribuições no Aspose.Tasks

## Introdução

Neste tutorial você descobrirá **como adicionar múltiplas colunas personalizadas** a uma visualização de atribuição com Aspose.Tasks para .NET. Colunas personalizadas permitem expor dados extras — como notas, custos ou sinalizadores personalizados — diretamente em relatórios exportados. Ao final do guia você será capaz de formatar a largura da coluna personalizada, exportar o projeto para XML e adaptar a visualização para atender às necessidades de gerenciamento de projetos.

## Respostas Rápidas
- **O que posso alcançar?** Exibir quaisquer dados de atribuição em colunas personalizadas e controlar sua aparência.  
- **Qual formato o suporta?** Exportar o projeto para XML (ou outros formatos) usando `Spreadsheet2003SaveOptions`.  
- **Preciso de uma licença?** Sim, uma licença válida do Aspose.Tasks é necessária para uso em produção.  
- **Quais versões do .NET funcionam?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6+.  
- **Quantas colunas posso adicionar?** Ilimitado – basta criar instâncias adicionais de `AssignmentViewColumn`.

## O que são múltiplas colunas personalizadas?
Múltiplas colunas personalizadas são campos definidos pelo usuário que aparecem ao lado das colunas padrão de atribuição quando um projeto é salvo ou exportado. Elas oferecem flexibilidade para expor qualquer propriedade de um objeto `ResourceAssignment`, como notas personalizadas, códigos de custo ou valores calculados.

## Por que adicionar múltiplas colunas personalizadas à visualização de atribuições?
- **Relatórios aprimorados:** Inclua informações específicas do projeto que não são cobertas pelas colunas internas.  
- **Melhor tomada de decisão:** As partes interessadas podem ver exatamente os dados que precisam sem precisar vasculhar arquivos brutos.  
- **Formatação consistente:** Controle a largura da coluna e a conversão de texto para uma saída limpa e legível.  

## Pré‑requisitos

Antes de começar, certifique‑se de que você tem:

1. Conhecimento básico da linguagem de programação C#.  
2. Biblioteca Aspose.Tasks para .NET instalada. Caso não a tenha, você pode baixá‑la **[aqui](https://releases.aspose.com/tasks/net/)**.  
3. Um ambiente de desenvolvimento integrado (IDE) como o Visual Studio.  

## Guia Passo a Passo

### Etapa 1: Importar Namespaces
Primeiro, importe os namespaces que fornecem as classes que usaremos para trabalhar com projetos e visualizações.

```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.Saving;
using Aspose.Tasks.Visualization;
```

### Etapa 2: Carregar o Projeto
Crie uma instância de `Project` e carregue um arquivo MPP existente.

```csharp
// The path to th documents directory.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "CreateProject2.mpp");
```

### Etapa 3: Criar Opções de Salvamento de Planilha
Instancie `Spreadsheet2003SaveOptions` – este objeto permite personalizar a visualização de atribuição antes da exportação.

```csharp
var options = new Spreadsheet2003SaveOptions();
```

### Etapa 4: Definir Coluna Personalizada
Crie um `AssignmentViewColumn` para cada dado que você deseja exibir. Abaixo adicionamos uma coluna **Notes** com largura de 200 pontos.

```csharp
var column = new AssignmentViewColumn("Notes", 200, delegate(ResourceAssignment assignment) { return assignment.Get(Asn.NotesText); });
```

**Dica:** Para adicionar *múltiplas* colunas personalizadas, repita esta etapa com nomes de campo diferentes e lógica de delegate, então adicione cada instância a `options.AssignmentView.Columns`.

### Etapa 5: Adicionar Coluna Personalizada às Opções
Adicione a coluna (ou colunas) à coleção `Columns` da visualização de atribuição.

```csharp
options.AssignmentView.Columns.Add(column);
```

### Etapa 6: Iterar Através das Atribuições (Depuração Opcional)
Você pode percorrer as atribuições para verificar se o texto da coluna personalizada está sendo gerado corretamente.

```csharp
foreach (var assignment in project.ResourceAssignments)
{
    foreach (var col in options.AssignmentView.Columns)
    {
        var assnCol = (AssignmentViewColumn)col;
        Console.WriteLine("Column Field: " + assnCol.Field);
        Console.WriteLine("Column Text (converted): " + assnCol.GetColumnText(assignment));
        Console.WriteLine();
    }
}
```

### Etapa 7: Salvar o Projeto com Colunas Personalizadas
Finalmente, salve o projeto. O exemplo salva em XML, mas você pode escolher qualquer formato suportado.

```csharp
project.Save(OutDir + "UsingSpreadsheet2003SaveOptions_out.xml", options);
```

## Como exportar o projeto para XML com colunas personalizadas?
Ao chamar `project.Save` com o `Spreadsheet2003SaveOptions` configurado, o Aspose.Tasks grava os dados do projeto — incluindo todas as **múltiplas colunas personalizadas** — no arquivo XML escolhido. Isso facilita o compartilhamento de informações de projeto enriquecidas com outros sistemas ou partes interessadas.

## Formatar a largura da coluna personalizada para melhor legibilidade
O segundo parâmetro do construtor `AssignmentViewColumn` controla a largura da coluna (medida em pontos). Ajuste esse valor conforme a quantidade de texto que você espera. Por exemplo, uma largura de **300** funciona bem para notas mais longas, enquanto **100** é suficiente para sinalizadores curtos.

## Problemas Comuns e Soluções
- **O texto da coluna aparece em branco:** Certifique‑se de que o delegate retorna uma string e que a propriedade subjacente da atribuição (por exemplo, `Asn.NotesText`) está preenchida.  
- **As colunas não são visíveis no arquivo exportado:** Verifique se `options.AssignmentView.Columns` contém suas colunas personalizadas antes de chamar `Save`.  
- **A largura parece ser ignorada:** Alguns formatos de exportação têm suas próprias regras de layout; o XML respeita a largura, mas PDF/HTML podem precisar de estilo adicional.

## Perguntas Frequentes

### Q1: Posso adicionar múltiplas colunas personalizadas à visualização de atribuições?
**R:** Sim, basta criar objetos `AssignmentViewColumn` adicionais e adicioná‑los a `options.AssignmentView.Columns`.

### Q2: Existem conversores predefinidos disponíveis para campos comuns de atribuição?
**R:** Sim, o Aspose.Tasks fornece conversores embutidos para muitos campos padrão, facilitando a extração de dados sem escrever delegates personalizados.

### Q3: Posso personalizar a aparência das colunas personalizadas, como formatar texto ou aplicar estilos?
**R:** Absolutamente. Além de definir a largura, você pode modificar fonte, alinhamento e outras propriedades visuais através das opções de estilo da coluna.

### Q4: É possível remover colunas padrão da visualização de atribuições?
**R:** Você pode excluir colunas padrão removendo‑as da coleção `Columns` ou definindo sua largura como zero.

### Q5: O Aspose.Tasks suporta exportação de projetos para outros formatos além de planilhas com colunas personalizadas?
**R:** Sim, o Aspose.Tasks pode exportar para PDF, HTML, XML e muitos outros formatos mantendo as definições de colunas personalizadas.

---

**Última atualização:** 2026-03-19  
**Testado com:** Aspose.Tasks 24.12 para .NET  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}