---
date: 2026-07-14
description: Aprenda como parar Resource Assignment Java, gerenciar atribuições de
  recursos e ver exemplos usando Aspose.Tasks for Java neste guia passo a passo.
keywords:
- stop resource assignment java
- Aspose.Tasks Java
- resource assignment management
- project scheduling Java
lastmod: 2026-07-14
linktitle: Parar e retomar Resource Assignments no Aspose.Tasks
og_description: Pare Resource Assignment Java com Aspose.Tasks. Este tutorial mostra
  como pausar e retomar atribuições, lidar com datas e integrar a API sem Microsoft
  Project.
og_image_alt: Guide to stop and resume resource assignments in Aspose.Tasks for Java
og_title: Parar Resource Assignment Java – Guia Aspose.Tasks
schemas:
- author: Aspose
  dateModified: '2026-07-14'
  description: Learn how to stop resource assignment java, manage resource assignments,
    and view examples using Aspose.Tasks for Java in this step‑by‑step guide.
  headline: How to Stop Resource Assignment Java – Resume with Aspose.Tasks
  type: TechArticle
- questions:
  - answer: Use `ra.set(Asn.STOP, yourDateObject);` where `yourDateObject` is a `java.util.Date`.
    question: How do I programmatically set a stop date for an assignment?
  - answer: The API does not enforce chronological order; however, the scheduler will
      treat the assignment as active only after the later of the two dates, so you
      should validate dates yourself.
    question: What happens if the resume date is earlier than the stop date?
  - answer: Yes, iterate through `prj.getResourceAssignments()` and check `ra.get(Asn.STOP)
      != null`.
    question: Can I filter assignments to only those that have a stop date set?
  - answer: Set the stop date to `null` with `ra.set(Asn.STOP, null);` and then save
      the project.
    question: Is it possible to remove a stop date once set?
  - answer: Absolutely. The `Asn` enum provides constants for all assignment fields,
      such as `Asn.START`, `Asn.FINISH`, etc.
    question: Does Aspose.Tasks support other date‑related fields like start, finish,
      or actual start?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- stop resource assignment
- Aspose.Tasks
- Java project scheduling
- resource management
title: Como parar Resource Assignment Java – Retomar com Aspose.Tasks
url: /pt/java/resource-assignments/stop-resume-assignment/
weight: 23
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Como interromper a atribuição de recursos Java – Retomar com Aspose.Tasks

## Introdução
Neste tutorial você aprenderá **como interromper a atribuição de recursos java** e, posteriormente, retomá‑la usando Aspose.Tasks para Java. Aspose.Tasks é uma API Java robusta que permite ler e gravar arquivos Microsoft Project, manipular cronogramas e controlar atribuições de recursos — tudo sem precisar do Microsoft Project instalado. Vamos percorrer cada passo, explicar por que cada linha é importante e compartilhar dicas práticas que você pode aplicar a planos de projeto do mundo real.

## Respostas Rápidas
- **O que significa “parar atribuição”?** Marca uma atribuição de recurso como temporariamente inativa a partir de uma data de parada específica.  
- **Posso retomar a mesma atribuição mais tarde?** Sim, definindo uma data de retomada na mesma atribuição.  
- **Preciso do Microsoft Project para usar esta API?** Não, Aspose.Tasks funciona independentemente do Microsoft Project.  
- **Qual versão do Java é necessária?** Java 8 ou superior é recomendado.  
- **Onde posso baixar a biblioteca?** Na página oficial de download do Aspose.Tasks Java.

## Como interromper a atribuição de recursos java?
Carregue seu projeto, localize o `ResourceAssignment` alvo, defina a data `STOP`, opcionalmente defina uma data `RESUME` e, em seguida, salve o arquivo. Essa sequência pausa o trabalho pelo período especificado e o reativa automaticamente após a data de retomada, proporcionando controle preciso sobre os calendários de recursos sem edições manuais de arquivo.

## O que significa “como interromper atribuição” no contexto do Aspose.Tasks?
Interromper uma atribuição indica ao agendador que ignore o trabalho alocado a um recurso após a **data de parada** até a **data de retomada** (se houver). Isso é útil para lidar com férias, indisponibilidade de equipamentos ou qualquer período em que um recurso não deva ser considerado ativo.

## Por que usar Aspose.Tasks para gerenciar atribuições de recursos?
Aspose.Tasks permite controlar programaticamente as datas de atribuição, eliminando edições manuais e reduzindo o risco de erros. Suporta **mais de 50 formatos de entrada e saída** e pode processar projetos com **até 10.000 tarefas** mantendo o uso de memória abaixo de 200 MB, pois transmite dados em vez de carregar todo o arquivo na memória. A API funciona em qualquer SO que suporte Java, oferecendo flexibilidade multiplataforma.

## Pré-requisitos
Antes de começar, certifique‑se de que você tem:

