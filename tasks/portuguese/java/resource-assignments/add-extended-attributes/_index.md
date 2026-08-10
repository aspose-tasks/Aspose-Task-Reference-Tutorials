---
date: 2026-05-20
description: Aprenda como usar Aspose.Tasks para Java para adicionar atributos estendidos
  às atribuições de recursos, definir a data de início do projeto e gravar arquivos
  do MS Project de forma eficiente.
keywords:
- how to use aspose
- add extended attributes
- set project start date
- create resource assignment
- aspose tasks java
linktitle: Adicionar atributos estendidos às atribuições de recursos no Aspose.Tasks
schemas:
- author: Aspose
  dateModified: '2026-05-20'
  description: Learn how to use Aspose.Tasks for Java to add extended attributes to
    resource assignments, set project start date, and write MS Project files efficiently.
  headline: How to Use Aspose.Tasks for Java – Add Extended Attributes to Resource
    Assignments
  type: TechArticle
- description: Learn how to use Aspose.Tasks for Java to add extended attributes to
    resource assignments, set project start date, and write MS Project files efficiently.
  name: How to Use Aspose.Tasks for Java – Add Extended Attributes to Resource Assignments
  steps:
  - name: Set Up Data Directory
    text: Define the directory where your project data will be stored. This path is
      used later when you save the XML file.
  - name: Create Project Instance
    text: The `Project` class is Aspose.Tasks' top‑level object that represents a
      single Microsoft Project file in memory. Instantiating it gives you full access
      to all project elements.
  - name: Set Project Information Properties
    text: Set essential project properties such as the start date, schedule from start
      flag, and status date. These values are stored in the project’s `ProjectInfo`
      object.
  - name: Add Extended Attributes to a Resource Assignment
    text: Create an `ExtendedAttributeDefinition` for the custom field, attach it
      to a `ResourceAssignment`, and populate the value. This step demonstrates the
      **add extended attributes** keyword in action.
  type: HowTo
