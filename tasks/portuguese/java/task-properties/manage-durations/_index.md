---
date: 2026-02-20
description: Explore como adicionar tarefas ao projeto e gerenciar durações com Aspose.Tasks
  para Java. Aprenda como definir a duração e como converter a duração facilmente.
linktitle: Manage Durations of Tasks in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Adicionar Tarefa ao Projeto e Gerenciar Durações com Aspose.Tasks
url: /pt/java/task-properties/manage-durations/
weight: 20
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Adicionar Tarefa ao Projeto e Gerenciar Durações com Aspose.Tasks

## Introdução
Neste tutorial você aprenderá **como adicionar tarefa ao projeto** e controlar sua duração usando Aspose.Tasks para Java. Seja construindo uma nova ferramenta de planejamento de projetos ou ampliando uma solução existente, dominar o manuseio de duração de tarefas é essencial para agendamento e relatórios precisos.

## Respostas Rápidas
- **O que significa “add task to project”?** Cria um novo objeto Task sob a raiz do projeto ou em uma tarefa resumo específica.  
- **Qual classe representa uma duração?** `com.aspose.tasks.Duration`.  
- **Como definir a duração?** Use `task.set(Tsk.DURATION, project.getDuration(value, TimeUnitType))`.  
- **Posso converter uma duração para outra unidade?** Sim, chame `duration.convert(TimeUnitType.Hour)` ou qualquer outro `TimeUnitType`.  
- **Preciso de uma licença para produção?** Uma licença válida do Aspose.Tasks é necessária para uso comercial.

## O que é “add task to project”?
Adicionar uma tarefa a um projeto significa criar um objeto `Task` e anexá-lo à hierarquia de tarefas do projeto. Esta operação é o primeiro passo antes de você poder definir trabalho, recursos ou duração para essa tarefa.

## Por que gerenciar durações de tarefas?
Durações precisas impulsionam cronogramas realistas, alocação de recursos e análise do caminho crítico. Com Aspose.Tasks você pode definir, ler, converter e ajustar durações programaticamente, proporcionando controle total sobre os cronogramas do projeto.

## Pré-requisitos
Antes de começar, certifique‑se de que você tem o seguinte:

- Java Development Kit (JDK): Certifique‑se de que o Java está instalado em sua máquina. Você pode baixá‑lo [aqui](https://www.oracle.com/java/technologies/javase-downloads.html).
- Biblioteca Aspose.Tasks: Baixe e inclua a biblioteca Aspose.Tasks em seu projeto. Você pode encontrar a biblioteca [aqui](https://releases.aspose.com/tasks/java/).

## Importar Pacotes
No seu projeto Java, importe os pacotes necessários para trabalhar com Aspose.Tasks:
```java
import com.aspose.tasks.Duration;
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.TimeUnitType;
import com.aspose.tasks.Tsk;
```

## Etapa 1: Configurar Seu Projeto
```java
// Create a new project
Project project = new Project();
```

## Etapa 2: Adicionar uma Nova Tarefa (add task to project)
```java
// Add a new task to the project
Task task = project.getRootTask().getChildren().add("Task");
```

## Como definir a duração
Agora que a tarefa existe, você pode definir seu comprimento. Por padrão, as durações são expressas em dias.

## Etapa 3: Obter e Converter a Duração da Tarefa
```java
// Get task duration in days (default time unit)
Duration duration = task.get(Tsk.DURATION);
System.out.println("Duration equals 1 day: " + duration.toString().equals("1 day"));
// Convert duration to hours time unit
duration = duration.convert(TimeUnitType.Hour);
System.out.println("Duration equals 8 hrs: " + duration.toString().equals("8 hrs"));
```

## Como converter a duração
O método `convert` permite traduzir um `Duration` de um `TimeUnitType` para outro (por exemplo, dias → horas, semanas → dias).

## Etapa 4: Atualizar a Duração da Tarefa para 1 Semana
```java
// Increase task duration to 1 week
task.set(Tsk.DURATION, project.getDuration(1, TimeUnitType.Week));
System.out.println("Duration equals 1 wk: " + task.get(Tsk.DURATION).toString().equals("1 wk"));
```

## Etapa 5: Diminuir a Duração da Tarefa
```java
// Decrease task duration
task.set(Tsk.DURATION, task.get(Tsk.DURATION).subtract(0.5));
System.out.println("Duration equals 0.5 wks: " + task.get(Tsk.DURATION).toString().equals("0.5 wks"));
```

Seguindo estas etapas, você adicionou com sucesso **uma tarefa a um projeto** e gerenciou sua duração usando Aspose.Tasks para Java.

## Armadilhas Comuns e Dicas
- **Armadilha:** Esquecer de converter a duração antes de realizar operações aritméticas pode levar a resultados incorretos. Sempre verifique a unidade com `duration.getTimeUnit()`.
- **Dica:** Use `project.getDuration(value, TimeUnitType)` para criar durações na unidade desejada em vez de converter depois.
- **Armadilha:** Definir uma duração negativa lançará uma exceção. Certifique‑se de validar os valores de entrada.

## Conclusão
Neste guia abordamos como **adicionar tarefa ao projeto**, ler sua duração padrão, **definir duração** e **converter duração** para diferentes unidades de tempo. Agora você pode integrar essas técnicas em aplicações de agendamento maiores para um planejamento de projetos preciso.

## Perguntas Frequentes
### O Aspose.Tasks é compatível com todas as versões do Java?
Aspose.Tasks é compatível com Java 6 e versões posteriores.

### Posso usar o Aspose.Tasks em projetos comerciais?
Sim, você pode usar o Aspose.Tasks tanto em projetos pessoais quanto comerciais. Visite [aqui](https://purchase.aspose.com/buy) para detalhes de licenciamento.

### Onde posso encontrar suporte e recursos adicionais?
Visite o [fórum Aspose.Tasks](https://forum.aspose.com/c/tasks/15) para suporte da comunidade e discussões.

### Como posso obter uma licença temporária para fins de teste?
Você pode obter uma licença temporária [aqui](https://purchase.aspose.com/temporary-license/) para teste e avaliação.

### Existe uma versão de avaliação gratuita disponível para o Aspose.Tasks?
Sim, você pode acessar a avaliação gratuita [aqui](https://releases.aspose.com/) para explorar o Aspose.Tasks antes de fazer a compra.

## Perguntas Frequentes

**Q: Como altero a duração de uma tarefa depois que ela foi definida?**  
A: Recupere a duração atual com `task.get(Tsk.DURATION)`, modifique‑a (por exemplo, `add`, `subtract` ou `convert`) e, em seguida, defina‑a novamente usando `task.set(Tsk.DURATION, newDuration)`.

**Q: Posso definir uma duração em minutos?**  
A: Sim, use `TimeUnitType.Minute` ao chamar `project.getDuration(value, TimeUnitType.Minute)`.

**Q: Alterar a duração atualiza automaticamente as datas de início e término da tarefa?**  
A: Apenas se o modo de agendamento do projeto estiver definido como automático. Caso contrário, pode ser necessário recalcular o cronograma com `project.calculateCriticalPath()`.

**Q: É possível obter a duração como um número bruto?**  
A: Chame `duration.getTimeSpan()` para obter o valor numérico na unidade de tempo atual.

**Q: O que acontece se eu subtrair mais do que a duração atual?**  
A: A API lançará um `ArgumentOutOfRangeException`. Sempre valide se a duração resultante permanece positiva.

---

**Última atualização:** 2026-02-20  
**Testado com:** Aspose.Tasks for Java (latest)  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}