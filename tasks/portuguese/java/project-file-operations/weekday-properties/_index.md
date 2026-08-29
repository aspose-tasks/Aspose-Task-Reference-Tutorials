---
date: 2026-03-29
description: Aprenda como alterar os dias por mês e gerenciar outras propriedades
  dos dias da semana no Aspose.Tasks para Java. Personalize as datas de início da
  semana, modifique o calendário do projeto e salve o projeto como XML.
linktitle: Weekday Properties in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Alterar Dias por Mês com as Propriedades de Dia da Semana do Aspose.Tasks
url: /pt/java/project-file-operations/weekday-properties/
weight: 25
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Alterar Dias Por Mês com as Propriedades de Dia da Semana do Aspose.Tasks

## Introdução
O Aspose.Tasks for Java permite que você **alterar dias por mês** e ajuste fino de outras configurações de dia da semana sem precisar do Microsoft Project instalado. Seja alinhando o calendário do projeto a um mês fiscal não padrão ou simplesmente precisando ajustar o dia de início da semana, este tutorial orienta você pelos cenários mais comuns — recuperar o dia de início da semana atual, personalizar a data de início da semana, modificar o calendário do projeto e salvar o projeto como XML.

## Respostas Rápidas
- **Posso mudar o número de dias por mês?** Sim, use `Prj.DAYS_PER_MONTH` no objeto `Project`.  
- **Como personalizar a data de início da semana?** Defina `Prj.WEEK_START_DAY` para um valor `DayType` (por exemplo, `DayType.Monday`).  
- **Qual formato posso usar para exportar o projeto?** O exemplo salva o arquivo como XML com `SaveFileFormat.Xml`.  
- **É necessária uma licença para uso em produção?** Uma licença válida do Aspose.Tasks é necessária para implantações que não sejam de avaliação.  
- **Quais IDEs são suportadas?** Qualquer IDE Java, como IntelliJ IDEA, Eclipse ou NetBeans, funciona.

## O que é “alterar dias por mês” no Aspose.Tasks?
Alterar dias por mês significa atualizar a propriedade `Prj.DAYS_PER_MONTH` de uma instância `Project`. Essa propriedade informa ao mecanismo quantos dias úteis ele deve considerar em cada mês, o que afeta diretamente o agendamento de tarefas e os cálculos de custos.

## Por que modificar as propriedades do calendário do projeto?
Personalizar o calendário do projeto — como definir um dia de início da semana diferente ou alterar minutos por dia — ajuda a:

- Alinhar cronogramas com semanas de trabalho regionais.  
- Modelar padrões de trabalho não padrão (por exemplo, semanas de 4 dias).  
- Garantir relatórios precisos para contratos que utilizam calendários personalizados.

