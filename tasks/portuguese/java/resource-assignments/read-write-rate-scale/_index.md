---
date: 2026-01-10
description: Aprenda como ler a escala de taxa e gerenciar atribuições de recursos
  no Aspose.Tasks para Java. Defina recurso material, como definir a escala e atribuir
  recursos à tarefa.
linktitle: Read and Write Rate Scale for Resource Assignments in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Como ler a escala de taxa e escrever a escala de taxa para atribuições de recursos
  no Aspose.Tasks
url: /pt/java/resource-assignments/read-write-rate-scale/
weight: 20
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Como Ler a Escala de Taxa e Gravar a Escala de Taxa para Atribuições de Recursos no Aspose.Tasks

Neste tutorial você descobrirá **como ler a escala de taxa** e ajustar as configurações para atribuições de recursos usando Aspose.Tasks for Java. Seja construindo um agendador, uma ferramenta de relatórios ou simplesmente precisando automatizar atualizações de projetos, dominar a manipulação da escala de taxa oferece controle detalhado sobre recursos materiais e de trabalho.

## Respostas Rápidas
- **Qual é a classe principal para manipulação de taxa?** `ResourceAssignment` com a propriedade `Asn.RATE_SCALE`.  
- **Qual enum define as opções de escala?** `RateScaleType` (Day, Week, Month, etc.).  
- **Preciso de uma licença para executar o exemplo?** Uma licença de avaliação gratuita funciona para testes; uma licença comercial é necessária para produção.  
- **Posso alterar a escala após salvar?** Sim – recarregue o projeto e modifique `Asn.RATE_SCALE` conforme mostrado.  
- **IDE suportadas?** Qualquer IDE Java (IntelliJ IDEA, Eclipse, NetBeans) pode compilar o código.

## O que é Escala de Taxa?
A escala de taxa determina a unidade de tempo (dia, semana, mês, etc.) à qual a taxa de custo de um recurso é aplicada. Ajustar a escala permite modelar o consumo de material ou o esforço de trabalho com precisão.

## Por que ler e gravar a escala de taxa?
Ler a escala atual ajuda a auditar cronogramas existentes, enquanto gravar uma nova escala permite alinhar os recursos com as políticas de cobrança ou consumo do projeto. Isso é especialmente útil ao **definir custos de recurso material** ou quando você precisa **definir a escala** para calendários de trabalho não padrão.

## Pré-requisitos
Antes de começarmos, certifique-se de que você possui os seguintes pré-requisitos:
1. **Ambiente de Desenvolvimento Java** – JDK 8 ou superior instalado.  
2. **Biblioteca Aspose.Tasks for Java** – Baixe e instale a biblioteca a partir de [here](https://releases.aspose.com/tasks/java/).

## Importar Pacotes
Primeiro, importe as classes necessárias do Aspose.Tasks.

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
Agora nós **atribuímos recursos à tarefa** e especificamos **como definir a escala** usando `RateScaleType.Week`. Isso ilustra tanto a leitura quanto a gravação da escala de taxa.

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
Recarregue o projeto salvo e **leia a escala de taxa** para confirmar que foi gravada corretamente.

```java
Project resavedProject = new Project("output.mpp");
ResourceAssignment resavedMaterialResourceAssignment = resavedProject.getResourceAssignments().getByUid(1);
System.out.println(resavedMaterialResourceAssignment.get(Asn.RATE_SCALE));
ResourceAssignment resavedNonMaterialResourceAssignment = resavedProject.getResourceAssignments().getByUid(2);
```

## Armadilhas Comuns & Dicas
- **Incompatibilidade de UID** – Ao recuperar atribuições por UID, certifique-se de que os valores de UID correspondam aos atribuídos durante a criação.  
- **Tipo de Recurso Incorreto** – Usar `ResourceType.Material` para um recurso de trabalho fará com que os cálculos de taxa se comportem de forma inesperada.  
- **Formato de Salvamento** – Sempre salve usando `SaveFileFormat.Mpp` (ou outro formato suportado) para preservar campos personalizados como a escala de taxa.

## Conclusão
Gerenciar e inspecionar a escala de taxa para atribuições de recursos no Aspose.Tasks for Java é simples uma vez que você conhece as classes e propriedades relevantes. Seguindo este guia, você pode **ler informações de taxa**, **definir objetos de recurso material**, **definir a escala** e **atribuir recursos à tarefa** com confiança.

## Perguntas Frequentes

**Q: Posso usar Aspose.Tasks for Java com qualquer IDE Java?**  
A: Sim, Aspose.Tasks for Java é compatível com todas as principais IDEs Java, incluindo IntelliJ IDEA, Eclipse e NetBeans.

**Q: O Aspose.Tasks suporta outros formatos de arquivo além de MPP?**  
A: Sim, o Aspose.Tasks suporta vários formatos de arquivo, incluindo MPP, XML e HTML.

**Q: O Aspose.Tasks é adequado para gerenciamento de projetos em nível empresarial?**  
A: Absolutamente, o Aspose.Tasks oferece recursos abrangentes para gerenciar projetos de qualquer escala, tornando‑o adequado para gerenciamento de projetos em nível empresarial.

**Q: Posso personalizar ainda mais as atribuições de recursos além da escala de taxa?**  
A: Sim, o Aspose.Tasks fornece amplas capacidades para personalizar atribuições de recursos, incluindo ajustes de custo, trabalho e duração.

**Q: Existe um fórum da comunidade para suporte ao Aspose.Tasks?**  
A: Sim, você pode encontrar suporte e interagir com outros usuários no fórum do Aspose.Tasks [here](https://forum.aspose.com/c/tasks/15).

---

**Última atualização:** 2026-01-10  
**Testado com:** Aspose.Tasks for Java 24.12 (latest at time of writing)  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}