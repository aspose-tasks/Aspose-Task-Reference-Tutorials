---
date: 2026-10-05
description: Aprenda como criar um projeto de teste e calcular dias entre datas usando
  Aspose.Tasks para Java, adicionar um campo personalizado e manipular arquivos MPP
  de forma eficiente.
keywords:
- create test project
- calculate days between dates
- define extended attribute
- set deadline Aspose.Tasks
- manipulate mpp file
lastmod: 2026-10-05
linktitle: Trabalhar com fórmulas no Aspose.Tasks
og_description: Crie um projeto de teste e calcule dias entre datas usando Aspose.Tasks
  para Java. Este guia mostra como adicionar um campo personalizado, definir prazos
  de tarefas e salvar o projeto como um arquivo MPP.
og_image_alt: 'Aspose.Tasks Java tutorial: create test project and calculate date
  differences'
og_title: Criar projeto de teste e calcular dias entre datas
schemas:
- author: Aspose
  dateModified: '2026-10-05'
  description: Learn how to create test project and calculate days between dates using
    Aspose.Tasks for Java, add a custom field, and manipulate MPP files efficiently.
  headline: Create test project and calculate days between dates
  type: TechArticle
- description: Learn how to create test project and calculate days between dates using
    Aspose.Tasks for Java, add a custom field, and manipulate MPP files efficiently.
  name: Create test project and calculate days between dates
  steps:
  - name: Create a test project with a custom field
    text: We begin by **creating a test project** and adding a custom field that will
      later hold our formula result. > *Pro tip:* `CreateTestProjectWithCustomField()`
      is a helper method that builds a minimal schedule and registers an extended
      attribute ready for formula assignment.
  - name: Define an extended attribute (add custom field)
    text: Next, we **define an extended attribute** – essentially the custom field
      – and give it a friendly alias. This is where we **add custom field** logic.
      - **Alias** makes the field readable in Project. - **Formula** calculates the
      number of days between a task’s *Finish* date and its *Deadline* – the c
  - name: Set deadline for a task (add deadline task & set task deadline)
    text: Now we **add deadline task** data by setting the *Deadline* property on
      a specific task. - The `Calendar` instance defines the exact deadline moment.
      - `set(Tsk.DEADLINE, …)` **sets task deadline** for the chosen task.
  - name: Save the project (manipulate Microsoft Project file)
    text: Finally, we **manipulate Microsoft Project** by persisting the changes to
      an MPP file. You can open `SaveFile.mpp` in Microsoft Project to see the custom
      field, formula result, and deadline reflected in the schedule.
  type: HowTo