## Pré-requisitos
- **Java Development Kit (JDK)** – Instale o JDK mais recente da Oracle.  
- **Biblioteca Aspose.Tasks for Java** – Baixe-a do site oficial [here](https://releases.aspose.com/tasks/java/).  
- **IDE de sua escolha** – IntelliJ IDEA, Eclipse ou NetBeans.

## Importar Pacotes
Primeiro, importe as classes essenciais do Aspose.Tasks:

```java
import com.aspose.tasks.DayType;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
```

## Etapa 1: Carregar Arquivo do Projeto
```java
String dataDir = "Your Data Directory";
Project project = new Project(dataDir + "project.mpp");
```
Isso carrega um arquivo Microsoft Project existente (`project.mpp`) da pasta que você especificar.

## Etapa 2: Exibir Propriedades de Dia da Semana
```java
System.out.println("Week Start Date : " + project.get(Prj.WEEK_START_DAY).toString());
System.out.println("Days Per Month : " + project.get(Prj.DAYS_PER_MONTH).toString());
System.out.println("Minutes Per Day : " + project.get(Prj.MINUTES_PER_DAY).toString());
System.out.println("Minutes Per Week : " + project.get(Prj.MINUTES_PER_WEEK).toString());
```
Aqui recuperamos e imprimimos as configurações atuais de dia da semana, incluindo o **dia de início da semana** e **dias por mês**.

## Etapa 3: Definir Propriedades de Dia da Semana
```java
Project prj = new Project();
project.set(Prj.WEEK_START_DAY, DayType.Monday);
project.set(Prj.DAYS_PER_MONTH, 24);
project.set(Prj.MINUTES_PER_DAY, 540);
project.set(Prj.MINUTES_PER_WEEK, 3240);
```
Nesta etapa, **alteramos dias por mês** para 24, definimos a semana para iniciar na segunda‑feira e ajustamos os minutos por dia/semana. Isso demonstra como **modificar o calendário do projeto** programaticamente.

## Etapa 4: Salvar Projeto
```java
prj.save(dataDir + "savedProject.xml", SaveFileFormat.Xml);
```
O projeto modificado é persistido usando o formato **salvar projeto como XML**, que é útil para integração com outras ferramentas ou para armazenamento sob controle de versão.

## Etapa 5: Exibir Resultado
```java
System.out.println("Process completed Successfully");
```
Uma simples confirmação de que as operações terminaram sem erros.

## Como Personalizar a Data de Início da Semana
Se sua organização segue um calendário que começa no domingo, substitua `DayType.Monday` por `DayType.Sunday`. A mesma propriedade (`Prj.WEEK_START_DAY`) é usada, tornando a alteração simples.

## Como Recuperar o Dia de Início da Semana
Você pode chamar `project.get(Prj.WEEK_START_DAY)` a qualquer momento para **recuperar a informação do dia de início da semana**, como mostrado na Etapa 2.

## Como Modificar o Calendário do Projeto
Além do dia de início da semana, você também pode ajustar `Prj.MINUTES_PER_DAY` e `Prj.MINUTES_PER_WEEK` para refletir horas de trabalho personalizadas ou padrões de turnos.

## Problemas Comuns e Soluções
- **Valor de tipo de dia incorreto** – Certifique-se de usar o enum `DayType` (por exemplo, `DayType.Monday`).  
- **Erros de caminho de arquivo** – Verifique se `dataDir` termina com o separador de arquivos apropriado (`/` ou `\`).  
- **Licença não definida** – Se você vir avisos de licença, registre sua licença Aspose.Tasks antes de criar o objeto `Project`.

## Perguntas Frequentes

**Q: O Aspose.Tasks for Java pode lidar com estruturas de projeto complexas?**  
A: Sim, o Aspose.Tasks for Java oferece suporte abrangente para lidar com estruturas de projeto complexas com facilidade.

**Q: O Aspose.Tasks for Java é compatível com diferentes versões de arquivos do Microsoft Project?**  
A: Absolutamente, o Aspose.Tasks for Java suporta várias versões de arquivos do Microsoft Project, garantindo compatibilidade entre plataformas.

**Q: Posso integrar o Aspose.Tasks for Java nas minhas aplicações Java existentes?**  
A: Sim, o Aspose.Tasks for Java oferece capacidades de integração perfeitas, permitindo que você melhore suas aplicações Java com recursos poderosos de gerenciamento de projetos.

**Q: O Aspose.Tasks for Java fornece documentação e suporte?**  
A: Sim, você pode acessar documentação extensa e suporte da comunidade para o Aspose.Tasks for Java em seu [website](https://releases.aspose.com/).

**Q: Existe uma versão de avaliação gratuita disponível para o Aspose.Tasks for Java?**  
A: Sim, você pode baixar uma versão de avaliação gratuita do Aspose.Tasks for Java no [website](https://reference.aspose.com/tasks/java/) para explorar seus recursos antes de fazer a compra.

**Última Atualização:** 2026-03-29  
**Testado Com:** Aspose.Tasks for Java 24.11  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}