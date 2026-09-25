---
date: 2026-09-25
description: Aprenda como recuperar códigos de moeda de arquivos MS Project usando
  Aspose.Tasks para Java – a maneira rápida de obter o código de moeda que os desenvolvedores
  Java precisam.
keywords:
- retrieve currency code java
- Aspose.Tasks Java
- MS Project currency
- read MS Project file
lastmod: 2026-09-25
linktitle: Gerenciar códigos de moeda no Aspose.Tasks
og_description: Recuperar código de moeda Java de arquivos MS Project usando Aspose.Tasks.
  Este guia mostra como ler o projeto, extrair o identificador de moeda ISO e aplicá-lo
  em aplicações Java.
og_image_alt: Screenshot of Java code extracting currency code from an MS Project
  file using Aspose.Tasks
og_title: Recuperar código de moeda Java do MS Project
schemas:
- author: Aspose
  dateModified: '2026-09-25'
  description: Learn how to retrieve currency codes from MS Project files using Aspose.Tasks
    for Java – the quick way to get currency code Java developers need.
  headline: Retrieve currency code java from MS Project with Aspose.Tasks
  type: TechArticle
- description: Learn how to retrieve currency codes from MS Project files using Aspose.Tasks
    for Java – the quick way to get currency code Java developers need.
  name: Retrieve currency code java from MS Project with Aspose.Tasks
  steps:
  - name: set up data directory
    text: Define the folder that contains your *.mpp* file. Adjust the path to match
      your environment so the runtime can locate the project file.
  - name: load the project file
    text: The `Project` class is Aspose.Tasks' top‑level object that represents a
      single MS Project file in memory. Creating an instance reads the file and builds
      an in‑memory model you can query.
  - name: retrieve currency code
    text: The `Prj.CURRENCY_CODE` constant identifies the property that stores the
      ISO currency identifier. Calling `prj.get(Prj.CURRENCY_CODE)` returns the three‑letter
      code in a single operation. The output will be the three‑letter ISO currency
      code (e.g., `USD`, `EUR`, `GBP`) that the project is configured
  - name: how to retrieve currency code in Java (additional context)
    text: Load your project, call `prj.get(Prj.CURRENCY_CODE)`, and store the result
      in a `String`. You can then pass this value to any financial service, reporting
      engine, or UI component that requires a currency identifier.
  - name: (optional) use the currency code
    text: 'Typical downstream scenarios include: - **Report generation** – prepend
      the code to cost columns (`USD 1,200`). - **API integration** – send the ISO
      code to payment gateways that demand a currency parameter. - **Data consolidation**
      – group multiple projects by currency for portfolio‑level analysis.'
  type: HowTo
