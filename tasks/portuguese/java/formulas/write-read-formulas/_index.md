---
date: 2026-10-10
description: Aprenda como criar campo personalizado aspose em Java, aplicar uma double
  task cost formula e salvar o arquivo de projeto usando Aspose.Tasks. Inclui a leitura
  de fórmulas do MS Project.
keywords:
- create custom field aspose
- double task cost formula
- add custom field formula
- calculate task cost
lastmod: 2026-10-10
linktitle: Exemplo de Fórmula de Campo Personalizado – Salvar Arquivo de Projeto
og_description: Aprenda como criar campo personalizado aspose em Java, aplicar uma
  double task cost formula e salvar o arquivo de projeto usando Aspose.Tasks. Inclui
  a leitura de fórmulas do MS Project.
og_image_alt: 'Guide: create custom field aspose and save project file with Aspose.Tasks
  Java'
og_title: Como criar campo personalizado aspose e salvar o arquivo de projeto
schemas:
- author: Aspose
  dateModified: '2026-10-10'
  description: Learn how to create custom field aspose in Java, apply a double task
    cost formula, and save the project file using Aspose.Tasks. Includes reading MS
    Project formulas.
  headline: How to create custom field aspose and save project file
  type: TechArticle
- description: Learn how to create custom field aspose in Java, apply a double task
    cost formula, and save the project file using Aspose.Tasks. Includes reading MS
    Project formulas.
  name: How to create custom field aspose and save project file
  steps:
  - name: '**Java Development Kit (JDK)** – Java 8 or higher installed on your machine.'
    text: '**Java Development Kit (JDK)** – Java 8 or higher installed on your machine.'
  - name: '**Aspose.Tasks for Java** – Download and install from [Aspose.Tasks Java
      download page](https://releases.aspose.com/tasks/java/).'
    text: '**Aspose.Tasks for Java** – Download and install from [Aspose.Tasks Java
      download page](https://releases.aspose.com/tasks/java/).'
  - name: '**Integrated Development Environment (IDE)** – Choose your preferred IDE
      for Java development (IntelliJ IDEA, Eclipse, VS Code, etc.).'
    text: '**Integrated Development Environment (IDE)** – Choose your preferred IDE
      for Java development (IntelliJ IDEA, Eclipse, VS Code, etc.).'
  type: HowTo
- questions:
  - answer: Yes, Aspose.Tasks supports a wide range of MS Project versions, from older
      .mpp formats to the latest releases, covering over 30 file format variations.
    question: Is Aspose.Tasks compatible with all versions of MS Project?
  - answer: Absolutely. The API is designed for seamless integration; just add the
      Aspose.Tasks JAR to your project’s classpath and start using the `Project` class.
    question: Can I integrate Aspose.Tasks into my existing Java project?
  - answer: The library supports most native MS Project formula syntax, including
      arithmetic, logical, and built‑in functions. Complex custom functions may require
      workarounds, but common calculations like **double task cost formula** work
      out of the box.
    question: Are there any limitations to the types of formulas I can create?
  - answer: Yes, the library runs on any platform that supports Java, including Windows,
      Linux, and macOS, and can handle projects up to 2 GB without loading the entire
      file into memory.
    question: Does Aspose.Tasks support multi‑platform deployment?
  - answer: Visit the [Aspose.Tasks community forum](https://forum.aspose.com/c/tasks/15)
      for community help, or open a support ticket if you have a commercial license.
    question: How can I get technical support for Aspose.Tasks?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- custom field
- Aspose.Tasks
- Java project automation
title: Como criar campo personalizado aspose e salvar o arquivo de projeto
url: /pt/java/formulas/write-read-formulas/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Como criar campo personalizado aspose e salvar arquivo de projeto

## Introdução
Neste tutorial você verá um **exemplo de fórmula de campo personalizado** que mostra como **salvar um arquivo de projeto**, escrever e ler fórmulas do MS Project e aplicar uma **fórmula de custo de tarefa dobrado** usando Aspose.Tasks for Java. Ao final, você entenderá por que campos personalizados são poderosos, como incorporar cálculos diretamente em um projeto e como persistir essas alterações para relatórios futuros. O foco principal é **criar campo personalizado aspose** para que você possa automatizar cálculos de custo em qualquer fluxo de trabalho baseado no MS Project.

## Respostas rápidas
- **O que faz “save project file”?** Ele grava todas as alterações em memória de volta para um arquivo .mpp no disco.  
- **Posso adicionar fórmulas de campo personalizado?** Sim – você pode criar um campo personalizado e atribuir uma fórmula como “double task cost”.  
- **Preciso de licença para executar o código?** Um teste gratuito funciona para avaliação; uma licença comercial é necessária para produção.  
- **Qual IDE funciona melhor?** Qualquer IDE Java (IntelliJ IDEA, Eclipse, VS Code) compilará o exemplo.  
- **A API é compatível com a versão mais recente do MS Project?** Aspose.Tasks suporta todos os formatos .mpp recentes.

## O que é “save project file” no Aspose.Tasks?
Salvar um arquivo de projeto significa preservar o estado atual do objeto `Project` — incluindo tarefas, recursos e quaisquer fórmulas personalizadas — para um arquivo físico do Microsoft Project (`.mpp`). Essa operação é essencial após modificar dados, como adicionar um campo personalizado ou alterar custos de tarefas. A chamada `save` grava toda a estrutura do projeto no disco, tornando as alterações disponíveis para ferramentas de relatório subsequentes.

## Por que adicionar um campo personalizado e criar uma fórmula de campo personalizado?
Você adiciona um campo personalizado quando precisa armazenar informações que os campos nativos não cobrem. Anexar uma fórmula — como uma que **double task cost** — automatiza cálculos, elimina atualizações manuais e garante que toda vez que o custo base mudar, o valor derivado seja atualizado instantaneamente. Essa abordagem reduz erros e mantém os dados do cronograma consistentes entre as equipes.

## Pré-requisitos
1. **Java Development Kit (JDK)** – Java 8 ou superior instalado na sua máquina.  
2. **Aspose.Tasks for Java** – Baixe e instale a partir da [Aspose.Tasks Java download page](https://releases.aspose.com/tasks/java/).  
3. **Integrated Development Environment (IDE)** – Escolha sua IDE preferida para desenvolvimento Java (IntelliJ IDEA, Eclipse, VS Code, etc.).

## Importando pacotes
As classes `Project`, `ExtendedAttribute` e relacionadas estão no namespace `com.aspose.tasks`. Importe-as no início do seu arquivo fonte para que o compilador possa resolver os tipos.

```java
import com.aspose.tasks.*;
import java.io.IOException;
import java.math.BigDecimal;
import java.util.Objects;
```

## Etapa 1: configurar diretório de dados
Defina a pasta onde seus arquivos MS Project estão armazenados. É aqui que você carregará o arquivo de origem e, posteriormente, **salvará o arquivo de projeto**.

```java
// The path to the documents directory.
String dataDir = "Your Data Directory";
```

## Etapa 2: carregar arquivo de projeto
A classe `Project` representa um arquivo Microsoft Project na memória, fornecendo acesso a tarefas, recursos e campos personalizados. Carregar o arquivo fornece um modelo de objeto manipulável.

```java
Project project = new Project(dataDir + "project.mpp");
```

## Etapa 3: adicionar campo personalizado e criar fórmula de campo personalizado
Nesta etapa, **adicionamos um campo personalizado** “Double Costs” e **criamos uma fórmula de campo personalizado** que multiplica o `[Cost]` da tarefa por 2, implementando efetivamente uma **fórmula de custo de tarefa dobrado**. O método `setFormula` incorpora o cálculo diretamente no arquivo do projeto.

```java
project.set(Prj.NEW_TASKS_ARE_MANUAL, new NullableBool(false));
ExtendedAttributeDefinition attr = ExtendedAttributeDefinition.createTaskDefinition(
        CustomFieldType.Text, ExtendedAttributeTask.Text1, "Custom");
attr.setAlias("Double Costs");
attr.setFormula("[Cost]*2");   // This formula doubles the task cost
project.getExtendedAttributes().add(attr);
```

## Etapa 4: adicionar tarefa e definir custo
Crie uma nova tarefa e atribua um custo base de `100`. Quando o projeto for salvo, o campo personalizado exibirá automaticamente `200` devido à fórmula definida anteriormente.

```java
Task task = project.getRootTask().getChildren().add("Task");
task.set(Tsk.COST, BigDecimal.valueOf(100));
```

## Etapa 5: salvar arquivo de projeto
O método `save` grava o projeto atualizado, incluindo o novo campo personalizado e seus valores calculados, em `saved.mpp`. Isso persiste as alterações de **criar campo personalizado aspose** para quaisquer consumidores subsequentes.

```java
project.save(dataDir + "saved.mpp", SaveFileFormat.Mpp);
```

## Problemas comuns e soluções
| Problema | Razão | Correção |
|----------|-------|----------|
| **Fórmula não aplicada** | Campo personalizado não adicionado à coleção `ExtendedAttributes` do projeto. | Garanta que `project.getExtendedAttributes().add(attr);` seja executado antes de salvar. |
| **Arquivo não encontrado** | Caminho `dataDir` incorreto. | Verifique se a string do diretório termina com um separador de caminho (`/` ou `\\`). |
| **Custo aparece como 0** | Custo da tarefa não definido antes de salvar. | Chame `task.set(Tsk.COST, ...)` antes de `project.save`. |

## Perguntas frequentes
**Q: O Aspose.Tasks é compatível com todas as versões do MS Project?**  
A: Sim, o Aspose.Tasks suporta uma ampla gama de versões do MS Project, desde formatos .mpp mais antigos até as versões mais recentes, cobrindo mais de 30 variações de formato de arquivo.

**Q: Posso integrar o Aspose.Tasks ao meu projeto Java existente?**  
A: Absolutamente. A API foi projetada para integração perfeita; basta adicionar o JAR do Aspose.Tasks ao classpath do seu projeto e começar a usar a classe `Project`.

**Q: Existem limitações nos tipos de fórmulas que posso criar?**  
A: A biblioteca suporta a maior parte da sintaxe nativa de fórmulas do MS Project, incluindo aritmética, lógica e funções incorporadas. Funções personalizadas complexas podem exigir soluções alternativas, mas cálculos comuns como **double task cost formula** funcionam imediatamente.

**Q: O Aspose.Tasks suporta implantação multiplataforma?**  
A: Sim, a biblioteca funciona em qualquer plataforma que suporte Java, incluindo Windows, Linux e macOS, e pode lidar com projetos de até 2 GB sem carregar o arquivo inteiro na memória.

**Q: Como posso obter suporte técnico para o Aspose.Tasks?**  
A: Visite o [Aspose.Tasks community forum](https://forum.aspose.com/c/tasks/15) para ajuda da comunidade, ou abra um ticket de suporte se você possuir uma licença comercial.

## Conclusão
Neste **exemplo de fórmula de campo personalizado** abordamos como **salvar o arquivo de projeto**, **adicionar um campo personalizado** e **criar uma fórmula de custo de tarefa dobrado** que duplica automaticamente o custo da tarefa. Seguindo estas etapas, você pode automatizar cálculos, enriquecer os dados do seu projeto e garantir que todas as alterações sejam persistidas para relatórios e análises futuras. A técnica de **criar campo personalizado aspose** é uma forma poderosa de estender o MS Project sem trabalho manual em planilhas.

---

**Última atualização:** 2026-10-10  
**Testado com:** Aspose.Tasks for Java 24.12  
**Autor:** Aspose

## Tutoriais relacionados

- [Como criar arquivo MPP – Criar e salvar projeto vazio no formato MPP com Aspose.Tasks](/tasks/java/project-configuration/create-save-mpp/)
- [Como criar projeto aspose.tasks – Definir novos atributos de tarefa](/tasks/java/project-file-operations/set-attributes-new-tasks/)
- [Ler atributos de tarefa estendidos com Aspose.Tasks for Java](/tasks/java/task-properties/extended-task-attributes/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}