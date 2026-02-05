---
date: 2026-02-05
description: Aprenda como adicionar feriados a um calendário, atribuir o calendário
  a um projeto e salvar o arquivo do MS Project como MPP usando o Aspose.Tasks para
  Java.
linktitle: Update Calendar to MPP Format in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Adicionar feriados ao calendário e salvar como MPP com Aspose.Tasks
url: /pt/java/calendars/update-to-mpp/
weight: 16
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Adicionar Feriados ao Calendário e Salvar como MPP com Aspose.Tasks

## Introdução

Na gestão moderna de projetos você frequentemente precisa **add holidays to calendar** arquivos, criar um **MS Project calendar**, e então compartilhar o cronograma no formato nativo MPP. Seja consolidando cronogramas de múltiplas fontes ou migrando dados legados, gerar um calendário programaticamente elimina erros manuais e acelera a entrega. Este tutorial orienta você por todo o processo de criação de um calendário no MS Project, personalizando‑o com feriados, **assign calendar to project**, e finalmente **convert project to MPP** usando a API Aspose.Tasks Java.

## Respostas Rápidas
- **O que este tutorial cobre?** Adicionar feriados a um calendário, atribuí‑lo a um projeto e salvar o resultado como um arquivo MPP com Aspose.Tasks para Java.  
- **Preciso de licença?** Um teste gratuito funciona para desenvolvimento; uma licença comercial é necessária para produção.  
- **Qual versão do Java é necessária?** Java 8 ou superior (JDK 8+).  
- **Posso personalizar o calendário?** Sim – você pode adicionar horários de trabalho, exceções e feriados.  
- **Quanto tempo leva a implementação?** Cerca de 10‑15 minutos para um calendário básico.  

## O que é “create calendar MS Project”?

Criar um **calendar MS Project** significa definir programaticamente os dias úteis, horas e exceções que orientam o agendamento de tarefas dentro de um arquivo Microsoft Project. Usando Aspose.Tasks você pode **java create project calendar**, modificá‑lo e persistir as alterações sem nunca abrir a interface do Microsoft Project.

## Por que usar Aspose.Tasks para esta tarefa?

- **Compatibilidade total .NET/Java** – funciona em qualquer plataforma que suporte Java.  
- **Nenhuma instalação de COM ou Office necessária** – ideal para automação server‑side e **automate schedule generation**.  
- **API rica** – suporta todas as propriedades de calendário, incluindo semanas de trabalho personalizadas e feriados.  
- **Saída direta MPP** – você pode **save project as MPP** sem conversões intermediárias.

## Pré‑requisitos

