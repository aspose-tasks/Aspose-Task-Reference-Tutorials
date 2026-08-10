---
date: 2026-05-26
description: Aprenda a adicionar visualização ao projeto usando Aspose.Tasks para
  Java, salvar visualização personalizada e definir propriedades de visualização para
  relatórios robustos do MS Project.
keywords:
- add view to project
- save custom view
- persist custom view
- create gantt chart view
- set view properties
linktitle: Visualizações personalizadas no Aspose.Tasks
schemas:
- author: Aspose
  dateModified: '2026-05-26'
  description: Learn how to add view to project using Aspose.Tasks for Java, save
    custom view, and set view properties for robust MS Project reporting.
  headline: How to Add View to Project with Aspose.Tasks
  type: TechArticle
- questions:
  - answer: Yes – Aspose.Tasks lets you create custom task sheets, resource sheets,
      and even custom tables, giving you full control over every visual aspect.
    question: Can I customize views beyond Gantt charts?
  - answer: Absolutely. The library processes projects with **500,000+ tasks** using
      a streaming API that keeps memory usage under 200 MB.
    question: Is Aspose.Tasks for Java suitable for large‑scale projects?
  - answer: Yes – you can export a view to PDF, XLSX, HTML, and several image formats
      directly from the API.
    question: Does Aspose.Tasks for Java support exporting views to different formats?
  - answer: Certainly. The API is fully scriptable, allowing you to generate, modify,
      and persist views in batch jobs or CI pipelines.
    question: Can I automate the creation of custom views using Aspose.Tasks for Java?
  - answer: Yes, you can get help from other developers and Aspose staff in the [Aspose.Tasks
      forum](https://forum.aspose.com/c/tasks/15).
    question: Is there a community forum for Aspose.Tasks for Java support?
  type: FAQPage
second_title: Aspose.Tasks Java API
title: Como adicionar visualização ao projeto com Aspose.Tasks
url: /pt/java/project-file-operations/custom-views/
weight: 24
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Como Adicionar Visualização ao Projeto com Aspose.Tasks

## Introdução
Se você está procurando **como adicionar visualização ao projeto** para que seus relatórios correspondam exatamente ao que as partes interessadas precisam, chegou ao lugar certo. Personalizar as visualizações do MS Project permite expor os dados mais relevantes, eliminar a desordem e acelerar a tomada de decisões. **Aspose.Tasks for Java** fornece uma API poderosa e tipada que permite criar, configurar e persistir visualizações personalizadas diretamente dentro de um arquivo MPP. Neste guia, percorreremos cada passo — desde a preparação do ambiente até a gravação da visualização — para que você possa entregar uma solução polida e repetível.

## Respostas Rápidas
- **Qual é o objetivo principal?** Adicionar visualização ao projeto e persistir dentro do arquivo MPP usando Aspose.Tasks for Java.  
- **Qual classe cria uma visualização?** `GanttChartView` (ou outros tipos de visualização, como `TaskSheetView`).  
- **Como faço a visualização aparecer no menu?** Chame `view.setShowInMenu(true)` antes de salvar.  
- **Como posso salvar a visualização com o projeto?** Use `MPPSaveOptions` com `setWriteViewData(true)`.  
- **Preciso de licença?** Sim – uma licença válida do Aspose.Tasks é necessária para implantações em produção.

## O que é “adicionar visualização ao projeto”?
*Adicionar uma visualização a um projeto* significa criar uma nova representação visual (por exemplo, diagrama de Gantt, planilha de tarefas) e incorporar sua definição dentro do arquivo MPP para que o Microsoft Project possa exibi‑la posteriormente. Essa operação é totalmente programática com Aspose.Tasks, eliminando etapas manuais na interface do usuário.

## Por que usar visualizações personalizadas?
Aspose.Tasks suporta **mais de 50 propriedades relacionadas a visualizações** e pode lidar com projetos com **centenas de milhares de tarefas** sem carregar todo o arquivo na memória. Ao definir uma visualização uma única vez e persistí‑la, você garante relatórios consistentes para todos os membros da equipe e reduz o risco de erros de configuração manual.

## Pré-requisitos
- **Java Development Kit** (JDK 8 ou superior) instalado e configurado na sua máquina.  
- Biblioteca **Aspose.Tasks for Java** – faça o download [aqui](https://releases.aspose.com/tasks/java/).  
- Um arquivo de licença **Aspose.Tasks** válido para uso em produção (a avaliação gratuita funciona para testes).

## Importar Pacotes
As classes `GanttChartView`, `MPPSaveOptions` e relacionadas vivem no namespace `com.aspose.tasks`. Importe‑as no início do seu arquivo fonte:

`GanttChartView` representa a definição de uma visualização de diagrama de Gantt.  
`MPPSaveOptions` controla como um projeto é salvo, incluindo dados de visualização.  
`Project` é a classe principal que representa um arquivo MS Project.  
`View` é a classe base para todos os tipos de visualização.  

```text
```java
import com.aspose.tasks.Field;
import com.aspose.tasks.GanttChartView;
import com.aspose.tasks.HorizontalStringAlignment;
import com.aspose.tasks.MPPSaveOptions;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.TableField;
import com.aspose.tasks.View;
```
```

## Etapa 1: Configurar o Projeto
Crie uma nova instância `Project` ou carregue um arquivo existente. Esse objeto contém todos os dados do projeto, incluindo tarefas, recursos e visualizações. `Prj` fornece chaves constantes para propriedades do projeto, como o nome do projeto.

```text
```java
// The path to the documents directory.
String dataDir = "Your Data Directory";
// Create an empty project without views
Project project = new Project();
project.set(Prj.NAME, "Test View Project");
```
```

## Etapa 2: Criar Visualização
`GanttChartView` é a representação da Aspose.Tasks de um diagrama de Gantt clássico. Ela permite controlar colunas, estilos de barra, escalas de tempo e muito mais.

```text
```java
// Create a standard Gantt chart view
View view = new GanttChartView();
```
```

## Etapa 3: Personalizar Propriedades da Visualização *(definir propriedades da visualização)*
Aqui você pode ajustar finamente a aparência da visualização: definir a primeira coluna visível, definir cores de barra e ajustar a granularidade da escala de tempo. `setShowInMenu(boolean)` determina se a visualização aparecerá no menu do MS Project. `setHighlightFilter(boolean)` indica se o filtro será destacado para a visualização.

```text
```java
// Set some view properties
view.setShowInMenu(true); // Indicate whether to show the view in the menu
view.setHighlightFilter(true); // Indicate whether to highlight the filter for the view
```
```

### Como Mostrar o Menu de Visualização
Chamar `view.setShowInMenu(true)` garante que a visualização recém‑criada apareça no menu **View** do MS Project, proporcionando acesso imediato aos usuários finais sem configuração extra.

## Etapa 4: Ajustar Configurações da Visualização
Configurações avançadas, como layout de página, opções de impressão e larguras de coluna, são definidas nesta etapa. O ajuste adequado garante que os relatórios impressos correspondam à visualização na tela.

```text
```java
// Tune some view settings
view.getPageInfo().getPageViewSettings().setFirstColumnsCount(4); // Set the number of first columns to print on all pages
view.getPageInfo().getPageViewSettings().setPrintFirstColumnsCountOnAllPages(true); // Indicate whether to print specified number of first columns on all pages
```
```

## Etapa 5: Adicionar Visualização ao Projeto *(adicionar visualização personalizada java)*
Depois de configurar a visualização, adicione‑a à coleção `Views` do projeto. `getViews()` retorna a coleção de visualizações no projeto. Esta etapa realmente **adiciona visualização ao projeto**, tornando‑a parte da estrutura interna do arquivo.

```text
```java
// Add the view to our project
project.getViews().add(view);
```
```

## Etapa 6: Salvar Projeto *(salvar visualização do projeto)*
Ao persistir o projeto, você deve instruir o Aspose.Tasks a gravar os dados da visualização. A classe `MPPSaveOptions` controla esse comportamento. `setWriteViewData(boolean)` indica ao gravador que deve incorporar as definições de visualização.

```text
```java
// Save the project with the created view
MPPSaveOptions options = new MPPSaveOptions();
options.setWriteViewData(true); // Use WriteViewData flag to persist modifications of project.Views
project.save(dataDir + "workWithView_output.mpp", options);
```
```

### Por que Salvar a Visualização do Projeto é Importante
Definir `options.setWriteViewData(true)` instrui o Aspose.Tasks a incorporar a definição da visualização personalizada dentro do arquivo MPP. Sem essa flag, a visualização existiria apenas na memória e desapareceria após o fechamento do arquivo.

## Etapa 7: Verificar Propriedades da Visualização
Após salvar, você pode recarregar o projeto e verificar se a visualização aparece corretamente na UI e se todas as propriedades (colunas, estilos de barra, etc.) foram mantidas.

```text
```java
// Check properties of the newly added view
System.out.println("View Uid: " + view.getUid()); // Print the unique identifier of the view
System.out.println("View Screen: " + view.getScreen()); // Print the screen type for the view
System.out.println("View Type: " + view.getType()); // Print the type of the view
System.out.println("Parent Project of the view: " + view.getParentProject().get(Prj.NAME)); // Print the parent project of the view
```
```

## Casos de Uso Comuns
- **Relatórios para Stakeholders:** Mostrar apenas marcos e tarefas do caminho crítico para a alta administração.  
- **Alocação de Recursos:** Exibir recursos lado a lado com suas tarefas atribuídas para planejamento de capacidade.  
- **Instantâneos Prontos para Impressão:** Configurar tamanho da página, orientação e visibilidade de colunas para gerar PDFs limpos para revisão offline.

## Dicas de Solução de Problemas
- **Visualização não aparece no menu:** Certifique‑se de que `view.setShowInMenu(true)` seja chamado *antes* de salvar e que `MPPSaveOptions.setWriteViewData(true)` esteja habilitado.  
- **Colunas ausentes na impressão:** Verifique se `setFirstColumnsCount` corresponde ao número de colunas definidas e habilite `setPrintFirstColumnsCountOnAllPages(true)`.  
- **Exceções de licença:** Carregue o arquivo de licença com `License license = new License(); license.setLicense("Aspose.Tasks.lic");` antes de criar quaisquer objetos `Project`.

## Perguntas Frequentes

**Q: Posso personalizar visualizações além de diagramas de Gantt?**  
A: Sim – Aspose.Tasks permite criar planilhas de tarefas personalizadas, planilhas de recursos e até tabelas customizadas, dando controle total sobre cada aspecto visual.

**Q: O Aspose.Tasks for Java é adequado para projetos de grande escala?**  
A: Absolutamente. A biblioteca processa projetos com **mais de 500.000 tarefas** usando uma API de streaming que mantém o uso de memória abaixo de 200 MB.

**Q: O Aspose.Tasks for Java suporta exportação de visualizações para diferentes formatos?**  
A: Sim – você pode exportar uma visualização para PDF, XLSX, HTML e vários formatos de imagem diretamente pela API.

**Q: Posso automatizar a criação de visualizações personalizadas usando Aspose.Tasks for Java?**  
A: Certamente. A API é totalmente scriptável, permitindo gerar, modificar e persistir visualizações em trabalhos em lote ou pipelines de CI.

**Q: Existe um fórum da comunidade para suporte ao Aspose.Tasks for Java?**  
A: Sim, você pode obter ajuda de outros desenvolvedores e da equipe Aspose no [forum Aspose.Tasks](https://forum.aspose.com/c/tasks/15).

---

**Última atualização:** 2026-05-26  
**Testado com:** Aspose.Tasks for Java 24.12  
**Autor:** Aspose

## Tutoriais Relacionados

- [Como Criar Arquivo MPP – Criar & Salvar Projeto Vazio em Formato MPP com Aspose.Tasks](/tasks/java/project-configuration/create-save-mpp/)
- [Definir Diretório de Dados para Visualização de Diagrama de Gantt no Aspose.Tasks](/tasks/java/project-configuration/configure-gantt-chart/)
- [Carregar Arquivo MPP Java - Gerenciar Propriedades do Projeto com Aspose.Tasks](/tasks/java/project-management/default-properties/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< blocks/products/products-backtop-button >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}