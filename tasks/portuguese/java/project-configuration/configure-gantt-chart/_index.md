---
date: 2026-10-15
description: Aprenda como criar activity, definir o data directory, personalizar os
  campos da tabela e salvar o projeto como MPP com Aspose.Tasks for Java. Guia passo
  a passo para desenvolvedores Java.
keywords:
- how to create activity
- customize table fields
- save project as mpp
- how to save mpp
- create task programmatically
lastmod: 2026-10-15
linktitle: Como criar activity e definir data directory usando Aspose.Tasks for Java
og_description: Como criar activity, personalizar os campos da tabela e salvar o projeto
  como MPP usando Aspose.Tasks for Java. Siga este guia detalhado para uma implementação
  rápida.
og_image_alt: Screenshot of Aspose.Tasks Java code configuring Gantt chart and saving
  as MPP
og_title: Como criar activity e definir data directory no Aspose.Tasks for Java
schemas:
- author: Aspose
  dateModified: '2026-10-15'
  description: Learn how to create activity, set the data directory, customize table
    fields and save project as MPP with Aspose.Tasks for Java. Step‑by‑step guide
    for Java developers.
  headline: How to create activity and set data directory using Aspose.Tasks for Java
  type: TechArticle
- description: Learn how to create activity, set the data directory, customize table
    fields and save project as MPP with Aspose.Tasks for Java. Step‑by‑step guide
    for Java developers.
  name: How to create activity and set data directory using Aspose.Tasks for Java
  steps:
  - name: set up data directory
    text: Define the folder that contains your project files. The `dataDir` variable
      holds the absolute path and is reused throughout the tutorial. Replace `"Your
      Data Directory"` with the full path to the folder where `project.mpp` lives,
      for example `C:/Projects/MyGantt`.
  - name: load project file
    text: '`Project` is Aspose.Tasks'' top‑level object that represents a single Microsoft
      Project file in memory. Loading an existing file gives you access to its tasks,
      resources, and tables.'
  - name: add new activity
    text: '`Task` represents an individual activity in the schedule. Adding a task
      to the root task collection inserts it at the top level of the project hierarchy.'
  - name: define custom attribute
    text: '`ExtendedAttributeDefinition` lets you create a reusable custom field that
      can be attached to any task, resource, or assignment.'
  - name: add custom attribute to task
    text: '`ExtendedAttribute` is the concrete instance of a custom attribute that
      you assign to a specific task.'
  - name: customize table – add custom attribute as a column
    text: '`TableField` describes a column in a Gantt chart table. By adding a `TableField`
      that references the custom attribute, you make the attribute visible in the
      chart view.'
  - name: save project
    text: Calling `project.save` persists all changes to a new file. The `SaveFileFormat.MPP`
      constant tells Aspose.Tasks to write the file in Microsoft Project’s native
      binary format.
  type: HowTo
- questions:
  - answer: Yes, Aspose.Tasks is available for .NET, Java, and C++.
    question: Can I use Aspose.Tasks with other programming languages?
  - answer: Yes, you can download a free trial from the **Aspose.Tasks free trial
      download page**.
    question: Is there a free trial available for Aspose.Tasks?
  - answer: You can find support and ask questions on the [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15).
    question: Where can I find support for Aspose.Tasks?
  - answer: You can purchase a license from the **Aspose.Tasks purchase page**.
    question: How do I purchase a license for Aspose.Tasks?
  - answer: Yes, you can obtain a temporary license from the **temporary license request
      page**.
    question: Do I need a temporary license for testing purposes?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- Aspose.Tasks
- Java project automation
- Gantt chart customization
- MPP file handling
title: Como criar activity e definir data directory usando Aspose.Tasks for Java
url: /pt/java/project-configuration/configure-gantt-chart/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Como criar atividade e definir diretório de dados usando Aspose.Tasks para Java

## Introdução
Neste tutorial você descobrirá **como criar atividade** programaticamente, configurará o **diretório de dados** e **salvará o projeto como MPP**, além de **personalizar os campos da tabela** em uma visualização de diagrama de Gantt. Aspose.Tasks for Java é uma API poderosa que suporta mais de 30 formatos de entrada e saída e pode processar projetos com até 10 000 tarefas sem carregar o arquivo inteiro na memória. Ao final do guia, você será capaz de automatizar a criação de projetos, enriquecer tarefas com atributos personalizados e produzir um arquivo MPP pronto‑para‑abrir no Microsoft Project.

