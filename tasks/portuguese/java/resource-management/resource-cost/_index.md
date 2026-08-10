---
date: 2026-06-15
description: Aprenda como gerenciar custos em arquivos do MS Project usando Aspose.Tasks
  for Java, incluindo como carregar um arquivo MPP e ler actual cost work e budgeted
  cost schedule.
keywords:
- how to manage costs
- actual cost work
- load mpp file
- budgeted cost schedule
linktitle: Manipular Resource Cost no Aspose.Tasks
schemas:
- author: Aspose
  dateModified: '2026-06-15'
  description: Learn how to manage costs in MS Project files using Aspose.Tasks for
    Java, including how to load an MPP file and read actual cost work and budgeted
    cost schedule.
  headline: How to Manage Costs in MS Project with Aspose.Tasks for Java
  type: TechArticle
- description: Learn how to manage costs in MS Project files using Aspose.Tasks for
    Java, including how to load an MPP file and read actual cost work and budgeted
    cost schedule.
  name: How to Manage Costs in MS Project with Aspose.Tasks for Java
  steps:
  - name: Basic understanding of Java programming.
    text: Basic understanding of Java programming.
  - name: Aspose.Tasks for Java library added to your project (Maven/Gradle or manual
      JAR).
    text: Aspose.Tasks for Java library added to your project (Maven/Gradle or manual
      JAR).
  - name: Access to a Microsoft Project file (`.mpp`) you want to analyze.
    text: Access to a Microsoft Project file (`.mpp`) you want to analyze.
  type: HowTo
- questions:
  - answer: Yes, it fully supports nested summary tasks, multiple resource calendars,
      and custom fields across all supported Project versions.
    question: Can Aspose.Tasks for Java handle complex project structures?
  - answer: Absolutely. Aspose.Tasks reads and writes files from Microsoft Project
      2000 up to the latest 2023 format.
    question: Is the library compatible with different versions of Microsoft Project
      files?
  - answer: Yes, the API returns standard Java objects, allowing seamless integration
      with logging frameworks, ORM tools, or reporting libraries.
    question: Can I integrate Aspose.Tasks for Java with other Java libraries?
  - answer: Aspose provides dedicated forum support, detailed documentation, and responsive
      email assistance for licensed users.
    question: Does Aspose.Tasks for Java offer customer support?
  - answer: You can download a 30‑day evaluation license from the Aspose website to
      explore all features without cost.
    question: Is there a free trial available for Aspose.Tasks for Java?
  type: FAQPage
second_title: Aspose.Tasks Java API
title: Como Gerenciar Custos no MS Project com Aspose.Tasks for Java
url: /pt/java/resource-management/resource-cost/
weight: 18
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Como Gerenciar Custos no MS Project com Aspose.Tasks para Java

## Introdução

Gerenciar orçamentos de projetos é uma responsabilidade central para qualquer gerente de projeto, e **como gerenciar custos** de forma eficaz pode determinar o sucesso ou o fracasso de um projeto. Aspose.Tasks para Java oferece controle programático sobre arquivos Microsoft Project, permitindo ler e atualizar dados de custo de recursos sem nunca abrir o arquivo .mpp manualmente. Neste tutorial você verá passo a passo como carregar um arquivo MPP, inspecionar o trabalho de custo real e extrair o cronograma de custo orçado para cada recurso.

## Respostas Rápidas
- **O que o Aspose.Tasks para Java faz?** Ele lê e grava arquivos Microsoft Project (.mpp) sem exigir a instalação do Microsoft Project.  
- **Como posso carregar um arquivo MPP?** Use `new Project("path/to/file.mpp")` – a API analisa o arquivo na memória.  
- **Quais campos de custo estão disponíveis?** Actual Cost Work (ACWP), Budgeted Cost of Work Scheduled (BCWS) e Budgeted Cost of Work Performed (BCWP).  
- **Preciso de uma licença para desenvolvimento?** Uma licença temporária gratuita funciona para testes; uma licença completa é necessária para produção.  
- **Quais versões do Java são suportadas?** Java 8 e posteriores, incluindo Java 17 LTS.

## Como Gerenciar Custos no MS Project?

Carregue seu projeto com `new Project("yourFile.mpp")`, então itere através de cada objeto `Resource` para ler propriedades relacionadas a custos como ACWP, BCWS e BCWP. Aspose.Tasks converte automaticamente os valores internos de custo para a moeda do projeto, permitindo exibi-los ou armazená‑los diretamente. Essa abordagem elimina cálculos manuais em planilhas e garante consistência de dados em todos os relatórios do projeto.

## Pré-requisitos

1. Compreensão básica de programação Java.  
2. Biblioteca Aspose.Tasks para Java adicionada ao seu projeto (Maven/Gradle ou JAR manual).  
3. Acesso a um arquivo Microsoft Project (`.mpp`) que você deseja analisar.  

## Importar Pacotes

As classes `Project` e `Resource` são os pontos de entrada para trabalhar com os dados do projeto.

