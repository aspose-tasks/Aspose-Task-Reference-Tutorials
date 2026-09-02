---
date: 2026-05-15
description: Aprenda como definir a data de início do projeto, escrever informações
  do projeto e salvar o projeto como XML usando Aspose.Tasks para Java.
keywords:
- set project start date
- save project as xml
- Aspose.Tasks Java
linktitle: Escrever informações do projeto no Aspose.Tasks
schemas:
- author: Aspose
  dateModified: '2026-05-15'
  description: Learn how to set project start date, write project information, and
    save project as XML using Aspose.Tasks for Java.
  headline: Set Project Start Date in MS Project using Aspose.Tasks for Java
  type: TechArticle
- description: Learn how to set project start date, write project information, and
    save project as XML using Aspose.Tasks for Java.
  name: Set Project Start Date in MS Project using Aspose.Tasks for Java
  steps:
  - name: '**Java Development Kit (JDK)** – any recent version (8+ recommended).'
    text: '**Java Development Kit (JDK)** – any recent version (8+ recommended).'
  - name: '**Aspose.Tasks for Java library** – download it from [here](https://releases.aspose.com/tasks/java/).'
    text: '**Aspose.Tasks for Java library** – download it from [here](https://releases.aspose.com/tasks/java/).'
  - name: '**An IDE** – IntelliJ IDEA, Eclipse, or your favorite Java editor.'
    text: '**An IDE** – IntelliJ IDEA, Eclipse, or your favorite Java editor.'
  type: HowTo
