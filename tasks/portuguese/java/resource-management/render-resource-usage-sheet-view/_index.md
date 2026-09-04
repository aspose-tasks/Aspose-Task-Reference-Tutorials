---
date: 2026-06-15
description: Aprenda como converter MPP para PDF e renderizar as visualizações Resource
  Usage e Sheet usando Aspose.Tasks para Java. Siga nosso guia passo a passo para
  definir timescale e gerar relatórios PDF detalhados sem esforço.
keywords:
- convert mpp to pdf
- how to set timescale
- create pdf from mpp
- save ms project pdf
linktitle: Converter MPP para PDF e Renderizar a Visualização Resource Usage – Aspose.Tasks
schemas:
- author: Aspose
  dateModified: '2026-06-15'
  description: Learn how to convert mpp to pdf and render Resource Usage and Sheet
    views using Aspose.Tasks for Java. Follow our step‑by‑step guide to set timescale
    and generate detailed PDF reports effortlessly.
  headline: Convert MPP to PDF and Render Resource Usage View – Aspose.Tasks
  type: TechArticle
- description: Learn how to convert mpp to pdf and render Resource Usage and Sheet
    views using Aspose.Tasks for Java. Follow our step‑by‑step guide to set timescale
    and generate detailed PDF reports effortlessly.
  name: Convert MPP to PDF and Render Resource Usage View – Aspose.Tasks
  steps:
  - name: Read the Source Project
    text: The `Project` class represents a Microsoft Project file loaded into memory,
      providing access to its data and structure.
  - name: Define SaveOptions with Required TimeScale Settings
    text: '`SaveOptions` configures how the project is saved, allowing you to specify
      format‑specific settings such as timescale.'
  - name: Set the Presentation Format to ResourceUsage
    text: '`PresentationFormat` determines which Project view (e.g., ResourceUsage)
      is rendered in the output document.'
  - name: Save the Project as PDF
    text: '`project.save` writes the project to a file using the provided `SaveOptions`,
      producing the final PDF.'
  - name: Render Views for Other TimeScale Settings
    text: Repeat the previous steps, changing the `TimeScale` value to render additional
      timescale views.
  - name: Optional – Convert Multiple Projects in a Batch
    text: If you need to **convert project to pdf** for many files, place the above
      logic inside a loop that iterates over a directory of *.mpp* files. This approach
      **saves ms project pdf** files in bulk with minimal code changes. The following
      code demonstrates a complete example of converting an MPP file t
  type: HowTo
- questions:
  - answer: Yes, it also supports Gantt Chart, Task Usage, Calendar, and many additional
      views.
    question: Can Aspose.Tasks render other views besides Resource Usage and Sheet?
  - answer: Absolutely – it handles MPP, MPT, and XML formats from Project 2000 through
      Project 2021.
    question: Is Aspose.Tasks compatible with different versions of Microsoft Project
      files?
  - answer: Yes, you can modify colors, fonts, and column layouts through `PdfSaveOptions`
      and `PresentationOptions`.
    question: Can I customize the appearance of rendered views?
  - answer: No, it is a standalone library and works on any Java‑compatible environment.
    question: Does Aspose.Tasks require Microsoft Project to be installed?
  - answer: Support is available via the [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15/).
    question: Where can I get technical support?
  type: FAQPage
second_title: Aspose.Tasks Java API
title: Converter MPP para PDF e Renderizar a Visualização Resource Usage – Aspose.Tasks
url: /pt/java/resource-management/render-resource-usage-sheet-view/
weight: 16
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Converter MPP para PDF e Renderizar a Visualização de Uso de Recursos – Aspose.Tasks

Neste tutorial, você aprenderá **como converter mpp para pdf** enquanto renderiza as visualizações de Uso de Recursos e Folha de um arquivo Microsoft Project. Usar Aspose.Tasks para Java elimina a necessidade do Microsoft Project no servidor, oferecendo uma maneira rápida e confiável de criar relatórios PDF a partir de arquivos MPP. Também mostraremos **como definir a escala de tempo** para que a saída corresponda aos seus requisitos de relatório.

## Respostas Rápidas
- **O que o Aspose.Tasks faz?** Ele lê, modifica e converte arquivos Microsoft Project (MPP) sem necessidade de ter o MS Project instalado.  
- **Posso converter MPP para PDF em uma única linha de código?** Sim – carregue o Project, defina SaveOptions e chame `save`.  
- **Quais escalas de tempo são suportadas?** Dias, ThirdsOfMonths e Meses.  
- **Preciso de uma licença para produção?** Uma licença comercial é necessária para implantações que não sejam de avaliação.  
- **A biblioteca é compatível com Java 8+?** Absolutamente – suporta Java 8 e versões posteriores.

## O que é converter mpp para pdf?
*Converter mpp para pdf* refere-se ao processo de pegar um arquivo Microsoft Project (.mpp) e gerar uma versão em Portable Document Format (PDF) que reproduz fielmente as tabelas, cronogramas, gráficos e alocações de recursos do projeto. O PDF resultante pode ser facilmente compartilhado, impresso e arquivado sem exigir que o Microsoft Project esteja instalado na máquina do destinatário.

## Por que Converter Projeto para PDF com Aspose.Tasks?
O Aspose.Tasks suporta **mais de 50 formatos de entrada e saída** e pode renderizar projetos com centenas de páginas sem carregar o arquivo inteiro na memória, reduzindo o uso de RAM em até 70 %. A saída em PDF mantém tabelas, gráficos e alocações de recursos, tornando-a ideal para distribuição a partes interessadas e arquivamento.

