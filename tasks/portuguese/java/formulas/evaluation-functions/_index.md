---
date: 2026-10-10
description: Aprenda a adicionar atributo estendido no Aspose.Tasks, usar funções
  de avaliação e gerar relatórios de projeto com esta biblioteca Java de gerenciamento
  de projetos.
keywords:
- how to add extended attribute
- add custom field task
- java project management library
lastmod: 2026-10-10
linktitle: Suporte a Funções de Avaliação nas Fórmulas do Aspose.Tasks
og_description: Aprenda a adicionar atributo estendido no Aspose.Tasks, usar funções
  de avaliação e gerar relatórios de projeto com esta biblioteca Java de gerenciamento
  de projetos.
og_image_alt: Aspose.Tasks Java tutorial showing how to add extended attribute and
  use evaluation functions
og_title: Como adicionar atributo estendido nas fórmulas do Aspose.Tasks
schemas:
- author: Aspose
  dateModified: '2026-10-10'
  description: Learn how to add extended attribute in Aspose.Tasks, use evaluation
    functions, and generate project reports with this Java project management library.
  headline: How to add extended attribute in Aspose.Tasks formulas
  type: TechArticle
- questions:
  - answer: Yes, Aspose.Tasks for Java supports evaluation of a wide range of MS Project
      functions, allowing for complex calculations within Java applications.
    question: Can Aspose.Tasks for Java handle complex MS Project formulas?
  - answer: Yes, Aspose.Tasks for Java supports various versions of Microsoft Project
      files, including MPP, MPT, and XML formats.
    question: Is Aspose.Tasks for Java compatible with different versions of Microsoft
      Project files?
  - answer: Yes, you can download a free trial version of Aspose.Tasks for Java from
      the website [Aspose.Tasks for Java purchase page](https://purchase.aspose.com/buy).
    question: Can I try Aspose.Tasks for Java before purchasing?
  - answer: You can get support from the Aspose.Tasks community forum [Aspose.Tasks
      community forum](https://forum.aspose.com/c/tasks/15).
    question: How can I get support for Aspose.Tasks for Java?
  - answer: Yes, you can obtain a temporary license for testing purposes from the
      Aspose website [Aspose temporary license page](https://purchase.aspose.com/temporary-license/).
    question: Is there a temporary license available for Aspose.Tasks for Java?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- add extended attribute
- java project management library
- Aspose.Tasks
- evaluation functions
- custom field task
title: Como adicionar atributo estendido nas fórmulas do Aspose.Tasks
url: /pt/java/formulas/evaluation-functions/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Como adicionar atributo estendido nas fórmulas do Aspose.Tasks

## Introdução
Aspose.Tasks for Java é uma **biblioteca Java de gerenciamento de projetos** que permite gerar relatórios de projetos criando um objeto `Project` em Java e avaliando funções do Microsoft Project diretamente no seu código. Ao incorporar essas fórmulas, você pode executar cálculos sofisticados, gerar relatórios personalizados e automatizar a análise de projetos sem sair do seu ambiente de desenvolvimento. Neste tutorial, percorreremos a criação de um objeto de projeto, a adição de um atributo estendido e o uso de funções de avaliação para **adicionar dados de tarefa de campo personalizado**.

## Respostas rápidas
- **O que significa “create project object java”?** Ele cria uma instância `Project` na memória que você pode manipular programaticamente.  
- **Qual biblioteca é necessária?** Aspose.Tasks for Java (download do site oficial).  
- **Preciso de uma licença?** Uma licença temporária ou completa do Aspose.Tasks é necessária para uso em produção; uma avaliação gratuita está disponível.  
- **Posso usar campos personalizados?** Sim – você pode **adicionar atributo estendido** às tarefas e tratá-los como campos personalizados.  
- **Isso é compatível com todos os formatos de arquivo do Project?** Aspose.Tasks suporta 3 formatos principais (MPP, MPT, XML) e mais de 50 formatos adicionais de entrada/saída.

## Pré-requisitos
Antes de começar, certifique-se de que você tem:

1. **Ambiente de Desenvolvimento Java** – JDK 8+ e uma IDE como IntelliJ IDEA ou Eclipse.  
2. **Biblioteca Aspose.Tasks for Java** – Baixe e inclua a biblioteca da [página de download do Aspose.Tasks for Java](https://releases.aspose.com/tasks/java/).

## Importar pacotes
Adicione o namespace Aspose.Tasks à sua classe Java para que você possa trabalhar com projetos, tarefas e atributos estendidos:

```java
import com.aspose.tasks.*;
```

## Gerar relatório de projeto – create project object java
A classe `Project` representa um arquivo Microsoft Project na memória, expondo tarefas, recursos e dados personalizados. Instanciar esta classe fornece um contêiner para todos os elementos do projeto que você definirá.

```java
Project project = new Project();
```

A linha acima **creates project object java** que começa vazia e pronta para personalização.

## Como adicionar atributo estendido
A classe `ExtendedAttributeDefinition` define um campo personalizado que pode ser anexado às tarefas. Para adicionar um atributo estendido, crie uma instância desta classe com o tipo `Number`, atribua-lhe um alias como “Sine”, adicione-a à coleção `ExtendedAttributes` do projeto e, em seguida, vincule-a a cada tarefa que requer o campo personalizado.

```java
ExtendedAttributeDefinition attr = ExtendedAttributeDefinition.createTaskDefinition(CustomFieldType.Number, ExtendedAttributeTask.Number1, "Sine");
```

Aqui nós **add extended attribute** do tipo `Number` chamado “Sine” e o associamos às tarefas.

## Adicionar o atributo estendido ao projeto
Registre a definição do atributo no projeto para que cada tarefa possa referenciá-lo.

```java
project.getExtendedAttributes().add(attr);
```

## Criar uma nova tarefa
`Task` representa um item de trabalho no projeto e pode conter campos personalizados.

```java
Task task = project.getRootTask().getChildren().add("Task");
```

## Adicionar tarefa de campo personalizado ao projeto
Vincule o atributo estendido definido anteriormente à tarefa recém-criada, dando à tarefa um campo personalizado “Sine” que você pode usar em fórmulas ou cálculos.

```java
ExtendedAttribute a = attr.createExtendedAttribute();
task.getExtendedAttributes().add(a);
```

Agora a tarefa contém um campo personalizado “Sine” que você pode usar em fórmulas ou cálculos. Esta também é a forma de **add custom field task** dados programaticamente.

## Por que usar funções de avaliação?
Funções de avaliação permitem incorporar fórmulas nativas do Microsoft Project (por exemplo, `Sin([Start])`) diretamente no Aspose.Tasks, possibilitando cálculos em tempo real sem processamento externo. Isso mantém toda a lógica do projeto em um único local, reduz erros de sincronização de dados e acelera a geração de relatórios. Aspose.Tasks suporta a avaliação de mais de 100 funções do MS Project, fornecendo um motor de cálculo abrangente dentro do Java.

## Problemas comuns e soluções
| Problema | Solução |
|----------|----------|
| **Formula returns `NaN`** | Verifique se o tipo do campo personalizado corresponde ao tipo numérico esperado. |
| **Extended attribute not visible** | Certifique-se de que a definição do atributo seja adicionada ao projeto **antes** de criar tarefas. |
| **License exception** | Instale uma licença temporária ou completa **Aspose.Tasks license**; o modo de avaliação pode limitar certos recursos. |
| **Missing temporary license** | Obtenha uma **licença temporária Aspose** no site da Aspose. |

## Perguntas frequentes

**Q: O Aspose.Tasks for Java pode lidar com fórmulas complexas do MS Project?**  
A: Sim, o Aspose.Tasks for Java suporta a avaliação de uma ampla gama de funções do MS Project, permitindo cálculos complexos dentro de aplicações Java.

**Q: O Aspose.Tasks for Java é compatível com diferentes versões de arquivos do Microsoft Project?**  
A: Sim, o Aspose.Tasks for Java suporta várias versões de arquivos do Microsoft Project, incluindo os formatos MPP, MPT e XML.

**Q: Posso experimentar o Aspose.Tasks for Java antes de comprar?**  
A: Sim, você pode baixar uma versão de avaliação gratuita do Aspose.Tasks for Java no site [Aspose.Tasks for Java purchase page](https://purchase.aspose.com/buy).

**Q: Como posso obter suporte para o Aspose.Tasks for Java?**  
A: Você pode obter suporte no fórum da comunidade Aspose.Tasks [Aspose.Tasks community forum](https://forum.aspose.com/c/tasks/15).

**Q: Existe uma licença temporária disponível para o Aspose.Tasks for Java?**  
A: Sim, você pode obter uma licença temporária para fins de teste no site da Aspose [Aspose temporary license page](https://purchase.aspose.com/temporary-license/).

## Conclusão
Seguindo estas etapas, você aprendeu como **create project object**, **add extended attribute**, e aproveitar as funções de avaliação para **generate project report** automaticamente. Agora você pode expandir essa base para criar análises de projeto mais avançadas, painéis personalizados ou ferramentas de agendamento automatizado — tudo alimentado pelo Aspose.Tasks for Java.

---

**Última atualização:** 2026-10-10  
**Testado com:** Aspose.Tasks for Java 24.10  
**Autor:** Aspose

## Tutoriais relacionados

- [Colunas personalizadas e atributos estendidos no gerenciamento de projetos Java](/tasks/java/project-management/extended-attributes/)
- [Ler atributos de tarefa estendidos com Aspose.Tasks for Java](/tasks/java/task-properties/extended-task-attributes/)
- [Como usar Aspose.Tasks for Java – Adicionar atributos estendidos às atribuições de recursos](/tasks/java/resource-assignments/add-extended-attributes/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}