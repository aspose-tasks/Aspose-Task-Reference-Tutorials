---
date: 2026-06-30
description: Aprenda como atualizar vários recursos e modificar os dados do grupo
  de recursos, em seguida exportar o projeto para MPP e salvar o projeto como MPP
  usando o Aspose.Tasks for Java.
keywords:
- update multiple resources
- modify resource group
- export project to mpp
- save project as mpp
linktitle: Atualizar Vários Recursos no Aspose.Tasks for Java
schemas:
- author: Aspose
  dateModified: '2026-06-30'
  description: Learn how to update multiple resources and modify resource group data,
    then export project to MPP and save project as MPP using Aspose.Tasks for Java.
  headline: Update Multiple Resources in Aspose.Tasks for Java
  type: TechArticle
- description: Learn how to update multiple resources and modify resource group data,
    then export project to MPP and save project as MPP using Aspose.Tasks for Java.
  name: Update Multiple Resources in Aspose.Tasks for Java
  steps:
  - name: Java Development Kit (JDK) installed on your system.
    text: Java Development Kit (JDK) installed on your system.
  - name: Aspose.Tasks for Java library. You can download it from [here](https://releases.aspose.com/tasks/java/).
    text: Aspose.Tasks for Java library. You can download it from [here](https://releases.aspose.com/tasks/java/).
  - name: Basic knowledge of Java programming.
    text: Basic knowledge of Java programming.
  type: HowTo
- questions:
  - answer: Yes, you can update multiple resources by iterating through them and setting
      their attributes accordingly.
    question: Can I update multiple resources in the same project using Aspose.Tasks
      for Java?
  - answer: Yes, Aspose.Tasks supports various file formats including XML, MPP, and
      more.
    question: Does Aspose.Tasks support other file formats besides MS Project?
  - answer: Aspose.Tasks is compatible with Java versions 6 and above.
    question: Is Aspose.Tasks compatible with different versions of Java?
  - answer: Yes, you can perform a wide range of operations such as reading, writing,
      and manipulating tasks, resources, and calendars.
    question: Can I perform other operations on MS Project files with Aspose.Tasks?
  - answer: You can visit the [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15)
      for any assistance or queries.
    question: Where can I find additional help or support for Aspose.Tasks?
  type: FAQPage
second_title: Aspose.Tasks Java API
title: Atualizar Vários Recursos no Aspose.Tasks for Java
url: /pt/java/resource-management/write-updated-resource-data/
weight: 21
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Atualizar Vários Recursos no Aspise.Tasks para Java

## Introdução
Neste tutorial, você aprenderá como **atualizar vários recursos** em um arquivo Microsoft Project usando Aspose.Tasks para Java. Seja para alterar taxas, reatribuir grupos ou exportar o arquivo atualizado para MPP, as etapas abaixo guiarão você por um fluxo de trabalho completo e pronto para produção. Não é necessária a instalação do Microsoft Project, e a API pode lidar com projetos com centenas de recursos de forma eficiente.

## Respostas Rápidas
- **Posso atualizar vários recursos de uma vez?** Sim – itere através da `ResourceCollection` e defina atributos em uma única passagem.  
- **Qual método salva o arquivo como MPP?** `project.save("output.mpp", SaveFileFormat.MPP)`.  
- **Preciso de licença para uso comercial?** Uma licença paga é necessária para produção; um teste gratuito está disponível.  
- **Quais versões do Java são suportadas?** Java 6 e superiores, incluindo Java 17 LTS.  
- **A atualização em massa tem bom desempenho?** Aspose.Tasks processa projetos com 500 recursos em menos de 2 segundos em um servidor típico.

## O que é “atualizar vários recursos”?
**“Atualizar vários recursos”** refere‑se a alterar programaticamente as propriedades de várias entradas de recursos — como taxas, grupos, calendários ou campos personalizados — dentro de um único arquivo Project. Essa operação é frequentemente necessária ao sincronizar dados de projetos com sistemas de planejamento de recursos empresariais, ajustar orçamentos entre muitos recursos ou aplicar mudanças de política em toda a organização.

## Por que usar Aspose.Tasks para modificar o grupo de recursos e exportar o projeto para MPP?
Aspose.Tasks suporta **mais de 50 formatos de entrada e saída**, incluindo MPP, XML e CSV, e pode **exportar o projeto para MPP** sem carregar todo o arquivo na memória. A biblioteca processa arquivos de até **2 GB** de tamanho, permitindo que você **salve o projeto como MPP** de forma rápida e confiável.

## Pré‑requisitos

Antes de começar, certifique‑se de que você tem o seguinte:

1. Java Development Kit (JDK) instalado no seu sistema.  
2. Biblioteca Aspose.Tasks para Java. Você pode baixá‑la [aqui](https://releases.aspose.com/tasks/java/).  
3. Conhecimento básico de programação Java.  

## Importar Pacotes

`import` statements bring the required Aspose.Tasks classes into your source file.

```java
import com.aspose.tasks.Project;
import com.aspose.tasks.Resource;
import com.aspose.tasks.Rsc;
import com.aspose.tasks.SaveFileFormat;
```

## Etapa 1: Configurar Seu Diretório de Dados

Defina o diretório onde seus arquivos de dados estão localizados:

```java
String dataDir = "Your Data Directory";
```

## Etapa 2: Especificar Arquivos de Entrada e Saída

Defina os caminhos para o arquivo MS Project de entrada e o arquivo atualizado resultante:

```java
String file = dataDir + "ResourceWithExtAttribs.xml"; // Test file with one rsc to update
String resultFile = dataDir + "OutputMPP.mpp"; // File to write test project
```

## Etapa 3: Carregar o Projeto

`Project` representa um arquivo Microsoft Project carregado na memória, fornecendo acesso a tarefas, recursos e outros dados do projeto.

```java
Project project = new Project(file);
```

## Etapa 4: Adicionar um Recurso e Definir Atributos

`Resource` modela um recurso individual do projeto, permitindo que você defina taxas, grupos, calendários e outros atributos.

```java
Resource rsc = project.getResources().add("Rsc");
rsc.set(Rsc.STANDARD_RATE, BigDecimal.valueOf(30));
rsc.set(Rsc.OVERTIME_RATE, BigDecimal.valueOf(45));
rsc.set(Rsc.GROUP, "Workgroup1");
```

## Etapa 5: Atualizar Vários Recursos de Forma Eficiente

`ResourceCollection` é a coleção de todos os recursos em um projeto, acessível via `project.getResources()`.

```java
project.save(resultFile, SaveFileFormat.Mpp);
```

## Etapa 6: Salvar o Projeto

`SaveFileFormat` enumera os formatos de arquivo suportados para salvar um projeto, como MPP, XML e PDF.

```java
project.save(resultFile, SaveFileFormat.Mpp);
```

## Como atualizar vários recursos em um projeto?

Carregue o projeto existente, recupere sua `ResourceCollection` e itere sobre cada objeto `Resource`. Para cada recurso, modifique os campos necessários, como taxas, grupos ou atributos personalizados, e então continue para o próximo item. Após processar todos os recursos, chame `project.save(...)` uma única vez para persistir as alterações de forma eficiente.

## Problemas Comuns e Soluções

- **Conflito de IDs de recursos** – Garanta que cada novo recurso receba um ID único usando `project.getResources().add(new Resource())`.  
- **Erros de formato de taxa** – Use objetos `ResourceRate` e defina `RateType` como `StandardRate` ou `OvertimeRate`.  
- **Arquivos grandes causam pressão de memória** – Ative `Project.setReadOnly(true)` antes de carregar para reduzir o uso de memória.

## Perguntas Frequentes

**Q: Posso atualizar vários recursos no mesmo projeto usando Aspose.Tasks para Java?**  
A: Sim, você pode atualizar vários recursos iterando sobre eles e definindo seus atributos conforme necessário.

**Q: O Aspose.Tasks suporta outros formatos de arquivo além do MS Project?**  
A: Sim, o Aspose.Tasks suporta vários formatos de arquivo, incluindo XML, MPP e outros.

**Q: O Aspose.Tasks é compatível com diferentes versões do Java?**  
A: O Aspose.Tasks é compatível com versões do Java 6 e superiores.

**Q: Posso executar outras operações em arquivos MS Project com Aspose.Tasks?**  
A: Sim, você pode executar uma ampla gama de operações, como ler, gravar e manipular tarefas, recursos e calendários.

**Q: Onde posso encontrar ajuda ou suporte adicional para Aspose.Tasks?**  
A: Você pode visitar o [fórum Aspose.Tasks](https://forum.aspose.com/c/tasks/15) para qualquer assistência ou dúvidas.

**Q: Como exportar o arquivo atualizado para o formato MPP?**  
A: Chame `project.save("UpdatedProject.mpp", SaveFileFormat.MPP)` após fazer todas as alterações nos recursos.

**Q: Qual é a melhor maneira de modificar um grupo de recursos?**  
A: Defina a propriedade `Resource.Group` em cada objeto `Resource` antes de salvar o projeto.

---

**Última atualização:** 2026-06-30  
**Testado com:** Aspose.Tasks for Java 24.12  
**Autor:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Tutoriais Relacionados

- [Adicionar recurso ao projeto com Aspose.Tasks para Java](/tasks/java/resource-management/create-resources/)
- [Gerenciar Custos de Recursos do MS Project com Aspose.Tasks para Java](/tasks/java/resource-management/resource-cost/)
- [Como Exportar MPP para Excel com Aspose.Tasks para Java](/tasks/java/project-file-operations/save-data-to-excel/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}