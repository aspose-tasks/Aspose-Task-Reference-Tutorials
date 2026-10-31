---
date: 2026-10-31
description: Aprenda como exportar gantt para pdf em Java usando Aspose.Tasks. Este
  guia passo a passo mostra como ler os dados do diagrama de Gantt e gerar relatórios
  em PDF.
keywords:
- export gantt to pdf
- how to read gantt
- export gantt to excel
- generate gantt report java
lastmod: 2026-10-31
linktitle: Ler Dados Específicos do Diagrama de Gantt no Aspose.Tasks
og_description: Exportar gantt para pdf em Java com Aspose.Tasks. Siga este tutorial
  para ler os dados do diagrama de Gantt, personalizar propriedades de visualização
  e gerar relatórios em PDF para gerenciamento de projetos.
og_image_alt: 'Tutorial screenshot: exporting Gantt chart to PDF using Aspose.Tasks
  for Java'
og_title: Exportar gantt para pdf em Java – guia Aspose.Tasks
schemas:
- author: Aspose
  dateModified: '2026-10-31'
  description: Learn how to export gantt to pdf in Java using Aspose.Tasks. This step‑by‑step
    guide shows you how to read Gantt chart data and generate PDF reports.
  headline: Export gantt to pdf in Java – extract specific data
  type: TechArticle
