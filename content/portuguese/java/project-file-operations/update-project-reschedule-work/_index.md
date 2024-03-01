---
title: Atualizar e reprogramar MS Project em Aspose.Tasks
linktitle: Atualizar projeto e reprogramar trabalho incompleto em Aspose.Tasks
second_title: API Java Aspose.Tasks
description: Aprenda como atualizar e reagendar arquivos do MS Project programaticamente usando Aspose.Tasks para Java.
type: docs
weight: 23
url: /pt/java/project-file-operations/update-project-reschedule-work/
---
## Introdução
O Microsoft Project é um software de gerenciamento de projetos amplamente utilizado que permite aos usuários gerenciar tarefas, recursos e cronogramas com eficiência. Aspose.Tasks for Java fornece um conjunto poderoso de APIs para manipular arquivos do Microsoft Project programaticamente. Neste tutorial, aprenderemos como atualizar arquivos do MS Project e reagendar trabalhos incompletos usando Aspose.Tasks for Java.
## Pré-requisitos
Antes de começarmos, certifique-se de ter o seguinte:
1. Java Development Kit (JDK) instalado em seu sistema.
2.  Aspose.Tasks para biblioteca Java. Você pode baixá-lo em[aqui](https://releases.aspose.com/tasks/java/).
3. Compreensão básica da linguagem de programação Java.

## Importar pacotes
Primeiro, importe os pacotes necessários em seu código Java:
```java
import com.aspose.tasks.NullableBool;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.Task;
import com.aspose.tasks.TaskLink;
import com.aspose.tasks.TaskLinkType;
import com.aspose.tasks.TimeUnitType;
import com.aspose.tasks.Tsk;
import java.util.Calendar;
```
## Etapa 1: configurar o projeto
Inicialize um novo objeto Project e defina tarefas dentro dele juntamente com suas durações e dependências.
```java
String dataDir = "Your Data Directory";
Project project = new Project();
// Defina tarefas e suas durações
// ...
// Definir dependências de tarefas
// ...
// Salve o estado inicial do projeto
project.save(dataDir + "not_updated.xml", SaveFileFormat.Xml);
```
## Etapa 2: atualizar o trabalho do projeto
Atualize o trabalho do projeto para marcá-lo como concluído até uma determinada data.
```java
Calendar cal = Calendar.getInstance();
cal.set(2014, Calendar.JANUARY, 28, 17, 0, 0);
project.updateProjectWorkAsComplete(cal.getTime(), false);
// Salve o projeto atualizado
project.save(dataDir + "updated.xml", SaveFileFormat.Xml);
```
## Etapa 3: reprogramar trabalho incompleto
Reprograme qualquer trabalho incompleto para começar após uma data especificada.
```java
cal.set(2014, Calendar.JANUARY, 28, 17, 0, 0);
project.rescheduleUncompletedWorkToStartAfter(cal.getTime());
// Salvar o projeto reprogramado
project.save(dataDir + "rescheduled.xml", SaveFileFormat.Xml);
```

## Conclusão
Neste tutorial, aprendemos como atualizar arquivos do MS Project e reagendar trabalhos incompletos usando Aspose.Tasks for Java. Isto pode ser particularmente útil em cenários em que os cronogramas dos projetos precisam de ajustes com base no progresso ou na mudança de prioridades.

## Perguntas frequentes
### P: O Aspose.Tasks for Java pode lidar com estruturas de projetos complexas?
R: Sim, Aspose.Tasks for Java fornece APIs robustas para gerenciar tarefas, dependências, recursos e outros elementos do projeto com eficiência.
### P: Existe uma versão de teste disponível para Aspose.Tasks for Java?
 R: Sim, você pode obter uma avaliação gratuita em[aqui](https://releases.aspose.com/).
### P: Como posso obter suporte para Aspose.Tasks for Java?
 R: Você pode visitar o[Fórum Aspose.Tasks](https://forum.aspose.com/c/tasks/15) para qualquer assistência ou dúvida.
### P: Posso adquirir uma licença temporária do Aspose.Tasks for Java?
 R: Sim, licenças temporárias estão disponíveis para compra[aqui](https://purchase.aspose.com/temporary-license/).
### P: Onde posso encontrar documentação detalhada para Aspose.Tasks for Java?
 R: Você pode consultar a documentação[aqui](https://reference.aspose.com/tasks/java/) para guias abrangentes e referências de API.