A classe `Project` é o objeto de nível superior do Aspose.Tasks que representa um único arquivo Microsoft Project na memória.  
```text
```java
import com.aspose.tasks.Project;
import com.aspose.tasks.Resource;
import com.aspose.tasks.Rsc;
```
```

## Etapa 1: Definir o Diretório de Dados

Primeiro, especifique a pasta que contém seu arquivo `.mpp`. Esse caminho pode ser absoluto ou relativo ao diretório de trabalho da sua aplicação.

```text
```java
String dataDir = "Your Data Directory";
```
```

## Etapa 2: Carregar o Arquivo MS Project

`Project` carrega o arquivo e constrói um modelo de objetos que você pode consultar. A API analisa o arquivo sem precisar do Microsoft Project instalado, suportando mais de 30 formatos de entrada.

```text
```java
Project prj = new Project(dataDir + "ResourceCosts.mpp");
```
```

## Etapa 3: Percorrer os Recursos

Objetos `Resource` representam pessoas, equipamentos ou materiais que consomem orçamento. Você pode percorrer a coleção `project.getResources()` para acessar cada um.

```text
```java
for (Resource res : prj.getResources()) {
```
```

## Etapa 4: Verificar Nome e Custos do Recurso

Para cada recurso, verifique se o nome está definido, então leia os campos de custo. O método `getActualCost()` retorna o **actual cost work** (ACWP), enquanto `getBudgetedCost()` fornece o **budgeted cost schedule** (BCWS/BCWP).

```text
```java
if (res.get(Rsc.NAME) != null) {
    System.out.println(res.get(Rsc.COST));
    System.out.println(res.get(Rsc.ACWP));
    System.out.println(res.get(Rsc.BCWS));
    System.out.println(res.get(Rsc.BCWP));
}
```
```

## Por que Usar Aspose.Tasks para Java para Carregar um Arquivo MPP?

Aspose.Tasks suporta **mais de 30 formatos de arquivo** (incluindo `.mpp`, `.xml` e `.xlsx`) e pode processar projetos com **até 10.000 tarefas** usando menos de 200 MB de RAM. A biblioteca realiza todos os cálculos no lado do servidor, eliminando a necessidade de uma cópia licenciada do Microsoft Project.

## Problemas Comuns e Soluções

- **Nomes de recurso nulos:** Alguns arquivos legados contêm recursos de espaço reservado. Sempre verifique `resource.getName() != null` antes de acessar propriedades de custo.  
- **Arquivos grandes causando pressão de memória:** `LoadOptions` é uma classe de configuração que permite especificar quais dados do projeto carregar. Use `project.setLoadOptions(LoadOptions.setLoadResourceData(false))` para carregar apenas os dados necessários, habilitando-os posteriormente, se preciso.  
- **Incompatibilidades de moeda:** A API respeita as configurações de moeda do projeto; você pode sobrescrevê‑las com `project.getRootTask().setCostRateTable(CostRateTableType.CostRateTable1)` se necessário. `CostRateTableType` enumera as diferentes tabelas de taxa de custo que podem ser aplicadas a uma tarefa.

## Perguntas Frequentes

**Q: O Aspose.Tasks para Java pode lidar com estruturas de projeto complexas?**  
A: Sim, ele oferece suporte total a tarefas resumidas aninhadas, múltiplos calendários de recursos e campos personalizados em todas as versões de Project suportadas.

**Q: A biblioteca é compatível com diferentes versões de arquivos Microsoft Project?**  
A: Absolutamente. Aspose.Tasks lê e grava arquivos do Microsoft Project 2000 até o formato mais recente de 2023.

**Q: Posso integrar Aspose.Tasks para Java com outras bibliotecas Java?**  
A: Sim, a API devolve objetos Java padrão, permitindo integração fluida com frameworks de logging, ferramentas ORM ou bibliotecas de relatórios.

**Q: O Aspose.Tasks para Java oferece suporte ao cliente?**  
A: Aspose fornece suporte dedicado em fóruns, documentação detalhada e assistência por e‑mail responsiva para usuários licenciados.

**Q: Existe uma avaliação gratuita disponível para Aspose.Tasks para Java?**  
A: Você pode baixar uma licença de avaliação de 30 dias no site da Aspose para explorar todos os recursos sem custo.

---

**Last Updated:** 2026-06-15  
**Tested With:** Aspose.Tasks for Java 24.12  
**Author:** Aspose

## Tutoriais Relacionados

- [Como Calcular Variação de Custos e Gerenciar Custos de Atribuição com Aspose.Tasks](/tasks/java/resource-assignments/assignment-cost/)
- [Orçamento, Trabalho e Gerenciamento de Custos para Tarefas no Aspose.Tasks](/tasks/java/task-properties/task-budget-work-cost/)
- [Adicionar recurso ao projeto com Aspose.Tasks para Java](/tasks/java/resource-management/create-resources/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< blocks/products/products-backtop-button >}}
{{< /blocks/products/pf/main-wrap-class >}}