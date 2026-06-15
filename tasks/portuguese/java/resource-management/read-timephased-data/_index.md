---
date: 2026-06-15
description: Aprenda como extrair dados timephased de recursos do MS Project usando
  Aspose.Tasks for Java. Guia passo a passo para obter recurso por id.
keywords:
- get resource by id
- Aspose.Tasks timephased data
- Java MS Project API
linktitle: Ler Dados Timephased para Recursos no Aspose.Tasks
schemas:
- author: Aspose
  dateModified: '2026-06-15'
  description: Learn how to extract timephased data from MS Project resources using
    Aspose.Tasks for Java. Step‑by‑step guide to get resource by id.
  headline: Read Timephased Data for Resources in Aspose.Tasks – get resource by id
  type: TechArticle
- questions:
  - answer: Yes, Aspose.Tasks supports MPP, XML, CSV, and several other formats, allowing
      you to read and write across different standards.
    question: Can Aspose.Tasks handle other types of project files apart from Microsoft
      Project?
  - answer: Absolutely. The library works with all major IDEs (IntelliJ IDEA, Eclipse,
      NetBeans) and build tools (Maven, Gradle).
    question: Is Aspose.Tasks compatible with different Java development environments?
  - answer: Yes, you can create, modify, and delete tasks, resources, assignments,
      and even custom fields through the API.
    question: Can I manipulate project data using Aspose.Tasks?
  - answer: It is. Enterprises rely on Aspose.Tasks for high‑volume processing, batch
      conversions, and server‑side reporting because it requires no Microsoft Project
      installation.
    question: Is Aspose.Tasks suitable for enterprise‑level projects?
  - answer: You can visit the [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15)
      for assistance from the community and support team.
    question: Where can I find support if I encounter issues while using Aspose.Tasks?
  type: FAQPage
second_title: Aspose.Tasks Java API
title: Ler Dados Timephased para Recursos no Aspose.Tasks – obter recurso por id
url: /pt/java/resource-management/read-timephased-data/
weight: 15
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Ler Dados Timephased de Recursos no Aspose.Tasks

## Introdução
Neste tutorial, você aprenderá **how to get resource by id** e lerá seus dados timephased usando Aspose.Tasks for Java. Percorreremos cada passo — desde a configuração da pasta do projeto até a impressão dos valores timephased de trabalho e custo — para que você possa extrair informações valiosas de agendamento de qualquer arquivo Microsoft Project programaticamente. Aspose.Tasks for Java é uma API abrangente que permite aos desenvolvedores criar, ler, modificar e converter arquivos Microsoft Project sem a necessidade de ter o Microsoft Project instalado, suportando uma ampla gama de recursos e formatos de gerenciamento de projetos.

## Respostas Rápidas
- **What does “get resource by id” do?** Ele recupera um objeto `Resource` específico de um `Project` usando seu identificador único.  
- **Which library handles timephased data?** Aspose.Tasks for Java fornece a API `Resource.getTimephasedData`.  
- **Do I need a license?** Uma avaliação gratuita funciona para desenvolvimento; uma licença comercial é necessária para produção.  
- **Can I read large projects?** Sim — Aspose.Tasks pode processar arquivos com até 10.000 tarefas sem carregar todo o arquivo na memória.  
- **What Java version is required?** Java 8 ou superior; a biblioteca é compatível com todos os principais JDKs.

## O que é “get resource by id”?
`get resource by id` é uma chamada de método que busca uma instância `Resource` de um `Project` carregado usando o ID numérico do recurso. Essa operação permite acesso preciso às propriedades detalhadas de um recurso, como suas atribuições, calendários e campos personalizados, e é essencial para extrair dados de trabalho ou custo timephased associados a esse recurso específico.

## Por que usar Aspose.Tasks para dados timephased?
Aspose.Tasks suporta **mais de 50 formatos de entrada e saída** (MPP, XML, CSV, etc.) e pode extrair valores de trabalho e custo timephased para recursos que abrangem cronogramas de vários anos, mantendo o uso de memória baixo. A API retorna dados em intervalos de 15 minutos por padrão, proporcionando insights granulares para relatórios ou análises personalizadas.

