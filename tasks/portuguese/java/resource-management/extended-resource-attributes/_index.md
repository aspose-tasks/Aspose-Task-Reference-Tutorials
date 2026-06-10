---
date: 2026-06-10
description: Aprenda como criar atributo estendido em Java, carregar um arquivo Microsoft
  Project, definir valores numéricos e salvar o projeto como XML usando Aspose.Tasks
  for Java.
keywords:
- create extended attribute java
- custom attribute Aspose.Tasks
- Java project management
linktitle: Manipular atributos de recurso estendidos no Aspose.Tasks
schemas:
- author: Aspose
  dateModified: '2026-06-10'
  description: Learn how to create extended attribute in Java, load a Microsoft Project
    file, set numeric values, and save the project as XML using Aspose.Tasks for Java.
  headline: How to create extended attribute in Java with Aspose.Tasks
  type: TechArticle
- description: Learn how to create extended attribute in Java, load a Microsoft Project
    file, set numeric values, and save the project as XML using Aspose.Tasks for Java.
  name: How to create extended attribute in Java with Aspose.Tasks
  steps:
  - name: Define Data Directory
    text: '`Paths` is a utility class that provides methods to obtain a file system
      path in a platform‑independent way.'
  - name: Load Microsoft Project File
    text: '`Project` represents a Microsoft Project file in memory, allowing read
      and write access to its contents.'
  - name: Define the Custom Attribute
    text: '`ExtendedAttributeDefinition` defines the schema of a new custom field
      that can be attached to resources or tasks.'
  - name: Set Numeric Value in Java
    text: '`ExtendedAttributeResource` holds the value of a custom attribute for a
      specific resource instance.'
  - name: Add Resource and Attach the Custom Attribute
    text: '`Resource` models a project resource such as a person, equipment, or material.'
  - name: Save Project as XML
    text: '`SaveFileFormat` enumerates the supported output formats for saving a project,
      including XML.'
  - name: Display Result
    text: '`System.out.println` prints a line of text to the standard console output.'
  type: HowTo
- questions:
  - answer: Yes – use `ExtendedAttributeTask` instead of `ExtendedAttributeResource`
      when defining the attribute schema.
    question: Can I create custom attributes for tasks as well as resources?
  - answer: Absolutely. Create separate `ExtendedAttributeDefinition` objects for
      each attribute and attach them to the desired resources or tasks.
    question: Is it possible to add multiple custom attributes at once?
  - answer: Aspose.Tasks supports XML, MPP, PDF, HTML, and more than 30 additional
      formats. In this example we used `SaveFileFormat.Xml`.
    question: What formats can I save the project in?
  - answer: A temporary evaluation license is sufficient for testing. For any production
      deployment, a full commercial license is required.
    question: Do I need a license for development builds?
  - answer: Call `resource.getExtendedAttributes()` and iterate over the collection;
      retrieve the stored value with `getNumericValue()` or `getTextValue()`.
    question: How do I read back the custom attribute values later?
  type: FAQPage
second_title: Aspose.Tasks Java API
title: Como criar atributo estendido em Java com Aspose.Tasks
url: /pt/java/resource-management/extended-resource-attributes/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Como criar atributo estendido em Java com Aspose.Tasks

## Introdução
Neste guia prático, você **criará um atributo estendido em Java** para um arquivo Microsoft Project usando o Aspose.Tasks. Vamos percorrer o carregamento de um projeto existente, a definição de um novo atributo numérico, a atribuição de um valor a um recurso e, finalmente, a persistência das alterações como um arquivo XML. Ao final, você terá um padrão de código reutilizável que pode ser inserido em qualquer solução de gerenciamento de projetos baseada em Java.

## Respostas Rápidas
- **O que é um atributo estendido?**  
  Um campo definido pelo usuário (ex.: Idade, Nível de Habilidade) que armazena dados extras para recursos ou tarefas.  
- **Qual API o cria?**  
  Aspose.Tasks for Java fornece a classe `ExtendedAttributeDefinition` para definir e gerenciar atributos personalizados.  
- **Preciso de uma licença?**  
  Uma licença de avaliação temporária funciona para desenvolvimento; uma licença completa é necessária para implantações em produção.  
- **Posso armazenar números?**  
  Sim – use `setNumericValue(BigDecimal)` para atribuir valores decimais precisos.  
- **Como persisto as alterações?**  
  Chame `project.save("output.xml", SaveFileFormat.Xml)` para gravar o projeto atualizado no formato XML.

## O que é um atributo personalizado?
Um **atributo personalizado** (também conhecido como atributo estendido) é uma coluna adicional que você pode adicionar a recursos ou tarefas no Microsoft Project. Ele permite capturar dados que não são cobertos pelos campos padrão, como idade do funcionário, nível de certificação ou qualquer métrica específica do negócio.

## Por que criar um atributo estendido em Java?
Criar um atributo estendido em Java permite enriquecer programaticamente os dados do projeto, garantindo consistência entre arquivos e possibilitando relatórios automatizados. Ao definir o atributo uma única vez, você pode aplicá‑lo a qualquer número de recursos ou tarefas sem inserção manual, economizando tempo e reduzindo erros.

- **Adaptar os dados à sua organização** – armazene qualquer métrica que seja importante para você sem soluções manuais no Excel.  
- **Permitir relatórios mais ricos** – consulte o campo personalizado posteriormente para painéis ou análises.  
- **Manter a consistência** – aplique programaticamente a mesma definição em dezenas de projetos, eliminando erros humanos.  
- **Testado em desempenho** – Aspose.Tasks processa projetos com até 10.000 tarefas e 5.000 recursos sem carregar todo o arquivo na memória, de acordo com os benchmarks do produto.

## Pré‑requisitos
Antes de começar, certifique‑se de que você tem:

