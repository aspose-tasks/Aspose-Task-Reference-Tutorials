---
title: Configurar opções do MS Project XLSX em Aspose.Tasks para .NET
linktitle: Configurando opções XLSX em Aspose.Tasks
second_title: API Aspose.Tasks .NET
description: Aprenda como configurar as opções do MS Project XLSX em Aspose.Tasks for .NET. Personalize colunas, codificação e muito mais facilmente.
type: docs
weight: 11
url: /pt/net/file-format-options/configuring-xlsx-options/
---
## Introdução
O Microsoft Project (MS Project) é uma ferramenta poderosa para gerenciamento de projetos, e o Aspose.Tasks for .NET fornece integração perfeita para trabalhar com arquivos do MS Project programaticamente. Neste tutorial, percorreremos o processo de configuração das opções do MS Project XLSX usando Aspose.Tasks for .NET.
## Pré-requisitos
Antes de começarmos, certifique-se de ter o seguinte:
### 1. Aspose.Tasks para .NET instalado
 Certifique-se de ter o Aspose.Tasks for .NET instalado em seu ambiente de desenvolvimento. Caso contrário, você pode baixá-lo no[Página de download do Aspose.Tasks para .NET](https://releases.aspose.com/tasks/net/).
### 2. Compreensão básica de C# e .NET Framework
É necessária familiaridade com a linguagem de programação C# e com a estrutura .NET para acompanhar este tutorial.
### 3. Arquivo do Microsoft Project
Tenha em mãos um arquivo do Microsoft Project (MPP) que deseja configurar e salvar como um arquivo XLSX.

## Importando Namespaces
Para começar, importe os namespaces necessários:
```csharp
    using Aspose.Tasks;
    using System.Text;
    
    using Aspose.Tasks.Saving;
    using Aspose.Tasks.Visualization;
```

## Etapa 1: carregar o projeto
```csharp
var project = new Project("YourProjectFile.mpp");
```
Carregue o arquivo do Microsoft Project que você deseja configurar.
## Etapa 2: definir XlsxOptions
```csharp
var options = new XlsxOptions();
```
 Crie uma instância de`XlsxOptions` para definir as configurações para salvar como XLSX.
## Etapa 3: adicionar colunas do gráfico de Gantt
```csharp
var col = new GanttChartColumn("WBS", 100, delegate(Task task) { return task.Get(Tsk.WBS); });
options.View.Columns.Add(col);
```
Adicione as colunas desejadas do gráfico de Gantt às opções.
## Etapa 4: adicionar colunas de visualização de recursos
```csharp
var rscCol = new ResourceViewColumn("Cost center", 100, delegate(Resource resource) { return resource.Get(Rsc.CostCenter); });
options.ResourceView.Columns.Add(rscCol);
```
Inclua as colunas desejadas para a visualização de recursos nas opções.
## Etapa 5: adicionar colunas de visualização de tarefas
```csharp
var assnCol = new AssignmentViewColumn("Notes", 200, delegate(ResourceAssignment assignment) { return assignment.Get(Asn.NotesText); });
options.AssignmentView.Columns.Add(assnCol);
```
Adicione as colunas desejadas para a visualização da tarefa nas opções.
## Etapa 6: definir a codificação
```csharp
options.Encoding = Encoding.Unicode;
```
Defina a codificação do arquivo de saída.
## Etapa 7: salve o projeto como XLSX
```csharp
project.Save("OutputFile.xlsx", options);
```
Salve o projeto com as opções configuradas como um arquivo XLSX.

## Conclusão
Neste tutorial, aprendemos como configurar as opções do MS Project XLSX usando Aspose.Tasks for .NET. Seguindo essas etapas, você pode personalizar o formato de saída de acordo com suas necessidades, aumentando a flexibilidade e a usabilidade do seu fluxo de trabalho de gerenciamento de projetos.
## Perguntas frequentes

### P: Posso configurar colunas diferentes para o Gráfico de Gantt, Visualização de Recursos e Visualização de Atribuições separadamente?

R: Sim, você pode personalizar colunas independentemente para cada visualização usando Aspose.Tasks for .NET.

### P: Existe uma versão de teste disponível antes de comprar o Aspose.Tasks for .NET?

 R: Sim, você pode baixar uma versão de avaliação gratuita no site[Página de lançamentos do Aspose.Tasks para .NET](https://releases.aspose.com/).

### P: Como posso obter suporte se encontrar algum problema ou tiver dúvidas durante a implementação?

 R: Você pode visitar o[Fórum Aspose.Tasks](https://forum.aspose.com/c/tasks/15) pela assistência da comunidade e da equipe de suporte do Aspose.

### P: Posso gerar arquivos XLSX com Aspose.Tasks for .NET em plataformas não Windows?

R: Aspose.Tasks for .NET foi projetado principalmente para plataformas Windows, mas você pode explorar opções de compatibilidade para outras plataformas.

### P: Há alguma opção de licença temporária disponível para fins de teste?

 R: Sim, você pode obter uma licença temporária do[Página de licença temporária Aspose.Tasks](https://purchase.aspose.com/temporary-license/).