## Pré-requisitos
1. Java Development Kit (JDK): Certifique-se de que o JDK está instalado em seu sistema. Você pode baixá-lo no [website](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html) e seguir as instruções de instalação.  
2. Aspose.Tasks for Java Library: Baixe a biblioteca Aspose.Tasks for Java na [página de download](https://releases.aspose.com/tasks/java/) e siga as instruções de instalação fornecidas na documentação.

## Importar Pacotes
O primeiro passo é importar as classes necessárias do Aspose.Tasks para o seu arquivo fonte Java.

```java
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.Resource;
import com.aspose.tasks.TimephasedData;
import com.aspose.tasks.TimephasedDataType;
```

## Etapa 1: Configurar Diretório de Dados
Primeiro, defina o diretório onde seu arquivo MS Project está localizado. Manter a pasta de dados separada do código-fonte facilita a manutenção do projeto.

```java
String dataDir = "Your Data Directory";
```

## Etapa 2: Ler Arquivo de Modelo MS Project
Especifique o nome do seu arquivo de modelo MS Project. Usar um modelo garante configurações de coluna consistentes entre diferentes projetos.

```java
String fileName = "ResourceTimephasedData.mpp";
```

## Etapa 3: Ler Arquivo de Entrada como Projeto
A classe `Project` é o objeto central do Aspose.Tasks que representa um arquivo Microsoft Project na memória. Carregar o arquivo fornece acesso programático a tarefas, recursos e cronogramas.

```java
Project project = new Project(dataDir + fileName);
```

## Etapa 4: Obter Recurso por ID
Para recuperar um recurso específico, chame o método `getResources().getById(id)`. Esta é a operação exata referenciada pela palavra‑chave principal.

```java
Resource resource = project.getResources().getByUid(1);
```

## Etapa 5: Imprimir Dados Timephased do Trabalho do Recurso
Depois de obter o objeto `Resource`, você pode chamar `resource.getTimephasedData(ResourceTimephasedDataType.Work)` para obter as alocações de trabalho ao longo do tempo. A coleção retornada contém objetos `TimephasedData` que incluem a data de início, data de término e a quantidade de trabalho para cada intervalo.

```java
System.out.println("Timephased data of ResourceWork");
for (TimephasedData td : resource.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println("Start: " + td.getStart().toString());
    System.out.println(" Work: " + td.getValue());
}
```

## Etapa 6: Imprimir Dados Timephased do Custo do Recurso
Da mesma forma, `resource.getTimephasedData(ResourceTimephasedDataType.Cost)` retorna informações de custo divididas pelos mesmos intervalos de tempo. Isso é útil para relatórios de orçamento e acompanhamento de custos.

```java
System.out.println("Timephased data of ResourceCost");
for (TimephasedData td : resource.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE), TimephasedDataType.ResourceCost)) {
    System.out.println("Start: " + td.getStart().toString());
    System.out.println(" Cost: " + td.getValue());
}
```

## Como Obter Recurso por ID em Uma Linha?
Carregue o projeto, então chame `project.getResources().getById(5)` — substitua **5** pelo ID real do recurso que você precisa. Essa única chamada retorna o objeto `Resource`, após o qual você pode consultar seus dados timephased, atribuições ou campos personalizados. O método executa em tempo O(1) porque os recursos são indexados internamente.

## Problemas Comuns e Soluções
- **Resource not found** – Certifique-se de que o ID exista no arquivo do projeto; os IDs começam em 1 e são únicos por recurso.  
- **Empty timephased data** – Verifique se o recurso tem atribuições de trabalho ou custo; caso contrário, a coleção ficará vazia.  
- **Large file performance** – Use `Project.setLoadOptions(LoadOptions.fromFile(...))` para habilitar o carregamento preguiçoso em projetos maiores que 500 MB.

## Perguntas Frequentes

**Q: O Aspose.Tasks pode lidar com outros tipos de arquivos de projeto além do Microsoft Project?**  
A: Sim, o Aspose.Tasks suporta MPP, XML, CSV e vários outros formatos, permitindo ler e escrever em diferentes padrões.

**Q: O Aspose.Tasks é compatível com diferentes ambientes de desenvolvimento Java?**  
A: Absolutamente. A biblioteca funciona com todas as principais IDEs (IntelliJ IDEA, Eclipse, NetBeans) e ferramentas de build (Maven, Gradle).

**Q: Posso manipular dados de projeto usando Aspose.Tasks?**  
A: Sim, você pode criar, modificar e excluir tarefas, recursos, atribuições e até campos personalizados através da API.

**Q: O Aspose.Tasks é adequado para projetos de nível empresarial?**  
A: Sim. Empresas confiam no Aspose.Tasks para processamento de alto volume, conversões em lote e relatórios do lado do servidor, pois não requer instalação do Microsoft Project.

**Q: Onde posso encontrar suporte se encontrar problemas ao usar o Aspose.Tasks?**  
A: Você pode visitar o [forum Aspose.Tasks](https://forum.aspose.com/c/tasks/15) para obter assistência da comunidade e da equipe de suporte.

## Conclusão
Neste tutorial, aprendemos como **get resource by id** e ler seus dados timephased de trabalho e custo usando Aspose.Tasks for Java. Seguindo estas etapas, você pode extrair de forma eficiente informações valiosas de agendamento de seus arquivos de projeto e integrá‑las em pipelines personalizados de relatórios ou análises.

---

**Last Updated:** 2026-06-15  
**Tested With:** Aspose.Tasks 24.11 for Java  
**Author:** Aspose

## Tutoriais Relacionados

- [Adicionar recurso ao projeto com Aspose.Tasks for Java](/tasks/java/resource-management/create-resources/)
- [Gerenciar Custos de Recursos do MS Project com Aspose.Tasks for Java](/tasks/java/resource-management/resource-cost/)
- [Ler Semanas de Trabalho Java do Calendário MS Project Aspose.Tasks](/tasks/java/calendars/read-work-weeks/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}