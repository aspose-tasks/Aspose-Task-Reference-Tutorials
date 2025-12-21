---
date: 2025-12-21
description: Aprenda a personalizar visualizações de diagramas de Gantt, gerenciar
  a visualização de projetos e salvar o projeto como PDF usando Aspose.Tasks para
  Java. Ajuste a contagem da escala de tempo sem esforço.
linktitle: Set Time Scale Count in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Personalizar Gráfico de Gantt – Dominando a Contagem da Escala de Tempo no
  MS Project no Aspose.Tasks
url: /pt/java/project-file-operations/set-time-scale-count/
weight: 22
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Personalizar Gráfico de Gantt – Dominando a Contagem da Escala de Tempo no MS Project com Aspose.Tasks

## Introdução
Se você precisa **personalizar o visual do gráfico de Gantt** no Microsoft Project, controlar a contagem da escala de tempo é uma técnica fundamental. Com o Aspose.Tasks para Java você pode definir programaticamente os níveis inferior e intermediário da escala de tempo, ajustar a visibilidade das marcas de graduação e, em seguida, **salvar o projeto como PDF** para compartilhar com as partes interessadas. Este tutorial orienta você por todo o processo — desde a configuração do ambiente até a geração de um PDF refinado que reflete sua visualização de Gantt personalizada.

## Respostas Rápidas
- **O que significa “personalizar o gráfico de Gantt”?** Ajustar os níveis da escala de tempo, cores e layout para atender às suas necessidades de relatório.  
- **Qual método da API define a contagem do nível inferior?** `view.getBottomTimescaleTier().setCount(int)`.  
- **Posso gerar um PDF diretamente a partir do projeto?** Sim — use `project.save(..., SaveFileFormat.Pdf)`.  
- **Preciso de licença para uso em produção?** É necessária uma licença comercial; uma versão de avaliação gratuita está disponível.  
- **Qual versão do Java é suportada?** Java 8 ou superior funciona com a versão mais recente da biblioteca Aspose.Tasks.

## O que significa “personalizar o gráfico de Gantt” no Aspose.Tasks?
Personalizar um gráfico de Gantt significa alterar programaticamente seus componentes visuais — como intervalos da escala de tempo, marcas de graduação e barras de tarefas — para que o gráfico se alinhe à forma como você deseja **gerenciar a visualização do projeto**. Ao mudar a contagem da escala de tempo, você controla quantos dias, semanas ou meses cada segmento representa, tornando o gráfico mais claro para diferentes públicos.

## Pré‑requisitos
Antes de começar, verifique se você tem:

1. **Ambiente de Desenvolvimento Java** – JDK 8 ou mais recente instalado.  
2. **Biblioteca Aspose.Tasks para Java** – Baixe-a em [here](https://releases.aspose.com/tasks/java/).  
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

### Etapa 1: Definir o Diretório de Dados
Especifique onde seus arquivos de projeto serão lidos e gravados:

```java
String dataDir = "Your Data Directory";
```

Substitua `"Your Data Directory"` pelo caminho absoluto na sua máquina.

### Etapa 2: Criar uma Nova Instância de Projeto
Instancie um objeto `Project` novo que conterá todas as tarefas e configurações de visualização:

```java
Project project = new Project();
```

### Etapa 3: Configurar a Visualização do Gráfico de Gantt
Crie um objeto `GanttChartView` — é aqui que você **gerará código Java de visualização Gantt** para controlar a aparência do gráfico:

```java
GanttChartView view = new GanttChartView();
```

### Etapa 4: Definir a Contagem da Escala de Tempo para o Nível Inferior
Ajuste o nível inferior para mostrar dois intervalos e ocultar as marcas de graduação:

```java
view.getBottomTimescaleTier().setCount(2);
view.getBottomTimescaleTier().setShowTicks(false);
```

### Etapa 5: Definir a Contagem da Escala de Tempo para o Nível Intermediário
Aplique a mesma configuração ao nível intermediário:

```java
view.getMiddleTimescaleTier().setCount(2);
view.getMiddleTimescaleTier().setShowTicks(false);
```

### Etapa 6: Adicionar a Visualização Personalizada ao Projeto
Anexe a visualização que você acabou de configurar à instância `Project`:

```java
project.getViews().add(view);
```

### Etapa 7: Inserir Tarefas de Exemplo (Dados de Teste)
Crie algumas tarefas com durações específicas para ilustrar o gráfico de Gantt personalizado:

```java
Task task1 = project.getRootTask().getChildren().add("Task 1");
Task task2 = project.getRootTask().getChildren().add("Task 2");
task1.set(Tsk.DURATION, task1.getParentProject().getDuration(24, TimeUnitType.Hour));
task2.set(Tsk.DURATION, task1.getParentProject().getDuration(40, TimeUnitType.Hour));
```

### Etapa 8: Salvar o Projeto como PDF
Por fim, exporte o projeto — incluindo seu **gráfico de Gantt personalizado** — para um arquivo PDF:

```java
project.save(dataDir + "temp.pdf", SaveFileFormat.Pdf);
```

O PDF resultante demonstra como os níveis inferior e intermediário da escala de tempo foram **personalizados**, oferecendo às partes interessadas uma visualização clara e imprimível do cronograma.

## Problemas Comuns & Solução de Problemas
- **PDF está em branco** – Verifique se o caminho `dataDir` termina com um separador de arquivos (`/` ou `\`) e se o diretório existe.  
- **Marcas de graduação ainda aparecem** – Confirme que `setShowTicks(false)` foi chamado em ambos os níveis.  
- **Duração não foi aplicada** – Certifique‑se de que está usando `TimeUnitType.Hour` (ou a unidade apropriada) ao criar durações.

## Perguntas Frequentes

**P: O Aspose.Tasks para Java consegue lidar com arquivos de projeto de grande escala?**  
R: Sim, a biblioteca é otimizada para processamento de alto desempenho de dados de projeto extensos.

**P: O Aspose.Tasks para Java é compatível com diferentes IDEs Java?**  
R: Absolutamente – funciona perfeitamente com Eclipse, IntelliJ IDEA, NetBeans e outras IDEs populares.

**P: Posso personalizar a aparência dos gráficos de Gantt além das configurações da escala de tempo?**  
R: Sim, o Aspose.Tasks oferece amplas opções de estilo, como cores de barras, fontes e linhas de grade.

**P: Existe uma versão de avaliação disponível para o Aspose.Tasks para Java?**  
R: Sim, você pode obter uma versão de avaliação gratuita em [here](https://releases.aspose.com/).

**P: Onde posso obter suporte para o Aspose.Tasks para Java?**  
R: Você pode encontrar suporte e assistência no fórum Aspose.Tasks [here](https://forum.aspose.com/c/tasks/15).

**P: Como altero programaticamente a cor de fundo do gráfico de Gantt?**  
R: Use o método `view.getGanttChartProperties().setBackgroundColor(Color)` após importar `java.awt.Color`.

## Conclusão
Seguindo estas etapas, você aprendeu a **personalizar os níveis da escala de tempo do gráfico de Gantt**, melhorar a **visualização do projeto** e **salvar o projeto como PDF** usando o Aspose.Tasks para Java. Essa abordagem lhe dá controle total sobre a saída visual, facilitando o compartilhamento de cronogramas claros e profissionais com sua equipe ou clientes.

---

**Última atualização:** 2025-12-21  
**Testado com:** Aspose.Tasks para Java 24.12 (mais recente na data de escrita)  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}