- questions:
  - answer: Yes, the API reads multi‑level task hierarchies, resource pools, custom
      fields, and calendars without limitation.
    question: Can Aspose.Tasks handle complex project structures?
  - answer: Absolutely. It supports MPP, XML, XER, and other formats from Project
      98 through the latest Office releases.
    question: Is Aspose.Tasks compatible with different versions of MS Project files?
  - answer: Comprehensive API reference, code examples, and dedicated technical support
      are available on the Aspose website.
    question: Does Aspose.Tasks provide documentation and support?
  - answer: A free trial is offered so you can evaluate all features, including currency
      code extraction.
    question: Can I try Aspose.Tasks before purchasing?
  - answer: Temporary licenses are available from the [website](https://purchase.aspose.com/temporary-license/).
    question: Where can I obtain a temporary license for evaluation?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- retrieve currency
- Aspose.Tasks
- Java project automation
- MS Project
title: Recuperar código de moeda Java do MS Project com Aspose.Tasks
url: /pt/java/currency/currency-codes/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Recuperar código de moeda java do MS Project com Aspose.Tasks

## Introdução
Neste tutorial você aprenderá **como recuperar o código de moeda java** de um arquivo MS Project usando a API Aspose.Tasks para Java. Seja para gerar relatórios financeiros multimoeda, consolidar projetos em diferentes regiões ou simplesmente exibir o símbolo monetário correto em um sistema downstream, os passos abaixo levarão você da configuração do ambiente à chamada de uma única linha que devolve o identificador ISO da moeda. Ao final do guia você estará confortável em carregar qualquer formato de arquivo Project suportado e extrair o código de moeda de três letras, como `USD`, `EUR` ou `GBP`.

## Respostas rápidas
- **O que a API faz?** Lê arquivos MS Project e expõe propriedades como o código da moeda.  
- **Qual linguagem é usada?** Java, via a biblioteca Aspose.Tasks para Java.  
- **Preciso de licença?** Um teste gratuito funciona para desenvolvimento; uma licença comercial é necessária para produção.  
- **Posso recuperar o código em uma linha?** Sim—`prj.get(Prj.CURRENCY_CODE)` devolve a string do código da moeda instantaneamente.  
- **É compatível com todas as versões do Project?** Aspose.Tasks suporta mais de 20 formatos de entrada, incluindo arquivos legados MPP, XML e XER.

## O que significa ler um arquivo ms project?
Ler um arquivo MS Project significa abrir programaticamente um *.mpp* (ou qualquer outro formato suportado, como XML ou XER) e acessar suas estruturas de dados internas. Essas estruturas incluem tarefas, recursos, calendários, tabelas de custos e configurações financeiras. Ao analisar o arquivo, você pode extrair informações sem iniciar o Microsoft Project, possibilitando relatórios automatizados, migrações e fluxos de integração.

## Por que usar Aspose.Tasks para ler arquivos msproject?
Aspose.Tasks oferece uma solução pura‑Java que elimina a necessidade de interop COM ou de uma instalação local do Microsoft Project. Suporta mais de 20 formatos de arquivo, pode lidar com projetos com milhares de tarefas usando menos de 100 MB de memória e fornece um modelo de objetos rico. O acesso direto a constantes como `Prj.CURRENCY_CODE` permite recuperar informações de moeda instantaneamente e de forma confiável.

## Pré‑requisitos
Antes de mergulharmos no código, certifique‑se de que você tem o seguinte:

### Kit de desenvolvimento Java (JDK) instalado
É necessário um JDK recente (11 ou superior). Baixe-o no site oficial da Oracle: [aqui](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html).

### Biblioteca Aspose.Tasks para Java
Obtenha os binários mais recentes do Aspose.Tasks para Java e adicione‑os ao classpath do seu projeto. A documentação completa e os links de download estão disponíveis [aqui](https://reference.aspose.com/tasks/java/).

## Importar pacotes
A classe `Project` e as constantes `Prj` vivem no namespace `com.aspose.tasks`. Importe‑as no topo do seu arquivo fonte Java:

```java
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
```

## Guia passo a passo

### Etapa 1: configurar diretório de dados
Defina a pasta que contém seu arquivo *.mpp*. Ajuste o caminho para corresponder ao seu ambiente, de modo que o tempo de execução possa localizar o arquivo do projeto.

```java
String dataDir = "Your Data Directory";
```

### Etapa 2: carregar o arquivo do projeto
A classe `Project` é o objeto de nível superior do Aspose.Tasks que representa um único arquivo MS Project na memória. Criar uma instância lê o arquivo e constrói um modelo em memória que pode ser consultado.

```java
Project prj = new Project(dataDir + "project.mpp");
```

### Etapa 3: recuperar o código da moeda
A constante `Prj.CURRENCY_CODE` identifica a propriedade que armazena o identificador ISO da moeda. Chamar `prj.get(Prj.CURRENCY_CODE)` devolve o código de três letras em uma única operação.

```java
System.out.println(prj.get(Prj.CURRENCY_CODE));
```
A saída será o código ISO de três letras (por exemplo, `USD`, `EUR`, `GBP`) que o projeto está configurado para usar.

### Etapa 4: como recuperar o código da moeda em Java (contexto adicional)
Carregue seu projeto, chame `prj.get(Prj.CURRENCY_CODE)` e armazene o resultado em uma `String`. Você pode então passar esse valor para qualquer serviço financeiro, mecanismo de relatório ou componente de UI que exija um identificador de moeda.

### Etapa 5: (opcional) usar o código da moeda
Cenários downstream típicos incluem:

- **Geração de relatórios** – prefixar o código nas colunas de custo (`USD 1.200`).  
- **Integração de API** – enviar o código ISO para gateways de pagamento que exigem um parâmetro de moeda.  
- **Consolidação de dados** – agrupar múltiplos projetos por moeda para análise em nível de portfólio.

## Problemas comuns e soluções
| Problema | Motivo | Solução |
|----------|--------|---------|
| **Saída nula** | O arquivo do projeto não define uma moeda (padrão é vazio). | Defina a moeda no Microsoft Project ou atribua‑a via `prj.set(Prj.CURRENCY_CODE, "USD");` antes da leitura. |
| **Arquivo não encontrado** | Caminho `dataDir` incorreto. | Verifique o caminho e assegure‑se de que o nome do arquivo corresponde exatamente, incluindo diferenciação de maiúsculas e minúsculas. |
| **Versão de arquivo não suportada** | Arquivo *.mpp* muito antigo ou corrompido. | Atualize para a versão mais recente do Aspose.Tasks ou converta o arquivo para um formato mais novo no Microsoft Project primeiro. |

## Perguntas frequentes

**P: O Aspose.Tasks pode lidar com estruturas de projeto complexas?**  
R: Sim, a API lê hierarquias de tarefas multinível, pools de recursos, campos personalizados e calendários sem limitação.

**P: O Aspose.Tasks é compatível com diferentes versões de arquivos MS Project?**  
R: Absolutamente. Suporta MPP, XML, XER e outros formatos do Project 98 até as versões mais recentes do Office.

**P: O Aspose.Tasks fornece documentação e suporte?**  
R: Referência completa da API, exemplos de código e suporte técnico dedicado estão disponíveis no site da Aspose.

**P: Posso experimentar o Aspose.Tasks antes de comprar?**  
R: Um teste gratuito é oferecido para que você avalie todos os recursos, incluindo a extração do código de moeda.

**P: Onde posso obter uma licença temporária para avaliação?**  
R: Licenças temporárias estão disponíveis no [site](https://purchase.aspose.com/temporary-license/).

---

**Última atualização:** 2026-09-25  
**Testado com:** Aspose.Tasks para Java (versão mais recente)  
**Autor:** Aspose

## Tutoriais relacionados

- [Propriedades do Project Java – Ler Metadados com Aspose.Tasks](/tasks/java/project-properties/)
- [Como Ler Informações do Projeto do Microsoft Project com Aspose.Tasks para Java](/tasks/java/project-properties/read-project-info/)
- [Recuperar Códigos de Estrutura do MS Project no Aspose.Tasks](/tasks/java/project-file-operations/retrieve-outline-codes/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}