---
date: 2026-06-10
description: Aprenda como ler a taxa e como escrever a escala de taxa para atribuições
  de recursos usando o Aspose.Tasks para Java. Suporta recursos materiais, múltiplos
  formatos e projetos grandes.
keywords:
- how to read rate
- how to write rate
- write rate scale
- Aspose.Tasks rate scale
- resource assignments Java
linktitle: Ler e Escrever a Escala de Taxa para Atribuições de Recursos no Aspose.Tasks
schemas:
- author: Aspose
  dateModified: '2026-06-10'
  description: Learn how to read rate and how to write rate scale for resource assignments
    using Aspose.Tasks for Java. Supports material resources, multiple formats, and
    large projects.
  headline: How to Read Rate Scale and Write Rate Scale for Resource Assignments in
    Aspose.Tasks
  type: TechArticle
- questions:
  - answer: Yes, Aspose.Tasks for Java is compatible with all major Java IDEs, including
      IntelliJ IDEA, Eclipse, and NetBeans.
    question: Can I use Aspose.Tasks for Java with any Java IDE?
  - answer: Yes, Aspose.Tasks supports various file formats, including MPP, XML, and
      HTML.
    question: Does Aspose.Tasks support other file formats besides MPP?
  - answer: Absolutely, Aspose.Tasks offers comprehensive features for managing projects
      of any scale, making it suitable for enterprise‑level project management.
    question: Is Aspose.Tasks suitable for enterprise‑level project management?
  - answer: Yes, Aspose.Tasks provides extensive capabilities for customizing resource
      assignments, including cost, work, and duration adjustments.
    question: Can I customize resource assignments further beyond rate scale?
  - answer: Yes, you can find support and interact with other users on the Aspose.Tasks
      forum [here](https://forum.aspose.com/c/tasks/15).
    question: Is there a community forum for Aspose.Tasks support?
  type: FAQPage
second_title: Aspose.Tasks Java API
title: Como Ler a Escala de Taxa e Escrever a Escala de Taxa para Atribuições de Recursos
  no Aspose.Tasks
url: /pt/java/resource-assignments/read-write-rate-scale/
weight: 20
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Como Ler a Escala de Taxa e Definir a Escala de Taxa para Atribuições de Recursos no Aspose.Tasks

Neste tutorial você descobrirá **como ler a taxa** e ajustá‑la para atribuições de recursos usando Aspose.Tasks para Java. Seja construindo um agendador, uma ferramenta de relatórios ou simplesmente precisando automatizar atualizações de projetos, dominar a manipulação da escala de taxa oferece controle detalhado sobre recursos materiais e de trabalho.

## Respostas Rápidas
`ResourceAssignment` vincula uma tarefa a um recurso e contém dados específicos da atribuição.  
`Asn` contém constantes para campos de atribuição, incluindo `RATE_SCALE`.  
`RateScaleType` enum lista possíveis unidades de tempo para a escala de taxa.  

- **Qual é a classe principal para manipulação de taxa?** `ResourceAssignment` com a propriedade `Asn.RATE_SCALE`.  
- **Qual enum define as opções de escala?** `RateScaleType` (Day, Week, Month, etc.).  
- **Preciso de uma licença para executar o exemplo?** Uma licença de avaliação gratuita funciona para testes; uma licença comercial é necessária para produção.  
- **Posso alterar a escala após salvar?** Sim – recarregue o projeto e modifique `Asn.RATE_SCALE` conforme mostrado.  
- **IDEs suportados?** Qualquer IDE Java (IntelliJ IDEA, Eclipse, NetBeans) pode compilar o código.

## Como ler a escala de taxa para atribuições de recursos?

Carregue o projeto, localize a `ResourceAssignment` desejada e chame `getRateScale()` – isso retorna um valor `RateScaleType` que indica se a taxa é aplicada por dia, semana, mês ou outra unidade. A resposta é imediata e requer apenas duas chamadas de API, tornando‑a ideal para scripts de auditoria ou exibições de UI.

## Como definir a escala de taxa para atribuições de recursos?

Crie ou recupere um objeto `ResourceAssignment`, defina sua propriedade `Asn.RATE_SCALE` para o `RateScaleType` desejado (por exemplo, `RateScaleType.Week`) e, em seguida, salve o projeto. Essa única alteração de propriedade atualiza automaticamente os cálculos de custo e persiste em todos os formatos de arquivo suportados. Após definir a escala, pode ser necessário ajustar a taxa padrão ou a taxa de horas extras do recurso para refletir a nova unidade de tempo, garantindo que os cálculos de custo permaneçam precisos.

## O que é Escala de Taxa?

A escala de taxa determina a unidade de tempo (dia, semana, mês, etc.) à qual a taxa de custo de um recurso é aplicada. Ajustar a escala permite modelar o consumo de material ou o esforço de mão‑de‑obra com precisão. Por exemplo, definir a escala para Week significa que a taxa de custo é interpretada como custo por semana, e o custo total de uma tarefa é calculado com base no número de semanas que o recurso está atribuído.

## Por que ler e definir a escala de taxa?

Ler a escala atual ajuda a auditar cronogramas existentes, enquanto definir uma nova escala permite alinhar os recursos com as políticas de cobrança ou consumo do projeto. Isso é especialmente útil ao **definir custos de recurso material** ou quando você precisa **definir a escala** para calendários de trabalho não‑padrão.

## Pré‑requisitos
Antes de começarmos, certifique-se de que você tem os seguintes pré‑requisitos:
1. **Ambiente de Desenvolvimento Java** – JDK 8 ou superior instalado.  
2. **Biblioteca Aspose.Tasks para Java** – Baixe e instale a biblioteca a partir de [aqui](https://releases.aspose.com/tasks/java/).

## Importar Pacotes
A classe `ResourceAssignment` representa um vínculo entre uma tarefa e um recurso, enquanto `RateScaleType` enumera as possíveis unidades de tempo para uma taxa. Importe as classes necessárias do Aspose.Tasks antes de começar a codificar.  

`Project` é o objeto principal que carrega e salva arquivos Microsoft Project.  
`Resource` define um recurso do projeto, como trabalho ou material.  
`ResourceType` enum especifica se um recurso é de trabalho ou material.  
`Task` representa um item de trabalho na programação do projeto.  
`SaveFileFormat` enum define o formato de saída ao salvar um projeto.

```java
import com.aspose.tasks.Asn;
import com.aspose.tasks.Project;
import com.aspose.tasks.RateScaleType;
import com.aspose.tasks.Resource;
import com.aspose.tasks.ResourceAssignment;
import com.aspose.tasks.ResourceType;
import com.aspose.tasks.Rsc;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.Task;
import java.io.IOException;
```

## Etapa 1: Configurar seu projeto Java
Crie um projeto Maven ou Gradle e adicione o JAR do Aspose.Tasks ao seu classpath. Esta etapa garante que o compilador possa localizar as classes importadas.

## Etapa 2: Carregar o Arquivo de Projeto
Carregue o arquivo Microsoft Project existente com o qual deseja trabalhar.

```java
String dataDir = "Your Data Directory";
Project project = new Project(dataDir + "New project 2013.mpp");
```

## Etapa 3: Adicionar uma Tarefa
Crie uma nova tarefa que receberá atribuições de recursos posteriormente.

```java
Task task = project.getRootTask().getChildren().add("t1");
```

## Etapa 4: Definir Recursos
Aqui nós **definimos recurso material** e um recurso de trabalho regular. Observe o uso de `ResourceType.Material` para o recurso do tipo material.

```java
Resource materialResource = project.getResources().add("materialResource");
materialResource.set(Rsc.TYPE, ResourceType.Material);
Resource nonMaterialResource = project.getResources().add("nonMaterialResource");
nonMaterialResource.set(Rsc.TYPE, ResourceType.Work);
```

## Etapa 5: Atribuir Recursos à Tarefa
Agora nós **atribuímos recursos à tarefa** e especificamos **como definir a escala** usando `RateScaleType.Week`. Isso ilustra tanto a leitura quanto a escrita da escala de taxa.

```java
ResourceAssignment materialResourceAssignment = project.getResourceAssignments().add(task, materialResource);
materialResourceAssignment.set(Asn.RATE_SCALE, RateScaleType.Week);
ResourceAssignment nonMaterialResourceAssignment = project.getResourceAssignments().add(task, nonMaterialResource);
nonMaterialResourceAssignment.set(Asn.RATE_SCALE, RateScaleType.Week);
```

## Etapa 6: Salvar o Projeto
Persista as alterações em um novo arquivo para que possamos, posteriormente, verificar a escala de taxa armazenada.

```java
project.save("output.mpp", SaveFileFormat.Mpp);
```

## Etapa 7: Recuperar Atribuições de Recursos
Recarregue o projeto salvo e **leia a escala de taxa** para confirmar que foi escrita corretamente.

```java
Project resavedProject = new Project("output.mpp");
ResourceAssignment resavedMaterialResourceAssignment = resavedProject.getResourceAssignments().getByUid(1);
System.out.println(resavedMaterialResourceAssignment.get(Asn.RATE_SCALE));
ResourceAssignment resavedNonMaterialResourceAssignment = resavedProject.getResourceAssignments().getByUid(2);
```

## Armadilhas Comuns & Dicas
- **UID Mismatch** – Ao recuperar atribuições por UID, certifique‑se de que os valores de UID correspondam aos atribuídos durante a criação.  
- **Incorrect Resource Type** – Usar `ResourceType.Material` para um recurso de trabalho fará com que os cálculos de taxa se comportem inesperadamente.  
- **Saving Format** – Sempre salve usando `SaveFileFormat.Mpp` (ou outro formato suportado) para preservar campos personalizados como a escala de taxa.  
- **Large Projects** – Aspose.Tasks pode processar arquivos com **500+ pages** sem carregar todo o documento na memória, graças à sua arquitetura de streaming.

## Perguntas Frequentes

**Q: Posso usar Aspose.Tasks para Java com qualquer IDE Java?**  
A: Sim, Aspose.Tasks para Java é compatível com todas as principais IDEs Java, incluindo IntelliJ IDEA, Eclipse e NetBeans.

**Q: O Aspose.Tasks suporta outros formatos de arquivo além de MPP?**  
A: Sim, Aspose.Tasks suporta vários formatos de arquivo, incluindo MPP, XML e HTML.

**Q: O Aspose.Tasks é adequado para gerenciamento de projetos em nível empresarial?**  
A: Absolutamente, Aspose.Tasks oferece recursos abrangentes para gerenciar projetos de qualquer escala, tornando‑o adequado para gerenciamento de projetos em nível empresarial.

**Q: Posso personalizar ainda mais as atribuições de recursos além da escala de taxa?**  
A: Sim, Aspose.Tasks fornece amplas capacidades para personalizar atribuições de recursos, incluindo ajustes de custo, trabalho e duração.

**Q: Existe um fórum da comunidade para suporte ao Aspose.Tasks?**  
A: Sim, você pode encontrar suporte e interagir com outros usuários no fórum Aspose.Tasks [aqui](https://forum.aspose.com/c/tasks/15).

---

**Última Atualização:** 2026-06-10  
**Testado com:** Aspose.Tasks para Java 24.12 (latest at time of writing)  
**Autor:** Aspose

## Tutoriais Relacionados

- [Criar Atribuições de Recursos no Aspose.Tasks](/tasks/java/resource-assignments/create-resource-assignments/)
- [Como Modificar Atribuições – Ler Recursos Compartilhados com Aspose](/tasks/java/resource-assignments/read-shared-resource-assignments/)
- [Como Adicionar Notas às Atribuições de Recursos no Aspose.Tasks](/tasks/java/resource-assignments/resource-assignment-notes/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}