- questions:
  - answer: Yes, Aspose.Tasks provides APIs for .NET, Java, and other platforms, allowing
      you to manipulate Microsoft Project files in the language of your choice.
    question: Can I use Aspose.Tasks with other programming languages?
  - answer: Absolutely. Download a fully functional trial from the [Aspose.Tasks download
      page](https://releases.aspose.com/).
    question: Is there a free trial available for Aspose.Tasks?
  - answer: The official docs are hosted at [Aspose.Tasks Java API Reference](https://reference.aspose.com/tasks/java/).
    question: Where can I find detailed documentation for Aspose.Tasks?
  - answer: Visit the [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15) to
      ask questions and share experiences with the community.
    question: How can I get support for Aspose.Tasks?
  - answer: A temporary license is available for short‑term testing; you can request
      one from the [temporary license request page](https://purchase.aspose.com/temporary-license/).
    question: Do I need a temporary license for evaluation?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- Aspose.Tasks
- Java project automation
- custom fields
- date calculations
title: Criar projeto de teste e calcular dias entre datas
url: /pt/java/formulas/work-with-formulas/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Criar projeto de teste e calcular dias entre datas

Em este tutorial você **criará um projeto de teste** e **calculará dias entre datas** adicionando um campo personalizado, definindo um atributo estendido e aplicando uma fórmula do Microsoft Project através da biblioteca Aspose.Tasks para Java. Seja para gerar cronogramas, calcular prazos ou automatizar relatórios, o Aspose.Tasks permite manipular dados do Project programaticamente sem necessidade de instalação desktop, suportando mais de 50 formatos de entrada e saída e lidando com arquivos de centenas de páginas em modo de memória eficiente.

## Respostas rápidas
- **O que o tutorial cobre?** Ele mostra como criar um projeto de teste, definir um atributo estendido, definir o prazo de uma tarefa e usar uma fórmula para calcular dias entre datas.  
- **Qual biblioteca é necessária?** Aspose.Tasks para Java (última versão).  
- **Preciso de licença?** Uma avaliação gratuita funciona para desenvolvimento; uma licença comercial é necessária para uso em produção.  
- **Qual IDE posso usar?** Qualquer IDE Java (IntelliJ IDEA, Eclipse, VS Code) que suporte JDK 8+.  
- **Quanto tempo leva a implementação?** Aproximadamente 10‑15 minutos para copiar o código e executá‑lo.

## O que é “calcular dias entre datas” no Aspose.Tasks?
No Aspose.Tasks, uma fórmula é uma string que pode referenciar campos de tarefa e executar cálculos. `[Deadline] - [Finish]` é a sintaxe de fórmula que o Aspose.Tasks usa para retornar a diferença numérica em dias entre dois campos de data. O resultado é armazenado como um valor numérico que representa dias inteiros, que você pode exibir em um campo personalizado ou usar em cálculos adicionais.

## Por que usar Aspose.Tasks para calcular dias entre datas?
O Aspose.Tasks fornece **cobertura total da API** para todas as propriedades de Project, Task e Resource, funciona em Windows, Linux e macOS, e **não requer Microsoft Project ou Office** instalados. O motor pode processar projetos com **mais de 500 tarefas** em menos de um segundo em hardware de servidor típico, tornando‑o ideal para pipelines CI, contêineres Docker e processamento em lote de alto volume.

## Como definir prazo para uma tarefa
java.util.Calendar é uma classe Java que representa um momento específico no tempo. Você define um prazo atribuindo um valor `java.util.Calendar` ao campo `Tsk.DEADLINE` de uma tarefa. Após criar a instância Calendar, defina seu ano, mês e dia para o prazo desejado, então chame `task.set(Tsk.DEADLINE, calendar);`. O prazo é armazenado no arquivo do projeto e pode ser usado em fórmulas como `[Deadline] - [Finish]`.

## Como definir atributo estendido
Um atributo estendido é um campo personalizado que armazena o resultado da sua fórmula. Você o cria uma vez, atribui um alias amigável e anexa a expressão `[Deadline] - [Finish]` para que cada tarefa possa calcular automaticamente o intervalo. Crie‑o instanciando `ExtendedAttribute`, definindo seu Alias, atribuindo a fórmula e adicionando‑o à coleção do projeto.

## Pré‑requisitos
Antes de começar, certifique‑se de que você tem o seguinte:

- **Java Development Kit (JDK) 8+** – faça o download no site da Oracle ou adote o OpenJDK.  
- **Aspose.Tasks para Java** – obtenha o JAR mais recente na [página de download do Aspose.Tasks para Java](https://releases.aspose.com/tasks/java/) e adicione‑lo ao classpath do seu projeto ou às dependências Maven/Gradle.

## Importar pacotes
Primeiro, importe as classes que precisaremos:

```java
import com.aspose.tasks.*;
import java.util.Calendar;
```

## Guia passo a passo

### Etapa 1: Criar um projeto de teste com um campo personalizado
Começamos **criando um projeto de teste** e adicionando um campo personalizado que mais tarde conterá o resultado da nossa fórmula.

```java
Project project = CreateTestProjectWithCustomField();
```

> *Dica profissional:* `CreateTestProjectWithCustomField()` é um método auxiliar que cria um cronograma mínimo e registra um atributo estendido pronto para atribuição de fórmula.

### Etapa 2: Definir um atributo estendido (adicionar campo personalizado)
Em seguida, **definimos um atributo estendido** – essencialmente o campo personalizado – e atribuímos a ele um alias amigável. É aqui que adicionamos a lógica do **campo personalizado**.

```java
ExtendedAttributeDefinition attr = project.getExtendedAttributes().get(0);
attr.setAlias("Days from finish to deadline");
attr.setFormula("[Deadline] - [Finish]");
```

- **Alias** torna o campo legível no Project.  
- **Fórmula** calcula o número de dias entre a data *Finish* de uma tarefa e sua *Deadline* – o núcleo de *calcular dias entre datas*.

### Etapa 3: Definir prazo para uma tarefa (adicionar tarefa de prazo & definir prazo da tarefa)
Agora **adicionamos dados de tarefa de prazo** definindo a propriedade *Deadline* em uma tarefa específica.

```java
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.set(2015, Calendar.MARCH, 26, 8, 0, 0);
Task task = project.getRootTask().getChildren().getById(1);
task.set(Tsk.DEADLINE, cal.getTime());
```

- A instância `Calendar` define o momento exato do prazo.  
- `set(Tsk.DEADLINE, …)` **define o prazo da tarefa** para a tarefa escolhida.

### Etapa 4: Salvar o projeto (manipular arquivo Microsoft Project)
Por fim, **manipulamos o Microsoft Project** persistindo as alterações em um arquivo MPP.

```java
project.save("SaveFile.mpp", SaveFileFormat.Mpp);
```

Você pode abrir `SaveFile.mpp` no Microsoft Project para ver o campo personalizado, o resultado da fórmula e o prazo refletidos no cronograma.

## Problemas comuns e soluções
| Problema | Solução |
|----------|---------|
| **Fórmula não está sendo avaliada** | Certifique‑se de que a string `Formula` do atributo usa nomes de campo corretos (ex.: `[Deadline]`, `[Finish]`). |
| **Tarefa não encontrada** | Verifique se o ID da tarefa (`1` no exemplo) existe; use `project.getRootTask().getChildren().size()` para depurar. |
| **Exceção de licença** | Aplique uma licença válida do Aspose.Tasks antes de chamar quaisquer métodos da API (`License license = new License(); license.setLicense("Aspose.Tasks.lic");`). |

## Perguntas frequentes

**Q: Posso usar Aspose.Tasks com outras linguagens de programação?**  
A: Sim, o Aspose.Tasks fornece APIs para .NET, Java e outras plataformas, permitindo manipular arquivos Microsoft Project na linguagem de sua escolha.

**Q: Existe uma avaliação gratuita disponível para Aspose.Tasks?**  
A: Absolutamente. Baixe uma avaliação totalmente funcional na [página de download do Aspose.Tasks](https://releases.aspose.com/).

**Q: Onde posso encontrar documentação detalhada do Aspose.Tasks?**  
A: A documentação oficial está hospedada em [Aspose.Tasks Java API Reference](https://reference.aspose.com/tasks/java/).

**Q: Como posso obter suporte para Aspose.Tasks?**  
A: Visite o [fórum do Aspose.Tasks](https://forum.aspose.com/c/tasks/15) para fazer perguntas e compartilhar experiências com a comunidade.

**Q: Preciso de uma licença temporária para avaliação?**  
A: Uma licença temporária está disponível para testes de curto prazo; você pode solicitar uma na [página de solicitação de licença temporária](https://purchase.aspose.com/temporary-license/).

---

**Última atualização:** 2026-10-05  
**Testado com:** Aspose.Tasks para Java 24.12 (última versão no momento da escrita)  
**Autor:** Aspose

## Tutoriais relacionados

- [Como criar arquivo MPP – Criar e salvar projeto vazio no formato MPP com Aspose.Tasks](/tasks/java/project-configuration/create-save-mpp/)
- [Definir data de início do projeto no MS Project usando Aspose.Tasks para Java](/tasks/java/project-properties/write-project-info/)
- [Como criar atributo estendido em Java com Aspose.Tasks](/tasks/java/resource-management/extended-resource-attributes/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}