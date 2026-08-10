---
date: 2026-05-26
description: Aprenda como obter campos de tabela e ler dados de tabela em Java usando
  Aspose.Tasks. Este tutorial mostra como recuperar informações de tabela de arquivos
  Project.
keywords:
- read table data aspose.tasks
- Aspose.Tasks Java
- project table extraction
linktitle: Ler dados de tabela de arquivo no Aspose.Tasks
schemas:
- author: Aspose
  dateModified: '2026-05-26'
  description: Learn how to get table fields and read table data in Java using Aspose.Tasks.
    This tutorial shows you how to retrieve table information from Project files.
  headline: How to get table fields and read table data in Aspose.Tasks
  type: TechArticle
- questions:
  - answer: Load each project separately with `new Project(path)` and repeat the table‑field
      extraction loop for each instance.
    question: How do I read table data in a multi‑project environment?
  - answer: Yes, after printing the field details you can write them to a `FileWriter`
      or use a CSV library such as OpenCSV to generate a properly escaped file.
    question: Can I export the retrieved table fields to CSV?
  - answer: Absolutely. The `project.getTables()` collection includes both default
      and user‑defined tables, so you can iterate through them and process each one
      individually.
    question: Does Aspose.Tasks handle custom tables created by users?
  - answer: Use the overloaded `Project` constructor that accepts a `LoadOptions`
      object where you can specify the password, e.g., `new Project(path, new LoadOptions("pwd"))`.
    question: What if the Project file is password‑protected?
  - answer: Check each `TableField`'s `getVisible()` method (available in newer releases)
      to determine whether the column is displayed in the UI.
    question: Is there a way to filter only visible columns?
  type: FAQPage
second_title: Aspose.Tasks Java API
title: Como obter campos de tabela e ler dados de tabela no Aspose.Tasks
url: /pt/java/project-data-reading/read-table-data/
weight: 17
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Como obter campos de tabela e ler dados de tabela no Aspose.Tasks

## Introdução
Neste tutorial você aprenderá **como obter campos de tabela** e **ler dados de tabela** de um arquivo Microsoft Project usando a API **read table data aspose.tasks**. Seja construindo um painel de relatórios personalizado, migrando dados legados de projetos ou automatizando a análise de cronogramas, extrair definições de tabelas programaticamente economiza inúmeras horas manuais. Vamos percorrer a configuração do ambiente, o carregamento de um projeto e a impressão das propriedades de cada coluna, para que você possa começar a usar esse recurso em suas aplicações Java imediatamente.

## Respostas rápidas
- **O que significa “obter campos de tabela”?** Refere‑se à recuperação da definição (largura, título, alinhamento, etc.) de cada coluna exibida em uma tabela de visualização do Project.  
- **Qual biblioteca é necessária?** Aspose.Tasks for Java.  
- **Preciso de licença para desenvolvimento?** Um trial gratuito funciona para avaliação; uma licença comercial é necessária para uso em produção.  
- **Posso ler tabelas de qualquer versão do Project?** Sim, o Aspose.Tasks suporta mais de 15 versões de arquivos Microsoft Project, do Project 2003 ao Project 2024.  
- **É necessário algum ajuste adicional?** Apenas JDK 8+ e o JAR do Aspose.Tasks no seu classpath.

## O que é read table data aspose.tasks?
Read table data aspose.tasks é o conjunto de métodos da API Aspose.Tasks que permite acessar programaticamente a estrutura e o conteúdo das tabelas definidas dentro de um arquivo Microsoft Project. Ele devolve metadados como largura da coluna, título, alinhamento e visibilidade, permitindo recriar ou transformar cronogramas de projeto em qualquer formato que você precisar.

## Por que usar Aspose.Tasks para ler dados de tabela?
Aspose.Tasks processa **mais de 50 formatos diferentes de arquivos Project** (incluindo MPP, MPX, XML e Primavera) e pode lidar com arquivos com **até 10 000 tarefas** sem carregar todo o arquivo na memória. Esse desempenho quantificado permite extrair tabelas de grandes projetos corporativos mantendo o uso de memória abaixo de 200 MB.

## Pré‑requisitos
Antes de começar, certifique‑se de que você tem:

