---
date: 2026-09-30
description: Aprenda como criar atributo estendido de tarefa usando Aspose.Tasks for
  Java, a principal biblioteca de gerenciamento de projetos Java para adicionar campos
  personalizados de tarefa.
keywords:
- create task extended attribute
- java project management library
- add custom task field
lastmod: 2026-09-30
linktitle: Como criar atributo estendido de tarefa com Aspose.Tasks Java
og_description: Aprenda como criar atributo estendido de tarefa usando Aspose.Tasks
  for Java, a principal biblioteca de gerenciamento de projetos Java para adicionar
  campos personalizados de tarefa.
og_image_alt: 'Developer guide: create task extended attribute in Aspose.Tasks Java'
og_title: Como criar atributo estendido de tarefa com Aspose.Tasks Java
schemas:
- author: Aspose
  dateModified: '2026-09-30'
  description: Learn how to create task extended attribute using Aspose.Tasks for
    Java, the leading java project management library for adding custom task fields.
  headline: How to create task extended attribute with Aspose.Tasks Java
  type: TechArticle
- questions:
  - answer: Yes, Aspose.Tasks for Java integrates smoothly with any Java ecosystem,
      including Spring, Hibernate, and Apache POI.
    question: Can I use Aspose.Tasks for Java with other Java libraries?
  - answer: Absolutely. The library is engineered to handle multi‑thousand‑task projects
      and supports streaming to keep memory usage low.
    question: Is Aspose.Tasks for Java suitable for large‑scale project management
      applications?
  - answer: Yes, you need a valid commercial license. You can review the details on
      the [Aspose.Tasks website](https://purchase.aspose.com/buy).
    question: Are there any licensing considerations for using Aspose.Tasks for Java
      in a commercial project?
  - answer: Visit the [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15) for
      community help, or open a support ticket through your Aspose account.
    question: How can I get support or assistance with Aspose.Tasks for Java?
  - answer: Yes, you can access a free trial version on the [Aspose.Tasks free trial](https://releases.aspose.com/)
      page.
    question: Can I try Aspose.Tasks for Java before purchasing?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- aspose.tasks
- java project management
- extended attributes
- task customization
title: Como criar atributo estendido de tarefa com Aspose.Tasks Java
url: /pt/java/task-properties/add-extended-attributes/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Como criar atributo estendido de tarefa com Aspose.Tasks Java

## Introdução
Neste tutorial você aprenderá a **criar atributo estendido de tarefa** em um arquivo Microsoft Project usando Aspose.Tasks para Java. Adicionar campos personalizados permite capturar dados específicos do projeto que não são cobertos pelas colunas nativas, oferecendo controle mais granular sobre relatórios e planejamento de recursos. Ao final do guia, você será capaz de adicionar atributos de texto simples, habilitados para lista de valores e de duração a qualquer tarefa.

## Respostas rápidas
- **O que significa “atributo estendido”?** É um campo personalizado que você define e anexa a tarefas, recursos ou atribuições.  
- **Qual biblioteca adiciona essa capacidade?** Aspose.Tasks para Java, uma biblioteca Java de gerenciamento de projetos.  
- **Preciso de licença para experimentar?** Sim – um teste gratuito de 30 dias está disponível no site da Aspose.  
- **Posso adicionar valores de lista?** Absolutamente; você pode fornecer uma lista de valores permitidos para campos de texto ou duração.  
- **A API é compatível com Java 8 e posteriores?** Sim, suporta Java 8+ e funciona em todos os principais sistemas operacionais.

## O que é um atributo estendido de tarefa?
Um atributo estendido de tarefa é uma coluna definida pelo usuário que armazena informações adicionais para cada tarefa em um arquivo Project. Ele se comporta como um campo nativo, mas pode conter qualquer tipo de dado que você precisar, como texto, números, datas ou durações.

## Por que usar Aspose.Tasks para Java?
Aspose.Tasks suporta **mais de 50 formatos de arquivo** e pode processar projetos com **mais de 10 000 tarefas** sem exigir a instalação do Microsoft Project. A biblioteca funciona totalmente offline, garantindo privacidade dos dados e desempenho determinístico para soluções em escala empresarial.

## Pré‑requisitos
Antes de começar, certifique‑se de que você tem:

- Conhecimento básico de programação Java.  
- A biblioteca Aspose.Tasks para Java instalada. Você pode baixá‑la no [site](https://releases.aspose.com/tasks/java/).  
- Um IDE Java (IntelliJ IDEA, Eclipse ou VS Code) configurado em sua máquina.

## Importar pacotes
As instruções `import` dão acesso às classes principais que você precisará, como `Project`, `ExtendedAttributeDefinition` e `ExtendedAttribute`.  

`Project` representa um arquivo Microsoft Project e fornece métodos para ler, modificar e salvar o arquivo.  
`ExtendedAttributeDefinition` define um campo personalizado que pode ser anexado a tarefas, recursos ou atribuições.  
`ExtendedAttribute` é uma instância de uma definição que contém o valor real para uma entidade específica.

## Como adicionar um atributo estendido de texto simples a uma tarefa?
Para adicionar um atributo estendido de texto simples, primeiro carregue o projeto, depois crie uma definição do tipo Text, adicione‑a à coleção do projeto, crie uma tarefa, instancie o atributo a partir da definição, defina seu valor de texto, anexe‑o à tarefa e, finalmente, salve o projeto.

### 1. Definir o caminho do diretório de documentos
Especifique onde seus arquivos de origem e saída estão localizados.

```java
import java.io.IOException;
import com.aspose.tasks.*;
```

### 2. Criar um novo projeto
Instancie um objeto `Project`, opcionalmente carregando um arquivo .mpp existente.

```java
String dataDir = "Your Document Directory";
```

### 3. Criar uma definição de atributo estendido do tipo Text1
Defina o campo personalizado como uma coluna de texto simples chamada “Text1”.

```java
Project project = new Project(dataDir + "project.mpp");
```

### 4. Adicionar a definição à coleção de atributos estendidos do projeto
Registre a nova definição para que o projeto a reconheça.

```java
ExtendedAttributeDefinition taskExtendedAttributeText1Definition = ExtendedAttributeDefinition.createTaskDefinition(CustomFieldType.Text, ExtendedAttributeTask.Text1, "Task City Name");
```

### 5. Adicionar uma tarefa ao projeto
Crie uma tarefa que receberá o campo personalizado.

```java
project.getExtendedAttributes().add(taskExtendedAttributeText1Definition);
```

### 6. Criar um atributo estendido a partir da definição de atributo
Gere uma instância que você pode vincular a uma tarefa específica.

```java
Task task = project.getRootTask().getChildren().add("Task 1");
```

### 7. Atribuir um valor ao atributo estendido gerado
Defina o texto real que deseja armazenar, por exemplo, “Revisão de Design”.

```java
ExtendedAttribute taskExtendedAttributeText1 = taskExtendedAttributeText1Definition.createExtendedAttribute();
```

### 8. Adicionar o atributo estendido à tarefa
Anexe a instância do atributo à coleção `ExtendedAttributes` da tarefa.

```java
taskExtendedAttributeText1.setTextValue("London");
```

### 9. Salvar o projeto
Grave o projeto atualizado no disco no formato desejado.

```java
task.getExtendedAttributes().add(taskExtendedAttributeText1);
```

## Como adicionar um atributo de texto com opção de lista de valores?
Ao adicionar um atributo de texto com lista de valores, você segue os mesmos passos de um atributo de texto simples, mas antes de adicionar a definição preenche sua coleção `LookupValues` com as strings permitidas. Esses valores aparecem como uma lista suspensa no Microsoft Project, garantindo consistência dos dados.

## Como adicionar um atributo de duração com opção de lista de valores?
Para adicionar um atributo de duração com lista de valores, substitua o tipo `Text1` por `Duration2` ao criar a definição, depois preencha a coleção `LookupValues` com strings de duração como “1 dia”, “2 dias”, etc. Após a definição ser adicionada ao projeto, crie a instância do atributo, defina um valor de duração, anexe‑a a uma tarefa e salve o arquivo.

## Problemas comuns e solução de erros
- **Valores de lista não aparecem** – Certifique‑se de adicionar cada entrada de lista à coleção `LookupValues` *antes* de chamar `project.getExtendedAttributes().add(definition)`.  
- **Valor do atributo não é salvo** – Verifique se você adiciona a instância `ExtendedAttribute` à tarefa *depois* de definir seu valor.  
- **Tamanho do arquivo cresce inesperadamente** – Ao trabalhar com projetos muito grandes, considere chamar `project.setSaveOptions(new ProjectSaveOptions())` para habilitar salvamento incremental.

## Perguntas frequentes

**Q: Posso usar Aspose.Tasks para Java com outras bibliotecas Java?**  
A: Sim, Aspose.Tasks para Java integra‑se perfeitamente com qualquer ecossistema Java, incluindo Spring, Hibernate e Apache POI.

**Q: Aspose.Tasks para Java é adequado para aplicações de gerenciamento de projetos em grande escala?**  
A: Absolutamente. A biblioteca foi projetada para lidar com projetos de milhares de tarefas e suporta streaming para manter o uso de memória baixo.

**Q: Existem considerações de licenciamento ao usar Aspose.Tasks para Java em um projeto comercial?**  
A: Sim, você precisa de uma licença comercial válida. Você pode revisar os detalhes no [site da Aspose.Tasks](https://purchase.aspose.com/buy).

**Q: Como posso obter suporte ou assistência com Aspose.Tasks para Java?**  
A: Visite o [fórum Aspose.Tasks](https://forum.aspose.com/c/tasks/15) para ajuda da comunidade, ou abra um ticket de suporte através da sua conta Aspose.

**Q: Posso experimentar Aspose.Tasks para Java antes de comprar?**  
A: Sim, você pode acessar uma versão de teste gratuito na página de [teste gratuito Aspose.Tasks](https://releases.aspose.com/).

---

**Última atualização:** 2026-09-30  
**Testado com:** Aspose.Tasks para Java 24.10  
**Autor:** Aspose  

```java
project.save(dataDir + "PlainTextExtendedAttribute_out.mpp", SaveFileFormat.Mpp);
```

## Tutoriais Relacionados

- [Colunas personalizadas e atributos estendidos em gerenciamento de projetos Java](/tasks/java/project-management/extended-attributes/)
- [Ler atributos estendidos de tarefa com Aspose.Tasks para Java](/tasks/java/task-properties/extended-task-attributes/)
- [Como criar projeto aspose.tasks – Definir novos atributos de tarefa](/tasks/java/project-file-operations/set-attributes-new-tasks/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}