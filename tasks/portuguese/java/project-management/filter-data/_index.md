---
date: 2026-06-05
description: Aprenda a filtrar arquivos MPP usando Aspose.Tasks para Java, personalize
  os critérios de filtro e filtre tarefas por data para otimizar a gestão de projetos.
keywords:
- how to filter mpp
- filter tasks by date
- Aspose.Tasks Java filter
- project management Java API
linktitle: Como filtrar arquivos MPP usando Aspose.Tasks para Java
schemas:
- author: Aspose
  dateModified: '2026-06-05'
  description: Learn how to filter MPP files using Aspose.Tasks for Java, customize
    filter criteria, and filter tasks by date to streamline project management.
  headline: How to Filter MPP Files Using Aspose.Tasks for Java
  type: TechArticle
- questions:
  - answer: It means extracting a subset of project data based on defined conditions.
    question: What does “filter mpp” mean?
  - answer: Aspose.Tasks for Java provides a comprehensive API for creating and applying
      filters.
    question: Which library handles this?
  - answer: A free trial works for development; a commercial license is required for
      production.
    question: Do I need a license?
  - answer: Yes – each entity type has its own filter collection.
    question: Can I filter tasks, resources, and assignments?
  - answer: Aspose.Tasks supports Java 8 and later versions.
    question: Is Java 8 or higher required?
  type: FAQPage
second_title: Aspose.Tasks Java API
title: Como filtrar arquivos MPP usando Aspose.Tasks para Java
url: /pt/java/project-management/filter-data/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Como Filtrar Arquivos MPP Usando Aspose.Tasks para Java

## Introdução
Se você está trabalhando com arquivos do Microsoft Project (*.mpp*) em uma aplicação Java, frequentemente precisará **filtrar arquivos MPP** para isolar as tarefas, recursos ou atribuições que são mais importantes. Neste tutorial, percorreremos **como filtrar mpp** programaticamente com Aspose.Tasks para Java, mostraremos como **personalizar critérios de filtro** e demonstraremos um cenário prático de “filtrar tarefas por data”. Ao final, você terá um trecho pronto‑para‑usar que pode ser inserido em qualquer projeto Java.

## Respostas Rápidas
- **O que significa “filter mpp”?** Significa extrair um subconjunto dos dados do projeto com base em condições definidas.  
- **Qual biblioteca lida com isso?** Aspose.Tasks para Java fornece uma API abrangente para criar e aplicar filtros.  
- **Preciso de uma licença?** Um teste gratuito funciona para desenvolvimento; uma licença comercial é necessária para produção.  
- **Posso filtrar tarefas, recursos e atribuições?** Sim – cada tipo de entidade tem sua própria coleção de filtros.  
- **É necessário Java 8 ou superior?** Aspose.Tasks suporta Java 8 e versões posteriores.

## O que é “how to filter mpp” em Java?
`How to filter mpp` é o processo de usar os objetos `Filter` do Aspose.Tasks para selecionar apenas os elementos do projeto que atendem a predicados específicos, como data de início, custo ou campos personalizados. Carregue um `Project`, recupere um `Filter` e a API retornará uma coleção que corresponde aos seus critérios, permitindo relatórios focados ou integração downstream.

## Por que personalizar critérios de filtro?
Critérios de filtro personalizados permitem que você direcione tarefas de alto risco, itens atrasados ou recursos com orçamento excedido, transformando um arquivo de projeto massivo em uma visualização concisa e acionável. Aspose.Tasks suporta **50+ tipos de filtro predefinidos** e permite criar filtros personalizados ilimitados, reduzindo o tempo de triagem manual de dados em até 70 %.

## Pré-requisitos
Antes de começar, certifique‑se de que você tem:

