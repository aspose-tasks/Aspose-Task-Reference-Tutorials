---
date: 2026-06-05
description: Aprenda como criar atribuição de recursos com Aspose.Tasks para Java,
  adicionar recursos a um projeto e gerenciar propriedades de atraso de nivelamento.
keywords:
- create resource assignment aspotasks
- Aspose.Tasks Java
- leveling delay properties
linktitle: Manipular propriedades de atraso de nivelamento para atribuições de recursos
  no Aspose.Tasks
schemas:
- author: Aspose
  dateModified: '2026-06-05'
  description: Learn how to create resource assignment with Aspose.Tasks for Java,
    add resources to a project, and manage leveling delay properties.
  headline: Create Resource Assignment with Aspose.Tasks for Java
  type: TechArticle
- questions:
  - answer: Yes, Aspose.Tasks integrates smoothly with libraries such as Jackson for
      JSON handling or Apache POI for additional spreadsheet operations, allowing
      you to build richer project‑management solutions.
    question: Can I use Aspose.Tasks with other Java libraries?
  - answer: Aspose.Tasks supports 12+ file formats—including .MPP (2003‑2021), .XML,
      .XER, .CSV, .PDF, .HTML, and .MPP12—ensuring seamless round‑trip editing across
      all major Project versions.
    question: Is Aspose.Tasks compatible with different versions of Microsoft Project
      files?
  - answer: You can find support and community discussions on the [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15).
    question: Where can I find additional support for Aspose.Tasks?
  - answer: Yes, a fully functional free trial is available from the [releases page](https://releases.aspose.com/).
    question: Can I try Aspose.Tasks before purchasing?
  - answer: Request a temporary license from the [temporary license page](https://purchase.aspose.com/temporary-license/)
      to run the library without evaluation restrictions.
    question: How can I obtain a temporary license for evaluation?
  type: FAQPage
second_title: Aspose.Tasks Java API
title: Criar atribuição de recursos com Aspose.Tasks para Java
url: /pt/java/resource-assignments/leveling-delay-properties/
weight: 17
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Criar Atribuição de Recurso com Aspose.Tasks para Java

Neste guia abrangente, você aprenderá **como criar atribuição de recurso aspotasks** usando a biblioteca Aspose.Tasks para Java. Seja construindo um mecanismo de agendamento personalizado, automatizando atualizações em massa de projetos, ou simplesmente precisando manipular arquivos do Microsoft Project sem o aplicativo de desktop, dominar estas etapas permite que você mantenha os dados do seu projeto precisos e totalmente controláveis.

## Respostas Rápidas
- **O que significa “add resource to project”?** Ele cria uma nova entrada de recurso que pode ser atribuída a tarefas posteriormente.  
- **Posso definir um atraso de nivelamento após a atribuição?** Sim, usando os campos `Asn.DELAY` ou `Asn.LEVELING_DELAY`.  
- **Preciso de uma licença para executar este código?** Uma avaliação gratuita funciona para desenvolvimento; uma licença paga é necessária para produção.  
- **Qual versão do Java é suportada?** Java 8 ou superior.  
- **Isso é compatível com todos os formatos de arquivo do MS Project?** Aspose.Tasks suporta mais de 12 formatos — incluindo .MPP, .XML, .XER, .CSV, .PDF e mais.

## O que é “add resource to project” no Aspose.Tasks?
Adicionar um recurso a um projeto significa criar um objeto `Resource` dentro do modelo `Project`. Esse objeto pode ser posteriormente vinculado a tarefas via `ResourceAssignment`, permitindo que você rastreie trabalho, custos e configurações de nivelamento. Ao inserir um recurso, você fornece ao agendador algo para alocar, e pode posteriormente consultar ou modificar suas propriedades, como disponibilidade, taxas e atribuições de calendário.

## Por que lidar com propriedades de atraso de nivelamento?
O atraso de nivelamento indica ao agendador que ele deve adiar o início de uma atribuição superalocada, distribuindo o trabalho de forma mais uniforme ao longo da linha do tempo. Ao configurar esse atraso, você evita datas de início irrealistas, reduz avisos de superalocação e produz um cronograma que reflete restrições de recursos do mundo real. Ajustar o atraso também oferece controle granular sobre a quantidade de folga que o mecanismo pode inserir, ajudando você a cumprir os prazos do projeto enquanto respeita os limites de recursos.

## Como criar atribuição de recurso aspotasks?
Carregue seu objeto `Project`, adicione uma tarefa, crie um recurso e, em seguida, vincule-os com um `ResourceAssignment`. Esse fluxo de ponta a ponta permite que você construa programaticamente uma estrutura completa de projeto e controle imediatamente o atraso de nivelamento na atribuição. O processo demonstra o fluxo de trabalho principal: inicialização do projeto, definição de tarefa, criação de recurso, vinculação de atribuição e, finalmente, aplicação de parâmetros de agendamento como o atraso de nivelamento.

## Pré-requisitos
Antes de começarmos, certifique-se de que você tem os seguintes pré-requisitos:
1. Java Development Kit (JDK): Certifique-se de que o Java JDK está instalado em seu sistema. Você pode baixá-lo e instalá-lo a partir do [website](https://www.oracle.com/java/technologies/javase-jdk15-downloads.html).  
2. Biblioteca Aspose.Tasks para Java: Baixe a biblioteca Aspose.Tasks para Java a partir da [download page](https://releases.aspose.com/tasks/java/).

## Importar Pacotes
As importações a seguir trazem as classes principais do Aspose.Tasks necessárias para a manipulação de projetos.  
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

## Como criar atribuição de recurso aspotasks?
Carregue seu objeto `Project`, adicione uma tarefa, crie um recurso e, em seguida, vincule-os com um `ResourceAssignment`. Esse fluxo de ponta a ponta permite que você construa programaticamente uma estrutura completa de projeto e controle imediatamente o atraso de nivelamento na atribuição. O processo demonstra o fluxo de trabalho principal: inicialização do projeto, definição de tarefa, criação de recurso, vinculação de atribuição e, finalmente, aplicação de parâmetros de agendamento como o atraso de nivelamento.

## Etapa 1: Criar um Objeto Project
A classe `Project` é o contêiner de nível superior do Aspose.Tasks que representa um arquivo de projeto completo na memória. Instanciá‑la fornece uma base limpa para adicionar tarefas, recursos e atribuições.
```java
Project prj = new Project();
```

## Etapa 2: Criar uma Tarefa
A classe `Task` representa um único item de trabalho no cronograma. Adicionar uma tarefa demonstra **como adicionar tarefa** programaticamente e fornece um alvo para a próxima atribuição de recurso.
```java
Task task = prj.getRootTask().getChildren().add("Task 1");
```

## Etapa 3: Definir Data de Início e Duração da Tarefa
Defina quando a tarefa começa e quanto tempo ela durará. Datas de início corretas são essenciais porque os cálculos de nivelamento as utilizam como base para qualquer atraso que você especificar posteriormente.
```java
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.set(2000, Calendar.JANUARY, 3, 8, 0, 0);
task.set(Tsk.START, cal.getTime());
task.set(Tsk.DURATION, prj.getDuration(8));
```

## Etapa 4: Adicionar um Recurso
Agora nós **add resource to project** criando uma nova entrada `Resource`. A classe `Resource` representa uma pessoa, equipamento ou material que pode ser atribuído a tarefas.
```java
Resource resource = prj.getResources().add("Resource 1");
```

## Etapa 5: Criar uma Atribuição de Recurso
`ResourceAssignment` vincula um `Task` a um `Resource`. Essa associação permite registrar trabalho, custo e detalhes de nivelamento para um recurso específico em uma tarefa específica.
```java
ResourceAssignment assignment = prj.getResourceAssignments().add(task, resource);
```

## Etapa 6: Definir Atraso de Nivelamento
Configure o atraso de nivelamento para a atribuição. Definir como zero significa nenhum atraso adicional, mas você pode ajustar o valor conforme necessário. O campo `Asn.DELAY` contém o atraso em minutos; `Asn.LEVELING_DELAY` é um alias que funciona da mesma forma.
```java
assignment.set(Asn.DELAY, prj.getDuration(0, TimeUnitType.Day));
```

## Etapa 7: Exibir Resultados
Imprima as propriedades importantes para verificar se tudo foi configurado corretamente. Esta etapa ajuda a confirmar que os valores de recurso, tarefa e atraso são exatamente o que você espera antes de salvar o arquivo.
```java
System.out.println("Delay: " + assignment.get(Asn.DELAY));
System.out.println("Leveling Delay: " + assignment.get(Asn.LEVELING_DELAY));
System.out.println("Process completed Successfully");
```

## Armadilhas Comuns & Dicas
- **Armadilha:** Esquecer de definir a data de início da tarefa pode fazer com que a atribuição padrão seja o início do projeto.  
- **Dica:** Use `prj.getDuration(value, TimeUnitType.Day)` para controlar a granularidade do atraso.  
- **Dica:** Após adicionar vários recursos, chame `prj.updateResourceAssignments()` para permitir que o agendador recalcule o nivelamento.  
- **Pro dica:** Para projetos grandes (mais de 10.000 tarefas) habilite `prj.setAutoCalculate(false)` antes de atualizações em massa, então chame `prj.calculate()` uma vez ao final para melhorar o desempenho.

## Perguntas Frequentes

**Q: Posso usar Aspose.Tasks com outras bibliotecas Java?**  
A: Sim, o Aspose.Tasks integra-se perfeitamente com bibliotecas como Jackson para manipulação de JSON ou Apache POI para operações adicionais de planilhas, permitindo que você construa soluções de gerenciamento de projetos mais robustas.

**Q: O Aspose.Tasks é compatível com diferentes versões de arquivos do Microsoft Project?**  
A: O Aspose.Tasks suporta mais de 12 formatos de arquivo — incluindo .MPP (2003‑2021), .XML, .XER, .CSV, .PDF, .HTML e .MPP12 — garantindo edição de ida e volta sem interrupções em todas as principais versões do Project.

**Q: Onde posso encontrar suporte adicional para Aspose.Tasks?**  
A: Você pode encontrar suporte e discussões da comunidade no [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15).

**Q: Posso experimentar o Aspose.Tasks antes de comprar?**  
A: Sim, um teste gratuito totalmente funcional está disponível na [releases page](https://releases.aspose.com/).

**Q: Como posso obter uma licença temporária para avaliação?**  
A: Solicite uma licença temporária na [temporary license page](https://purchase.aspose.com/temporary-license/) para executar a biblioteca sem restrições de avaliação.

**Última Atualização:** 2026-06-05  
**Testado com:** Aspose.Tasks for Java 24.11  
**Autor:** Aspose

## Tutoriais Relacionados

- [Criar Atribuições de Recurso no Aspose.Tasks](/tasks/java/resource-assignments/create-resource-assignments/)
- [Gerenciar Orçamento de Atribuição Java usando Aspose.Tasks](/tasks/java/resource-assignments/assignment-budget/)
- [Como Parar Atribuição e Retomar Atribuições de Recurso no Aspose.Tasks](/tasks/java/resource-assignments/stop-resume-assignment/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}