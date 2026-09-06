---
date: 2026-08-24
description: Aprenda a adicionar recurso ao MS Project, definir a taxa padrão e outras
  propriedades de recurso no MS Project usando Aspose.Tasks para Java e gerenciar
  recursos de forma eficiente.
keywords:
- add resource ms project
- set resource rate
- manage ms project resources
- create ms project file
lastmod: 2026-08-24
linktitle: Definir propriedades de recurso no Aspose.Tasks
og_description: Adicionar recurso ao MS Project e definir taxa padrão usando Aspose.Tasks
  para Java. Aprenda os pré-requisitos, código passo a passo e solução de problemas
  neste guia conciso.
og_image_alt: Screenshot of Aspose.Tasks Java code setting resource rates
og_title: Adicionar recurso ao MS Project e definir taxa com Aspose.Tasks (Java)
schemas:
- author: Aspose
  dateModified: '2026-08-24'
  description: Learn how to add resource ms project, set standard rate and other resource
    properties in MS Project using Aspose.Tasks for Java, and manage resources efficiently.
  headline: How to add resource ms project with Aspose.Tasks
  type: TechArticle
- description: Learn how to add resource ms project, set standard rate and other resource
    properties in MS Project using Aspose.Tasks for Java, and manage resources efficiently.
  name: How to add resource ms project with Aspose.Tasks
  steps:
  - name: Install JDK 8 or newer. You can download it from the [Oracle website](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html).
    text: Install JDK 8 or newer. You can download it from the [Oracle website](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html).
  - name: Choose an IDE such as IntelliJ IDEA, Eclipse, or NetBeans and configure
      it for Java development.
    text: Choose an IDE such as IntelliJ IDEA, Eclipse, or NetBeans and configure
      it for Java development.
  - name: Download the latest Aspose.Tasks for Java package from the [download page](https://releases.aspose.com/tasks/java/).
    text: Download the latest Aspose.Tasks for Java package from the [download page](https://releases.aspose.com/tasks/java/).
  - name: Add the JAR files to your project’s classpath or declare the Maven/Gradle
      dependency as shown in the product documentation.
    text: Add the JAR files to your project’s classpath or declare the Maven/Gradle
      dependency as shown in the product documentation.
  type: HowTo
- questions:
  - answer: Yes, it supports all major Project formats, including large files with
      thousands of tasks and resources, preserving every field without data loss.
    question: Can Aspose.Tasks for Java handle complex MS Project files?
  - answer: Yes, you can access a free trial of Aspose.Tasks for Java from the [Aspose.Tasks
      free trial page](https://releases.aspose.com/).
    question: Is there a free trial available?
  - answer: You can seek assistance on the [support forum](https://forum.aspose.com/c/tasks/15).
    question: Where can I get support for Aspose.Tasks for Java?
  - answer: A temporary license is available from the [temporary license page](https://purchase.aspose.com/temporary-license/).
    question: How do I obtain a temporary license for evaluation?
  - answer: Purchase a full license from the [purchase page](https://purchase.aspose.com/buy).
    question: Where can I purchase a licensed version?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- aspose tasks
- java project automation
- ms project resources
- resource rate
title: Como adicionar recurso ao MS Project com Aspose.Tasks
url: /pt/java/resource-management/set-resource-properties/
weight: 20
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Adicionar recurso ms project e definir taxa no Aspose.Tasks

## Introdução
Se você está desenvolvendo aplicações Java que precisam ler ou gravar arquivos Microsoft Project, **adicionar um recurso ms project** e configurar sua taxa padrão é uma tarefa rotineira, porém essencial. Neste guia você verá como criar um objeto `Project`, adicionar um recurso e definir tanto as taxas padrão quanto as de hora extra usando Aspose.Tasks para Java. Ao final, você será capaz de automatizar cálculos de custo e manter seus cronogramas de projeto atualizados sem precisar que o Microsoft Project esteja instalado.

## Respostas rápidas
- **Qual classe representa um arquivo Project?** `Project`
- **Qual chamada adiciona um novo recurso?** `project.getResources().add()`
- **Como definir a taxa padrão?** `rsc.set(Rsc.STANDARD_RATE, BigDecimal.valueOf(...))`
- **É necessária uma licença para uso em produção?** Sim, você deve carregar uma licença válida do Aspose.Tasks.
- **Quais versões do Java são suportadas?** Java 8 e posteriores (Java 17+ recomendado).

## O que é “definir taxa padrão”?
A operação *definir taxa padrão* atribui um custo horário padrão a um recurso. Essa taxa é usada pelos gerentes de projeto para calcular despesas de mão‑de‑obra, gerar relatórios de custo e prever orçamentos, garantindo que os cálculos reflitam o preço esperado do trabalho realizado por cada recurso ao longo do ciclo de vida do projeto.

## Por que definir taxas com Aspose.Tasks?
Aspose.Tasks pode processar **mais de 50 formatos de entrada e saída**, incluindo MPP, MPX, XML e arquivos Primavera, e lida com projetos de centenas de páginas sem carregar todo o arquivo na memória. Isso permite processamento em lote de alta performance em servidores Windows, Linux ou macOS, reduzindo o esforço manual em até 90 % em cenários típicos de automação.

## Pré-requisitos
Antes de começar, certifique‑se de que os itens a seguir estejam prontos:

### Configuração do ambiente de desenvolvimento Java
1. Instale o JDK 8 ou mais recente. Você pode baixá‑lo no [Oracle website](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html).  
2. Escolha uma IDE como IntelliJ IDEA, Eclipse ou NetBeans e configure‑a para desenvolvimento Java.

### Instalação do Aspose.Tasks para Java
1. Baixe o pacote mais recente do Aspose.Tasks para Java na [download page](https://releases.aspose.com/tasks/java/).  
2. Adicione os arquivos JAR ao classpath do seu projeto ou declare a dependência Maven/Gradle conforme mostrado na documentação do produto.

## Importar pacotes
Importe as classes principais do Aspose.Tasks que você precisará. Esta etapa fornece acesso aos tipos `Project`, `Resource` e `Rsc` usados mais adiante.

```java
import com.aspose.tasks.Project;
import com.aspose.tasks.Resource;
import com.aspose.tasks.Rsc;
import java.math.BigDecimal;
```

## Etapa 1: criar um objeto project
A classe `Project` é o objeto de nível superior que representa um arquivo MS Project inteiro na memória. Instanciá‑la cria um projeto em branco que pode ser preenchido com tarefas, recursos e outros dados.

```java
Project project = new Project();
```

## Etapa 2: adicionar um recurso (add resource ms project)
A classe `Resource` modela um único recurso do projeto, como uma pessoa, equipamento ou material. Adicionar um recurso via `project.getResources().add()` retorna uma instância `Resource` não nula pronta para configuração de propriedades.

```java
Resource rsc = project.getResources().add("Rsc");
```

## Etapa 3: definir propriedades do recurso (como definir taxas)
O enum `Rsc` contém constantes para campos de recurso como `STANDARD_RATE` e `OVERTIME_RATE`.  
Você define as taxas padrão e de hora extra chamando `set` no objeto `Resource` com os valores apropriados do enum `Rsc`. As taxas são armazenadas como `BigDecimal` para preservar a precisão monetária.

```java
// Set standard rate for the resource
rsc.set(Rsc.STANDARD_RATE, BigDecimal.valueOf(15));
// Set overtime rate for the resource
rsc.set(Rsc.OVERTIME_RATE, BigDecimal.valueOf(20));
```

## Problemas comuns e soluções
| Problema | Por que acontece | Solução |
|----------|------------------|---------|
| `NullPointerException` ao chamar `set` | O recurso não foi adicionado corretamente. | Certifique‑se de que `project.getResources().add()` retorne um `Resource` não nulo. |
| As taxas aparecem como 0 no arquivo salvo | Usando `int` em vez de `BigDecimal`. | Sempre use `BigDecimal.valueOf()` para valores monetários. |
| Licença não encontrada | Arquivo de licença não carregado antes de criar `Project`. | Carregue a licença (`License license = new License(); license.setLicense("Aspose.Tasks.lic");`) no início do programa. |

## Conclusão
Agora você sabe como **adicionar recurso ms project**, criar um objeto `Project` e **definir taxas padrão e de hora extra** usando Aspose.Tasks para Java. Essa capacidade permite automatizar cálculos de custo, gerar relatórios personalizados e gerenciar totalmente recursos do MS Project a partir de qualquer aplicação Java.

## Perguntas frequentes
**P: O Aspose.Tasks para Java pode lidar com arquivos MS Project complexos?**  
R: Sim, ele suporta todos os principais formatos do Project, incluindo arquivos grandes com milhares de tarefas e recursos, preservando todos os campos sem perda de dados.

**P: Há uma versão de avaliação gratuita disponível?**  
R: Sim, você pode acessar uma avaliação gratuita do Aspose.Tasks para Java na [Aspose.Tasks free trial page](https://releases.aspose.com/).

**P: Onde posso obter suporte para Aspose.Tasks para Java?**  
R: Você pode buscar assistência no [support forum](https://forum.aspose.com/c/tasks/15).

**P: Como obtenho uma licença temporária para avaliação?**  
R: Uma licença temporária está disponível na [temporary license page](https://purchase.aspose.com/temporary-license/).

**P: Onde posso comprar uma versão licenciada?**  
R: Compre uma licença completa na [purchase page](https://purchase.aspose.com/buy).

---

**Last Updated:** 2026-08-24  
**Tested With:** Aspose.Tasks for Java 24.12 (latest at time of writing)  
**Author:** Aspose

## Tutoriais Relacionados

- [Como Criar Recursos – Gerenciamento de Recursos com Aspose.Tasks para Java](/tasks/java/resource-management/)
- [Adicionar recurso ao projeto com Aspose.Tasks para Java](/tasks/java/resource-management/create-resources/)
- [Como Adicionar Recurso ao Projeto e Manipular Propriedades de Atraso de Nivelamento no Aspose.Tasks](/tasks/java/resource-assignments/leveling-delay-properties/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}