1. **Java Development Kit (JDK)** – versão 8 ou mais recente.  
2. **Aspose.Tasks for Java** – faça o download na [download page](https://releases.aspose.com/tasks/java/).  
3. **Um IDE** – IntelliJ IDEA, Eclipse ou NetBeans funcionará bem.  

## Importar Pacotes
`Filter`, `FilterCollection`, `FilterCriteria`, `ItemType` e `Project` são classes principais usadas para definir e aplicar filtros aos dados do projeto.

```java
import com.aspose.tasks.Filter;
import com.aspose.tasks.FilterCollection;
import com.aspose.tasks.FilterCriteria;
import com.aspose.tasks.ItemType;
import com.aspose.tasks.Project;
import java.util.List;
```

## Guia Passo a Passo

### Etapa 1: Configurar o Projeto
Primeiro, crie uma instância `Project` que aponte para o arquivo MPP que você deseja analisar e, em seguida, carregue‑a na memória. Esta única etapa prepara todo o modelo do projeto para filtragem, validação e manipulação adicional, permitindo que você acesse tarefas, recursos e atribuições através da API.

### Como configuro o projeto para filtrar arquivos MPP?
A classe `Project` carrega e representa um arquivo MPP na memória. Crie uma instância `Project` que aponte para o arquivo MPP que você deseja analisar e, em seguida, carregue‑a na memória. Esta única etapa prepara todo o modelo do projeto para filtragem, validação e manipulação adicional, permitindo que você acesse tarefas, recursos e atribuições através da API.

### Como posso recuperar e inspecionar um filtro?
Objetos `Filter` encapsulam definições de filtro usadas para selecionar itens do projeto. Aspose.Tasks armazena filtros predefinidos como “All Tasks” ou “Critical Tasks”. Use `project.getTaskFilters().getByName("My Filter")` ou acesso baseado em índice para obter um objeto `Filter`, então examine sua coleção `FilterCriteria` para ver cada regra e o operador lógico (AND/OR) que as combina, garantindo que o filtro atenda aos seus requisitos.

### Como iterar através de linhas de critérios aninhadas?
`FilterCriteriaGroup` representa um grupo de critérios de filtro combinados com um operador lógico. Os filtros podem conter grupos de critérios, cada um com seu próprio operador. Percorra `filter.getCriteria().getRows()` e, para qualquer linha que seja um `FilterCriteriaGroup`, recorra às suas linhas filhas. Essa travessia permite que você compreenda totalmente a lógica de filtro complexa, como “(Start < today AND Cost > 1000) OR Priority = High”, e ajuste os critérios conforme necessário.

### Como imprimir informações de critérios para depuração?
Após percorrer a árvore de critérios, exiba o nome do campo, o operador de teste e o valor de cada linha no console. Esse dump simples ajuda a verificar se o filtro corresponde às regras de negócio pretendidas antes de aplicá‑lo a projetos grandes, facilitando a identificação de operadores ou valores incorretos.

### Como criar um filtro totalmente novo programaticamente?
Instancie um `Filter` com `new Filter("My Filter")`, então adicione‑o à coleção de filtros de tarefas do projeto usando `project.getTaskFilters().add(filter)`. Em seguida, preencha sua coleção `FilterCriteria` com as linhas desejadas, especificando nomes de campos, operadores de teste e valores para definir exatamente quais tarefas devem ser incluídas quando o filtro for aplicado.

### Posso aplicar um filtro a recursos em vez de tarefas?
A coleção `ResourceFilters` contém definições de filtros aplicáveis a recursos. Sim – use `project.getResourceFilters()` para trabalhar com filtros específicos de recursos da mesma forma que os filtros de tarefas. Após adicionar ou recuperar um filtro, configure seu `FilterCriteria` como faria para tarefas, então aplique‑o à coleção de recursos para obter o conjunto filtrado de recursos.

### É possível combinar múltiplos filtros com lógica OR?
Crie um `FilterCriteriaGroup` pai com sua `Operation` definida como `OR`, então adicione objetos `FilterCriteria` individuais como filhos. Esse grupo avaliará cada critério filho e retornará itens que satisfaçam qualquer um deles, permitindo combinar vários filtros simples em uma seleção mais ampla.

### O Aspose.Tasks suporta filtragem em campos personalizados?
O enum `CustomField` fornece identificadores para campos personalizados definidos em um projeto. Absolutamente. Referencie campos personalizados via o enum `CustomField`, e eles se comportam como qualquer campo interno em expressões de filtro. Você pode incluí‑los nas linhas `FilterCriteria`, usando os mesmos operadores e valores, permitindo consultas poderosas em dados definidos pelo usuário juntamente com atributos padrão do projeto.

### Qual o impacto de desempenho da filtragem em arquivos MPP grandes?
A filtragem é executada totalmente na memória e normalmente processa um projeto de 1.000 tarefas em menos de 200 ms. Para arquivos com milhares de tarefas, considere carregar apenas as seções necessárias usando `ProjectReader` e aplicar filtros após o carregamento seletivo, o que mantém o uso de memória baixo e mantém tempos de resposta rápidos mesmo em projetos muito grandes.

---

**Última Atualização:** 2026-06-05  
**Testado com:** Aspose.Tasks for Java 24.10  
**Autor:** Aspose

## Tutoriais Relacionados

- [Carregar Arquivo MPP Java - Gerenciar Propriedades do Projeto com Aspose.Tasks](/tasks/java/project-management/default-properties/)
- [Aspose.Tasks Java - Leitura Fácil de Dados do MS Project Online](/tasks/java/project-data-reading/read-project-online/)
- [Definir Data de Início do Projeto no MS Project usando Aspose.Tasks para Java](/tasks/java/project-properties/write-project-info/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< blocks/products/products-backtop-button >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

```java
import com.aspose.tasks.Filter;
import com.aspose.tasks.FilterCollection;
import com.aspose.tasks.FilterCriteria;
import com.aspose.tasks.ItemType;
import com.aspose.tasks.Project;
import java.util.List;
```

```java
String dataDir = "Your Data Directory";
Project project = new Project(dataDir + "Project2003.mpp");
```

```java
Filter filter = project.getTaskFilters().toList().get(1);
```

```java
System.out.println(filter.getCriteria().getCriteriaRows().size());
System.out.println(filter.getCriteria().getOperation());
```

```java
FilterCriteria criteria1 = filter.getCriteria().getCriteriaRows().get(0);
System.out.println(criteria1.getTest());
System.out.println(criteria1.getField());
```

```java
FilterCriteria criteria2 = filter.getCriteria().getCriteriaRows().get(1);
System.out.println(criteria2.getOperation());
System.out.println(criteria2.getCriteriaRows().size());
```

```java
FilterCriteria criteria21 = criteria2.getCriteriaRows().get(0);
System.out.println(criteria21.getTest());
System.out.println(criteria21.getField());
FilterCriteria criteria22 = criteria2.getCriteriaRows().get(1);
System.out.println(criteria22.getTest());
System.out.println(criteria22.getField());
```