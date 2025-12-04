---
date: 2025-12-03
description: Aprenda como criar calendário no MS Project, converter o projeto para
  MPP e salvar o projeto MPP sem esforço usando Aspose.Tasks para Java.
language: pt
linktitle: Update Calendar to MPP Format in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Criar Calendário no MS Project e Salvar como MPP com Aspose.Tasks
url: /java/calendars/update-to-mpp/
weight: 16
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Criar Calendário MS Project e Salvar como MPP com Aspose.Tasks

## Introdução

Na gestão moderna de projetos você frequentemente precisa **criar arquivos de calendário MS Project** e, em seguida, compartilhá‑los no formato nativo MPP. Seja consolidando cronogramas de múltiplas fontes ou migrando dados legados, gerar um calendário programaticamente economiza tempo e elimina erros manuais. Este tutorial orienta você por todo o processo de criação de um calendário no MS Project, sua personalização e, finalmente, **converter o projeto para MPP** usando a API Aspose.Tasks para Java.

## Respostas Rápidas
- **O que este tutorial cobre?** Criação de um calendário no MS Project e salvamento como arquivo MPP com Aspose.Tasks para Java.  
- **Preciso de licença?** Uma avaliação gratuita funciona para desenvolvimento; uma licença comercial é necessária para produção.  
- **Qual versão do Java é necessária?** Java 8 ou superior (JDK 8+).  
- **Posso personalizar o calendário?** Sim – você pode adicionar horários de trabalho, exceções e feriados.  
- **Quanto tempo leva a implementação?** Cerca de 10‑15 minutos para um calendário básico.

## O que significa “criar calendário MS Project”?

Criar um calendário MS Project significa definir programaticamente os dias úteis, horas e exceções que orientam o agendamento de tarefas dentro de um arquivo Microsoft Project. Usando Aspose.Tasks você pode construir, modificar e persistir esses calendários sem nunca abrir a interface do Microsoft Project.

## Por que usar Aspose.Tasks para esta tarefa?

- **Compatibilidade total .NET/Java** – funciona em qualquer plataforma que suporte Java.  
- **Nenhum COM ou instalação do Office necessária** – ideal para automação no servidor.  
- **API rica** – suporta todas as propriedades de calendário, incluindo semanas de trabalho personalizadas e feriados.  
- **Saída direta em MPP** – você pode **salvar projeto MPP** sem conversões intermediárias.

## Pré‑requisitos

1. **Java Development Kit (JDK) 8+** – verifique que `java -version` retorna 1.8 ou superior.  
2. **Aspose.Tasks for Java** – baixe o JAR mais recente em [Aspose website](https://releases.aspose.com/tasks/java/).  
3. **IDE** – IntelliJ IDEA, Eclipse ou qualquer editor de sua preferência.  
4. **Conhecimento básico de Java** – familiaridade com classes, métodos e I/O de arquivos.

## Guia Passo a Passo

### Passo 1: Importar Pacotes Necessários

Primeiro, traga as classes Aspose.Tasks e as utilidades Java para o escopo.

```java
import com.aspose.tasks.*;

import java.util.Date;
import java.util.GregorianCalendar;
```

### Passo 2: Configurar o Diretório de Dados

Defina onde seus arquivos de modelo de entrada e saída ficarão. Substitua o placeholder pelo caminho real na sua máquina.

```java
String dataDir = "Your Data Directory";
```

### Passo 3: Definir Nomes de Arquivo de Entrada e Saída

Carregaremos um arquivo MPP existente (ou um projeto em branco) e gravaremos o resultado em um novo arquivo.

```java
String resultFile = "OutputMpp.mpp";
String newFile = "SampleMpp.mpp";
```

### Passo 4: Carregar o Projeto e Adicionar um Novo Calendário

Crie uma instância `Project` a partir do arquivo fonte e adicione um calendário chamado **“Calendar 1”**.

```java
Project project = new Project(dataDir + newFile);
Calendar cal1 = project.getCalendars().add("Calendar 1");
```

### Passo 5: Personalizar o Calendário (Opcional)

Se precisar de horários de trabalho específicos, feriados ou exceções, chame seu próprio método auxiliar. O exemplo usa `GetTestCalendar` como placeholder.

```java
GetTestCalendar(cal1); // Additional method for customizing calendar if required
```

> **Dica profissional:** Você pode manipular diretamente `cal1.getWeekDays()` para definir as horas de trabalho de cada dia da semana.

### Passo 6: Atribuir o Calendário ao Projeto

Informe ao projeto para usar o calendário recém‑criado em todos os seus cálculos de agendamento.

```java
project.set(Prj.CALENDAR, cal1);
```

### Passo 7: Salvar o Projeto como MPP

Agora **converta o projeto para MPP** salvando-o com a opção `SaveFileFormat.Mpp`.

```java
project.save(dataDir + resultFile, SaveFileFormat.Mpp);
```

### Passo 8: Confirmar Conclusão Bem‑sucedida

Uma mensagem simples no console indica que o processo terminou sem erros.

```java
System.out.println("Process completed Successfully");
```

## Casos de Uso Comuns

- **Geração automática de cronogramas** para projetos recorrentes (ex.: sprints semanais).  
- **Migração de calendários legados em CSV ou Excel** para um arquivo MS Project completo.  
- **Relatórios no lado do servidor** onde um serviço web devolve um arquivo MPP sob demanda.  

## Solução de Problemas & Armadilhas Frequentes

| Problema | Causa | Solução |
|----------|-------|---------|
| `NullPointerException` em `project.save` | `dataDir` aponta para uma pasta inexistente | Garanta que o diretório exista ou crie‑o programaticamente. |
| Calendário não aplicado às tarefas | Tarefas ainda referenciam o calendário padrão | Após definir `Prj.CALENDAR`, também atualize `Task.CALENDAR` de cada tarefa se elas foram sobrescritas anteriormente. |
| Arquivo de saída com 0 KB | Falta de permissões de gravação | Execute a JVM com direitos adequados ao sistema de arquivos ou escolha um caminho gravável. |

## Perguntas Frequentes

**P: O Aspose.Tasks for Java é compatível com diferentes versões do MS Project?**  
R: Sim, o Aspose.Tasks for Java suporta uma ampla gama de versões do MS Project, do Project 2007 até a versão mais recente, garantindo compatibilidade perfeita.

**P: Posso personalizar calendários de acordo com requisitos específicos do projeto?**  
R: Absolutamente. Você pode definir dias úteis, criar semanas de trabalho personalizadas, adicionar feriados e até criar múltiplos calendários dentro de um único arquivo de projeto.

**P: O Aspose.Tasks for Java oferece suporte para resolução de problemas e assistência?**  
R: Sim, você pode obter ajuda no fórum da comunidade Aspose.Tasks [aqui](https://forum.aspose.com/c/tasks/15).

**P: Existe uma avaliação gratuita disponível para o Aspose.Tasks for Java?**  
R: Sim, uma avaliação totalmente funcional está disponível [aqui](https://releases.aspose.com/).

**P: Como posso obter uma licença temporária para o Aspose.Tasks for Java?**  
R: Licenças temporárias podem ser solicitadas através do site da Aspose [aqui](https://purchase.aspose.com/temporary-license/).

---

**Última atualização:** 2025-12-03  
**Testado com:** Aspose.Tasks for Java 24.12  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}