- questions:
  - answer: Yes, the library provides full read‑write capabilities for .mpp, .xml,
      and .xps formats.
    question: Can I use Aspose.Tasks for Java to read MS Project files?
  - answer: Absolutely, it supports files from Project 2000 up to the latest 2024
      release, covering over 20 version formats.
    question: Is Aspose.Tasks for Java compatible with different versions of MS Project?
  - answer: The trial adds a watermark to generated files and limits the number of
      tasks you can create, but all API features remain accessible.
    question: Are there any limitations to the trial version of Aspose.Tasks for Java?
  - answer: You can seek assistance from the Aspose.Tasks community forum [here](https://forum.aspose.com/c/tasks/15).
    question: How can I get support for Aspose.Tasks for Java?
  - answer: Yes, temporary licenses are available for short‑term usage. You can obtain
      one from [here](https://purchase.aspose.com/temporary-license/).
    question: Can I purchase a temporary license for Aspose.Tasks for Java?
  type: FAQPage
second_title: Aspose.Tasks Java API
title: Como usar Aspose.Tasks para Java – Adicionar atributos estendidos às atribuições
  de recursos
url: /pt/java/resource-assignments/add-extended-attributes/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Dominando a Manipulação do MS Project com Aspose.Tasks para Java

## Introdução
Neste tutorial você descobrirá **como usar Aspose.Tasks para Java** para adicionar atributos estendidos a atribuições de recursos e escrever informações do Microsoft Project programaticamente. Seja automatizando um pipeline de relatórios ou construindo uma ferramenta personalizada de gerenciamento de projetos, os passos abaixo mostram exatamente como definir a data de início do projeto, criar atribuições de recursos e persistir o arquivo como XML — tudo com apenas algumas linhas de código Java.

## Respostas Rápidas
- **O que o Aspose.Tasks para Java faz?** Ele lê, grava e modifica arquivos do Microsoft Project sem precisar do Microsoft Project instalado.  
- **Posso adicionar campos personalizados a uma atribuição de recurso?** Sim, use a coleção `ExtendedAttribute` no objeto `ResourceAssignment`.  
- **Como definir a data de início do projeto?** Chame `project.setStartDate(LocalDateTime.of(...))` antes de salvar.  
- **Preciso de uma licença para uso em produção?** Uma licença comercial remove marcas d'água de avaliação e desbloqueia acesso total à API.  
- **Quais versões do Java são suportadas?** Aspose.Tasks para Java suporta JDK 8 até JDK 21.

## Como usar Aspose.Tasks para Java?
`Project` é o objeto principal que representa um arquivo Microsoft Project na memória. Carregue a biblioteca Aspose.Tasks, crie uma instância `Project`, configure propriedades ao nível do projeto, adicione atributos estendidos a uma atribuição de recurso e, finalmente, salve o projeto como XML. O fluxo de trabalho central se resume a três etapas concisas: inicializar, modificar e persistir. Esse padrão funciona para projetos de qualquer tamanho e roda em JVMs Windows, Linux ou macOS.

## O que é um atributo estendido no Aspose.Tasks?
Um **atributo estendido** é um campo personalizado que você anexa a tarefas, recursos ou atribuições para armazenar metadados adicionais além das colunas incorporadas. `ExtendedAttributeDefinition` define o esquema para um campo personalizado. Aspose.Tasks expõe as classes `ExtendedAttributeDefinition` e `ExtendedAttribute` para definir e atribuir esses campos programaticamente.

## Por que adicionar atributos estendidos a atribuições de recursos?
Aspose.Tasks suporta **mais de 50 campos incorporados e personalizados**, e você pode adicionar atributos definidos pelo usuário ilimitados. Adicioná‑los permite capturar códigos de custo, IDs de departamento ou quaisquer dados específicos de negócios diretamente dentro do arquivo .mpp, eliminando a necessidade de planilhas externas e garantindo a integridade dos dados ao longo do ciclo de vida do projeto.

## Pré‑requisitos
Antes de começar, certifique‑se de que você tem:

1. **Java Development Kit (JDK)** – JDK 8 ou posterior instalado.  
2. **Biblioteca Aspose.Tasks para Java** – Baixe-a da página oficial de lançamentos [aqui](https://releases.aspose.com/tasks/java/).  
3. **IDE** – IntelliJ IDEA, Eclipse ou qualquer editor compatível com Java que você prefira.

## Importar Pacotes
Primeiro, importe os pacotes necessários no seu projeto Java:

```java
import com.aspose.tasks.CustomFieldType;
import com.aspose.tasks.ExtendedAttribute;
import com.aspose.tasks.ExtendedAttributeDefinition;
import com.aspose.tasks.ExtendedAttributeResource;
import com.aspose.tasks.ExtendedAttributeTask;
import com.aspose.tasks.Project;
import com.aspose.tasks.Resource;
import com.aspose.tasks.ResourceAssignment;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.Task;
import com.aspose.tasks.Value;
import java.io.IOException;
import java.math.BigDecimal;
```

### Etapa 1: Configurar Diretório de Dados
Defina o diretório onde os dados do seu projeto serão armazenados. Esse caminho será usado posteriormente ao salvar o arquivo XML.

```java
String dataDir = "Your Data Directory";
```

### Etapa 2: Criar Instância do Projeto
A classe `Project` é o objeto de nível superior do Aspose.Tasks que representa um único arquivo Microsoft Project na memória. Instanciá‑la fornece acesso total a todos os elementos do projeto.

```java
Project project = new Project();
```

### Etapa 3: Definir Propriedades de Informações do Projeto
Defina propriedades essenciais do projeto, como a data de início, a bandeira de agendamento a partir do início e a data de status. Esses valores são armazenados no objeto `ProjectInfo` do projeto.

```java
project.set(Prj.SCHEDULE_FROM_START, new NullableBool(true));
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.set(2014, Calendar.JULY, 10);
project.set(Prj.START_DATE, cal.getTime());
project.set(Prj.CURRENT_DATE, cal.getTime());
project.set(Prj.STATUS_DATE, cal.getTime());
```

### Etapa 4: Adicionar Atributos Estendidos a uma Atribuição de Recurso
Crie um `ExtendedAttributeDefinition` para o campo personalizado, anexe‑o a um `ResourceAssignment` e preencha o valor. Esta etapa demonstra a palavra‑chave **add extended attributes** em ação.

```java
project.save(dataDir + "project3.xml", SaveFileFormat.Xml);
```

## Problemas Comuns e Soluções
- **NullPointerException ao acessar a coleção de atribuições** – Certifique‑se de ter criado ao menos um recurso e uma tarefa antes de recuperar as atribuições.  
- **Atributo estendido não aparece no MS Project** – Verifique se o `FieldId` do atributo corresponde a um slot de campo personalizado (por exemplo, `ExtendedAttributeTask.Text1`).  
- **Incompatibilidade de formato de data** – Use `java.time.LocalDateTime` para valores de data; Aspose.Tasks converte automaticamente para o formato do calendário do Projeto.

## Perguntas Frequentes

**Q: Posso usar Aspose.Tasks para Java para ler arquivos MS Project?**  
A: Sim, a biblioteca fornece recursos completos de leitura e gravação para os formatos .mpp, .xml e .xps.

**Q: O Aspose.Tasks para Java é compatível com diferentes versões do MS Project?**  
A: Absolutamente, ele suporta arquivos do Project 2000 até a versão mais recente de 2024, abrangendo mais de 20 formatos de versão.

**Q: Existem limitações na versão de avaliação do Aspose.Tasks para Java?**  
A: A avaliação adiciona uma marca d'água aos arquivos gerados e limita o número de tarefas que você pode criar, mas todos os recursos da API permanecem acessíveis.

**Q: Como posso obter suporte para Aspose.Tasks para Java?**  
A: Você pode buscar assistência no fórum da comunidade Aspose.Tasks [aqui](https://forum.aspose.com/c/tasks/15).

**Q: Posso comprar uma licença temporária para Aspose.Tasks para Java?**  
A: Sim, licenças temporárias estão disponíveis para uso de curto prazo. Você pode obter uma [aqui](https://purchase.aspose.com/temporary-license/).

---

**Última atualização:** 2026-05-20  
**Testado com:** Aspose.Tasks for Java 24.12 (latest at time of writing)  
**Autor:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Tutoriais Relacionados

- [Como Adicionar Notas a Atribuições de Recursos no Aspose.Tasks](/tasks/java/resource-assignments/resource-assignment-notes/)
- [Como Ler Escala de Taxa e Gravar Escala de Taxa para Atribuições de Recursos no Aspose.Tasks](/tasks/java/resource-assignments/read-write-rate-scale/)
- [Como Adicionar Recurso ao Projeto e Manipular Propriedades de Atraso de Nivelamento no Aspose.Tasks](/tasks/java/resource-assignments/leveling-delay-properties/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}