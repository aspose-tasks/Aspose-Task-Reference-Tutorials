---
date: 2026-09-09
description: Aprenda a identificar tarefas entre projetos usando Aspose.Tasks para
  Java. Explore integração perfeita, gerenciamento eficiente e exemplos do mundo real.
keywords:
- identify cross project tasks
- set document directory
- get task id java
lastmod: 2026-09-09
linktitle: Identificar tarefas entre projetos no Aspose.Tasks
og_description: Identificar tarefas entre projetos no Aspose.Tasks para Java. Aprenda
  a definir o diretório de documentos, recuperar IDs de tarefas e gerenciar projetos
  vinculados de forma eficiente.
og_image_alt: Screenshot of Aspose.Tasks Java API showing cross‑project task identification
og_title: Identificar tarefas entre projetos no Aspose.Tasks – Guia Java
schemas:
- author: Aspose
  dateModified: '2026-09-09'
  description: Learn how to identify cross project tasks using Aspose.Tasks for Java.
    Explore seamless integration, efficient management, and real‑world examples.
  headline: Identify cross project tasks in Aspose.Tasks
  type: TechArticle
- questions:
  - answer: Yes, Aspose.Tasks supports multiple languages, including Java, .NET, and
      more.
    question: Can I use Aspose.Tasks with other programming languages?
  - answer: Refer to the documentation **[here](https://reference.aspose.com/tasks/java/)**.
    question: Where can I find detailed documentation for Aspose.Tasks for Java?
  - answer: Yes, you can get a free trial **[here](https://releases.aspose.com/)**.
    question: Is there a free trial available for Aspose.Tasks for Java?
  - answer: Obtain a temporary license **[here](https://purchase.aspose.com/temporary-license/)**.
    question: How can I get temporary licensing for Aspose.Tasks?
  - answer: Visit the Aspose.Tasks support forum **[here](https://forum.aspose.com/c/tasks/15)**.
    question: Need help or have specific questions?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- Aspose.Tasks
- Java project management
- cross project tasks
- task linking
title: Identificar tarefas entre projetos no Aspose.Tasks
url: /pt/java/task-links/identify-cross-project-tasks/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Identificar tarefas entre projetos no Aspose.Tasks

## Introdução
Neste tutorial você aprenderá **como identificar tarefas entre projetos** com Aspose.Tasks para Java. Seja você quem mantém um portfólio de cronogramas interdependentes ou precisa auditar dependências externas, os passos abaixo mostram como localizar tarefas que referenciam outros arquivos de projeto, recuperar seus identificadores e trabalhar com elas programaticamente.

## Respostas rápidas
- **O que significa “identificar tarefas entre projetos”?** Significa localizar tarefas que referenciam ou dependem de tarefas em outro arquivo de projeto.  
- **Qual método imprime o ID da tarefa?** Use `externalTask.get(Tsk.ID)` para imprimir o ID da tarefa.  
- **Como definir o diretório do documento?** Atribua o caminho da pasta a uma variável `String` (por exemplo, `dataDir`).  
- **Qual propriedade recupera uma tarefa por UID?** Chame `getChildren().getByUid(yourUid)`.  
- **Preciso de uma licença para uso em produção?** Sim, uma licença válida do Aspose.Tasks é necessária para implantações comerciais.

## O que é “identificar tarefas entre projetos”?
Identificar tarefas entre projetos permite rastrear relações entre tarefas distribuídas em vários arquivos do Microsoft Project. Ao localizar tarefas que referenciam ou dependem de cronogramas externos, você pode entender como os itens de trabalho interagem entre os limites dos projetos, evitar esforços duplicados e manter cronogramas precisos. Essa capacidade é essencial para portfólios de grande escala onde tarefas são compartilhadas ou dependem de cronogramas externos.

## Por que usar Aspose.Tasks para Java?
Aspose.Tasks para Java suporta **mais de 50 formatos de entrada e saída** (incluindo MPP, MPX, XML e CSV) e pode processar projetos com **até 10.000 tarefas** sem carregar o arquivo inteiro na memória. A biblioteca funciona em qualquer plataforma compatível com JVM, não requer instalação do Microsoft Project e oferece acesso total à API para IDs, UIDs, IDs externos e metadados de vinculação.

## Pré-requisitos
- Um ambiente de desenvolvimento Java funcional (JDK 8 ou superior).  
- Aspose.Tasks para Java instalado. Você pode baixá-lo **[aqui](https://releases.aspose.com/tasks/java/)**.  
- Um arquivo de licença válido do Aspose.Tasks se você planeja executar o código em produção.

## Importar pacotes
A classe `Project` representa um arquivo Microsoft Project, `Task` representa uma tarefa individual e `Tsk` fornece constantes de campos de tarefa.  
```java
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.Tsk;
```

## Etapa 1: definir diretório do documento
A string `dataDir` contém o caminho para a pasta que contém seus arquivos `.mpp`.  
```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
```

## Etapa 2: carregar projeto externo
`Project externalProject` carrega o arquivo de projeto externo especificado para inspeção.  
```java
Project externalProject = new Project(dataDir + "External.mpp");
```

## Etapa 3: recuperar tarefa externa por uid
`externalProject.getChildren().getByUid(uid)` recupera uma tarefa da coleção de tarefas do projeto externo usando seu identificador único.  
```java
Task externalTask = externalProject.getRootTask().getChildren().getByUid(1);
```

## Etapa 4: imprimir ID da tarefa (caso de uso principal)
`externalTask.get(Tsk.ID)` retorna o ID interno atribuído pelo Aspose.Tasks para a tarefa especificada.  
```java
System.out.println(externalTask.get(Tsk.ID).toString());
```

## Etapa 5: imprimir ID original (externo) da tarefa
`externalTask.get(Tsk.ExternalID)` obtém o ID original da tarefa conforme definido no arquivo de projeto de origem.  
```java
System.out.println(externalTask.get(Tsk.EXTERNAL_ID).toString());
```

Repita as etapas acima para quaisquer tarefas adicionais que você precise rastrear entre projetos.

## Problemas comuns e dicas
- **Erros de caminho** – Certifique-se de que `dataDir` termina com o separador de arquivos apropriado (`/` ou `\\`).  
- **UID não encontrado** – Verifique se o UID existe no projeto externo; use `externalProject.getRootTask().getChildren().size()` para listar os UIDs disponíveis.  
- **Exceções de licença** – Uma licença ausente ou inválida lançará uma exceção de licença em tempo de execução.  
- **Projetos grandes** – Para projetos com mais de 5.000 tarefas, considere usar `ProjectReader` com a flag `LoadOptions` para transmitir dados e reduzir o consumo de memória.

## Perguntas frequentes

**Q: Posso usar Aspose.Tasks com outras linguagens de programação?**  
A: Sim, Aspose.Tasks suporta várias linguagens, incluindo Java, .NET e mais.

**Q: Onde posso encontrar documentação detalhada do Aspose.Tasks para Java?**  
A: Consulte a documentação **[aqui](https://reference.aspose.com/tasks/java/)**.

**Q: Existe um teste gratuito disponível para Aspose.Tasks para Java?**  
A: Sim, você pode obter um teste gratuito **[aqui](https://releases.aspose.com/)**.

**Q: Como posso obter licença temporária para Aspose.Tasks?**  
A: Obtenha uma licença temporária **[aqui](https://purchase.aspose.com/temporary-license/)**.

**Q: Precisa de ajuda ou tem perguntas específicas?**  
A: Visite o fórum de suporte do Aspose.Tasks **[aqui](https://forum.aspose.com/c/tasks/15)**.

---

**Última atualização:** 2026-09-09  
**Testado com:** Aspose.Tasks for Java 24.11 (latest at time of writing)  
**Autor:** Aspose

## Tutoriais relacionados

- [Criar dependências de tarefas de gerenciamento de projetos no Aspose.Tasks](/tasks/java/task-links/create-task-link/)
- [Definir data de início do projeto e gerenciar tarefas pai e filho no Aspose.Tasks](/tasks/java/task-properties/parent-child-tasks/)
- [Criar projeto MPP Java – Alterar progresso da tarefa com Aspose.Tasks](/tasks/java/task-properties/change-progress/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}