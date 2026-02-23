---
date: 2026-02-23
description: Aprenda a definir a data de início do projeto, definir a duração das
  tarefas e salvar o projeto como MPP usando Aspose.Tasks para Java. Gerencie tarefas
  principais e subtarefas de forma eficiente.
linktitle: Set Project Start Date and Manage Parent and Child Tasks in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Definir a Data de Início do Projeto e Gerenciar Tarefas Pai e Filho no Aspose.Tasks
url: /pt/java/task-properties/parent-child-tasks/
weight: 24
---

.{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Definir a Data de Início do Projeto e Gerenciar Tarefas Pai e Filho no Aspose.Tasks

## Introdução
Organizar tarefas de forma eficaz é a espinha dorsal de um gerenciamento de projetos bem‑sucedido, e **definir a data de início do projeto** corretamente é o primeiro passo para um cronograma bem estruturado. Neste tutorial você verá como **definir a data de início do projeto**, configurar durações de tarefas e gerenciar relacionamentos pai‑filho usando Aspose.Tasks for Java. Ao final, você estará pronto para **salvar o projeto como MPP**, atualizar percentuais de conclusão de tarefas e personalizar propriedades de tarefas para se adequar a qualquer cenário real.

## Respostas Rápidas
- **Como defino a data de início do projeto?** Use `proj.set(Prj.START_DATE, startDate);` após inicializar o objeto `Project`.  
- **Posso adicionar tarefas filhas sob uma tarefa pai?** Sim – chame `parentTask.getChildren().add("Child Task")`.  
- **Em que formato o Aspose.Tasks salva o arquivo?** Use `SaveFileFormat.Mpp` para **salvar o projeto como MPP**.  
- **Como atualizo a conclusão da tarefa?** Defina `Tsk.PERCENT_COMPLETE` no objeto da tarefa.  
- **Onde posso obter uma licença temporária?** Visite a página de licença temporária vinculada nas Perguntas Frequentes.

## Pré‑requisitos
Antes de mergulhar no tutorial, certifique‑se de que você possui os seguintes pré‑requisitos:
- Compreensão básica de programação Java.  
- Biblioteca Aspose.Tasks for Java instalada. Você pode baixá‑la [aqui](https://releases.aspose.com/tasks/java/).  
- Um Ambiente de Desenvolvimento Integrado (IDE) Java configurado em seu sistema.

## Importar Pacotes
Para começar, importe os pacotes necessários ao seu projeto Java. Esses pacotes facilitam a integração perfeita com as funcionalidades do Aspose.Tasks for Java.
```java
import com.aspose.tasks.ChildTasksCollector;
import com.aspose.tasks.ConstraintType;
import com.aspose.tasks.NullableBool;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.Task;
import com.aspose.tasks.TaskUtils;
import com.aspose.tasks.TimeUnitType;
import com.aspose.tasks.Tsk;
import java.io.IOException;
import java.util.Date;
import java.util.List;
```

## Etapa 1: Definir a Data de Início do Projeto
Comece definindo a data de início do projeto e outros parâmetros relevantes.
```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
Project proj = new Project(dataDir + "Blank2010.mpp");
proj.set(Prj.NEW_TASKS_ARE_MANUAL, new NullableBool(false));
// Additional code for package imports can be added here
double oneDay = 8d * 60d * 60d * 10000000d;
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.set(2014, 9, 13, 8, 0, 0);
Date startDate = cal.getTime();
proj.set(Prj.START_DATE, startDate);
```

## Etapa 2: Adicionar Tarefa Pai (Tarefa 1)
Crie uma tarefa pai chamada "Task 1" e configure suas propriedades, incluindo **definir a duração da tarefa**.
```java
Task task1 = proj.getRootTask().getChildren().add("Task 1");
cal.set(2014, 9, 13, 8, 0, 0);
task1.set(Tsk.START, cal.getTime());
task1.set(Tsk.DURATION, proj.getDuration(29, TimeUnitType.Day));
```

## Etapa 3: Adicionar Tarefa Pai (Tarefa 2) com Tarefas Filhas
Agora, adicione outra tarefa pai chamada "Task 2" e inclua tarefas filhas (Task 3 e Task 4).
```java
Task task2 = proj.getRootTask().getChildren().add("Task 2");
// Add child tasks to Task 2
Task task3 = task2.getChildren().add("Task 3");
Task task4 = task2.getChildren().add("Task 4");
// Additional configuration for Task 3 and Task 4 can be added here
```

## Etapa 4: Configurar Tarefas Filhas
Especifique datas de início, durações e restrições para Task 3 e Task 4.
```java
// Configure Task 3
cal.set(2014, 9, 15, 8, 0, 0);
task3.set(Tsk.START, cal.getTime());
task3.set(Tsk.DURATION, proj.getDuration(3, TimeUnitType.Day));
task3.set(Tsk.CONSTRAINT_TYPE, ConstraintType.StartNoEarlierThan);
task3.set(Tsk.CONSTRAINT_DATE, task3.get(Tsk.START));
// Configure Task 4
cal.set(2014, 9, 17, 8, 0, 0);
task4.set(Tsk.START, cal.getTime());
task4.set(Tsk.DURATION, proj.getDuration(3, TimeUnitType.Day));
task4.set(Tsk.CONSTRAINT_TYPE, ConstraintType.StartNoEarlierThan);
task4.set(Tsk.CONSTRAINT_DATE, task3.get(Tsk.START));
```

## Etapa 5: Atualizar Percentual de Conclusão da Tarefa
Ajuste o percentual de conclusão para Task 3 e Task 4 – é assim que você **atualiza a conclusão da tarefa**.
```java
task3.set(Tsk.PERCENT_COMPLETE, 50);
task4.set(Tsk.PERCENT_COMPLETE, 70);
```

## Etapa 6: Salvar o Projeto
Finalmente, **salvar o projeto como MPP** com as alterações aplicadas.
```java
proj.save(dataDir + "ProjectJava.mpp", SaveFileFormat.Mpp);
```

Este guia passo a passo demonstra como gerenciar tarefas pai e filho de forma eficaz usando Aspose.Tasks for Java. Experimente diferentes configurações para atender aos requisitos do seu projeto.

## Por que Personalizar Propriedades de Tarefas?
Personalizar propriedades de tarefas como datas de início, durações, restrições e percentuais de conclusão oferece controle granular sobre o comportamento do cronograma. Seja para alinhar tarefas à disponibilidade de recursos ou impor regras de negócio, o Aspose.Tasks permite **personalizar propriedades de tarefas** programaticamente.

## Problemas Comuns e Soluções
| Problema | Solução |
|----------|---------|
| **Data de início não aplicada** | Certifique‑se de chamar `proj.set(Prj.START_DATE, …)` **depois** de criar o objeto `Project` e antes de adicionar tarefas. |
| **Tarefas filhas herdam restrições incorretas** | Defina explicitamente `ConstraintType` e `ConstraintDate` de cada filha, conforme mostrado na Etapa 4. |
| **Arquivo salvo não pode ser aberto no MS Project** | Verifique se está usando a versão mais recente do Aspose.Tasks e salve com `SaveFileFormat.Mpp`. |
| **Percentual não refletindo na UI** | Após definir `Tsk.PERCENT_COMPLETE`, chame `proj.calculateTaskSchedule()` se precisar de datas recalculadas. |

## Perguntas Frequentes
### O Aspose.Tasks for Java é compatível com diferentes formatos de arquivo de projeto?
Sim, o Aspose.Tasks for Java suporta vários formatos de arquivo de projeto, incluindo MPP e XML.

### Posso personalizar propriedades de tarefas além do que é abordado neste tutorial?
Absolutamente! O Aspose.Tasks for Java oferece amplas opções de personalização para propriedades de tarefas.

### Existe um fórum da comunidade para Aspose.Tasks onde eu possa buscar suporte?
Sim, você pode visitar o [fórum do Aspose.Tasks](https://forum.aspose.com/c/tasks/15) para suporte da comunidade.

### Como posso obter uma licença temporária para Aspose.Tasks for Java?
Você pode obter uma licença temporária [aqui](https://purchase.aspose.com/temporary-license/).

### Onde posso encontrar documentação abrangente para Aspose.Tasks for Java?
A documentação está disponível [aqui](https://reference.aspose.com/tasks/java/).

**Perguntas e Respostas Adicionais**

**Q: Como obtenho programaticamente uma licença temporária?**  
A: Carregue o arquivo de licença temporária usando `License license = new License(); license.setLicense("Aspose.Tasks.lic");`.

**Q: Posso mudar a unidade padrão de duração da tarefa?**  
A: Sim – modifique o argumento `TimeUnitType` em `proj.getDuration(value, TimeUnitType.YourChoice)`.

**Q: Qual versão do Aspose.Tasks é necessária para usar `SaveFileFormat.Mpp`?**  
A: Todas as versões recentes (2022‑2026) suportam salvar como MPP; verifique as notas de versão para eventuais alterações incompatíveis.

---

**Última atualização:** 2026-02-23  
**Testado com:** Aspose.Tasks for Java 24.11  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}