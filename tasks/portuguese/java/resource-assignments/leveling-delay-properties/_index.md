---
date: 2026-01-07
description: Aprenda como adicionar recurso ao projeto e lidar com propriedades de
  atraso de nivelamento para atribuições de recursos usando Aspose.Tasks para Java.
linktitle: Handle Leveling Delay Properties for Resource Assignments in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Como adicionar recurso ao projeto e lidar com propriedades de atraso de nivelamento
  no Aspose.Tasks
url: /pt/java/resource-assignments/leveling-delay-properties/
weight: 17
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Como Adicionar Recurso ao Projeto e Manipular Propriedades de Atraso de Nivelamento no Aspose.Tasks

## Introdução
Neste tutorial, você aprenderá **como adicionar recurso ao projeto** enquanto também gerencia as propriedades de atraso de nivelamento para atribuições de recurso com o Aspose.Tasks para Java. Seja construindo um mecanismo de agendamento ou automatizando atualizações de projetos, dominar essas etapas permite manter seus dados de projeto precisos sem precisar do Microsoft Project instalado.

## Respostas Rápidas
- **O que significa “add resource to project”?** Cria uma nova entrada de recurso que pode ser atribuída a tarefas.  
- **Posso definir um atraso de nivelamento após a atribuição?** Sim, usando os campos `Asn.DELAY` ou `Asn.LEVELING_DELAY`.  
- **Preciso de licença para executar este código?** Uma avaliação gratuita funciona para desenvolvimento; uma licença paga é necessária para produção.  
- **Qual versão do Java é suportada?** Java 8 ou posterior.  
- **Isso é compatível com todos os formatos de arquivo do MS Project?** Aspose.Tasks suporta .MPP, .XML, .XER e mais.

## O que significa “add resource to project” no Aspose.Tasks?
Adicionar um recurso a um projeto significa criar um objeto `Resource` dentro do modelo `Project`. Esse objeto pode ser vinculado posteriormente a tarefas via `ResourceAssignment`, permitindo que você acompanhe trabalho, custos e configurações de nivelamento.

## Por que lidar com propriedades de atraso de nivelamento?
O atraso de nivelamento ajuda o agendador a distribuir o trabalho quando os recursos estão sobre‑alocados. Ao definir um atraso, você indica ao mecanismo que adie o início de uma atribuição, evitando conflitos e mantendo o projeto realista.