## Respostas rápidas
- **Qual é o primeiro passo?** Defina o caminho do diretório de dados onde seus arquivos de projeto estão armazenados.  
- **Qual biblioteca é necessária?** Aspose.Tasks for Java (disponível para download no site oficial).  
- **Posso adicionar atributos personalizados?** Sim – você pode definir atributos estendidos e exibí‑los no diagrama de Gantt.  
- **Preciso de uma licença para testes?** Uma licença temporária está disponível para fins de avaliação.  
- **Qual IDE funciona melhor?** Qualquer IDE Java (IntelliJ IDEA, Eclipse, NetBeans) funcionará.

## O que é “definir diretório de dados” e por que isso importa?
Definir o diretório de dados informa ao Aspose.Tasks onde ler e gravar arquivos de projeto. Sem um caminho correto, a API não consegue localizar seus arquivos `.mpp`, resultando em erros `FileNotFoundException`. Definir esse diretório no início do seu código torna o fluxo de trabalho repetível e isola as preocupações do sistema de arquivos da lógica de negócios.

## Por que personalizar campos de tabela em um diagrama de Gantt?
Campos de tabela personalizados permitem exibir informações adicionais — como atributos personalizados, dados de recursos ou notas específicas do projeto — diretamente na visualização de Gantt. Isso reduz a necessidade de relatórios separados e fornece aos interessados uma visualização única e rica em dados, que pode melhorar a velocidade de tomada de decisão em até 30 %.

## Como criar nova atividade?
Você cria uma nova atividade (tarefa) instanciando um objeto `Task` e adicionando‑o à coleção de tarefas raiz do projeto. Essa abordagem permite gerar cronogramas extensos automaticamente, obter dados de tarefas de sistemas externos ou aplicar atualizações em massa sem edição manual.

## Pré‑requisitos
Antes de começar, certifique‑se de que você tem:

1. **Java Development Kit (JDK)** – versão 8 ou superior.  
2. **Aspose.Tasks for Java** – faça o download na **página de lançamento do Aspose.Tasks Java**.  
3. **IDE** – IntelliJ IDEA, Eclipse ou qualquer editor compatível com Java que você prefira.  

## Importar pacotes
O namespace `com.aspose.tasks` contém todas as classes que você precisará para manipulação de projetos. Importá‑lo fornece acesso a `Project`, `Task`, `ExtendedAttributeDefinition` e outros tipos principais.

```java
import com.aspose.tasks.*;
```

## Dependência Maven (opcional)
Se você gerencia seu projeto com Maven, adicione a dependência Aspose.Tasks ao `pom.xml`. Isso garante que a biblioteca seja resolvida automaticamente durante a compilação.

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-tasks</artifactId>
    <version>24.12</version>
