---
date: 2025-12-23
description: Aprenda como atualizar arquivos do MS Project e reprogramar o trabalho
  não concluído usando o Aspose.Tasks para Java. Veja também como salvar o XML do
  MS Project.
linktitle: Update Project and Reschedule Uncompleted Work in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Atualizar o MS Project e Reprogramar o Trabalho com Aspose.Tasks
url: /pt/java/project-file-operations/update-project-reschedule-work/
weight: 23
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Atualizar MS Project e Reagendar Trabalho com Aspose.Tasks

## Introdução
Microsoft Project é uma ferramenta de gerenciamento de projetos amplamente usada que ajuda equipes a planejar, monitorar e entregar o trabalho no prazo. Quando os cronogramas mudam, você frequentemente precisa **update MS Project** programaticamente — marcar o trabalho como concluído, mover as tarefas restantes e manter a linha de base do projeto precisa. Aspose.Tasks for Java oferece uma API limpa e tipada para fazer exatamente isso sem abrir a interface gráfica. Neste tutorial você verá como atualizar um projeto, marcar o trabalho como finalizado até uma data específica e, em seguida, **how to reschedule MS Project** o trabalho que ainda está pendente.

## Respostas Rápidas
- **O que significa “update MS Project”?** Ele marca tarefas como concluídas até uma data fornecida e grava as alterações de volta no arquivo.  
- **Posso reagendar o trabalho restante automaticamente?** Sim — use `rescheduleUncompletedWorkToStartAfter` para avançar as tarefas não finalizadas.  
- **Qual formato de arquivo é salvo?** Os exemplos salvam o projeto como XML (`SaveFileFormat.Xml`).  
- **Preciso de uma licença para executar o código?** Uma avaliação gratuita funciona para desenvolvimento; uma licença comercial é necessária para produção.  
- **Qual versão do Java é necessária?** JDK 8 ou superior.

## O que é “update MS Project” no código?
Atualizar um projeto significa alterar programaticamente datas, durações ou percentuais de conclusão das tarefas e persistir essas alterações. Aspose.Tasks expõe métodos como `updateProjectWorkAsComplete` que aplicam as mudanças com base em uma `Date` de referência que você fornece.

## Por que usar Aspose.Tasks for Java para atualizar MS Project?
- **Sem dependência de UI** – automatize alterações em massa em vários arquivos.  
- **Alta fidelidade** – a biblioteca preserva todos os dados nativos do Project (recursos, calendários, campos personalizados).  
- **Multiplataforma** – execute o mesmo código no Windows, Linux ou macOS.  
- **Salvar MS Project XML** – você pode exportar o projeto atualizado para o formato XML amplamente suportado para ferramentas downstream.

## Pré‑requisitos
1. Java Development Kit (JDK) instalado.  
2. Biblioteca Aspose.Tasks for Java – faça o download [aqui](https://releases.aspose.com/tasks/java/).  
3. Familiaridade básica com a sintaxe Java e conceitos de orientação a objetos.

## Importar Pacotes
Primeiro, importe as classes necessárias do Aspose.Tasks e utilitários Java:

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
Crie uma nova instância `Project`, defina algumas tarefas de exemplo, configure suas durações e estabeleça dependências. Em seguida, persista o estado inicial para que você possa ver o efeito antes‑e‑depois.

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
Marque o trabalho como concluído até uma data de corte específica. Este é o núcleo do **update MS Project** — a API ajustará o progresso e as datas das tarefas automaticamente.

```java
Calendar cal = Calendar.getInstance();
cal.set(2014, Calendar.JANUARY, 28, 17, 0, 0);
project.updateProjectWorkAsComplete(cal.getTime(), false);
// Save the updated project
project.save(dataDir + "updated.xml", SaveFileFormat.Xml);
```

## Etapa 3: Reagendar Trabalho Não Concluído
Após marcar o trabalho concluído, costuma ser necessário avançar as tarefas restantes. A chamada a seguir move qualquer trabalho não finalizado para iniciar após a mesma data de corte, efetivamente **how to reschedule MS Project**.

```java
cal.set(2014, Calendar.JANUARY, 28, 17, 0, 0);
project.rescheduleUncompletedWorkToStartAfter(cal.getTime());
// Save the rescheduled project
project.save(dataDir + "rescheduled.xml", SaveFileFormat.Xml);
```

## Problemas Comuns e Soluções
| Problema | Motivo | Correção |
|----------|--------|----------|
| Tarefas não exibem datas atualizadas | O projeto foi salvo em um formato diferente (por exemplo, `.mpp`) | Use `SaveFileFormat.Xml` para manter a estrutura XML intacta. |
| `updateProjectWorkAsComplete` parece não fazer nada | A data de referência é anterior ao início do projeto | Certifique-se de que a data do `Calendar` esteja dentro do cronograma do projeto. |
| Tarefas reprogramadas se sobrepõem | Nenhum calendário ou nivelamento de recursos aplicado | Aplique um calendário `Project` ou use `Task.setStart` manualmente após o replanejamento. |

## Perguntas Frequentes (Estendidas)

**P: O Aspose.Tasks for Java pode lidar com estruturas de projeto complexas?**  
R: Sim, Aspose.Tasks for Java fornece APIs robustas para gerenciar tarefas, dependências, recursos e outros elementos do projeto de forma eficiente.

**P: Existe uma versão de avaliação disponível para Aspose.Tasks for Java?**  
R: Sim, você pode obter uma avaliação gratuita [aqui](https://releases.aspose.com/).

**P: Como posso obter suporte para Aspose.Tasks for Java?**  
R: Você pode visitar o [forum Aspose.Tasks](https://forum.aspose.com/c/tasks/15) para qualquer assistência ou dúvidas.

**P: Posso comprar uma licença temporária para Aspose.Tasks for Java?**  
R: Sim, licenças temporárias estão disponíveis para compra [aqui](https://purchase.aspose.com/temporary-license/).

**P: Onde encontro documentação detalhada para Aspose.Tasks for Java?**  
R: Consulte a documentação [aqui](https://reference.aspose.com/tasks/java/) para guias abrangentes e referências de API.

## Conclusão
Neste tutorial percorremos todo o processo de **update MS Project**, marcando o trabalho como concluído e, em seguida, **how to reschedule MS Project** as tarefas que permanecem incompletas. Ao salvar o projeto como XML você mantém a compatibilidade com outras ferramentas e preserva um registro claro das alterações. Use esses padrões para automatizar ajustes de cronograma em grandes portfólios, integrar com pipelines de CI ou criar painéis de relatórios personalizados.

---

**Última atualização:** 2025-12-23  
**Testado com:** Aspose.Tasks for Java 24.11  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}