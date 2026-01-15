---
date: 2026-01-15
description: Aprenda como salvar o projeto como PDF e renderizar as visualizações
  de Uso de Recursos e Planilha do MS Project usando Aspose.Tasks for Java. Siga nosso
  guia passo a passo para exportar o projeto para PDF sem esforço.
linktitle: Save Project as PDF – Render Resource Usage and Sheet View in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Salvar Projeto como PDF – Renderizar Uso de Recursos e Visualização de Planilha
  no Aspose.Tasks
url: /pt/java/resource-management/render-resource-usage-sheet-view/
weight: 16
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Salvar Projeto como PDF – Renderizar Uso de Recursos e Visualização de Planilha no Aspose.Tasks

## Introdução
Neste tutorial você descobrirá como **salvar projeto como PDF** enquanto renderiza as visualizações de Uso de Recursos e Planilha de um arquivo Microsoft Project. Seja para gerar um relatório imprimível para as partes interessadas ou converter arquivos MPP para um formato universalmente visualizável, o Aspose.Tasks para Java torna o processo simples — sem necessidade de instalação do Microsoft Project.

## Respostas Rápidas
- **O que faz “salvar projeto como pdf”?** Converte um arquivo de Projeto (MPP) em um documento PDF preservando a visualização selecionada.  
- **Qual visualização pode ser exportada?** Uso de Recursos, Planilha, Gantt, Uso de Tarefas e mais.  
- **Posso alterar a escala de tempo no PDF?** Sim — as opções incluem Dias, TerçosDeMeses e Meses.  
- **Preciso ter o Microsoft Project instalado?** Não, o Aspose.Tasks funciona de forma independente.  
- **É necessária uma licença para produção?** Sim, uma licença comercial é exigida para uso que não seja de avaliação.

## O que é “salvar projeto como PDF”?
Salvar um projeto como PDF cria uma representação estática e de alta resolução de uma visualização de Projeto escolhida. Isso é ideal para compartilhar com clientes, arquivar ou imprimir sem expor o arquivo de projeto subjacente.

## Por que usar Aspose.Tasks para exportar projeto para PDF?
- **Sem dependências externas** – funciona em qualquer plataforma que suporte Java.  
- **Controle granular** – você pode selecionar a visualização, escala de tempo e layout.  
- **Alta fidelidade** – o PDF reflete a aparência da visualização original do Project.  
- **Pronto para automação** – integre em pipelines CI, serviços de relatórios ou conversores em lote.

## Pré‑requisitos
Antes de prosseguir, certifique‑se de que você tem:

1. **Java Development Kit (JDK)** – versão mais recente recomendada.  
2. **Aspose.Tasks para Java** – faça o download na [página de download](https://releases.aspose.com/tasks/java/).  

## Importar Pacotes
Primeiro, importe as classes necessárias para o seu projeto Java:

```java
import com.aspose.tasks.PdfSaveOptions;
import com.aspose.tasks.PresentationFormat;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveOptions;
import com.aspose.tasks.Timescale;
import java.io.IOException;
```

## Guia Passo a Passo

### Etapa 1: Ler o Projeto Fonte
Carregue o arquivo MPP que você deseja converter.

```java
// The path to the documents directory.
String dataDir = "Your Data Directory";
// Read the source Project
Project project = new Project(dataDir + "ResourceUsageView.mpp");
```

### Etapa 2: Definir SaveOptions com a Escala de Tempo Necessária (Exportar Projeto para PDF)
Configure as opções de exportação PDF e defina a escala de tempo desejada.  
*Aqui usamos **Dias** como exemplo.*

```java
// Define the SaveOptions with required TimeScale settings as Days
SaveOptions options = new PdfSaveOptions();
options.setTimescale(Timescale.Days);
```

### Etapa 3: Definir o Formato de Apresentação para ResourceUsage
Escolha a visualização que você deseja renderizar. Neste caso, a visualização **Uso de Recursos**.

```java
// Set the Presentation format to ResourceUsage
options.setPresentationFormat(PresentationFormat.ResourceUsage);
```

### Etapa 4: Salvar o Projeto (Converter MPP para PDF)
Execute a conversão e gere o arquivo PDF.

```java
// Save the Project
project.save(dataDir + "result_days.pdf", options);
```

### Etapa 5: Renderizar Visualizações para Outras Configurações de Escala de Tempo (Alterar Escala de Tempo no PDF)
Repita as etapas anteriores para produzir PDFs com diferentes escalas de tempo, como **TerçosDeMeses** e **Meses**.

```java
// Set the Timescale settings to ThirdsOfMonths
options.setTimescale(Timescale.ThirdsOfMonths);
// Save the Project
project.save(dataDir + "result_thirds.pdf", options);

// Set the Timescale settings to Months
options.setTimescale(Timescale.Months);
// Save the project
project.save(dataDir + "result_months.pdf", options);
```

## Problemas Comuns e Soluções
- **Erros de arquivo não encontrado** – Verifique se `dataDir` aponta para a pasta correta e se o nome do arquivo MPP corresponde exatamente.  
- **PDF em branco** – Certifique‑se de que `PresentationFormat` corresponde a uma visualização que contenha dados (por exemplo, ResourceUsage).  
- **Escala de tempo incorreta** – Verifique se `options.setTimescale()` é chamado antes de cada `project.save()`.

## Perguntas Frequentes

### O Aspose.Tasks pode renderizar outras visualizações além de Uso de Recursos e Planilha?
O Aspose.Tasks suporta a renderização de várias visualizações, como Gráfico de Gantt, Uso de Tarefas e visualizações de Calendário, entre outras.

### O Aspose.Tasks é compatível com diferentes versões de arquivos do Microsoft Project?
Sim, o Aspose.Tasks suporta uma ampla gama de formatos de arquivos do Microsoft Project, incluindo MPP, MPT e formatos XML.

### Posso personalizar a aparência das visualizações renderizadas usando Aspose.Tasks?
Absolutamente! O Aspose.Tasks oferece opções extensas para personalizar a aparência e o layout das visualizações renderizadas de acordo com seus requisitos específicos.

### O Aspose.Tasks requer que o Microsoft Project esteja instalado no sistema?
Não, o Aspose.Tasks é uma biblioteca autônoma e não requer a instalação do Microsoft Project para funcionar.

### Existe suporte técnico disponível para usuários do Aspose.Tasks?
Sim, os usuários do Aspose.Tasks podem contar com suporte técnico através do [fórum do Aspose.Tasks](https://forum.aspose.com/c/tasks/15).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Última atualização:** 2026-01-15  
**Testado com:** Aspose.Tasks para Java 24.12  
**Autor:** Aspose  

---