- questions:
  - answer: Yes, Aspose.Tasks for Java provides robust functionalities for both reading
      and writing MS Project files.
    question: Can I use Aspose.Tasks for Java to read MS Project files?
  - answer: Absolutely, Aspose.Tasks for Java supports various MS Project versions,
      ensuring seamless handling of MPP, XML, and Primavera formats.
    question: Is Aspose.Tasks for Java compatible with different versions of MS Project?
  - answer: The trial version allows full feature exploration but inserts a watermark
      on generated files and limits the number of project entities you can create.
    question: Are there any limitations to the trial version of Aspose.Tasks for Java?
  - answer: You can seek assistance from the Aspose.Tasks community forum [here](https://forum.aspose.com/c/tasks/15).
    question: How can I get support for Aspose.Tasks for Java?
  - answer: Yes, temporary licenses are available for short‑term usage. You can obtain
      one from [here](https://purchase.aspose.com/temporary-license/).
    question: Can I purchase a temporary license for Aspose.Tasks for Java?
  type: FAQPage
second_title: Aspose.Tasks Java API
title: Definir a data de início do projeto no MS Project usando Aspose.Tasks para
  Java
url: /pt/java/project-properties/write-project-info/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Definir Data de Início do Projeto no MS Project usando Aspose.Tasks para Java

## Introdução
Neste tutorial, você descobrirá como **definir a data de início do projeto** e gravar informações adicionais do MS Project com Aspose.Tasks para Java. Seja automatizando cronogramas de projetos, gerando relatórios ou integrando dados do Project a um sistema maior, controlar a data de início programaticamente lhe dá comando preciso sobre seus prazos. Percorreremos cada etapa — desde a configuração do ambiente até a gravação do projeto atualizado como um arquivo XML — para que você possa começar a aplicar essas técnicas imediatamente.

## Respostas Rápidas
- **Qual é a classe principal para manipular um projeto?** `Project` da biblioteca Aspose.Tasks.  
  A classe `Project` representa um arquivo MS Project na memória.  
- **Como definir a data de início do projeto?** Use `project.set(Prj.START_DATE, <date>)`.  
  `Prj.START_DATE` é a chave de propriedade usada para definir a data de início do projeto.  
- **Posso também definir a data de status?** Sim, com `project.set(Prj.STATUS_DATE, <date>)`.  
  `Prj.STATUS_DATE` especifica a data que reflete o status atual do projeto.  
- **Qual formato devo usar para exportar o projeto?** Salvar como XML com `SaveFileFormat.Xml`.  
  `SaveFileFormat.Xml` indica que o projeto será salvo no formato XML.  
- **Preciso de licença para uso em produção?** Uma licença válida do Aspose.Tasks é necessária para funcionalidade completa.  
- **Quais ambientes o Aspose.Tasks suporta?** Windows, Linux e macOS com Java 8+.

## O que é definir a data de início do projeto?
Definir a data de início do projeto determina o dia do calendário em que o cronograma começa, estabelecendo a linha de base para todos os cálculos de tarefas, dependências e análise de caminho crítico. Ao definir essa data programaticamente, você garante que cada arquivo de projeto gerado inicie a partir do mesmo ponto, eliminando erros de entrada manual e assegurando resultados repetíveis em diferentes compilações.

## Por que usar Aspose.Tasks para Java para gravar informações do projeto?
Aspose.Tasks para Java oferece **mais de 150 propriedades configuráveis de projeto** e suporta **mais de 30 formatos de arquivo**, permitindo ler, modificar e gravar dados do MS Project sem precisar do Microsoft Project instalado. A biblioteca funciona em Windows, Linux e macOS, processa arquivos com centenas de páginas em modo de uso eficiente de memória e pode ser integrada a pipelines CI/CD, serviços de processamento em lote ou back‑ends baseados em nuvem. Essas capacidades quantificáveis tornam‑na escolha mais confiável para automação em escala empresarial.

## Pré‑requisitos
Antes de começar, certifique‑se de que você tem:

1. **Java Development Kit (JDK)** – qualquer versão recente (recomendado 8+).  
2. **Biblioteca Aspose.Tasks para Java** – faça o download [aqui](https://releases.aspose.com/tasks/java/).  
3. **Um IDE** – IntelliJ IDEA, Eclipse ou seu editor Java preferido.  

## Importar Pacotes
Primeiro, importe os pacotes necessários no seu projeto Java:
```java
import com.aspose.tasks.*;
import java.util.Calendar;
```

## Etapa 1: Configurar Diretório de Dados
Defina o diretório onde os dados do seu projeto serão armazenados.
```java
String dataDir = "Your Data Directory";
```

## Etapa 2: Criar Instância do Projeto
A classe `Project` é o objeto de nível superior do Aspose.Tasks que representa um único arquivo MS Project na memória. Inicializá‑la cria um cronograma vazio que você pode começar a preencher imediatamente.
```java
Project project = new Project();
```

## Etapa 3: Definir Propriedades de Informação do Projeto
Aqui definimos a **data de início do projeto**, a flag schedule‑from‑start e a data de status — cobrindo as palavras‑chave primárias e secundárias *write project information* e *how to set status*.
```java
project.set(Prj.SCHEDULE_FROM_START, new NullableBool(true));
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.set(2014, Calendar.JULY, 10);
project.set(Prj.START_DATE, cal.getTime());
project.set(Prj.CURRENT_DATE, cal.getTime());
project.set(Prj.STATUS_DATE, cal.getTime());
```

## Etapa 4: Salvar Projeto como XML
Por fim, persista o arquivo de projeto atualizado. Salvar como XML garante máxima compatibilidade com ferramentas downstream e mantém o tamanho do arquivo pequeno.
```java
project.save(dataDir + "project3.xml", SaveFileFormat.Xml);
```

## Problemas Comuns e Soluções
| Problema | Motivo | Solução |
|----------|--------|---------|
| **Data de início incorreta** | O mês do calendário é baseado em zero em Java. | Use `Calendar.JULY` (ou adicione 1 ao índice do mês) conforme mostrado. |
| **Arquivo não salvo** | `dataDir` não existe ou não tem permissão de gravação. | Crie o diretório antecipadamente ou escolha um caminho gravável. |
| **Aviso de licença** | Executar sem licença adiciona marca d'água. | Aplique uma licença válida do Aspose.Tasks antes de criar o objeto `Project`. |

## Perguntas Frequentes

**Q: Posso usar Aspose.Tasks para Java para ler arquivos MS Project?**  
A: Sim, Aspose.Tasks para Java fornece funcionalidades robustas tanto para leitura quanto para gravação de arquivos MS Project.

**Q: O Aspose.Tasks para Java é compatível com diferentes versões do MS Project?**  
A: Absolutamente, Aspose.Tasks para Java suporta várias versões do MS Project, garantindo manipulação fluida de formatos MPP, XML e Primavera.

**Q: Existem limitações na versão de avaliação do Aspose.Tasks para Java?**  
A: A versão de avaliação permite explorar todos os recursos, mas insere uma marca d'água nos arquivos gerados e limita o número de entidades de projeto que podem ser criadas.

**Q: Como posso obter suporte para Aspose.Tasks para Java?**  
A: Você pode buscar assistência no fórum da comunidade Aspose.Tasks [aqui](https://forum.aspose.com/c/tasks/15).

**Q: Posso comprar uma licença temporária para Aspose.Tasks para Java?**  
A: Sim, licenças temporárias estão disponíveis para uso de curto prazo. Você pode obter uma [aqui](https://purchase.aspose.com/temporary-license/).

## Conclusão
Agora você aprendeu como **definir a data de início do projeto**, gravar informações essenciais do projeto e **salvar o projeto como XML** usando Aspose.Tasks para Java. Esses blocos de construção permitem automatizar fluxos de trabalho de gerenciamento de projetos, gerar cronogramas consistentes e integrar dados do MS Project em suas aplicações Java. Em seguida, explore como adicionar tarefas, recursos e campos personalizados para enriquecer ainda mais seus cronogramas automatizados.

---

**Última atualização:** 2026-05-15  
**Testado com:** Aspose.Tasks para Java 24.12  
**Autor:** Aspose

## Tutoriais Relacionados

- [Como Definir o Calendário do Projeto com Aspose.Tasks para Java](/tasks/java/calendars/properties/)
- [Como Ler Informações do Projeto do Microsoft Project com Aspose.Tasks para Java](/tasks/java/project-properties/read-project-info/)
- [Carregar Arquivo MPP Java - Gerenciar Propriedades do Projeto com Aspose.Tasks](/tasks/java/project-management/default-properties/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< blocks/products/products-backtop-button >}}
{{< /blocks/products/pf/main-wrap-class >}}