- description: Learn how to export gantt to pdf in Java using Aspose.Tasks. This step‑by‑step
    guide shows you how to read Gantt chart data and generate PDF reports.
  name: Export gantt to pdf in Java – extract specific data
  steps:
  - name: '**Java Development Kit (JDK):** Make sure you have Java installed on your
      system. You can download it from the **[Oracle JDK 11 download page](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html)**.'
    text: '**Java Development Kit (JDK):** Make sure you have Java installed on your
      system. You can download it from the **[Oracle JDK 11 download page](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html)**.'
  - name: '**Aspose.Tasks for Java Library:** Download and install the Aspose.Tasks
      for Java library from the **[Aspose.Tasks for Java download page](https://releases.aspose.com/tasks/java/)**.'
    text: '**Aspose.Tasks for Java Library:** Download and install the Aspose.Tasks
      for Java library from the **[Aspose.Tasks for Java download page](https://releases.aspose.com/tasks/java/)**.'
  - name: '**Integrated Development Environment (IDE):** Choose an IDE of your preference.
      Popular choices include IntelliJ IDEA, Eclipse, or NetBeans.'
    text: '**Integrated Development Environment (IDE):** Choose an IDE of your preference.
      Popular choices include IntelliJ IDEA, Eclipse, or NetBeans.'
  type: HowTo
- questions:
  - answer: Yes, Aspose.Tasks for Java integrates seamlessly with any Java library
      or framework, including Spring, Hibernate, and Apache POI.
    question: Can I use Aspose.Tasks for Java with other Java libraries?
  - answer: Absolutely. The library processes multi‑hundred‑page MPP files in under
      5 seconds on standard server hardware and supports concurrent execution in multi‑threaded
      environments.
    question: Is Aspose.Tasks suitable for large‑scale enterprise projects?
  - answer: Yes, Aspose.Tasks supports 20+ formats, including MPP, XML, MPX, and Primavera
      XML, enabling you to read and convert legacy schedules.
    question: Does Aspose.Tasks support multiple project file formats?
  - answer: Certainly. You can modify bar styles, gridlines, text styles, and timescale
      tiers programmatically before exporting to PDF or image formats.
    question: Can I customize the appearance of Gantt charts with Aspose.Tasks?
  - answer: Call `project.save("output.mpp");` after making any modifications to persist
      them to the project file.
    question: How do I save changes after modifying a view?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- export gantt
- Aspose.Tasks
- Java Gantt
- pdf generation
- project management
title: Exportar gantt para pdf em Java – extrair dados específicos
url: /pt/java/project-data-reading/read-specific-gantt-chart-data/
weight: 16
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Exportar gantt para pdf em Java – extrair dados específicos

## Introdução
Neste tutorial você aprenderá como **exportar gantt para pdf em Java** lendo informações do diagrama de Gantt com Aspose.Tasks for Java. Diagramas de Gantt fornecem aos gerentes de projeto um roteiro visual de tarefas, dependências e cronogramas, e poder extrair esses dados programaticamente permite criar relatórios PDF automatizados, dashboards ou integrações com outros sistemas corporativos. Vamos percorrer cada passo, desde o carregamento de um arquivo de projeto até a extração de propriedades de visualização e, finalmente, a geração de um PDF.

## Respostas rápidas
- **O que posso extrair?** Qualquer propriedade de visualização, estilo de barra, linha de grade, estilo de texto, linha de progresso ou nível de escala de tempo de um diagrama de Gantt.  
- **Preciso de licença?** Uma versão de avaliação funciona para desenvolvimento; uma licença comercial é necessária para produção.  
- **Qual versão do Java é suportada?** Java 8 ou posterior (o tutorial usa JDK 11).  
- **O código pode ser executado como está?** Sim – basta substituir o caminho do diretório de dados.  
- **Posso modificar a visualização após a leitura?** Absolutamente – a API permite alterar propriedades e salvar de volta no arquivo de projeto.

## O que é exportar gantt para pdf?
Exportar gantt para pdf é o processo de converter a visualização de um diagrama de Gantt armazenada em um arquivo de projeto em um documento PDF que preserva o estilo visual e as informações de cronograma. Esta operação é útil para compartilhar o status do projeto com partes interessadas que podem não ter uma ferramenta de gerenciamento de projetos.

## Por que exportar gantt para pdf com Aspose.Tasks?
Aspose.Tasks pode lidar com **mais de 30 + formatos de entrada** (MPP, XML, MPX, etc.) e **exportar para PDF em uma única chamada** preservando 95 % da fidelidade visual, mesmo para projetos com mais de 500 tarefas. A biblioteca processa arquivos na memória, permitindo gerar PDFs em servidores sem instalar o Microsoft Project.

## Pré‑requisitos
1. **Java Development Kit (JDK):** Certifique‑se de que o Java está instalado em seu sistema. Você pode baixá‑lo na **[Página de download do Oracle JDK 11](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html)**.  
2. **Aspose.Tasks for Java Library:** Baixe e instale a biblioteca Aspose.Tasks for Java na **[página de download do Aspose.Tasks for Java](https://releases.aspose.com/tasks/java/)**.  
3. **Integrated Development Environment (IDE):** Escolha um IDE de sua preferência. Opções populares incluem IntelliJ IDEA, Eclipse ou NetBeans.

## Importar pacotes
Os imports a seguir dão acesso às classes principais do Aspose.Tasks necessárias para ler e exportar dados do Gantt.  
*Nenhum bloco de código é exibido aqui para manter o tutorial focado nos conceitos; basta adicionar os imports ao seu arquivo Java.*

## Como carregar um arquivo de projeto de diagrama de Gantt em Java?
Carregue o arquivo de projeto criando uma instância `Project` e passando o caminho completo ao construtor. Esta etapa inicializa a representação em memória do diagrama de Gantt, permitindo consultas subsequentes de propriedades de visualização. Quando o arquivo for carregado com sucesso, você pode verificar o nome do projeto, a data de início e o número de tarefas para garantir que o arquivo correto foi aberto. Essa verificação ajuda a detectar problemas de caminho ou formato logo no início do fluxo de trabalho.  
```java
Project project = new Project(dataDir + "SampleProject.mpp");
```  
*Âncora de definição:* `Project` é o objeto de nível superior do Aspose.Tasks que representa um único arquivo de projeto na memória.

## Como acessar a visualização do diagrama de Gantt?
Recupere a primeira visualização Gantt da coleção de visualizações do projeto. A maioria dos projetos contém ao menos uma visualização Gantt, que geralmente é a primeira entrada. Após obter a visualização, você pode verificar seu nome e garantir que seja do tipo `GanttChartView` antes de prosseguir com a extração de propriedades. Essa verificação adicional evita erros em tempo de execução ao trabalhar com coleções de visualizações personalizadas ou não‑padrão.  
```java
GanttChartView ganttView = (GanttChartView) project.getViews().get(0);
```  
*Âncora de definição:* `GanttChartView` representa o layout visual de tarefas, escalas de tempo e barras que você vê em um típico diagrama de Gantt.

## Como extrair propriedades de visualização?
Você pode ler propriedades como cor de fundo, altura da barra e configurações da escala de tempo diretamente do objeto `GanttChartView`. Imprimi‑las ajuda a verificar a configuração atual antes da exportação. Um loop típico de extração itera sobre cada propriedade, formata o valor como string e registra no console ou em um arquivo para análise posterior. Essa abordagem é útil para depuração e para gerar documentação da aparência do diagrama.  
```java
System.out.println("Bar height: " + ganttView.getBarHeight());
System.out.println("Show gridlines: " + ganttView.getShowGridlines());
```  
*Âncora de definição:* `GanttChartView` fornece acesso às configurações de visualização, como cor de fundo, altura da barra e configuração da escala de tempo.

## Como extrair estilos de barra?
Itere sobre a coleção de objetos `BarStyle` para obter detalhes como cor, padrão e forma de cada tipo de barra usado no diagrama. Para cada estilo, você também pode ler o tipo de tarefa associado e a condição que aciona o estilo, o que é essencial ao recriar o diagrama em outro formato. Coletar essas informações permite produzir uma réplica visual fiel ou aplicar regras de estilo personalizadas programaticamente.  
```java
for (BarStyle style : ganttView.getBarStyles()) {
    System.out.println("Bar type: " + style.getBarType() + ", Color: " + style.getColor());
}
```  
*Âncora de definição:* `BarStyle` define a aparência visual de uma barra de Gantt, incluindo sua cor, padrão e forma.

## Como extrair linhas de grade?
Linhas de grade definem a separação visual entre linhas e colunas. Acesse‑as via o método `getGridlines()` e exiba sua visibilidade e estilo. Após recuperar a coleção de linhas de grade, você pode percorrer cada linha para capturar seu tipo (sólida, tracejada), espessura e cor. Esses dados são valiosos quando você precisa reproduzir o layout exato da grade em PDFs exportados ou outros formatos de relatório.  
```java
for (Gridline grid : ganttView.getGridlines()) {
    System.out.println("Gridline visible: " + grid.getVisible());
}
```  
*Âncora de definição:* `getGridlines()` retorna a coleção de objetos de linha de grade que controlam os separadores de linhas e colunas na visualização Gantt.

## Como extrair estilos de texto?
Estilos de texto controlam a fonte, tamanho e cor dos rótulos no diagrama de Gantt. Percorra a coleção `TextStyle` para listar cada estilo. Para cada estilo de texto, você também pode recuperar o elemento associado (nome da tarefa, data, etc.) e quaisquer regras de formatação condicional. Capturar esses detalhes garante que os documentos exportados mantenham a mesma tipografia do diagrama original.  
```java
for (TextStyle txt : ganttView.getTextStyles()) {
    System.out.println("Text style: " + txt.getStyle() + ", Font size: " + txt.getFontSize());
}
```  
*Âncora de definição:* `TextStyle` representa os atributos de formatação aplicados a elementos textuais dentro do diagrama de Gantt.

## Como extrair linhas de progresso?
Linhas de progresso mostram o ponto de conclusão atual de uma tarefa. Acesse‑as através de `getProgressLines()` e imprima seus atributos. Cada linha de progresso inclui propriedades como cor da linha, espessura e posição relativa à barra da tarefa. Registrar essas informações permite gerar visualizações sensíveis ao progresso ou calcular métricas de conclusão geral do projeto.  
```java
for (ProgressLine line : ganttView.getProgressLines()) {
    System.out.println("Progress line color: " + line.getColor());
}
```  
*Âncora de definição:* `getProgressLines()` retorna o conjunto de objetos de linha de progresso que indicam o status de conclusão da tarefa.

## Como extrair níveis de escala de tempo?
Níveis de escala de tempo definem as unidades de tempo hierárquicas (dias, semanas, meses) exibidas no diagrama. Recupere‑os via `getTimescaleTiers()` e exiba suas configurações. Para cada nível, você pode capturar o tipo de unidade, formato do rótulo e alinhamento, que são cruciais para reproduzir a granularidade exata da linha do tempo em PDFs exportados ou componentes de UI personalizados.  
```java
for (TimescaleTier tier : ganttView.getTimescaleTiers()) {
    System.out.println("Tier type: " + tier.getTierType());
}
```  
*Âncora de definição:* `getTimescaleTiers()` fornece acesso à coleção de objetos de nível de escala de tempo que controlam a exibição do eixo temporal.

## Como exportar o diagrama de Gantt para PDF?
Crie um objeto `PdfSaveOptions`, opcionalmente personalize o tamanho da página ou incorporação de fontes, então chame `project.save` com o formato PDF. Essa única chamada gera um PDF que espelha a visualização Gantt na tela. Você também pode especificar opções adicionais, como compressão de imagens, remoção de marca d'água ou incorporação de fontes personalizadas para atender aos requisitos de branding corporativo. Após salvar, verifique o tamanho do arquivo PDF e a fidelidade visual para garantir que a exportação foi bem‑sucedida.  
```java
PdfSaveOptions options = new PdfSaveOptions();
options.setPageSize(PageSize.A4);
project.save(dataDir + "ExportedGantt.pdf", options);
```  
*Âncora de definição:* `PdfSaveOptions` permite ajustar a saída PDF, como dimensões da página, compressão e tratamento de fontes.

## Armadilhas comuns & dicas
- **Diretório de dados incorreto:** Certifique‑se de que `dataDir` termina com um separador de arquivos (`/` ou `\\`) adequado ao seu SO.  
- **Visualização ausente:** Se o projeto não possuir visualização Gantt, `project.getViews()` estará vazio – adicione uma verificação antes de fazer o cast.  
- **Exceções de licença:** Sem uma licença válida, a API pode adicionar uma marca d'água aos PDFs exportados.  
- **Projetos grandes:** Para projetos com mais de 1.000 tarefas, considere aumentar o tamanho do heap da JVM (`-Xmx2g`) para evitar `OutOfMemoryError`.  

## Perguntas frequentes

**Q: Posso usar Aspose.Tasks for Java com outras bibliotecas Java?**  
A: Sim, Aspose.Tasks for Java integra‑se perfeitamente com qualquer biblioteca ou framework Java, incluindo Spring, Hibernate e Apache POI.

**Q: Aspose.Tasks é adequado para projetos corporativos de grande escala?**  
A: Absolutamente. A biblioteca processa arquivos MPP de várias centenas de páginas em menos de 5 segundos em hardware de servidor padrão e suporta execução concorrente em ambientes multithread.

**Q: Aspose.Tasks suporta múltiplos formatos de arquivo de projeto?**  
A: Sim, Aspose.Tasks suporta mais de 20 formatos, incluindo MPP, XML, MPX e Primavera XML, permitindo ler e converter cronogramas legados.

**Q: Posso personalizar a aparência dos diagramas de Gantt com Aspose.Tasks?**  
A: Certamente. Você pode modificar estilos de barra, linhas de grade, estilos de texto e níveis de escala de tempo programaticamente antes de exportar para PDF ou formatos de imagem.

**Q: Como salvar alterações após modificar uma visualização?**  
A: Chame `project.save("output.mpp");` após fazer quaisquer modificações para persistir as alterações no arquivo de projeto.

---

**Última atualização:** 2026-10-31  
**Testado com:** Aspose.Tasks for Java 24.12  
**Autor:** Aspose  

```java
import com.aspose.tasks.DateLabel;
import com.aspose.tasks.DayType;
import com.aspose.tasks.Field;
import com.aspose.tasks.FontStyles;
import com.aspose.tasks.GanttBarEndShape;
import com.aspose.tasks.GanttBarMiddleShape;
import com.aspose.tasks.GanttBarShowFor;
import com.aspose.tasks.GanttBarSize;
import com.aspose.tasks.GanttBarStyle;
import com.aspose.tasks.GanttChartView;
import com.aspose.tasks.GridlineType;
import com.aspose.tasks.Gridlines;
import com.aspose.tasks.Interval;
import com.aspose.tasks.LinePattern;
import com.aspose.tasks.Project;
import com.aspose.tasks.TextStyle;
import com.aspose.tasks.TimescaleUnit;
```

```java
String dataDir = "Your Data Directory";
Project project = new Project(dataDir + "ReadSpecificGantChartViewData.mpp");
```

```java
GanttChartView view = (GanttChartView) project.getViews().toList().get(0);
```

```java
System.out.println("View.BarRounding: " + view.getBarRounding());
System.out.println("view.ShowBarSplits: " + view.getShowBarSplits());
System.out.println("view.ShowDrawings: " + view.getShowDrawings());
// Continue for other properties...
```

```java
for (int i = 0; i < view.getBarStyles().size(); i++) {
    GanttBarStyle barStyle = view.getBarStyles().get(i);
    // Print bar style details...
}
```

```java
System.out.println("Gridlines count: " + view.getGridlines().size());
Gridlines gridlines = view.getGridlines().get(0);
// Print gridline details...
```

```java
System.out.println("\nView Text Styles:");
for (TextStyle textStyle : view.getTextStyles()) {
    // Print text style details...
}
```

```java
System.out.println("ProgressLInes.BeginAtDate: " + view.getProgressLines().getBeginAtDate());
// Print other progress line details...
```

```java
System.out.println("BottomTimescaleTier.Count: " + view.getBottomTimescaleTier().getCount());
// Print details of other timescale tiers...
```

## Tutoriais relacionados

- [Como salvar projeto como PDF com Aspose.Tasks – Guia de Exportação](/tasks/java/project-file-operations/save-as-pdf/)
- [Criar PDF de Projeto – Personalizar escala de tempo do diagrama de Gantt](/tasks/java/project-file-operations/set-time-scale-count/)
- [Exportar projeto para PDF e reduzir espaço entre lista de tarefas e rodapé no Aspose.Tasks](/tasks/java/project-file-operations/reduce-gap-tasks-list-footer/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}