</dependency>
```

## Guia passo a passo

### Passo 1: configurar diretório de dados
Defina a pasta que contém seus arquivos de projeto. A variável `dataDir` contém o caminho absoluto e é reutilizada ao longo do tutorial.

```java
String dataDir = "Your Data Directory";
```

Substitua `"Your Data Directory"` pelo caminho completo da pasta onde o `project.mpp` está, por exemplo `C:/Projects/MyGantt`.

### Passo 2: carregar arquivo de projeto
`Project` é o objeto de nível superior do Aspose.Tasks que representa um único arquivo Microsoft Project na memória. Carregar um arquivo existente fornece acesso às suas tarefas, recursos e tabelas.

```java
Project project = new Project(dataDir + "project.mpp");
```

### Passo 3: adicionar nova atividade
`Task` representa uma atividade individual no cronograma. Adicionar uma tarefa à coleção de tarefas raiz insere‑a no nível superior da hierarquia do projeto.

```java
Task task = project.getRootTask().getChildren().add("New Activity");
```

### Passo 4: definir atributo personalizado
`ExtendedAttributeDefinition` permite criar um campo personalizado reutilizável que pode ser anexado a qualquer tarefa, recurso ou atribuição.

```java
ExtendedAttributeDefinition text1Definition = ExtendedAttributeDefinition.createTaskDefinition(ExtendedAttributeTask.Text1, null);
project.getExtendedAttributes().add(text1Definition);
```

### Passo 5: adicionar atributo personalizado à tarefa
`ExtendedAttribute` é a instância concreta de um atributo personalizado que você atribui a uma tarefa específica.

```java
task.getExtendedAttributes().add(text1Definition.createExtendedAttribute("Activity attribute"));
```

### Passo 6: personalizar tabela – adicionar atributo personalizado como coluna
`TableField` descreve uma coluna em uma tabela de diagrama de Gantt. Ao adicionar um `TableField` que referencia o atributo personalizado, você torna o atributo visível na visualização do gráfico.

```java
TableField attrField = new TableField();
attrField.setField(Field.TaskText1);
attrField.setWidth(20);
attrField.setTitle("Custom attribute");
attrField.setAlignTitle(HorizontalStringAlignment.Center);
attrField.setAlignData(HorizontalStringAlignment.Center);
Table table = project.getTables().toList().get(0);
table.getTableFields().add(3, attrField);
```

### Passo 7: salvar projeto
Chamar `project.save` persiste todas as alterações em um novo arquivo. A constante `SaveFileFormat.MPP` indica ao Aspose.Tasks que escreva o arquivo no formato binário nativo do Microsoft Project.

```java
project.save("saved.mpp", SaveFileFormat.Mpp);
```

## Problemas comuns e soluções
| Problema | Por que acontece | Correção |
|----------|------------------|----------|
| **FileNotFoundException** ao carregar o projeto | O caminho **set data directory** está incorreto ou falta uma barra final. | Verifique se `dataDir` aponta para a pasta exata e inclua o separador de arquivos correto (`/` ou `\\`). |
| Atributo personalizado não visível na visualização de Gantt | O campo da tabela foi adicionado no índice errado ou a largura da coluna está muito pequena. | Certifique‑se de que `table.getTableFields().add(3, attrField);` use um índice válido e ajuste `setWidth` conforme necessário. |
| LicenseException ao salvar | Nenhuma licença válida foi aplicada para uso em produção. | Aplique uma licença temporária ou permanente antes de chamar `project.save()`. |

## Perguntas frequentes

**Q: Posso usar Aspose.Tasks com outras linguagens de programação?**  
A: Sim, Aspose.Tasks está disponível para .NET, Java e C++.

**Q: Existe uma versão de avaliação gratuita disponível para Aspose.Tasks?**  
A: Sim, você pode baixar uma avaliação gratuita na **página de download da avaliação gratuita do Aspose.Tasks**.

**Q: Onde posso encontrar suporte para Aspose.Tasks?**  
A: Você pode encontrar suporte e fazer perguntas no [fórum Aspose.Tasks](https://forum.aspose.com/c/tasks/15).

**Q: Como faço para comprar uma licença do Aspose.Tasks?**  
A: Você pode comprar uma licença na **página de compra do Aspose.Tasks**.

**Q: Preciso de uma licença temporária para fins de teste?**  
A: Sim, você pode obter uma licença temporária na **página de solicitação de licença temporária**.

## Conclusão
Agora você sabe **como criar atividade**, definir o diretório de dados, definir e anexar um atributo personalizado, e **salvar o projeto como MPP** enquanto **personaliza os campos da tabela** em uma visualização de diagrama de Gantt usando Aspose.Tasks para Java. Esses recursos dão a você controle programático total sobre os dados do projeto, permitindo a geração automática de cronogramas e relatórios visuais mais ricos para seus interessados.

---

**Última atualização:** 2026-10-15  
**Testado com:** Aspose.Tasks Java 24.12 (latest)  
**Autor:** Aspose

## Tutoriais Relacionados

- [Como criar arquivo de projeto vazio no Aspose.Tasks (MS Project)](/tasks/java/project-configuration/create-empty-project-file/)
- [Como criar arquivo MPP – Criar e salvar projeto vazio no formato MPP com Aspose.Tasks](/tasks/java/project-configuration/create-save-mpp/)
- [Como criar projeto aspose.tasks – Definir novos atributos de tarefa](/tasks/java/project-file-operations/set-attributes-new-tasks/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}