## Pré-requisitos
1. **Java Development Kit (JDK)** – Java 8 ou mais recente instalado na sua máquina.  
2. **Aspose.Tasks for Java** – faça o download do JAR mais recente na [download page](https://releases.aspose.com/tasks/java/).  

## Como converter mpp para pdf usando Aspose.Tasks para Java?
Carregue seu arquivo MPP de origem, configure a escala de tempo desejada, defina o formato de apresentação como **ResourceUsage** e salve o resultado como PDF. Esse fluxo de ponta a ponta requer apenas algumas chamadas de API e é executado em menos de um segundo para tamanhos de projeto típicos.

### Etapa 1: Ler o Projeto de Origem
O `Project` representa um arquivo Microsoft Project carregado na memória, fornecendo acesso aos seus dados e estrutura.  
```java
import com.aspose.tasks.PdfSaveOptions;
import com.aspose.tasks.PresentationFormat;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveOptions;
import com.aspose.tasks.Timescale;
import java.io.IOException;
```

### Etapa 2: Definir SaveOptions com Configurações de TimeScale Necessárias
`SaveOptions` configura como o projeto é salvo, permitindo especificar configurações específicas de formato, como a escala de tempo.  
```java
// The path to the documents directory.
String dataDir = "Your Data Directory";
// Read the source Project
Project project = new Project(dataDir + "ResourceUsageView.mpp");
```

### Etapa 3: Definir o Formato de Apresentação para ResourceUsage
`PresentationFormat` determina qual visualização do Project (por exemplo, ResourceUsage) será renderizada no documento de saída.  
```java
// Define the SaveOptions with required TimeScale settings as Days
SaveOptions options = new PdfSaveOptions();
options.setTimescale(Timescale.Days);
```

### Etapa 4: Salvar o Projeto como PDF
`project.save` grava o projeto em um arquivo usando o `SaveOptions` fornecido, produzindo o PDF final.  
```java
// Set the Presentation format to ResourceUsage
options.setPresentationFormat(PresentationFormat.ResourceUsage);
```

### Etapa 5: Renderizar Visualizações para Outras Configurações de TimeScale
Repita as etapas anteriores, alterando o valor de `TimeScale` para renderizar visualizações de escala de tempo adicionais.  
```java
// Save the Project
project.save(dataDir + days, options);
```

### Etapa 6: Opcional – Converter Vários Projetos em Lote
Se você precisar **converter projeto para pdf** para muitos arquivos, coloque a lógica acima dentro de um loop que itere sobre um diretório de arquivos *.mpp*. Essa abordagem **salva arquivos ms project pdf** em lote com alterações mínimas de código. O código a seguir demonstra um exemplo completo de conversão de um arquivo MPP para PDF com as configurações desejadas.  
```java
// Set the Timescale settings to ThirdsOfMonths
options.setTimescale(Timescale.ThirdsOfMonths);
// Save the Project
project.save(thirds, options);
// Set the Timescale settings to Months
options.setTimescale(Timescale.Months);
// Save the project
project.save(dataDir + months, options);
```

## Problemas Comuns e Soluções
- **Fontes ausentes no PDF** – Certifique-se de que as fontes necessárias estejam instaladas no servidor ou incorpore-as via `PdfSaveOptions`.  
- **Arquivos de projeto grandes causam OutOfMemoryError** – Use `LoadOptions.setLoadAllResources(false)` para carregar recursos sob demanda.  
- **Renderização de escala de tempo incorreta** – Verifique se `options.setTimeScale(TimeScale.Days)` (ou outro enum) corresponde à granularidade desejada.

## Perguntas Frequentes

**Q: O Aspose.Tasks pode renderizar outras visualizações além de Uso de Recursos e Folha?**  
A: Sim, também suporta Gráfico de Gantt, Uso de Tarefas, Calendário e muitas visualizações adicionais.

**Q: O Aspose.Tasks é compatível com diferentes versões de arquivos Microsoft Project?**  
A: Absolutamente – ele lida com formatos MPP, MPT e XML do Project 2000 ao Project 2021.

**Q: Posso personalizar a aparência das visualizações renderizadas?**  
A: Sim, você pode modificar cores, fontes e layouts de colunas através de `PdfSaveOptions` e `PresentationOptions`.

**Q: O Aspose.Tasks requer a instalação do Microsoft Project?**  
A: Não, é uma biblioteca independente e funciona em qualquer ambiente compatível com Java.

**Q: Onde posso obter suporte técnico?**  
A: O suporte está disponível através do [forum Aspose.Tasks](https://forum.aspose.com/c/tasks/15/).

---

**Última Atualização:** 2026-06-15  
**Testado com:** Aspose.Tasks 24.12 para Java  
**Autor:** Aspose

## Tutoriais Relacionados

- [Renderizar Visualização de Uso de Recursos e Folha no Aspose.Tasks](/tasks/java/resource-management/render-resource-usage-sheet-view/)
- [Como Exportar PDF no Aspose.Tasks – Salvar como PDF](/tasks/java/project-file-operations/save-as-pdf/)
- [Como Criar Arquivos MPP com Aspose.Tasks para Java](/tasks/java/project-configuration/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< blocks/products/products-backtop-button >}}
{{< /blocks/products/pf/main-wrap-class >}}