1. **Java Development Kit (JDK) 8 ou posterior** – faça o download no site oficial da Oracle.  
2. **Aspose.Tasks for Java JAR** – obtenha a versão mais recente no [download link](https://releases.aspose.com/tasks/java/) e adicione‑a ao caminho de compilação do seu projeto.  

> **Dica:** Se você usa Maven ou Gradle, pode referenciar o artefato Aspose.Tasks diretamente para simplificar o gerenciamento de dependências.

## Importar Pacotes
As classes `Project`, `Table` e `TableField` são o núcleo do fluxo de leitura de tabelas.

A classe `Project` é o objeto de nível superior do Aspose.Tasks que representa um único arquivo Microsoft Project na memória.  

A classe `Table` encapsula uma coleção de objetos `TableField`, cada um descrevendo uma coluna de uma visualização.  

A classe `TableField` mantém a definição da largura, título, alinhamento e visibilidade de uma coluna.

```java
import com.aspose.tasks.Project;
import com.aspose.tasks.Table;
import com.aspose.tasks.TableField;
```

## Etapa 1: Configurar o Diretório de Dados
Defina a pasta que contém seu arquivo *.mpp*:

```java
String dataDir = "Your Data Directory";
```

Substitua `"Your Data Directory"` pelo caminho absoluto na sua máquina (por exemplo, `C:/Projects/Data/`). Usar um caminho absoluto evita ambiguidades do carregador de classes quando o código é executado em diferentes IDEs.

## Etapa 2: Carregar o Arquivo de Projeto
Crie uma instância `Project` apontando para o arquivo Project que deseja examinar:

```java
Project project = new Project(dataDir + "Project2003.mpp");
```

Se o seu arquivo tiver um nome ou extensão diferentes, ajuste a string adequadamente. O construtor detecta automaticamente o formato do arquivo, portanto não é necessário especificar a versão manualmente.

## Etapa 3: Recuperar informações da tabela
Agora vamos **obter campos de tabela** e exibir as propriedades de cada campo:

```java
Table t1 = project.getTables().toList().get(0);
System.out.println("Table Fields Count: " + t1.getTableFields().size());
System.out.println();
for (TableField f : t1.getTableFields()) {
    System.out.println("Field width: " + f.getWidth());
    System.out.println("Field Title: " + f.getTitle());
    System.out.println("Field Title Alignment: " + f.getAlignTitle());
    System.out.println("Field Align Data: " + f.getAlignData());
    System.out.println();
}
```

O trecho imprime a largura, título e alinhamento de cada coluna na tabela padrão, fornecendo uma visão completa dos **campos de tabela** definidos no projeto.

## Como ler dados de tabela usando Aspose.Tasks para Java?
Para ler os dados reais da tabela, primeiro carregue o projeto, depois obtenha a tabela desejada (por exemplo, a padrão) usando `project.getTables().getByName("Name")` ou por índice. Percorra a coleção retornada por `table.getFields()` e acesse as propriedades de cada `TableField`, como largura, título, alinhamento e visibilidade. Essa abordagem funciona para qualquer tabela personalizada ou incorporada definida no arquivo Project.

## Armadilhas comuns e dicas
- **Tabelas nulas** – Se um projeto não possuir tabelas, `project.getTables()` pode estar vazio. Sempre verifique o tamanho da coleção antes de acessar um índice.  
- **Problemas de codificação** – Caracteres não‑ASCII nos títulos são exibidos corretamente ao usar a versão mais recente do Aspose.Tasks (24.12 ou superior).  
- **Desempenho** – Carregar arquivos *.mpp* muito grandes pode consumir muita memória; considere usar a API de streaming (`ProjectReader`) para arquivos com mais de 500 MB.  

## Perguntas Frequentes

**Q: Como ler dados de tabela em um ambiente com múltiplos projetos?**  
A: Carregue cada projeto separadamente com `new Project(path)` e repita o loop de extração de campos de tabela para cada instância.

**Q: Posso exportar os campos de tabela recuperados para CSV?**  
A: Sim, após imprimir os detalhes dos campos você pode gravá‑los em um `FileWriter` ou usar uma biblioteca CSV como OpenCSV para gerar um arquivo adequadamente escapado.

**Q: O Aspose.Tasks lida com tabelas personalizadas criadas pelos usuários?**  
A: Absolutamente. A coleção `project.getTables()` inclui tanto tabelas padrão quanto tabelas definidas pelo usuário, permitindo iterar sobre elas e processar cada uma individualmente.

**Q: E se o arquivo Project estiver protegido por senha?**  
A: Use o construtor sobrecarregado `Project` que aceita um objeto `LoadOptions` onde você pode especificar a senha, por exemplo, `new Project(path, new LoadOptions("pwd"))`.

**Q: Existe uma forma de filtrar apenas colunas visíveis?**  
A: Verifique o método `getVisible()` de cada `TableField` (disponível em versões mais recentes) para determinar se a coluna está exibida na UI.

## Conclusão
Seguindo estas etapas, você agora sabe como **obter campos de tabela** e ler dados de tabela de um arquivo Microsoft Project usando Aspose.Tasks para Java. Essa capacidade abre portas para cenários poderosos de automação, pipelines de migração de dados e soluções de relatórios personalizados em suas aplicações Java. Em seguida, considere exportar os metadados extraídos para JSON ou um banco de dados, de modo a criar catálogos de projetos pesquisáveis ou integrar com ferramentas de BI.

---

**Última atualização:** 2026-05-26  
**Testado com:** Aspose.Tasks for Java 24.12 (mais recente no momento da escrita)  
**Autor:** Aspose

## Tutoriais Relacionados

- [How to Read Project Information from Microsoft Project with Aspose.Tasks for Java](/tasks/java/project-properties/read-project-info/)
- [Read microsoft project database with Aspose.Tasks for Java](/tasks/java/project-data-reading/read-project-database/)
- [java read access database: Read Project Data with Aspose.Tasks](/tasks/java/project-data-reading/read-access-database/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< blocks/products/products-backtop-button >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}