---
title: Configurar visualizações de uso em Aspose.Tasks
linktitle: Configurar visualizações de uso em Aspose.Tasks
second_title: API Aspose.Tasks .NET
description: Aprenda a configurar visualizações de uso de tarefas em Aspose.Tasks for .NET. Aprimore a visualização do projeto com etapas detalhadas. Baixe a biblioteca agora!
type: docs
weight: 17
url: /pt/net/text-view-configuration/usage-views/
---
## Introdução
Se você é um desenvolvedor .NET que deseja aprimorar seus recursos de gerenciamento de projetos, Aspose.Tasks é uma ferramenta poderosa que permite manipular arquivos do Microsoft Project sem esforço. Neste tutorial, vamos nos concentrar na configuração de visualizações de uso usando Aspose.Tasks for .NET. Acompanhe para obter insights sobre a renderização de visualizações de uso de tarefas com detalhes para melhor visualização do projeto.
## Pré-requisitos
Antes de mergulhar no tutorial, certifique-se de ter os seguintes pré-requisitos em vigor:
- Biblioteca Aspose.Tasks: certifique-se de ter a biblioteca Aspose.Tasks integrada ao seu projeto .NET. Se não, você pode baixá-lo[aqui](https://releases.aspose.com/tasks/net/) e siga as instruções de instalação.
- Diretório de documentos: configure um diretório onde os documentos do seu projeto são armazenados. Substitua "Seu diretório de documentos" nos trechos de código pelo caminho real para o diretório de documentos.
## Importar namespaces
No trecho de código fornecido, você notará o uso de determinados namespaces. Certifique-se de incluí-los em seu projeto para uma integração perfeita:
```csharp
using Aspose.Tasks;
using Aspose.Tasks.Visualization;
using Aspose.Tasks.Saving;
```
## Etapa 1: renderizar visualização de uso da tarefa com detalhes
Vamos começar renderizando uma visualização de uso da tarefa com detalhes. Siga esses passos:
## Etapa 1.1: Carregar Projeto
```csharp
// O caminho para o diretório de documentos.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "TaskUsageViewWithDetails.mpp");
```
## Etapa 1.2: Obtenha a visualização
```csharp
UsageView view = (TaskUsageView)project.DefaultView;
```
## Etapa 1.3: Personalizar configurações de visualização
```csharp
view.DisplayDetailsHeaderColumn = false;
view.RepeatDetailsHeaderOnAllRows = false;
view.DisplayShortDetailHeaderNames = false;
view.AlignDetailsData = HorizontalStringAlignment.Near;
```
## Passo 1.4: Salvar Projeto como PDF
```csharp
project.Save(DataDir + "task_usage1_out.pdf", SaveFileFormat.Pdf);
```
## Etapa 2: exibir coluna de cabeçalho de detalhes
Nesta etapa, modificaremos as configurações de visualização para exibir a coluna de cabeçalho de detalhes e salvaremos o projeto como PDF:
## Etapa 2.1: Exibir coluna de cabeçalho de detalhes
```csharp
view.DisplayDetailsHeaderColumn = true;
```
## Etapa 2.2: repetir o cabeçalho de detalhes em todas as linhas
```csharp
view.RepeatDetailsHeaderOnAllRows = true;
view.AlignDetailsData = HorizontalStringAlignment.Far;
```
## Passo 2.3: Salvar Projeto como PDF
```csharp
project.Save(DataDir + "task_usage2_out.pdf", SaveFileFormat.Pdf);
```
## Conclusão
Parabéns! Você configurou com êxito as visualizações de uso em Aspose.Tasks. Este tutorial fornece uma base para gerenciamento e visualização eficiente de projetos usando a biblioteca Aspose.Tasks.

### Perguntas frequentes
### P: Onde posso encontrar a documentação do Aspose.Tasks?
 A documentação abrangente está disponível[aqui](https://reference.aspose.com/tasks/net/).
### P: Como posso baixar o Aspose.Tasks para .NET?
 Baixe a biblioteca[aqui](https://releases.aspose.com/tasks/net/).
### P: Onde posso comprar o Aspose.Tasks?
 Você pode comprar Aspose.Tasks[aqui](https://purchase.aspose.com/buy).
### P: Existe uma avaliação gratuita disponível?
 Sim, explore a avaliação gratuita[aqui](https://releases.aspose.com/).
### P: Precisa de suporte ou tem dúvidas?
 Visite o fórum de suporte[aqui](https://forum.aspose.com/c/tasks/15).