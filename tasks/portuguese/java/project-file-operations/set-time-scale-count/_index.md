---
date: 2026-03-29
description: Aprenda a criar arquivos PDF de projetos enquanto personaliza a contagem
  da escala de tempo do diagrama de Gantt usando Aspose.Tasks para Java. Este guia
  mostra passo a passo como exportar o Gantt para PDF com controle total.
linktitle: Set Time Scale Count in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Criar PDF do Projeto – Personalizar a Escala de Tempo do Gráfico de Gantt
url: /pt/java/project-file-operations/set-time-scale-count/
weight: 22
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Criar PDF do Projeto – Personalizar Escala de Tempo do Gráfico de Gantt

## Introdução
Se você precisa **criar PDF do projeto** que reflita um gráfico de Gantt perfeitamente ajustado, controlar a contagem da escala de tempo é fundamental. Com Aspose.Tasks for Java você pode definir programaticamente os níveis inferior e médio da escala de tempo, ocultar as marcas de marcação e, em seguida, **salvar o projeto como PDF** para fácil distribuição. Neste tutorial, percorreremos tudo o que você precisa — desde a configuração do ambiente de desenvolvimento até a geração de um PDF refinado que exibe sua visualização de Gantt personalizada.

## Respostas Rápidas
- **O que significa “personalizar gráfico de Gantt”?** Ajustar os níveis da escala de tempo, cores e layout para atender às suas necessidades de relatório.  
- **Qual método da API define a contagem do nível inferior?** `view.getBottomTimescaleTier().setCount(int)`.  
- **Posso gerar um PDF diretamente a partir do projeto?** Sim — use `project.save(..., SaveFileFormat.Pdf)`.  
- **Preciso de licença para uso em produção?** É necessária uma licença comercial; uma versão de avaliação gratuita está disponível.  
- **Qual versão do Java é suportada?** Java 8 ou superior funciona com a biblioteca mais recente do Aspose.Tasks.

## O que é “personalizar gráfico de Gantt” no Aspose.Tasks?
Personalizar um gráfico de Gantt significa alterar programaticamente seus componentes visuais — como intervalos da escala de tempo, marcas de marcação e barras de tarefas — para que o gráfico se alinhe à forma como você deseja **gerenciar a visualização do projeto**. Ao mudar a contagem da escala de tempo, você controla quantos dias, semanas ou meses cada segmento representa, tornando o gráfico mais claro para diferentes públicos.

## Por que criar PDF do projeto com um gráfico de Gantt personalizado?
- **Saída pronta para stakeholders:** O PDF é visualizável universalmente, garantindo que todos vejam o mesmo layout de cronograma.  
- **Amigável para impressão:** Controle preciso dos níveis da escala de tempo evita impressões congestionadas ou ambíguas.  
- **Automação:** Integre a geração de PDF em pipelines de CI ou serviços de relatório para esforço zero manual.  

## Pré-requisitos
Antes de começar, certifique‑se de que você tem:

