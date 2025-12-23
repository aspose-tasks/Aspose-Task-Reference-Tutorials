---
date: 2025-12-23
description: Aprenda a usar o Aspose.Tasks Java para atualizar o cronograma do projeto,
  definir o dia de início da semana, alterar os dias por mês e personalizar o calendário
  do projeto de forma eficiente.
linktitle: Weekday Properties in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: aspose tasks java – Gerenciando propriedades de dias da semana
url: /pt/java/project-file-operations/weekday-properties/
weight: 25
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# aspose tasks java – Gerenciando Propriedades dos Dias da Semana

## Introdução
Aspose.Tasks for Java (aspose tasks java) é uma API robusta que permite a desenvolvedores Java trabalhar com arquivos Microsoft Project sem precisar do Microsoft Project instalado. Neste tutorial você aprenderá a **carregar um arquivo MPP**, **definir o dia inicial da semana**, **alterar os dias por mês** e, de forma geral, **personalizar o calendário do projeto** — todas etapas essenciais para atualizar o cronograma de um projeto. Ao final, você será capaz de ajustar programaticamente as propriedades dos dias da semana e salvar as alterações no formato que precisar.

## Respostas Rápidas
- **Qual é a classe principal para manipular projetos?** `Project` da biblioteca Aspose.Tasks.  
- **Como altero o dia inicial da semana?** Use `project.set(Prj.WEEK_START_DAY, DayType.Monday)`.  
- **Posso carregar um arquivo .mpp existente?** Sim — instancie `Project` com o caminho do arquivo.  
- **Qual método salva o projeto como XML?** `project.save(path, SaveFileFormat.Xml)`.  
- **Preciso de licença para desenvolvimento?** Uma avaliação gratuita funciona para testes; uma licença é necessária para produção.

## Pré‑requisitos
Antes de começar, certifique‑se de que você tem o seguinte:

- **Java Development Kit (JDK)** – última versão instalada.  
- **Aspose.Tasks for Java library** – faça o download [aqui](https://releases.aspose.com/tasks/java/).  
- **Uma IDE** como IntelliJ IDEA, Eclipse ou NetBeans.  

## Importar Pacotes
Para iniciar, importe as classes essenciais do Aspose.Tasks:

```java
import com.aspose.tasks.DayType;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
```

Agora vamos percorrer cada passo para gerenciar as propriedades dos dias da semana.

## Etapa 1: Carregar um Arquivo MPP
```java
String dataDir = "Your Data Directory";
Project project = new Project(dataDir + "project.mpp");
```
*Aqui nós **carregamos um arquivo .mpp existente** (`load mpp file`) para que possamos inspecionar e modificar as configurações de calendário.*

## Etapa 2: Exibir Propriedades Atuais dos Dias da Semana
```java
System.out.println("Week Start Date : " + project.get(Prj.WEEK_START_DAY).toString());
System.out.println("Days Per Month : " + project.get(Prj.DAYS_PER_MONTH).toString());
System.out.println("Minutes Per Day : " + project.get(Prj.MINUTES_PER_DAY).toString());
System.out.println("Minutes Per Week : " + project.get(Prj.MINUTES_PER_WEEK).toString());
```
Este código imprime o **dia inicial da semana**, **dias por mês**, **minutos por dia** e **minutos por semana** — os elementos principais que você frequentemente precisará para **personalizar o calendário do projeto**.

## Etapa 3: Definir Novas Propriedades dos Dias da Semana
```java
Project prj = new Project();
project.set(Prj.WEEK_START_DAY, DayType.Monday);
project.set(Prj.DAYS_PER_MONTH, 24);
project.set(Prj.MINUTES_PER_DAY, 540);
project.set(Prj.MINUTES_PER_WEEK, 3240);
```
Nesta etapa definimos o **dia inicial da semana** para segunda‑feira, **alteramos os dias por mês** para 24 e ajustamos as contagens de minutos diários e semanais. Essas configurações são típicas quando você precisa **atualizar o cronograma do projeto** para corresponder a um calendário de trabalho não padrão.

## Etapa 4: Salvar o Projeto Atualizado
```java
prj.save(dataDir + "savedProject.xml", SaveFileFormat.Xml);
```
O projeto modificado é salvo como um arquivo XML, facilitando o compartilhamento ou a importação em outras ferramentas.

## Etapa 5: Confirmar a Operação
```java
System.out.println("Process completed Successfully");
```
Uma simples mensagem no console informa que o fluxo de trabalho terminou sem erros.

## Problemas Comuns & Dicas
- **Caminho de arquivo incorreto** – Verifique se `dataDir` termina com uma barra ou use `Paths.get(...)` para caminhos independentes de plataforma.  
- **Licença não definida** – Em ambiente de produção, chame `License license = new License(); license.setLicense("Aspose.Tasks.Java.lic");` antes de criar `Project`.  
- **Dia inicial da semana inesperado** – Certifique‑se de usar o valor correto do enum `DayType` (por exemplo, `DayType.Sunday`).  

## Perguntas Frequentes

**Q: O Aspose.Tasks for Java pode lidar com estruturas de projeto complexas?**  
A: Sim, o Aspose.Tasks for Java oferece suporte abrangente para manipular estruturas de projeto complexas com facilidade.

**Q: O Aspose.Tasks for Java é compatível com diferentes versões de arquivos Microsoft Project?**  
A: Absolutamente, o Aspose.Tasks for Java suporta várias versões de arquivos Microsoft Project, garantindo compatibilidade em diferentes plataformas.

**Q: Posso integrar o Aspose.Tasks for Java nas minhas aplicações Java existentes?**  
A: Sim, o Aspose.Tasks for Java oferece capacidades de integração perfeitas, permitindo que você enriqueça suas aplicações Java com recursos avançados de gerenciamento de projetos.

**Q: O Aspose.Tasks for Java fornece documentação e suporte?**  
A: Sim, você pode acessar documentação extensa e suporte da comunidade para o Aspose.Tasks for Java em seu [site](https://releases.aspose.com/).

**Q: Existe uma versão de avaliação gratuita do Aspose.Tasks for Java?**  
A: Sim, você pode baixar uma versão de avaliação gratuita do Aspose.Tasks for Java em seu [site](https://reference.aspose.com/tasks/java/) para explorar os recursos antes de efetuar a compra.

---

**Última atualização:** 2025-12-23  
**Testado com:** Aspose.Tasks for Java 24.11  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}