1. **Java Development Kit** – JDK 8 ou mais recente instalado.  
2. **Aspose.Tasks for Java** – baixe a versão mais recente em [aqui](https://releases.aspose.com/tasks/java/).  
3. **IDE** – Eclipse, IntelliJ IDEA ou qualquer ambiente de desenvolvimento compatível com Java.  

## Como criar um atributo estendido em Java?
Carregue seu projeto, defina o atributo, anexe‑o a um recurso e salve o arquivo – tudo em alguns passos simples. As seções a seguir dividem cada passo em uma explicação concisa seguida do placeholder onde seu código real reside.

### Guia passo a passo

#### Importar Pacotes
`Project`, `ExtendedAttributeDefinition`, `ExtendedAttributeResource` e classes relacionadas residem no namespace `com.aspose.tasks`. Importe‑as no início do seu arquivo Java.

```java
import com.aspose.tasks.ExtendedAttribute;
import com.aspose.tasks.ExtendedAttributeDefinition;
import com.aspose.tasks.ExtendedAttributeResource;
import com.aspose.tasks.ExtendedAttributeTask;
import com.aspose.tasks.Project;
import com.aspose.tasks.Resource;
import com.aspose.tasks.SaveFileFormat;
import java.math.BigDecimal;
```

#### Etapa 1: Definir Diretório de Dados
`Paths` é uma classe utilitária que fornece métodos para obter um caminho de sistema de arquivos de forma independente da plataforma.

```java
String dataDir = "Your Data Directory";
```

#### Etapa 2: Carregar Arquivo Microsoft Project
`Project` representa um arquivo Microsoft Project na memória, permitindo acesso de leitura e escrita ao seu conteúdo.

```java
Project prj = new Project(dataDir + "ResourceWithExtAttribs.xml");
```

#### Etapa 3: Definir o Atributo Personalizado
`ExtendedAttributeDefinition` define o esquema de um novo campo personalizado que pode ser anexado a recursos ou tarefas.

```java
ExtendedAttributeDefinition myNumber1 = prj.getExtendedAttributes().getById((int) ExtendedAttributeTask.Number1);
if (myNumber1 == null) {
    myNumber1 = ExtendedAttributeDefinition.createResourceDefinition(ExtendedAttributeResource.Number1, "Age");
    prj.getExtendedAttributes().add(myNumber1);
}
```

#### Etapa 4: Definir Valor Numérico em Java
`ExtendedAttributeResource` contém o valor de um atributo personalizado para uma instância específica de recurso.

```java
ExtendedAttribute number1Resource = myNumber1.createExtendedAttribute();
number1Resource.setNumericValue(BigDecimal.valueOf(30.5345));
```

#### Etapa 5: Adicionar Recurso e Anexar o Atributo Personalizado
`Resource` modela um recurso de projeto, como uma pessoa, equipamento ou material.

```java
Resource rsc = prj.getResources().add("R1");
rsc.getExtendedAttributes().add(number1Resource);
```

#### Etapa 6: Salvar Projeto como XML
`SaveFileFormat` enumera os formatos de saída suportados para salvar um projeto, incluindo XML.

```java
prj.save(dataDir + "project5.xml", SaveFileFormat.Xml);
```

#### Etapa 7: Exibir Resultado
`System.out.println` imprime uma linha de texto na saída padrão do console.

```java
System.out.println("Process completed Successfully");
```

## Armadilhas Comuns & Dicas
- **Conflitos de ID de atributo:** Sempre chame `project.getExtendedAttributes().getById(id)` antes de criar uma nova definição para evitar identificadores duplicados.  
- **Manipulação de precisão:** Prefira `BigDecimal` em vez de `float`/`double` para valores numéricos exatos; isso evita erros de arredondamento em relatórios.  
- **Confiabilidade do caminho de arquivo:** Use `Paths.get(...).toAbsolutePath()` ou configure o diretório de trabalho da sua IDE para eliminar `FileNotFoundException`.  

## Perguntas Frequentes

**Q: Posso criar atributos personalizados para tarefas assim como para recursos?**  
A: Sim – use `ExtendedAttributeTask` em vez de `ExtendedAttributeResource` ao definir o esquema do atributo.

**Q: É possível adicionar vários atributos personalizados de uma vez?**  
A: Absolutamente. Crie objetos `ExtendedAttributeDefinition` separados para cada atributo e anexe‑os aos recursos ou tarefas desejados.

**Q: Em quais formatos posso salvar o projeto?**  
A: Aspose.Tasks suporta XML, MPP, PDF, HTML e mais de 30 formatos adicionais. Neste exemplo usamos `SaveFileFormat.Xml`.

**Q: Preciso de uma licença para compilações de desenvolvimento?**  
A: Uma licença de avaliação temporária é suficiente para testes. Para qualquer implantação em produção, é necessária uma licença comercial completa.

**Q: Como leio os valores dos atributos personalizados posteriormente?**  
A: Chame `resource.getExtendedAttributes()` e itere sobre a coleção; recupere o valor armazenado com `getNumericValue()` ou `getTextValue()`.

---

**Última atualização:** 2026-06-10  
**Testado com:** Aspose.Tasks for Java 24.12  
**Autor:** Aspose

## Tutoriais Relacionados

- [Como Criar Recursos – Gerenciamento de Recursos com Aspose.Tasks para Java](/tasks/java/resource-management/)
- [Criar campo personalizado Aspose - Manipular atributos estendidos](/tasks/java/project-management/extended-attributes/)
- [Como Criar Projeto – Definir Novos Atributos de Tarefa com Aspose.Tasks](/tasks/java/project-file-operations/set-attributes-new-tasks/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< blocks/products/products-backtop-button >}}
{{< /blocks/products/pf/main-wrap-class >}}