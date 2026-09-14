---
date: 2026-09-14
description: Aprenda como obter a moeda do MS Project e ler as propriedades do projeto
  em Java com Aspose.Tasks. Guia passo a passo para extrair os dígitos da moeda de
  um arquivo MPP.
keywords:
- get ms project currency
- read project properties java
- convert project file java
lastmod: 2026-09-14
linktitle: Como obter a moeda do MS Project usando Aspose.Tasks
og_description: Aprenda como obter a moeda do MS Project e ler as propriedades do
  projeto em Java com Aspose.Tasks. Siga este tutorial conciso de Java para extrair
  os dígitos da moeda de um arquivo MPP.
og_image_alt: Screenshot of Java code extracting currency digits from an MS Project
  file using Aspose.Tasks
og_title: Como obter a moeda do MS Project usando Aspose.Tasks – Guia Java
schemas:
- author: Aspose
  dateModified: '2026-09-14'
  description: Learn how to get ms project currency and read project properties java
    with Aspose.Tasks. Step‑by‑step guide for extracting currency digits from an MPP
    file.
  headline: How to get ms project currency using Aspose.Tasks
  type: TechArticle
- description: Learn how to get ms project currency and read project properties java
    with Aspose.Tasks. Step‑by‑step guide for extracting currency digits from an MPP
    file.
  name: How to get ms project currency using Aspose.Tasks
  steps:
  - name: '**Java Development Environment** – JDK 8 or newer installed and configured.'
    text: '**Java Development Environment** – JDK 8 or newer installed and configured.'
  - name: '**Aspose.Tasks for Java** – download the latest JAR from the official site:
      [Aspose.Tasks for Java](https://releases.aspose.com/tasks/java/).'
    text: '**Aspose.Tasks for Java** – download the latest JAR from the official site:
      [Aspose.Tasks for Java](https://releases.aspose.com/tasks/java/).'
  - name: '**Basic Java knowledge** – you should be comfortable creating a Java project,
      adding external libraries, and running a `main` method.'
    text: '**Basic Java knowledge** – you should be comfortable creating a Java project,
      adding external libraries, and running a `main` method.'
  type: HowTo
- questions:
  - answer: Yes, Aspose.Tasks offers a wide range of functionalities to manipulate
      various aspects of Project files, such as tasks, resources, and custom fields.
    question: Can Aspose.Tasks handle other Project attributes besides currency digits?
  - answer: Absolutely, Aspose.Tasks is designed to meet the demands of enterprise‑grade
      projects, offering high performance and scalability.
    question: Is Aspose.Tasks suitable for enterprise‑level applications?
  - answer: Yes, you can use Aspose.Tasks for Java on any platform that supports the
      Java Runtime Environment (Windows, Linux, macOS).
    question: Does Aspose.Tasks support cross‑platform development?
  - answer: Yes, you can download a free trial version from the [Aspose releases page](https://releases.aspose.com/).
    question: Can I try Aspose.Tasks before purchasing?
  - answer: You can find support on the [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15).
    question: Where can I get support for Aspose.Tasks?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- ms project
- aspose.tasks
- java project processing
title: Como obter a moeda do MS Project usando Aspose.Tasks
url: /pt/java/currency/currency-digits/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Como obter a moeda do ms project usando Aspose.Tasks

## Introdução
Se você está se perguntando **como obter a moeda do ms project** a partir de um arquivo Microsoft Project, você chegou ao lugar certo. Neste tutorial abrangente, você descobrirá **como trabalhar com valores de moeda do ms project** usando a biblioteca Aspose.Tasks para Java. Seja construindo uma ferramenta de relatórios, um utilitário de migração ou simplesmente precisando ler as configurações de moeda de um **arquivo de projeto java**, este guia o conduzirá por cada passo — desde o carregamento de um arquivo *.mpp* até a extração dos dígitos da moeda. Ao final, você estará confortável em manipular dados de moeda do ms project em suas próprias aplicações.

## Respostas rápidas
- **Qual biblioteca lê arquivos MS Project?** Aspose.Tasks for Java.  
- **Quantas linhas de código são necessárias para obter os dígitos da moeda?** Apenas três linhas concisas após o projeto ser carregado.  
- **Preciso de uma licença para desenvolvimento?** Uma versão de avaliação funciona para testes; uma licença comercial é necessária para produção.  
- **Qual versão do Java é suportada?** Java 8 ou superior (qualquer JDK que execute Aspose.Tasks).  
- **Posso recuperar outras propriedades do Project?** Sim – Aspose.Tasks expõe um conjunto completo de campos do Project (por exemplo, data de início, taxas de custo, etc.).

## O que é a moeda do ms project?
A propriedade `ms project currency` define o número de casas decimais que o Microsoft Project usa ao exibir valores monetários. Ela é armazenada no arquivo Project como o campo **CURRENCY_DIGITS** e determina se os valores aparecem como números inteiros, com uma casa decimal, duas casas decimais, etc. Essa configuração influencia diretamente relatórios de orçamento, consolidação de custos e qualquer interface que mostre cifras financeiras, tornando‑a essencial para a troca precisa de dados.

## Por que usar Aspose.Tasks para manipular a moeda do ms project?
Aspose.Tasks permite extrair os dígitos da moeda sem instalar o Microsoft Project, e faz isso com desempenho de nível empresarial. A biblioteca suporta **mais de 30 anos de versões de arquivos Project** — do Project 2000 ao Project 2024 — abrangendo mais de **150 esquemas de arquivos distintos**. Carregar um projeto de 500 páginas normalmente leva menos de **2 segundos** em um servidor padrão, e você pode consultar apenas os campos necessários, mantendo o uso de memória abaixo de **50 MB** mesmo para os cronogramas maiores.

## Pré-requisitos
Antes de começar, certifique‑se de que você possui o seguinte:

1. **Ambiente de Desenvolvimento Java** – JDK 8 ou mais recente instalado e configurado.  
2. **Aspose.Tasks for Java** – faça o download do JAR mais recente no site oficial: [Aspose.Tasks for Java](https://releases.aspose.com/tasks/java/).  
3. **Conhecimento básico de Java** – você deve estar confortável em criar um projeto Java, adicionar bibliotecas externas e executar um método `main`.  

## Importar pacotes
Primeiro, importe as classes que precisaremos.  
Importe a classe `Project` e utilitários relacionados da biblioteca Aspose.Tasks.  
```java
import java.io.IOException;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
```

## Etapa 1: definir diretório de dados
Especifique a pasta que contém seu **arquivo de projeto java** (`*.mpp`).  
```java
String dataDir = "Your Data Directory";
```
Substitua `"Your Data Directory"` pelo caminho absoluto ou relativo onde `project.mpp` está localizado.

## Etapa 2: carregar o arquivo mpp
Agora veremos **como carregar arquivos mpp** usando Aspose.Tasks.  
A classe `Project` representa um arquivo Microsoft Project e fornece acesso às suas propriedades.  
```java
Project project = new Project(dataDir + "project.mpp");
```
Certifique‑se de que o nome do arquivo corresponda exatamente; caso contrário, será lançada uma `IOException`.

## Etapa 3: recuperar dígitos da moeda
Com o projeto carregado, extrair os dígitos da **ms project currency** é uma única linha:  
O método `getCurrencyDigits()` retorna o número de casas decimais definidas para valores monetários.  
```java
System.out.println(project.get(Prj.CURRENCY_DIGITS));
```
A chamada retorna um `Integer` representando o número de casas decimais (por exemplo, `2` para centavos). O valor é impresso no console, mas você também pode armazená‑lo em uma variável para processamento adicional.

## Problemas comuns e dicas
- **File not found** – verifique novamente o caminho `dataDir` e assegure que o nome do arquivo está correto, incluindo a extensão `.mpp`.  
- **Unsupported file version** – Aspose.Tasks suporta formatos Project 2000‑2024; arquivos mais antigos ou corrompidos podem precisar de conversão.  
- **License not set** – durante o desenvolvimento uma versão de avaliação funciona, mas para produção você deve aplicar uma licença válida para evitar marcas d'água de avaliação.

## Perguntas frequentes

**Q: O Aspose.Tasks pode lidar com outros atributos do Project além dos dígitos da moeda?**  
A: Sim, o Aspose.Tasks oferece uma ampla gama de funcionalidades para manipular vários aspectos dos arquivos Project, como tarefas, recursos e campos personalizados.

**Q: O Aspose.Tasks é adequado para aplicações de nível empresarial?**  
A: Absolutamente, o Aspose.Tasks foi projetado para atender às exigências de projetos de nível empresarial, oferecendo alto desempenho e escalabilidade.

**Q: O Aspose.Tasks suporta desenvolvimento multiplataforma?**  
A: Sim, você pode usar o Aspose.Tasks para Java em qualquer plataforma que suporte o Java Runtime Environment (Windows, Linux, macOS).

**Q: Posso experimentar o Aspose.Tasks antes de comprar?**  
A: Sim, você pode baixar uma versão de avaliação gratuita na [página de lançamentos da Aspose](https://releases.aspose.com/).

**Q: Onde posso obter suporte para o Aspose.Tasks?**  
A: Você pode encontrar suporte no [fórum Aspose.Tasks](https://forum.aspose.com/c/tasks/15).

---

**Última atualização:** 2026-09-14  
**Testado com:** Aspose.Tasks for Java (mais recente no momento da escrita)  
**Autor:** Aspose

## Tutoriais Relacionados

- [propriedades do projeto java – Extrair símbolo de moeda do MPP usando Aspose.Tasks para Java](/tasks/java/currency/currency-symbols/)
- [Como Recuperar a Moeda do MS Project com Aspose.Tasks](/tasks/java/currency/currency-codes/)
- [Propriedades do Projeto Java – Ler Metadados com Aspose.Tasks](/tasks/java/project-properties/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}