- Java Development Kit (JDK) 8 ou mais recente instalado.  
- Biblioteca Aspose.Tasks for Java baixada. Você pode baixá‑la [aqui](https://releases.aspose.com/tasks/java/).  
- Compreensão básica de programação Java.  

## Importar Pacotes
As classes `Project`, `ResourceAssignment` e `Asn` estão no namespace `com.aspose.tasks`. Importe‑as no topo do seu arquivo‑fonte:

```java
import com.aspose.tasks.Asn;
import com.aspose.tasks.Project;
import com.aspose.tasks.ResourceAssignment;
import java.util.Calendar;
import java.util.GregorianCalendar;
import java.util.Objects;
```

## Etapa 1: Carregar o Arquivo de Projeto
A classe `Project` é o objeto de nível superior do Aspose.Tasks que representa um único arquivo Microsoft Project na memória. Criar uma instância carrega o arquivo e fornece acesso a tarefas, recursos e atribuições.

```java
// The path to the documents directory.
String dataDir = "Your Data Directory";
// Load the project file
Project prj = new Project(dataDir + "ResourceAssignmentVariance.mpp");
```

## Etapa 2: Percorrer as Atribuições de Recursos
Objetos `ResourceAssignment` expõem todos os campos relacionados a atribuições. Definimos uma **data mínima** para filtrar datas de placeholder e então iteramos por cada atribuição. Esse padrão é o exemplo padrão de *atribuição de recurso* para inspeção ou modificação.

```java
// Define minimum date
java.util.Date minDate = new GregorianCalendar(2000, Calendar.JANUARY, 1).getTime();
// Iterate through resource assignments
for (ResourceAssignment ra : prj.getResourceAssignments()) {
```

## Etapa 3: Verificar Datas de Parada e Retomada
Neste bloco examinamos os campos `STOP` e `RESUME` de cada atribuição. Se uma data for anterior à nossa `minDate`, tratamos como não definida (`"NA"`); caso contrário, exibimos a data real. Essa lógica é essencial para **gerenciar atribuições de recursos** corretamente.

```java
    // Check stop date
    if (ra.get(Asn.STOP).before(minDate)) {
        System.out.println("NA");
    } else {
        System.out.println(ra.get(Asn.STOP));
    }
    // Check resume date
    if (ra.get(Asn.RESUME).before(minDate)) {
        System.out.println("NA");
    } else {
        System.out.println(ra.get(Asn.RESUME));
    }
}
```

## Problemas Comuns e Soluções
- **Datas nulas** – `ra.get(Asn.STOP)` pode retornar `null`. Proteja‑se adicionando uma verificação de nulidade antes de chamar `.before(minDate)`.  
- **Caminho de arquivo incorreto** – Certifique‑se de que `dataDir` termina com um separador de caminho (`/` ou `\\`) adequado ao seu SO.  
- **Incompatibilidade de versão** – Use a versão mais recente do Aspose.Tasks for Java para evitar valores de enum ausentes.

## Perguntas Frequentes

**Q: Como definir programaticamente uma data de parada para uma atribuição?**  
A: Use `ra.set(Asn.STOP, seuObjetoDate);` onde `seuObjetoDate` é um `java.util.Date`.

**Q: O que acontece se a data de retomada for anterior à data de parada?**  
A: A API não impõe ordem cronológica; porém, o agendador tratará a atribuição como ativa apenas após a data mais tardia entre as duas, portanto você deve validar as datas manualmente.

**Q: Posso filtrar atribuições apenas para aquelas que têm uma data de parada definida?**  
A: Sim, itere através de `prj.getResourceAssignments()` e verifique `ra.get(Asn.STOP) != null`.

**Q: É possível remover uma data de parada após definida?**  
A: Defina a data de parada como `null` com `ra.set(Asn.STOP, null);` e então salve o projeto.

**Q: O Aspose.Tasks suporta outros campos relacionados a datas, como início, término ou início real?**  
A: Absolutamente. O enum `Asn` fornece constantes para todos os campos de atribuição, como `Asn.START`, `Asn.FINISH`, etc.

## Conclusão
Seguindo estas etapas, você agora sabe **como interromper a atribuição de recursos java**, inspecionar as datas de parada/retomada e retomar a atribuição quando necessário. Essa capacidade permite **gerenciar atribuições de recursos** com mais precisão, especialmente em cenários como férias de recursos ou indisponibilidade de equipamentos. Sinta‑se à vontade para ampliar o exemplo para atualizar datas, gerar relatórios ou integrar com sua própria lógica de agendamento.

---

**Last Updated:** 2026-07-14  
**Tested With:** Aspose.Tasks for Java 24.12  
**Author:** Aspose

## Tutoriais Relacionados

- [Criar Atribuições de Recursos no Aspose.Tasks](/tasks/java/resource-assignments/create-resource-assignments/)
- [Como Calcular Variação de Custo e Gerenciar Custos de Atribuição com Aspose.Tasks](/tasks/java/resource-assignments/assignment-cost/)
- [Como Adicionar Notas às Atribuições de Recursos no Aspose.Tasks](/tasks/java/resource-assignments/resource-assignment-notes/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< blocks/products/products-backtop-button >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}