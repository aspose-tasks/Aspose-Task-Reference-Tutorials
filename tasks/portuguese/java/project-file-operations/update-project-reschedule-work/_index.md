---
date: 2026-03-29
description: Aprenda como reprogramar o trabalho não concluído, atualizar o trabalho
  do projeto e salvar arquivos do MS Project como XML usando o Aspose.Tasks para Java.
linktitle: Update Project and Reschedule Uncompleted Work in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Reagendar Trabalho Não Concluído e Atualizar Arquivos do MS Project com Aspose.Tasks
url: /pt/java/project-file-operations/update-project-reschedule-work/
weight: 23
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Reagendar Trabalho Incompleto e Atualizar Arquivos MS Project com Aspose.Tasks

## Introdução
Microsoft Project é uma ferramenta de gerenciamento de projetos amplamente utilizada que ajuda equipes a planejar tarefas, alocar recursos e acompanhar cronogramas. Aspose.Tasks for Java fornece aos desenvolvedores uma API rica para manipular arquivos Microsoft Project programaticamente. Neste tutorial, você aprenderá como **atualizar o trabalho do projeto**, **reagendar trabalho incompleto** e **salvar o arquivo MS Project** no formato XML usando Aspose.Tasks for Java.

## Respostas Rápidas
- **O que significa “reagendar trabalho incompleto”?** Ele move qualquer trabalho de tarefa restante para começar após uma data escolhida, mantendo as partes concluídas intactas.  
- **Qual método marca o trabalho como concluído?** `project.updateProjectWorkAsComplete(date, false)`.  
- **Como persisto as alterações?** Use `project.save(<path>, SaveFileFormat.Xml)`.  
- **Preciso de uma licença para produção?** Sim, uma licença válida do Aspose.Tasks é necessária para uso comercial.  
- **Qual versão do Java é suportada?** Java 8 e posteriores são totalmente suportados.

## O que é “reagendar trabalho incompleto”?
Reagendar trabalho incompleto ajusta as datas de início de todas as tarefas que ainda não foram concluídas, fazendo com que comecem após uma data de corte especificada. Isso é útil quando o cronograma de um projeto muda devido a atrasos ou alterações de escopo.

## Por que usar Aspose.Tasks para atualizar o trabalho do projeto e reagendar tarefas?
- **Controle granular:** Defina diretamente as porcentagens de conclusão do trabalho e as datas.  
- **Sem interface gráfica necessária:** Automatize atualizações em massa em vários arquivos de projeto.  
- **Multiplataforma:** Funciona em qualquer sistema que execute Java.  
- **Preserva a integridade dos dados:** Todas as dependências, restrições e recursos permanecem consistentes.

## Pré-requisitos
Antes de começarmos, certifique‑se de que você tem o seguinte:
1. Java Development Kit (JDK) instalado em seu sistema.  
2. Biblioteca Aspose.Tasks for Java. Você pode baixá‑la [aqui](https://releases.aspose.com/tasks/java/).  
3. Compreensão básica da linguagem de programação Java.

## Importar Pacotes
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

## Etapa 1: Configurar o Projeto
Inicialize um novo objeto `Project`, defina tarefas, estabeleça durações e crie dependências. Isso cria o projeto de base que posteriormente atualizaremos e reagendaremos.
```java
String dataDir = "Your Data Directory";
Project project = new Project();
// Define tasks and their durations
// ...
// Define task dependencies
// ...
// Save the initial project state
project.save(dataDir + "not_updated.xml", SaveFileFormat.Xml);
```

## Etapa 2: Atualizar o Trabalho do Projeto
Marque o trabalho como concluído até uma data específica. Esta etapa demonstra a operação de **atualizar o trabalho do projeto**, que costuma ser a primeira ação antes de reagendar.
```java
Calendar cal = Calendar.getInstance();
cal.set(2014, Calendar.JANUARY, 28, 17, 0, 0);
project.updateProjectWorkAsComplete(cal.getTime(), false);
// Save the updated project
project.save(dataDir + "updated.xml", SaveFileFormat.Xml);
```

## Etapa 3: Reagendar Trabalho Incompleto
Agora deslocamos qualquer trabalho restante (incompleto) para que ele comece após a mesma data de corte. Esta é a funcionalidade central de **reagendar trabalho incompleto**.
```java
cal.set(2014, Calendar.JANUARY, 28, 17, 0, 0);
project.rescheduleUncompletedWorkToStartAfter(cal.getTime());
// Save the rescheduled project
project.save(dataDir + "rescheduled.xml", SaveFileFormat.Xml);
```

## Conclusão
Neste tutorial, abordamos como **atualizar o trabalho do projeto**, **reagendar trabalho incompleto** e **salvar o arquivo MS Project** como XML usando Aspose.Tasks for Java. Essas funcionalidades são essenciais quando os cronogramas de projetos precisam ser ajustados com base no progresso real ou nas prioridades de negócios em mudança.

## Perguntas Frequentes
### Q: O Aspose.Tasks for Java pode lidar com estruturas de projeto complexas?
A: Sim, o Aspose.Tasks for Java fornece APIs robustas para gerenciar tarefas, dependências, recursos e outros elementos do projeto de forma eficiente.  
### Q: Existe uma versão de avaliação disponível para Aspose.Tasks for Java?
A: Sim, você pode obter uma avaliação gratuita [aqui](https://releases.aspose.com/).  
### Q: Como posso obter suporte para Aspose.Tasks for Java?
A: Você pode visitar o [fórum Aspose.Tasks](https://forum.aspose.com/c/tasks/15) para qualquer assistência ou dúvida.  
### Q: Posso comprar uma licença temporária para Aspose.Tasks for Java?
A: Sim, licenças temporárias estão disponíveis para compra [aqui](https://purchase.aspose.com/temporary-license/).  
### Q: Onde posso encontrar documentação detalhada para Aspose.Tasks for Java?
A: Você pode consultar a documentação [aqui](https://reference.aspose.com/tasks/java/) para guias abrangentes e referências de API.

## Perguntas Frequentes Adicionais

**Q: Como garantir que o arquivo salvo seja compatível com versões mais antigas do Microsoft Project?**  
A: Salve o projeto usando `SaveFileFormat.Xml`; XML é amplamente suportado em várias versões do Project.

**Q: Posso reagendar apenas um subconjunto de tarefas em vez de todo o projeto?**  
A: Sim, você pode iterar sobre tarefas específicas e chamar `task.setStart(date)` após calcular a nova data de início.

**Q: O que acontece com as alocações de recursos ao reagendar trabalho incompleto?**  
A: As atribuições de recursos são automaticamente deslocadas para corresponder às novas datas de início das tarefas, preservando a lógica de alocação.

**Q: É possível desfazer uma operação de reagendamento programaticamente?**  
A: Você pode recarregar o arquivo de projeto original (ou um backup) para reverter quaisquer alterações.

**Q: O Aspose.Tasks suporta salvar em outros formatos como .mpp?**  
A: Absolutamente. Use `SaveFileFormat.MPP` para salvar no formato nativo do Microsoft Project.

---

**Última atualização:** 2026-03-29  
**Testado com:** Aspose.Tasks for Java 24.11  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}