## Pré‑requisitos
Antes de começarmos, certifique‑se de que você possui os seguintes pré‑requisitos:
1. Java Development Kit (JDK): Garanta que o Java JDK esteja instalado em seu sistema. Você pode baixá‑lo e instalá‑lo a partir do [site](https://www.oracle.com/java/technologies/javase-jdk15-downloads.html).  
2. Biblioteca Aspose.Tasks para Java: Baixe a biblioteca Aspose.Tasks para Java na [página de download](https://releases.aspose.com/tasks/java/).

## Importar Pacotes
Primeiro, importe os pacotes necessários ao seu projeto Java para usar as funcionalidades do Aspose.Tasks:
```java
import com.aspose.tasks.Asn;
import com.aspose.tasks.Project;
import com.aspose.tasks.Resource;
import com.aspose.tasks.ResourceAssignment;
import com.aspose.tasks.Task;
import com.aspose.tasks.TimeUnitType;
import com.aspose.tasks.Tsk;
import java.util.Calendar;
```

## Etapa 1: Criar um Objeto Project
Instancie um objeto `Project`, que servirá como contêiner para todas as tarefas, recursos e atribuições:
```java
Project prj = new Project();
```

## Etapa 2: Criar uma Tarefa
Adicione uma tarefa ao projeto. Isso demonstra **como adicionar tarefa** programaticamente:
```java
Task task = prj.getRootTask().getChildren().add("Task 1");
```

## Etapa 3: Definir Data de Início e Duração da Tarefa
Defina quando a tarefa começa e quanto tempo ela irá durar:
```java
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.set(2000, Calendar.JANUARY, 3, 8, 0, 0);
task.set(Tsk.START, cal.getTime());
task.set(Tsk.DURATION, prj.getDuration(8));
```

## Etapa 4: Adicionar um Recurso
Agora nós **add resource to project** criando uma nova entrada `Resource`:
```java
Resource resource = prj.getResources().add("Resource 1");
```

## Etapa 5: Criar uma Atribuição de Recurso
Vincule a tarefa e o recurso recém‑adicionado:
```java
ResourceAssignment assignment = prj.getResourceAssignments().add(task, resource);
```

## Etapa 6: Definir Atraso de Nivelamento
Configure o atraso de nivelamento para a atribuição. Definir como zero significa que não há atraso adicional, mas você pode ajustar o valor conforme necessário:
```java
assignment.set(Asn.DELAY, prj.getDuration(0, TimeUnitType.Day));
```

## Etapa 7: Exibir Resultados
Imprima as propriedades importantes para verificar se tudo foi configurado corretamente:
```java
System.out.println("Delay: " + assignment.get(Asn.DELAY));
System.out.println("Leveling Delay: " + assignment.get(Asn.LEVELING_DELAY));
System.out.println("Process completed Successfully");
```

## Armadilhas Comuns e Dicas
- **Armadilha:** Esquecer de definir a data de início da tarefa pode fazer com que a atribuição use a data de início do projeto por padrão.  
- **Dica:** Use `prj.getDuration(value, TimeUnitType.Day)` para controlar a granularidade do atraso.  
- **Dica:** Após adicionar vários recursos, chame `prj.updateResourceAssignments()` para que o agendador recalcule o nivelamento.

## Conclusão
Seguindo estas etapas, você agora sabe **como add resource to project**, atribuí‑lo a uma tarefa e gerenciar propriedades de atraso de nivelamento usando o Aspose.Tasks para Java. Esse conhecimento permite construir soluções robustas de automação de projetos que permanecem alinhadas com as restrições reais de recursos.

## Perguntas Frequentes
### Q: Posso usar Aspose.Tasks com outras bibliotecas Java?

A: Sim, o Aspose.Tasks pode ser integrado a outras bibliotecas Java para aprimorar as capacidades de gerenciamento de projetos.

### Q: O Aspose.Tasks é compatível com diferentes versões de arquivos do Microsoft Project?

A: Sim, o Aspose.Tasks suporta várias versões de arquivos do Microsoft Project, garantindo compatibilidade em diferentes ambientes.

### Q: Onde posso encontrar suporte adicional para o Aspose.Tasks?

A: Você pode encontrar suporte e recursos no [fórum Aspose.Tasks](https://forum.aspose.com/c/tasks/15).

### Q: Posso experimentar o Aspose.Tasks antes de comprar?

A: Sim, você pode obter uma avaliação gratuita do Aspose.Tasks na [página de releases](https://releases.aspose.com/).

### Q: Como posso obter uma licença temporária para o Aspose.Tasks?

A: Você pode solicitar uma licença temporária na [página de licença temporária](https://purchase.aspose.com/temporary-license/) para fins de avaliação.

## Perguntas Frequentes Adicionais

**Q: O que acontece se eu definir um atraso de nivelamento diferente de zero?**  
A: O agendador adiará o início da atribuição pela duração especificada, ajudando a resolver sobre‑alocações.

**Q: Posso recuperar o atraso de nivelamento após salvar o projeto?**  
A: Sim, você pode reabrir o arquivo do projeto e ler a propriedade `Asn.DELAY` da atribuição.

**Q: Existe uma maneira de aplicar atraso de nivelamento a todas as atribuições de uma vez?**  
A: Você pode iterar através de `prj.getResourceAssignments()` e definir o atraso para cada atribuição em um loop.

---

**Última atualização:** 2026-01-07  
**Testado com:** Aspose.Tasks para Java 24.11  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}