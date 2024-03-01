---
title: Atualizar dados de tarefas para formato MPP em Aspose.Tasks
linktitle: Atualizar dados de tarefas para formato MPP em Aspose.Tasks
second_title: API Java Aspose.Tasks
description: Aprenda como atualizar dados de tarefas para o formato MPP usando Aspose.Tasks for Java. Siga nosso guia passo a passo para um gerenciamento de projetos eficiente.
type: docs
weight: 35
url: /pt/java/task-properties/update-task-data/
---
## Introdução
Bem-vindo ao nosso guia passo a passo sobre como atualizar dados de tarefas para o formato MPP usando Aspose.Tasks for Java. Neste tutorial, orientaremos você durante o processo, garantindo que você entenda cada etapa com clareza. Aspose.Tasks for Java fornece uma solução robusta para trabalhar com arquivos do Microsoft Project e, ao final deste guia, você será capaz de atualizar com eficiência os dados da tarefa no formato MPP.
## Pré-requisitos
Antes de mergulharmos no tutorial, certifique-se de ter os seguintes pré-requisitos em vigor:
-  Aspose.Tasks para Java: certifique-se de ter a biblioteca Aspose.Tasks instalada. Você pode baixá-lo no[página de lançamento](https://releases.aspose.com/tasks/java/).
- Java Development Kit (JDK): Certifique-se de ter o Java instalado em seu sistema.
- Ambiente de Desenvolvimento Integrado (IDE): Use um IDE de sua escolha para desenvolvimento Java.
## Importar pacotes
Comece importando os pacotes necessários para o seu projeto Java. O trecho a seguir demonstra como importar pacotes:
```java
import com.aspose.tasks.ConstraintType;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.Task;
import com.aspose.tasks.TimeUnitType;
import com.aspose.tasks.Tsk;
import com.aspose.tasks.examples.TaskLinks.UpdatedTaskLinkDataToMpp;
```
## 1. Crie e configure a tarefa inicial
```java
// O caminho para o diretório de documentos.
String dataDir = "Your Document Directory";
long OneSec = 1000;
long OneMin = 60 * OneSec;
long OneHour = 60 * OneMin;
Project project = new Project(dataDir + "project.xml");
Task task1 = project.getRootTask().getChildren().add("First task");
//... (Continue com o resto do código)
```
## 2. Defina a data de início e duração
```java
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.set(2013, 12, 10, 8, 0, 0);
project.set(Prj.START_DATE, cal.getTime());
task1.set(Tsk.START, cal.getTime());
task1.set(Tsk.DURATION, project.getDuration(24, TimeUnitType.Hour));
//... (Continue com o resto do código)
```
## 3. Crie uma tarefa de resumo
```java
Task summary = project.getRootTask().getChildren().add("Summary task");
summary.getChildren().add(task1);
//... (Continue com o resto do código)
```
## 4. Defina prazo e notas de tarefas
```java
cal.setTime(task1.get(Tsk.START));
cal.add(java.util.Calendar.DATE, 10);
task1.set(Tsk.DEADLINE, cal.getTime());
task1.set(Tsk.NOTES_TEXT, "The first task.");
//... (Continue com o resto do código)
```
## 5. Configurar restrições de tarefas
```java
task1.set(Tsk.DURATION_FORMAT, TimeUnitType.DayEstimated);
task1.set(Tsk.CONSTRAINT_TYPE, ConstraintType.FinishNoLaterThan);
//... (Continue com o resto do código)
```
## 6. Crie tarefas adicionais
```java
//Crie 10 novas tarefas
for (int i = 0; i < 10; i++) {
    //... (Continue com o resto do código)
}
//... (Continue com o resto do código)
```
## 7. Salve o projeto
```java
// Salve o projeto
project.save(dataDir + "WritingUpdatedTaskDataToMpp.mpp", SaveFileFormat.Mpp);
```
Seguindo essas etapas, você atualizou com êxito os dados da tarefa para o formato MPP usando Aspose.Tasks for Java.
## Conclusão
Parabéns! Você concluiu um guia abrangente sobre como atualizar dados de tarefas no formato MPP usando Aspose.Tasks for Java. Esta poderosa biblioteca simplifica as tarefas de gerenciamento de projetos, tornando-a uma ferramenta valiosa para desenvolvedores Java.
## Perguntas frequentes
### P: Onde posso encontrar a documentação do Aspose.Tasks para Java?
 R: A documentação está disponível[aqui](https://reference.aspose.com/tasks/java/).
### P: Como posso baixar Aspose.Tasks para Java?
 R: Você pode baixá-lo no[página de lançamento](https://releases.aspose.com/tasks/java/).
### P: Existe uma avaliação gratuita disponível?
 R: Sim, você pode acessar o teste gratuito[aqui](https://releases.aspose.com/).
### P: Onde posso obter suporte para Aspose.Tasks for Java?
 R: Visite o fórum de suporte[aqui](https://forum.aspose.com/c/tasks/15).
### P: Vocês oferecem licenças temporárias para fins de teste?
 R: Sim, você pode obter uma licença temporária[aqui](https://purchase.aspose.com/temporary-license/).