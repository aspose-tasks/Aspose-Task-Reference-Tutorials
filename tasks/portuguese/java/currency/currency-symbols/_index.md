---
date: 2026-09-20
description: Aprenda a extrair o símbolo de moeda mpp e atualizar as propriedades
  do projeto usando Aspose.Tasks para Java. Altere e recupere o símbolo em apenas
  algumas linhas de código.
keywords:
- extract currency symbol mpp
- read project properties java
- retrieve currency symbol java
lastmod: 2026-09-20
linktitle: Extrair símbolo de moeda mpp usando Aspose.Tasks para Java
og_description: Aprenda a extrair o símbolo de moeda mpp e atualizar as propriedades
  do projeto usando Aspose.Tasks para Java. Rápido, confiável e pronto para produção.
og_image_alt: 'Guide: extract currency symbol mpp using Aspose.Tasks Java'
og_title: Como extrair o símbolo de moeda mpp com Aspose.Tasks Java
schemas:
- author: Aspose
  dateModified: '2026-09-20'
  description: Learn how to extract currency symbol mpp and update project properties
    using Aspose.Tasks for Java. Change and retrieve the symbol in just a few lines
    of code.
  headline: How to extract currency symbol mpp with Aspose.Tasks Java
  type: TechArticle
- description: Learn how to extract currency symbol mpp and update project properties
    using Aspose.Tasks for Java. Change and retrieve the symbol in just a few lines
    of code.
  name: How to extract currency symbol mpp with Aspose.Tasks Java
  steps:
  - name: '**Java Development Kit (JDK)** – version 8 or higher.'
    text: '**Java Development Kit (JDK)** – version 8 or higher.'
  - name: '**Aspose.Tasks for Java** – download the latest JAR from the [Aspose.Tasks
      download page](https://releases.aspose.com/tasks/java/).'
    text: '**Aspose.Tasks for Java** – download the latest JAR from the [Aspose.Tasks
      download page](https://releases.aspose.com/tasks/java/).'
  - name: A valid **project.mpp** file placed in a folder you can reference from your
      code.
    text: A valid **project.mpp** file placed in a folder you can reference from your
      code.
  type: HowTo
- questions:
  - answer: Yes, Aspose.Tasks lets you edit tasks, resources, assignments, calendars,
      and many more project properties.
    question: Can I manipulate other project attributes besides currency symbols using
      Aspose.Tasks?
  - answer: Absolutely. It supports MPP, MPT, and XML formats from Project 98 up to
      the latest releases.
    question: Is Aspose.Tasks compatible with different versions of MS Project files?
  - answer: Comprehensive API docs, code examples, and a dedicated support forum are
      available on the Aspose.Tasks website.
    question: Does Aspose.Tasks offer documentation and support for developers?
  - answer: Yes – a fully functional free trial can be downloaded from the [Aspose
      website](https://purchase.aspose.com/buy).
    question: Can I try Aspose.Tasks before purchasing it?
  - answer: Temporary licenses are provided on the [Aspose temporary‑license page](https://purchase.aspose.com/temporary-license/)
      for evaluation purposes.
    question: How can I obtain a temporary license for Aspose.Tasks?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- extract currency symbol
- Aspose.Tasks
- Java project properties
- MPP handling
title: Como extrair o símbolo de moeda mpp com Aspose.Tasks Java
url: /pt/java/currency/currency-symbols/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Extrair símbolo de moeda mpp usando Aspose.Tasks para Java

## Introdução
Neste tutorial você aprenderá a trabalhar com **propriedades de projeto Java** — especificamente como **extrair símbolo de moeda mpp** de um arquivo Microsoft Project (MPP) e como **alterar símbolo de moeda java** ou **recuperar símbolo de moeda java** usando a biblioteca Aspose.Tasks. Seja você quem está construindo uma ferramenta de relatórios financeiros, integrando dados do Project em um sistema ERP, ou simplesmente precisa exibir o símbolo de moeda correto na sua interface, dominar esta tarefa pequena, porém essencial, tornará suas aplicações Java mais robustas e amigáveis ao usuário.

## Respostas rápidas
- **O que significa “extrair símbolo de moeda mpp”?** Significa ler o símbolo de moeda armazenado em um arquivo MPP (Microsoft Project).  
- **Qual biblioteca lida com isso?** Aspose.Tasks para Java fornece uma API simples para a tarefa.  
- **Preciso de licença?** Um teste gratuito funciona para desenvolvimento; uma licença comercial é necessária para produção.  
- **Quanto tempo leva?** Com o código abaixo, você pode obter o símbolo em menos de um minuto.  
- **Posso também alterar o símbolo?** Sim — você pode definir um novo valor usando a mesma propriedade `Prj.CURRENCY_SYMBOL`.

## O que é “extrair símbolo de moeda mpp”?
Extrair o símbolo de moeda de um arquivo MPP significa ler a cadeia de um único caractere que o Microsoft Project armazena no cabeçalho do arquivo para representar a unidade monetária do projeto. Essa operação permite que você exiba o símbolo correto (como $, €, £) em suas próprias aplicações sem codificar um valor fixo.

## Por que atualizar o símbolo de moeda nas propriedades do projeto Java?
Atualizar o símbolo de moeda permite que você localize relatórios, faturas e painéis em tempo real. Empresas que executam projetos em várias regiões podem trocar o símbolo em um único passo, evitando a necessidade de duplicar todo o arquivo do projeto. Aspose.Tasks pode modificar a propriedade em memória e salvar o arquivo novamente, suportando projetos com até 2.000 tarefas sem impacto perceptível de desempenho.

## Pré‑requisitos
Antes de começarmos, certifique‑se de que você tem:

1. **Java Development Kit (JDK)** – versão 8 ou superior.  
2. **Aspose.Tasks para Java** – baixe o JAR mais recente na [página de download do Aspose.Tasks](https://releases.aspose.com/tasks/java/).  
3. Um arquivo **project.mpp** válido colocado em uma pasta que você possa referenciar a partir do seu código.

## Importar pacotes
Primeiro, importe as classes que precisaremos para trabalhar com arquivos Project.

```java
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
```

## Etapa 1: definir o diretório de dados
Informe à aplicação onde seu arquivo *.mpp* está localizado.

```java
String dataDir = "Your Data Directory";
```

> **Dica:** Use `System.getProperty("user.dir")` para construir um caminho absoluto que funcione em qualquer máquina.

## Etapa 2: carregar o arquivo MS Project
`Project` é o objeto de nível superior do Aspose.Tasks que representa um único arquivo Microsoft Project na memória. Criar esse objeto carrega a estrutura do arquivo sem exigir que o Microsoft Project esteja instalado.

```java
Project project = new Project(dataDir + "project.mpp");
```

## Etapa 3: recuperar (e opcionalmente alterar) o símbolo de moeda
`Prj.CURRENCY_SYMBOL` é a chave de propriedade que armazena o símbolo de moeda. Lê‑lo devolve o símbolo atual; atribuir uma nova string atualiza a definição de moeda do projeto.

```java
// Retrieve the current currency symbol
System.out.println(project.get(Prj.CURRENCY_SYMBOL));

// Example of changing it (uncomment to use)
// project.set(Prj.CURRENCY_SYMBOL, "€");
// System.out.println("New symbol: " + project.get(Prj.CURRENCY_SYMBOL));
```

A chamada `System.out.println` imprime o símbolo (por exemplo, `$`) no console, confirmando que a extração foi bem‑sucedida.

## Problemas comuns & como corrigi‑los
| Sintoma | Causa provável | Solução |
|---------|----------------|----------|
| `NullPointerException` em `project.get(...)` | Caminho do arquivo errado ou arquivo não encontrado | Verifique `dataDir` e o nome do arquivo; use `new File(dataDir).exists()` para depurar |
| Símbolo inesperado (ex.: `?`) | Projeto criado com localidade não padrão | Certifique‑se de que o arquivo MPP de origem realmente define um símbolo de moeda; você pode definir um programaticamente como mostrado acima |
| Erro de licença | Uso da versão de avaliação sem um arquivo de licença válido | Carregue sua licença com `License license = new License(); license.setLicense("Aspose.Tasks.Java.lic");` antes de criar o objeto `Project` |

## Perguntas frequentes

**P: Posso manipular outros atributos do projeto além de símbolos de moeda usando Aspose.Tasks?**  
R: Sim, o Aspose.Tasks permite editar tarefas, recursos, atribuições, calendários e muitas outras propriedades do projeto.

**P: O Aspose.Tasks é compatível com diferentes versões de arquivos MS Project?**  
R: Absolutamente. Ele suporta formatos MPP, MPT e XML do Project 98 até as versões mais recentes.

**P: O Aspose.Tasks oferece documentação e suporte para desenvolvedores?**  
R: Documentação completa da API, exemplos de código e um fórum de suporte dedicado estão disponíveis no site do Aspose.Tasks.

**P: Posso experimentar o Aspose.Tasks antes de comprá‑lo?**  
R: Sim — um teste gratuito totalmente funcional pode ser baixado no [site da Aspose](https://purchase.aspose.com/buy).

**P: Como posso obter uma licença temporária para o Aspose.Tasks?**  
R: Licenças temporárias são fornecidas na [página de licença temporária da Aspose](https://purchase.aspose.com/temporary-license/) para fins de avaliação.

---

**Última atualização:** 2026-09-20  
**Testado com:** Aspose.Tasks para Java 24.12 (mais recente no momento da escrita)  
**Autor:** Aspose

## Tutoriais relacionados

- [Propriedades do Projeto Java – Ler Metadados com Aspose.Tasks](/tasks/java/project-properties/)
- [Como Recuperar a Moeda do MS Project com Aspose.Tasks](/tasks/java/currency/currency-codes/)
- [Definir Data de Início do Projeto no MS Project usando Aspose.Tasks para Java](/tasks/java/project-properties/write-project-info/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}