1. **Java Development Kit (JDK) 8+** – certifique‑se de que `java -version` exibe 1.8 ou superior.  
2. **Aspose.Tasks for Java** – baixe o JAR mais recente do [Aspose website](https://releases.aspose.com/tasks/java/).  
3. **IDE** – IntelliJ IDEA, Eclipse ou qualquer editor de sua preferência.  
4. **Conhecimento básico de Java** – familiaridade com classes, métodos e I/O de arquivos.

## Como Adicionar Feriados ao Calendário

A seguir percorremos cada passo, desde a configuração do ambiente até a persistência do arquivo MPP final. Os blocos de código permanecem inalterados em relação ao tutorial original; as explicações ao redor foram ampliadas para maior clareza.

### Etapa 1: Importar Pacotes Necessários

Primeiro, traga as classes Aspose.Tasks e utilitários Java para o escopo.

```java
import com.aspose.tasks.*;

import java.util.Date;
import java.util.GregorianCalendar;
```

### Etapa 2: Configurar o Diretório de Dados

Defina onde seus arquivos de modelo de entrada e saída ficarão. Substitua o placeholder pelo caminho real em sua máquina.

```java
String dataDir = "Your Data Directory";
```

### Etapa 3: Definir Nomes de Arquivo de Entrada e Saída

Carregaremos um arquivo MPP existente (ou um projeto em branco) e escreveremos o resultado em um novo arquivo.

```java
String resultFile = "OutputMpp.mpp";
String newFile = "SampleMpp.mpp";
```

### Etapa 4: Carregar o Projeto e Adicionar um Novo Calendário

Crie uma instância `Project` a partir do arquivo fonte e adicione um calendário chamado **“Calendar 1”**.

```java
Project project = new Project(dataDir + newFile);
Calendar cal1 = project.getCalendars().add("Calendar 1");
```

### Etapa 5: Personalizar o Calendário (Opcional)

Se precisar de horários de trabalho específicos, feriados ou exceções, chame seu próprio método auxiliar. O exemplo usa `GetTestCalendar` como placeholder.

```java
GetTestCalendar(cal1); // Additional method for customizing calendar if required
```

> **Dica profissional:** Você pode manipular diretamente `cal1.getWeekDays()` para definir horas de trabalho para cada dia da semana, ou usar `cal1.getExceptions()` para **add holidays to calendar**.

### Etapa 6: Atribuir o Calendário ao Projeto

Informe ao projeto que ele deve usar o calendário recém‑criado para todos os seus cálculos de agendamento.

```java
project.set(Prj.CALENDAR, cal1);
```

### Etapa 7: Salvar o Projeto como MPP

Agora **convert project to MPP** salvando-o com a opção `SaveFileFormat.Mpp`.

```java
project.save(dataDir + resultFile, SaveFileFormat.Mpp);
```

### Etapa 8: Confirmar Conclusão Bem‑sucedida

Uma simples mensagem no console indica que o processo terminou sem erros.

```java
System.out.println("Process completed Successfully");
```

## Casos de Uso Comuns

- **Geração automática de cronograma** para projetos recorrentes (ex.: sprints semanais).  
- **Migração de calendários legados CSV ou Excel** para um arquivo MS Project completo.  
- **Relatórios server‑side** onde um serviço web devolve um arquivo MPP sob demanda.  

## Solução de Problemas e Armadilhas Comuns

| Problema | Causa | Solução |
|----------|-------|---------|
| `NullPointerException` ao `project.save` | `dataDir` aponta para uma pasta inexistente | Certifique‑se de que o diretório exista ou crie‑o programaticamente. |
| Calendário não aplicado às tarefas | As tarefas ainda referenciam o calendário padrão | Após definir `Prj.CALENDAR`, também atualize o `Task.CALENDAR` de cada tarefa se ele foi sobrescrito anteriormente. |
| Arquivo de saída tem 0 KB | Permissões de gravação ausentes | Execute a JVM com permissões de sistema de arquivos adequadas ou escolha um caminho gravável. |

## Perguntas Frequentes

**Q: O Aspose.Tasks for Java é compatível com diferentes versões do MS Project?**  
A: Sim, o Aspose.Tasks for Java suporta uma ampla gama de versões do MS Project, desde o Project 2007 até a versão mais recente, garantindo compatibilidade perfeita.

**Q: Posso personalizar calendários de acordo com requisitos específicos do projeto?**  
A: Absolutamente. Você pode definir dias úteis, definir semanas de trabalho personalizadas, adicionar feriados e até criar múltiplos calendários dentro de um único arquivo de projeto.

**Q: O Aspose.Tasks for Java oferece suporte para solução de problemas e assistência?**  
A: Sim, você pode obter ajuda no fórum da comunidade Aspose.Tasks [aqui](https://forum.aspose.com/c/tasks/15).

**Q: Existe um teste gratuito disponível para o Aspose.Tasks for Java?**  
A: Sim, um teste gratuito totalmente funcional está disponível [aqui](https://releases.aspose.com/).

**Q: Como posso obter uma licença temporária para o Aspose.Tasks for Java?**  
A: Licenças temporárias podem ser solicitadas via site da Aspose [aqui](https://purchase.aspose.com/temporary-license/).

**Última atualização:** 2026-02-05  
**Testado com:** Aspose.Tasks for Java 24.12  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}