1. **Ambiente de Desenvolvimento Java** – JDK 8 ou mais recente instalado.  
2. **Biblioteca Aspose.Tasks for Java** – Baixe-a [aqui](https://releases.aspose.com/tasks/java/).  
3. **Conhecimento Básico de Java** – Familiaridade com a sintaxe Java e conceitos orientados a objetos.

## Importar Pacotes
Importe as classes necessárias para o seu projeto Java:

```java
import com.aspose.tasks.GanttChartView;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.Task;
import com.aspose.tasks.TimeUnitType;
import com.aspose.tasks.Tsk;
```

## Guia Passo a Passo

### Etapa 1: Definir Diretório de Dados
Defina onde seus arquivos de projeto serão lidos e gravados:

```java
String dataDir = "Your Data Directory";
```

Substitua `"Your Data Directory"` pelo caminho absoluto na sua máquina.

### Etapa 2: Criar uma Nova Instância de Projeto
Instancie um novo objeto `Project` que conterá todas as tarefas e configurações de visualização:

```java
Project project = new Project();
```

### Etapa 3: Configurar a Visualização do Gráfico de Gantt
Crie um objeto `GanttChartView` — é aqui que você **gerará código Java de visualização de Gantt** para controlar a aparência do gráfico:

```java
GanttChartView view = new GanttChartView();
```

### Etapa 4: Definir a Contagem da Escala de Tempo para o Nível Inferior
Ajuste o nível inferior para mostrar dois intervalos e ocultar as marcas de marcação:

```java
view.getBottomTimescaleTier().setCount(2);
view.getBottomTimescaleTier().setShowTicks(false);
```

### Etapa 5: Definir a Contagem da Escala de Tempo para o Nível Médio
Aplique a mesma configuração ao nível médio:

```java
view.getMiddleTimescaleTier().setCount(2);
view.getMiddleTimescaleTier().setShowTicks(false);
```

### Etapa 6: Adicionar a Visualização Personalizada ao Projeto
Anexe a visualização que você acabou de configurar à instância `Project`:

```java
project.getViews().add(view);
```

### Etapa 7: Adicionar Tarefas de Exemplo (Dados de Teste)
Crie algumas tarefas com durações específicas para ilustrar o gráfico de Gantt personalizado:

```java
Task task1 = project.getRootTask().getChildren().add("Task 1");
Task task2 = project.getRootTask().getChildren().add("Task 2");
task1.set(Tsk.DURATION, task1.getParentProject().getDuration(24, TimeUnitType.Hour));
task2.set(Tsk.DURATION, task1.getParentProject().getDuration(40, TimeUnitType.Hour));
```

### Etapa 8: Salvar o Projeto como PDF
Finalmente, exporte o projeto — incluindo seu **gráfico de Gantt personalizado** — para um arquivo PDF:

```java
project.save(dataDir + "temp.pdf", SaveFileFormat.Pdf);
```

O PDF resultante demonstra como os níveis inferior e médio da escala de tempo foram **personalizados**, oferecendo aos stakeholders uma visualização clara e imprimível do cronograma.

## Problemas Comuns & Solução de Problemas
- **PDF está em branco** – Certifique‑se de que o caminho `dataDir` termina com um separador de arquivos (`/` ou `\`) e que o diretório exista.  
- **Marcas ainda aparecem** – Verifique se `setShowTicks(false)` foi chamado em ambos os níveis.  
- **Duração não aplicada** – Confirme que você está usando `TimeUnitType.Hour` (ou a unidade apropriada) ao criar durações.

## Perguntas Frequentes

**Q: O Aspose.Tasks for Java pode lidar com arquivos de projeto de grande escala?**  
A: Sim, a biblioteca é otimizada para processamento de alto desempenho de dados de projeto extensos.

**Q: O Aspose.Tasks for Java é compatível com diferentes IDEs Java?**  
A: Absolutamente – funciona perfeitamente com Eclipse, IntelliJ IDEA, NetBeans e outras IDEs populares.

**Q: Posso personalizar a aparência dos gráficos de Gantt além das configurações da escala de tempo?**  
A: Sim, o Aspose.Tasks oferece opções extensas de estilo, como cores de barras, fontes e linhas de grade.

**Q: Existe uma versão de avaliação disponível para o Aspose.Tasks for Java?**  
A: Sim, você pode obter uma versão de avaliação gratuita [aqui](https://releases.aspose.com/).

**Q: Onde posso obter suporte para o Aspose.Tasks for Java?**  
A: Você pode encontrar suporte e assistência no fórum Aspose.Tasks [aqui](https://forum.aspose.com/c/tasks/15).

**Q: Como altero programaticamente a cor de fundo do gráfico de Gantt?**  
A: Use o método `view.getGanttChartProperties().setBackgroundColor(Color)` após importar `java.awt.Color`.

## Conclusão
Seguindo estas etapas, você aprendeu a **criar PDF do projeto** com uma escala de tempo do gráfico de Gantt totalmente personalizada, melhorar a **visualização do projeto** e **salvar o projeto como PDF** usando Aspose.Tasks for Java. Essa abordagem oferece controle total sobre a saída visual, facilitando o compartilhamento de cronogramas claros e profissionais com sua equipe ou clientes.

---

**Last Updated:** 2026-03-29  
**Tested With:** Aspose.Tasks for Java (latest)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}